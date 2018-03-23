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
        tabList: array,
        // 滑动动画的时间，缺省为500，单位毫秒
        TransTime: number
        // 滑动动画的类型，缺省为 'ease-in'
        TransType: string
        // 激活的标签的样式，缺省为 'background: #000'
        TransActiver: string
    }

### 注意事项

1. 最多可以支持12个滑块;

2. 父组件需要改写 `slider_tab` 的样式时，css不可以使用 `scoped`

3. `tabList` 中可以插入html标签块

### 样式调整

在引用 `slider_tab` 的父组件 `<css>` 中写入样式即可

整个标签页包在 `slider_flexbox` 下
 
每一个标签的类为 `slider_flexbox_chlid`

每一个滑块的通道的类为 `slider_road`, 每个滑块类为 `slider_road > div`


### todo

1. `slider_flexbox_child` 的样式可定义，主要为transition-time

2. `slider_flexbox_child` 为纵

3. 复杂的动画。



