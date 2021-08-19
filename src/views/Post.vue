<template>
<div id="app1">
  <div class="body">
    <div class="step-box">
       <span>STEP3</span>
       <h4>ご相談内容を入力してください</h4> 
    </div> 
    <div class="question-box">
        <p>-ご相談内容-</p>
        <textarea class="formBox" v-model="message" placeholder="入力して下さい"></textarea>
        <p style="white-space: pre-line">{{ message }}</p>
    </div>
  </div>
    <router-link to="/about"><button class="button is-primary" id="next-btn">前へ戻る</button></router-link>
    <button class="button is-primary" id="next-btn">次へ進む</button>
</div>
</template>
<script>
export default {
  data() {
    return {
      message: ''
    };
  },
};

</script>

