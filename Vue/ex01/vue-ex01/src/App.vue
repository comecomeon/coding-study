<template>

<!-- =====메뉴======= -->
  <div class="menu">
    <a href="javascript:;" v-for="(메뉴, idx) in 메뉴들" :key="idx">{{ 메뉴 }}</a>
  </div>
<!-- =====메뉴======= -->

<!-- =====아이템======= -->
  <div v-for="(물건가격, idx) in 물건들과가격들배열" :key="idx" class="item">
    <h4>{{ 물건가격.물건 }} 원룸</h4>
    <p>{{ 물건가격.가격 }} 만원</p>
    <!-- 클릭 시 신고하기 메서드에 현재 아이템의 인덱스 전달 -->
    <div class="call">
      <button
        @click="신고하기(idx)"
        class="btn"
      >신고하기</button> <span>{{ 물건가격.신고수 }}</span>
    </div>
  </div>
<!-- =====아이템======= -->
</template>

<script>
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
.menu {
  background: linear-gradient(90deg, #4b6cb7 0%, #182848 100%);
  padding: 18px 0;
  border-radius: 8px;
  display: flex;
  justify-content: center;
  gap: 30px;
  margin-bottom: 40px;
  box-shadow: 0 2px 10px rgba(50,50,100,0.08);
}

.menu a {
  color: #fff;
  padding: 12px 28px;
  border-radius: 6px;
  font-weight: 600;
  letter-spacing: 1px;
  text-decoration: none;
  transition: background 0.2s, color 0.2s, box-shadow 0.2s;
}
.menu a:hover {
  background: rgba(255,255,255,0.15);
  color: #ffd700;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}

.item {
  width: 380px;
  margin: 28px auto;
  padding: 28px 24px;
  text-align: center;
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 4px 24px rgba(50,50,100,0.10);
  transition: transform 0.15s, box-shadow 0.15s;
  border: 1px solid #f0f1f6;
}
.item:hover {
  transform: translateY(-6px) scale(1.03);
  box-shadow: 0 8px 32px rgba(50,50,100,0.18);
  border-color: #b3b6ff;
}

.item h4 {
  font-size: 1.4rem;
  margin-bottom: 10px;
  color: #4b6cb7;
  font-weight: 700;
  letter-spacing: 1px;
}

.item p {
  font-size: 1.1rem;
  color: #222;
  margin: 0;
  font-weight: 500;
}

.call{
  display: flex;
  justify-content: center;
  align-items: center;
  margin-top: 20px;
}
.call button {
  background: #4b6cb7;
  color: #fff;
  padding: 10px 20px;
  border-radius: 6px;
  border: none;
  font-size: 1rem;
  font-weight: bold;
  transition: background 0.2s, transform 0.2s;
  cursor: pointer;
}
.call button:hover {
  background: #3a5f9d;
  transform: translateY(-2px);
}
.call span {
  margin-left: 10px;
  font-size: 1.2rem;
  color: #4b6cb7;
  font-weight: bold;
}
.call span:hover {
  color: #3a5f9d;
  transform: translateY(-2px);
}
.call span:active {
  transform: translateY(2px);
}

@media (max-width: 720px) {
  .item {
    width: 95%;
    padding: 18px 6px;
  }
  .menu {
    flex-direction: column;
    gap: 10px;
    padding: 12px 0;
  }
}

</style>
