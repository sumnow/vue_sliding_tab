# vue_sliding_tab

vue 的滑块标签

### 版本

1.0.1

### 使用说明

    <slider :sliderProperty="probj"></slider>

    import slider from 'vue_sliding_tab'

    probj: {
        // 滑块的名称，非必须，缺省为随机数字
        name: string,
        // 标签页的内容，缺省为[1,2,3,4]
        list: array,
        // 滑动动画的时间，缺省为500，单位毫秒
        TransTime: number
        // 滑动动画的类型，缺省为 'ease-in'
        TransType: string
        // 激活的标签的样式，缺省为 'background: #000'
        TransActiver: string
    }

### 注意事项

1. 最多可以支持12个滑块;

### 样式调整

整个标签页包在 `slider_flexbox` 下
 
每一个标签的类为 `slider_flexbox_chlid`

每一个滑块的通道的类为 `slider_road`, 每个滑块类为 `slider_road > div`



