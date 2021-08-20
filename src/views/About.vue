<template>
<div id="app1">
<div class="body">
  <div class="step-box">
    <span>STEP2</span>
    <h4>以下にお答えください</h4>
  </div>
  <div v-show="show >= 1">
    <div class="question-box">
      <p>-現在生命保険に加入されていますか?-</p>
      <label><input type="radio" v-model="radio" value="yes" @click="next()">はい</label>
      <label><input type="radio" v-model="radio" value="no" @click="next()">いいえ</label>
    </div>
  </div>
  <br>
  <div v-show="show >= 2">
    <div class="question-box">
      <p>-現在入院中ですか。または、最近3ヶ月以内に医師の診察、検査の結果、入院、手術を進められたことはありますか？-</p>
      <label><input type="radio" v-model="radio2" value="yes" @click="next()">はい</label>
      <label><input type="radio" v-model="radio2" value="no" @click="next()">いいえ</label>
    </div>
  </div>
  <br>
  <div v-show="show >= 3">
    <div class="question-box">
      <p>-過去5年以内に、病気やけがで、手術をうけたことまたは継続して7日以上の入院をしたことがありますか？-</p>
      <label><input type="radio" v-model="radio3" value="yes" @click="next()">はい</label>
      <label><input type="radio" v-model="radio3" value="no" @click="next()">いいえ</label>
    </div>
  </div>
</div>
<router-link to="/"><button class="back-btn button is-primary" id="back-btn">前へ戻る</button></router-link>
<router-link to="/post"><button class="button is-primary" id="next-btn">次へ進む</button></router-link>
</div> 
</template>
<script>
export default {
  data() {
    return {
      radio:'',
      radio2:'',
      radio3:'',
      show:1,
      nextButton:'',
      backButton:'',
    };
  },
  mounted() {
    this.nengoes = this.genereate();
  },
  methods: {
    next:function(){
      this.show++;
      if (this.show > 3) { 
        this.show = 3;
        } 
      }
    }
};
</script>


