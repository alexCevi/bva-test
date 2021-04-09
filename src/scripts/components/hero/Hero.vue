<template lang="pug">
.hero_container(:style="backgroundImage")
  .position_wrapper(:class="alignment")
    .content_container
      h1 {{ title }}
      p {{ copy }}
      button {{ ctatext }}
</template>

<script>
export default {
  name: "Hero",
  props: {
    image: String,
    alignment: String,
    title: String,
    url: String,
    copy: String,
    ctatext: String
  },
  computed: {
    backgroundImage() {
      return `background-image: url('${this.image}')`;
    }
  }
};
</script>

<style scoped lang="scss">
.hero_container {
  font-family: "Roboto", sans-serif;
  background-size: cover;
  background-position: center;
  width: 100%;
  padding: 100px 50px;
  h1 {
    color: #fff;
    font-weight: bold;
    font-size: 46px;
    margin-bottom: 0px;
    @media (max-width: 749px) {
      font-size: 36px;
    }
  }
  p {
    color: #fff;
    font-weight: 300;
    font-size: 24px;
    margin-top: 10px;
    line-height: 38px;
    @media (max-width: 749px) {
      font-size: 18px;
      line-height: 28px;
    }
  }
  button {
    color: #ffffff;
    background-color: #57ad68;
    font-weight: 300;
    font-size: 20px;
    border: none;
    padding: 13px 41px;
    border-radius: 35px;
    transition: all 0.3s ease;
    &:hover {
      color: #57ad68;
      background-color: #ffffff;
      cursor: pointer;
    }
  }
  .position_wrapper {
    display: flex;
    @media (max-width: 749px) {
      justify-content: center !important;
      text-align: center !important;
    }
  }
  .content_container {
    max-width: 850px;
  }
}
.right {
  text-align: left;
  justify-content: flex-end;
}
.center {
  justify-content: center;
  text-align: center;
}
</style>
