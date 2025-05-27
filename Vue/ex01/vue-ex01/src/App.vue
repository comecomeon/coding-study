<template>

<!-- =====메뉴======= -->
  <div class="menu">
    <a href="javascript:;" v-for="(메뉴, idx) in 메뉴들" :key="idx">{{ 메뉴 }}</a>
  </div>
<!-- =====메뉴======= -->

<!-- ===== 아이템 v-for문 예제 ======= -->
  <!--<div v-for="(물건가격, idx) in 물건들과가격들배열" :key="idx" class="item">
    <h4>{{ 물건가격.물건 }} 원룸</h4>
    <p>{{ 물건가격.가격 }} 만원</p>
    <!-- 클릭 시 신고하기 메서드에 현재 아이템의 인덱스 전달
    <div class="call">
      <button
        @click="신고하기(idx)"
        class="btn"
      >신고하기</button> <span>{{ 물건가격.신고수 }}</span>
    </div>
  </div> -->
<!-- ===== 아이템 v-for문 예제 ======= -->

<!-- ===== 아이템 ======= -->
  <div class="item">
    <img src="./assets/room0.jpg" alt="">
    <h4>{{ 물건들과가격들배열[0].물건 }}</h4>
    <p>{{ 물건들과가격들배열[0].가격 }} 만원</p>
    <div class="call">
      <button type="button" class="btn" @click="물건들과가격들배열[0].신고수++">허위매물 신고</button>
      <span>신고수 : {{ 물건들과가격들배열[0].신고수 }}</span>
    </div>
  </div>
  <div class="item">
    <img src="./assets/room1.jpg" alt="">
    <h4>{{ 물건들과가격들배열[1].물건 }}</h4>
    <p>{{ 물건들과가격들배열[1].가격 }} 만원</p>
    <div class="call">
      <button type="button" class="btn" @click="물건들과가격들배열[1].신고수++">허위매물 신고</button>
      <span>신고수 : {{ 물건들과가격들배열[1].신고수 }}</span>
    </div>
  </div>
  <div class="item">
    <img src="./assets/room2.jpg" alt="">
    <h4>{{ 물건들과가격들배열[2].물건 }}</h4>
    <p>{{ 물건들과가격들배열[2].가격 }} 만원</p>
    <div class="call">
      <button type="button" class="btn" @click="물건들과가격들배열[2].신고수++">허위매물 신고</button>
      <span>신고수 : {{ 물건들과가격들배열[2].신고수 }}</span>
    </div>
  </div>
<!-- ===== 아이템 ======= -->
</template>

<script>
import './css/main.css';
export default {
  name: 'App',
  data() {
    return {
      물건들과가격들배열: [
        { 물건: "중랑구", 가격: 50, 신고수: 0 },
        { 물건: "성북구", 가격: 60, 신고수: 0 },
        { 물건: "강남구", 가격: 70, 신고수: 0 }
      ],
      메뉴들: ["Home", "Products", "About"],
    }
  },
  methods: {
    // 여기에 메서드를 추가할 수 있습니다.
    // 신고하기 메서드: 인덱스를 받아 해당 아이템의 신고수 증가
    신고하기(idx) {
      this.물건들과가격들배열[idx].신고수++;
    }
  },
}
</script>

<style>


</style>
