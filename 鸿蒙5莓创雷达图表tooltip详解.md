大家好，欢迎回来鸿蒙5莓创图表组件的专场，我们这一期来深入讲解雷达图组件中最重要的交互功能——tooltip（提示层）属性的完整用法。作为数据可视化的"信息桥梁"，tooltip的灵活配置能极大提升图表的信息传达效率，下面我们以分层递进的方式全面解析每个配置项。

* * *

### 一、基础控制属性

#### 1. show 显示开关

作用：控制提示层的显示与隐藏 类型：Boolean 默认：true 场景：当需要动态控制提示层时（如移动端性能优化场景）

```
tooltip: { 
  show: false  // 隐藏所有提示层
}
```

#### 2. padding 内边距

作用：设置提示层内容与边框的间距 类型：Number 默认：10 场景：需要调整提示框紧凑度时

```
tooltip: {
  padding: 20,  // 扩大内边距
  backgroundColor: '#fff'
}
```

* * *

### 二、视觉样式配置

#### 3. backgroundColor 背景色

作用：设置提示层背景颜色 类型：String 默认：'rgba(0,0,0,0.7)' 可选值：颜色名称/十六进制/RGBA 场景：适配不同主题色时

```
tooltip: {
  backgroundColor: '#2c3e50',  // 深蓝色背景
  textStyle: { color: '#fff' }
}
```

#### 4. border 边框组

-   borderWidth：边框粗细（Number，默认0）
-   borderColor：边框颜色（String，默认'#333'） 场景：需要突出提示层时

```
tooltip: {
  borderWidth: 2,
  borderColor: '#e74c3c',  // 红色警示边框
  backgroundColor: '#f9f9f9'
}
```

* * *

### 三、高级指示器配置

#### 5. axisPointer 指示线

作用：设置坐标轴指示线类型及样式 类型：Object 子属性：

-   type：指示线类型（'line' | 'shadow'，默认'line'）
-   lineStyle：线型配置
-   -   width：线宽（默认1）
    -   type：线型（'solid' | 'dashed'，默认'solid'）
    -   color：颜色（默认'#DDE2EB'）
-   shadowStyle：阴影配置
-   -   color：阴影颜色（默认'rgba(150,150,150,0.2)'）
-   场景：多数据对比时需要高亮区域
-   ```
    tooltip: {
      axisPointer: {
        type: 'shadow',
        shadowStyle: {
          color: 'rgba(255,165,0,0.2)',  // 橙色阴影
          borderWidth: 0
        }
      }
    }
    ```
-   * * *
-   ### 四、文本样式体系
-   #### 6. textStyle 文本配置
-   作用：控制提示层文字样式 类型：Object 子属性：
-   -   color：文字颜色（String，默认'#fff'）
    -   fontWeight：字重（'normal' | 'bold'，默认'normal'）
    -   fontFamily：字体（String，默认'sans-serif'）
    -   fontSize：字号（Number，默认14）
-   场景：适配高对比度显示环境
-   ```
    tooltip: {
      textStyle: {
        color: '#2c3e50',
        fontWeight: 'bold',
        fontSize: 16,
        fontFamily: 'Microsoft YaHei'
      }
    }
    ```
-   * * *
-   ### 五、动画控制系统
-   #### 7. animationCurve 动画曲线
-   作用：设置提示层出现/消失的动画效果 类型：String 默认：'easeOutCubic' 可选值：'linear' | 'easeInOut' 等CSS动画曲线 场景：需要定制化动效时
-   ```
    tooltip: {
      animationCurve: 'easeInOutQuad'
    }
    ```
-   #### 8. animationFrame 动画时长
-   作用：控制动画持续时间（单位：毫秒） 类型：Number 默认：0（无动画） 场景：需要流畅过渡效果时
-   ```
    tooltip: {
      animationFrame: 300  // 300ms动画
    }
    ```
-   * * *
-   ### 六、综合实战案例
-   电商数据对比场景：对比华为与苹果手机在不同维度的表现
-   ```
    tooltip: {
      show: true,
      padding: 15,
      backgroundColor: 'rgba(255,255,255,0.95)',
      borderWidth: 1,
      borderColor: '#bdc3c7',
      textStyle: {
        color: '#2d3436',
        fontSize: 14,
        fontFamily: 'Arial'
      },
      axisPointer: {
        type: 'line',
        lineStyle: {
          width: 2,
          color: '#e74c3c',
          type: 'dashed'
        }
      },
      animationCurve: 'easeInOutBack',
      animationFrame: 200
    }
    ```
-   效果说明：白色半透明背景搭配红色虚线指示器，文字采用深灰色系，在保持专业性的同时提升可读性，200ms的弹性动画让交互更生动。
-   * * *
-   好，这期讲到这里就结束了，希望大家通过这篇深度解析，能像搭积木一样灵活运用tooltip的各个属性，打造出既专业又充满设计感的交互提示系统。在实际开发中，建议先规划好数据展示的优先级，再通过"背景色-文字色-指示线"的配色三原则来设计tooltip的视觉层次，让您的图表真正成为数据故事的讲述者！