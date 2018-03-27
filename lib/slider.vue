<template>
  <div class="slider_wrapper" :class="'slider_wrapper_'+name">
    <div class="slider_flexbox">
      <div v-for="(item, index) in list" :key="index" class="slider_flexbox_child"  @click="FslideTo(index)" :class="{active: index === slideActiveIndex}" v-html="item">
      </div>
      <div class="slider_road">
          <div :class="'slider_active'+slideActiveIndex">
            <div class="slider_road_inner"></div>
          </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      slideActiveIndex: 0,
      list: ["<span>123</span>", "<span>123</span>", "<span>123</span>"],
      listLen: 0,
      sliderTime: 0,
      sliderType: "",
      sliderActiver: "",
      tabActiver: '',
      name: '',
    };
  },
  props: {
    sliderData: Object
  },
  watch: {
    sliderData: {
      handler(v, o) {
        console.log(v)
        this.renderTime()
      },
      deep: true
    }
  },
  methods: {
    FslideTo(i) {
      this.slideActiveIndex = i;
    },
    FloadCssCode(code) {
      var style = document.createElement("style");
      style.type = "text/css";
      style.rel = "stylesheet";
      //for Chrome Firefox Opera Safari
      style.appendChild(document.createTextNode(code));
      //for IE
      //style.styleSheet.cssText = code;
      var head = document.getElementsByTagName("head")[0];
      head.appendChild(style);
    },
    defaultSetting(obj) {
      this.name = obj.name || Math.random()
      this.slideActiveIndex = parseInt(obj.slideActiveIndex) <= 12 ? parseInt(obj.slideActiveIndex) : 0 || 0;
      this.list = obj.tabList || [1,2,3];
      this.sliderTime = obj.sliderTime || 500;
      this.sliderType = obj.sliderType || 'linear';
      this.sliderActiver = obj.sliderActiver || 'background: #000';
      this.tabActiver = obj.tabActiver || '';
    },
    renderTime () {
      const l = this.list.length;
      this.defaultSetting(this.sliderData)
      this.FloadCssCode(
        `.slider_wrapper_${this.name} .slider_road>div {width: ${100 / this.list.length}%;transition: ${this.sliderTime}ms all ${this.sliderType};}
        .slider_wrapper_${this.name} .slider_road_inner {${this.sliderActiver};}
        .slider_wrapper_${this.name} .slider_flexbox_child.active{${this.tabActiver};transition-duration:${this.sliderTime}ms}`
      );
    }
  },
  mounted() {
    this.renderTime()
  }
};
</script>

<style scoped>

.slider_wrapper {
  flex: 1;
}

.slider_flexbox {
  position: relative;
  display: flex;
  justify-content: space-around;
}

.slider_flexbox_child {
  flex: 1;
  position: relative;
  z-index: 2;
  text-align: center;
  vertical-align: middle;
  background: transparent;
  cursor: pointer;
  transition-property: all;
  transition-timing-function: ease-in;
  transition-delay: 0;
}
.slider_road {
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}
.slider_road>div {
  height: 100%;
  transform: translateX(0);
}
.slider_road_inner {
  box-sizing: border-box;
  background-size: cover;
}

/* slider-animation */
.slider_road .slider_active1 {
  transform: translateX(100%);
}
.slider_road .slider_active2 {
  transform: translateX(200%);
}
.slider_road .slider_active3 {
  transform: translateX(300%);
}
.slider_road .slider_active4 {
  transform: translateX(400%);
}
.slider_road .slider_active5 {
  transform: translateX(500%);
}
.slider_road .slider_active6 {
  transform: translateX(600%);
}
.slider_road .slider_active7 {
  transform: translateX(700%);
}
.slider_road .slider_active8 {
  transform: translateX(800%);
}
.slider_road .slider_active9 {
  transform: translateX(900%);
}
.slider_road .slider_active10 {
  transform: translateX(1000%);
}
.slider_road .slider_active11 {
  transform: translateX(1100%);
}
.slider_road .slider_active12 {
  transform: translateX(1200%);
}
</style>



