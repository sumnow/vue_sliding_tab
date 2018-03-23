<template>
    <div class="slider_flexbox">
        <div v-for="(item, index) in list" :key="index" class="slider_flexbox_child"  @click="FslideTo(index)" :class="{active: index === slideActiveIndex}" v-html="item">
        </div>
        <div class="slider_road" :class="'slider_road_'+name">
            <div :class="'slider_active'+slideActiveIndex"></div>
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
      TransTime: 500,
      TransType: "ease-in",
      TransActiver: "#000",
      name: '',
    };
  },
  props: {
    sliderProperty: Object
  },
  watch: {
    slideActiveIndex(v, o) {}
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
      this.list = obj.list || [1,2,3];
      this.TransTime = obj.TransTime || 500;
      this.TransType = obj.TransType || 'ease-in';
      this.TransActiver = obj.TransActiver || 'background: #000';
    }
  },
  mounted() {
    const l = this.list.length;
    this.defaultSetting(this.sliderProperty)
    this.FloadCssCode(
      `.slider_road.slider_road_${this.name} div {width: ${100 / this.list.length}%;transition: ${
        this.TransTime
      }ms all ${this.TransType};${this.TransActiver};}`
    );
  }
};
</script>

<style scoped>
.slider_flexbox {
  position: relative;
  display: flex;
  justify-content: space-around;
}

.slider_flexbox_child {
  flex: 1;
  position: relative;
  z-index: 2;
  background: transparent;
  cursor: pointer;
  transition: all 500ms ease-in;
}
.slider_road {
  display: flex;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1;
}
.slider_road div {
  height: 100%;
  box-sizing: border-box;
  transform: translateX(0);
}






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



