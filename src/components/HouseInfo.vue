<template>
  <div class="house-info" id="house-info">
    <div class="content">
      <h3 class="title">建案資訊</h3>
      <div class="info">
        <div class="item" :key="infos[0]" v-for="infos in houseInfos">
          <h3 class="label">{{ infos[0] }}</h3>
          <a :href="infos[2]" class="desc" target="_blank" v-html="infos[1]" ></a>
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import info from "@/info";
import Footer from "@/layouts/Footer.vue";
export default {
  name: "houseInfo",
  components: {
    Footer
  },
  data() {
    return {
      houseInfos: info.houseInfos
    };
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
@import "@/assets/style/variableColor.scss";
.house-info {
  width: 100vw;
  background: #fff;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: top;
  position: relative;
  z-index: 1;
}
.content {
  width: 686px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  padding-bottom: 8vh;

  .decor-6 {
    width: 35vw;
    bottom: 0;
    right: 10vw;
    z-index: -1;
    img {
      width: 100%;
    }
  }
}

.title {
  font-size: 32px;
  line-height: 36px;
  margin: 60px 0;
  font-weight: 500;
  color: $house_title_color;
  font-family: $family3;
  width: 80vw;
  padding: 10px 20px;
}

.info {
  display: flex;
  flex-wrap: wrap;
}

.item {
  font-size: 24px;
  margin-bottom: 30px;
  margin-right: 160px;
  width: 240px;
  height: 30px;
  border-left: 4px solid $house_border_color;
  padding-left: 12px;
  display: flex;
  align-items: center;
  white-space: nowrap;

  &:nth-of-type(even) {
    margin-right: 0;
  }

  .label {
    font-size: 18px;
    color: $house_label_color;
    margin-bottom: 0;
    margin-right: 20px;
    white-space: nowrap;
    font-family: $family3;
    font-weight: 500;
  }

  .desc {
    font-size: 18px;
    text-align: left;
    line-height: 1.4;
    color: $house_desc_color;
    font-family: $family3;
    font-weight: 500;
  }
}

/* 螢幕尺寸標準 */
/* 手機尺寸 */
@media only screen and (max-width: 767px) {
  .content {
    width: 100%;
    margin-bottom: 20px;
    padding-bottom: 0;
  }

  .title {
    font-size: 24px;
    margin: 40px 0 24px;
    width: 100vw;
  }

  .item {
    margin-bottom: 20px;
    margin-right: 0;
    width: 100%;
    height: auto;
    margin-left: 20px;
    white-space: normal;
    .label,
    .desc {
      font-size: 16px;
    }
  }

  .info {
    width: 100%;
  }
}

/* 平板尺寸 */
@media only screen and (min-device-width: 768px) and (max-device-width: 1024px) {
  .content {
    width: 686px;
  }

  .title {
    font-size: 24px;
    margin: 40px 0 24px;
  }

  .item {
    margin-bottom: 20px;
  }
}

// 避免內容電腦過渡平板時，設計未考量的調整
@media only screen and (min-width: 1025px) and (max-width: 1199.98px) {
}
</style>