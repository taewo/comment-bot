<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h2>두려워 마세요.</h2>
    <h3>우리의 성공적인 댓글을 위해 최선을 다할게요.💑</h3>
    <div>
      <button @click="makeNewComment('direct')">다이렉트 댓글</button>
      <button @click="makeNewComment('diet')">다이어트 댓글</button>
      <br>
      <br>
      <button v-clipboard:copy="comment" v-clipboard:success="onCopy">복사하기</button>
    </div>
    <textarea v-model="comment" name id cols="30" rows="10" style="border:1px solid black;"></textarea>
  </div>
</template>

<script>
import Test1 from "./Test1";

export default {
  name: "HelloWorld",
  components: {
    Test1
  },
  data() {
    return {
      msg: "반가워요! 댓글봇이에요",
      comment: "",
      direct: {
        aSections: [
          "와 정말 대단하세요~!",
          "우와 수고많으셨어요!!",
          "수고하셨습니다~!",
          "다녀오시느라 수고 많으셨어요~!",
          "어머머 정말 잘 어울리세요!!",
          "너무 좋으셨겠어요~!",
          "정말 아름다우세요!!",
          "고생하셨습니다 !!",
          "오 상담까지 받으셨군요",
          "수고 많으셨어요~",
          "부지런하시네요 ㅎ"
        ],
        bSections: [
          "이제 시작이죠!",
          "정말 잘 준비하고 계시네요 ^^",
          "상담 받고 정말 짱이에요",
          "저희도 같은 곳으로 계약하려고 생각중이에요 ㅎ",
          "당일 계약까지 하고 오셨군요 ㅎ",
          "너무 너무 잘 어울려요~!",
          "상담 받으시면서 많은 정보 얻으셨겠네요~!",
          "상담 받으면서 알아가는게 참 많아요",
          "이제 부터 시작이죠!",
          "저희도 추천 받은 업체네요"
        ],
        cSections: [
          "앞으로 남은 기간도 잘 준비하세요",
          "정말 축하드립니다! 이제부터 시작이죠",
          "하나하나 잘 준비하세요~",
          "준비하는 재미가 쏠쏠하죠 ㅎㅎ",
          "포기하지 않고 잘 준비해나가세요~!",
          "축하드립니다! 홧팅!",
          "정말 축하드리면서 화이팅!",
          "차근차근 잘 준비하세요"
        ]
      },
      diet: {
        aSections: [
          "오 정말 대단해요!",
          "와 정말 대단하시네요",
          "와 부러워요 정말!",
          "헐 대박이네요!",
          "저라면 또르르르..",
          "오 역시 대단해요!!",
          "역시 대단하세요~~",
          "컥! 대박이네요~!"
        ],
        bSections: [
          "식단 지키기 정말 쉽지 않은데ㅠㅠ",
          "어떻게 포기 안하시고 꾸준히 대박!",
          "저는 식단 지키는게 제일 힘들었어요ㅠ",
          "식단 지키는게 젤 어렵던데 어떻해ㅠ",
          "저라면 성공 못했을꺼에요ㅠ",
          "성공하셨다니 대단해요",
          "다이어트 성공한 모습이 제 모습이라면..ㅠ",
          "꾸준함만이 정말 성공의 길인것 같아요",
          "부지런하게 식단도 하시다니 최고",
          "의지박약인 제겐 넘나도 부러운 이야기!",
          "제겐 너무나도 부러운 이야기네요 ㅠ",
          "저는 언제 저렇게 다이어트 성공할 수 있을까요",
          "저도 성공하고 싶어요 다이어트 ^_^"
        ],
        cSections: [
          "저도 남은 기간 열심히 해볼게요! 홧팅",
          "남은 기간도 포기말고 화이팅@@",
          "끝까지 포기 말고 화이팅입니다~!",
          "포기말고 끝까지 힘냅시다!!",
          "열심히 해봐야겠어요 저도 홧팅입니다",
          "다이어트 꼭 성공합시다!!아자자",
          "저도 본 받아서 화이팅"
        ]
      }
    };
  },
  methods: {
    onCopy() {
      console.log("----");
    },
    makeNewComment(type) {
      if (type === "direct") {
        this.comment = [
          this.direct.aSections[this.randomNumber(this.direct.aSections)],
          this.direct.bSections[this.randomNumber(this.direct.bSections)],
          this.direct.cSections[this.randomNumber(this.direct.cSections)]
        ].join(" ");
      } else {
        this.comment = [
          this.diet.aSections[this.randomNumber(this.diet.aSections)],
          this.diet.bSections[this.randomNumber(this.diet.bSections)],
          this.diet.cSections[this.randomNumber(this.diet.cSections)]
        ].join(" ");
      }
    },
    randomNumber(arr) {
      return Math.floor(Math.random() * arr.length);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
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

textarea {
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
