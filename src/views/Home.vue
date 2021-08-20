<template>
<div id="app1">
<div class="body">
  <div class="step-box">
    <span>STEP1</span>
    <h4>お客様情報を入力してください</h4>
  </div>
  <div class="question-box">
    <p>-性別-</p>
    <div class="boxes">
      <label><input type="radio" v-model="radio" value="yes" >男性</label>
      <label><input type="radio" v-model="radio" value="no" >女性</label>
    </div>
  </div>
  <br>
  <div class="question-box">
    <p>-生年月日-</p>
    <div class="boxes">
    <select id="year" v-model="year">
    <option v-for="number in imperial_Era" :key="number.year" :value="number.year">{{ number.label }}</option>
    </select>
    <label>年</label>
    <select v-model="month" @change="get_days">
    <option v-for="n in 12" :value="n" :key="n">{{ n }}</option>
    </select>月
    <select v-model="day">
    <option v-for="n in 31" :value="n" :key="n">{{ n }}</option>
    </select>日
    </div>
  </div>             
</div>
<router-link to="/about"><button class="button is-primary" id="next-btn">次へ進む</button></router-link>
</div>

</template>

<script>
export default {
  data() {
    return {
      year: 2000,
      month: 1,
      date: 1,
      day: 1,
      radio:'',
      radio2:'',
      radio3:'',
      imperial_Era : []
    };
  },
  mounted() {
    this.imperial_Era = this.genereate();
  },
  methods: {
    genereate() {
      const imperial_Era  = [];
      for (let y=2020; y>1920; y--) {
        if (y > 2018) {
          imperial_Era.push( {year: y, label: `${y} (令和${y-2018}年)`} );
        } else if (y > 1988) {
          imperial_Era.push( {year: y, label: `${y} (平成${y-1988}年)`} );
        } else if (y > 1925) {
          imperial_Era.push( {year: y, label: `${y} (昭和${y-1925}年)`} );
        } else if (y > 1911) {
          imperial_Era.push( {year: y, label: `${y} (大正${y-1911}年)`} );
        }
      }
      return imperial_Era;
    }
  }
};
</script>
