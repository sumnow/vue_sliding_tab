<template>
  <div class="hello">
      <div class="border">
        <h1>My friends</h1>
      </div>
      <div>
        <h3>吃饭</h3>
        <slider :sliderData="example0"></slider>
      </div>
      <div>
        <h3>分钟</h3>
        <slider :sliderData="example1"></slider>
      </div>
      <div>
        <h3>自动移动</h3>
        <slider :sliderData="nowsecond"></slider>
      </div>
  </div>
</template>

<script>
import slider from "vue_sliding_tab";

export default {
  name: "Demo",
  components: {
    slider
  },

  data() {
    return {
      example0: {
        name: "hour",
        tabList: [
          "<span>1</span>",
          "<span>2</span>",
          "<span>3</span>",
          "<span>4</span>",
          "<span>5</span>",
          "<span>6</span>"
        ],
        slideActiveIndex: 3,
        sliderTime: 400,
        sliderType: "cubic-bezier(0.68, -0.55, 0.265, 1.55)",
        sliderActiver:
          "height: 100%; background:green;border-bottom:3px solid red;margin: 0 10px",
        tabActiver: "color: red;"
      },
      nowsecond: {
        name: "second",
        tabList: [
          "<span>1</span>",
          "<span>2</span>",
          "<span>3</span>",
          "<span>4</span>",
          "<span>5</span>",
          "<span>6</span>",
          "<span>7</span>",
          "<span>8</span>",
          "<span>9</span>",
          "<span>10</span>",
          "<span>11</span>",
          "<span>12</span>"
        ],
        slideActiveIndex: 0,
        sliderTime: 200,
        sliderActiver:
          "height: 100%; border:1px solid red;border-radius: 10px;margin: 0 10px",
        tabActiver: "color: #000;font-weight: bolder;font-size:30px;"
      },
      example1: {
        name: "minute",
        slideActiveIndex: 0,
        tabList: [
          "<span>早安</span>",
          "<span>午安</span>",
          "<span>晚安</span>"
        ],
        sliderActiver: `height: 100%; background-image:url("https://files.cnblogs.com/files/mydia/timg.bmp");margin: 0 10px`,
        tabActiver: "color: #00ccff;"
      }
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.border {
  display: flex;
}
.border h1 {
  width: 200px;
  height: 100px;
  line-height: 100px;
}


.slider_flexbox {
  /* background: yellow; */
}
.slider_flexbox_child {
  color: grey;
  height: 100px;
  line-height: 100px;
}

.slider_wrapper_minute .slider_flexbox_child {
  color: blue;
}
</style>
