<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>두려워 마세요.</h2>
    <h3>우리의 성공적인 댓글을 위해 최선을 다할게요.💑</h3>
    <button @click="makeNewComment">다이렉트 댓글생성</button>
    <button @click="makeNewComment">박람회 댓글생성</button>
    <button @click="makeNewComment">다이어트 댓글생성</button><br><br>
    <Test1 :value123.sync="msg" /><br>
    {{msg}}
    <textarea v-model="comment" name="" id="" cols="30" rows="10"></textarea>
  </div>
</template>

<script>
import Test1 from './Test1'

export default {
  name: 'HelloWorld',
  components: {
    Test1
  },
  data () {
    return {
      msg: '반가워요! 댓글봇이에요',
      comment: '',
      aSections: [
        '와 정말 대단하세요~!',
        '우와 수고많으셨어요!!',
        '수고하셨습니다~!',
        '다녀오시느라 수고 많으셨어요~!',
        '어머머 정말 잘 어울리세요!!',
        '너무 좋으셨겠어요~!',
        '정말 아름다우세요!!',
        '고생하셨습니다 !!',
        '오 상담까지 받으셨군요'
      ],
      bSections: [
        '계약까지 하시고 정말 잘 준비하고 계시네요 ^^',
        '너무 너무 잘 어울려요~!',
        '상담 받으시면서 많은 정보 얻으셨겠네요~!',
        '상담 받으면서 알아가는게 참 많아요',
      ],
      cSections: [
        '앞으로 남은 기간도 잘 준비하세요',
        '정말 축하드립니다! 이제부터 시작이죠',
        '하나하나 잘 준비하세요~',
        '준비하는 재미가 쏠쏠하죠 ㅎㅎ',
        '포기하지 않고 잘 준비해나가세요~!',
        '축하드립니다! 홧팅!',
        '정말 축하드리면서 화이팅!',
        '차근차근 잘 준비하세요'
      ]
    }
  },
  methods: {
    makeNewComment(){
      this.comment = [this.aSections[this.randomNumber(this.aSections)], this.bSections[this.randomNumber(this.bSections)], this.cSections[this.randomNumber(this.cSections)]].join(' ')
    },
    randomNumber(arr) {
      return Math.floor(Math.random() * arr.length)
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}

textarea{
  width: 70%;
  height: 300px;
  font-size: 20px;
}

button {
  border: 1px solid gray;
  width: 88px;
  height: 40px;

}
</style>
