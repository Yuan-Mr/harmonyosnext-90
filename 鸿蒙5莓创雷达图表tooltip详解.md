### Hello everyone, welcome back to our special session on HarmonyOS 5 Berry Creative chart components. In this episode, we'll dive deep into the most important interactive feature of the radar chart component: the complete usage of the **tooltip** property. As the "information bridge" in data visualization, flexible configuration of tooltips can significantly enhance the efficiency of data communication. Let's systematically explore each configuration item step by step.  


### 一、Basic Control Properties  

#### 1. `show`: Visibility Toggle  
**Function**: Controls tooltip display.  
**Type**: Boolean  
**Default**: `true`  
**Scenario**: Dynamically hide tooltips (e.g., performance optimization on mobile).  

```json
tooltip: { 
  show: false  // Hide all tooltips
}
```  

#### 2. `padding`: Inner Spacing  
**Function**: Sets spacing between tooltip content and border.  
**Type**: Number  
**Default**: `10`  
**Scenario**: Adjust tooltip compactness.  

```json
tooltip: {
  padding: 20,  // Increase inner spacing
  backgroundColor: '#fff'
}
```  


### 二、Visual Style Configuration  

#### 3. `backgroundColor`: Background Color  
**Function**: Sets tooltip background color.  
**Type**: String  
**Default**: `'rgba(0,0,0,0.7)'`  
**Scenario**: Match different themes.  

```json
tooltip: {
  backgroundColor: '#2c3e50',  // Dark blue background
  textStyle: { color: '#fff' }
}
```  

#### 4. `border`: Border Group  
- `borderWidth`: Border thickness (Number, default `0`).  
- `borderColor`: Border color (String, default `'#333'`).  
**Scenario**: Highlight tooltips.  

```json
tooltip: {
  borderWidth: 2,
  borderColor: '#e74c3c',  // Red warning border
  backgroundColor: '#f9f9f9'
}
```  


### 三、Advanced Indicator Configuration  

#### 5. `axisPointer`: Axis Indicator  
**Function**: Configures axis indicator type and style.  
**Type**: Object  
**Sub-properties**:  
- `type`: Indicator type (`'line'` | `'shadow'`, default `'line'`).  
- `lineStyle`: Line configuration:  
  - `width`: Line width (default `1`).  
  - `type`: Line style (`'solid'` | `'dashed'`, default `'solid'`).  
  - `color`: Line color (default `'#DDE2EB'`).  
- `shadowStyle`: Shadow configuration:  
  - `color`: Shadow color (default `'rgba(150,150,150,0.2)'`).  

**Scenario**: Highlight regions in multi-data comparisons.  

```json
tooltip: {
  axisPointer: {
    type: 'shadow',
    shadowStyle: {
      color: 'rgba(255,165,0,0.2)',  // Orange shadow
      borderWidth: 0
    }
  }
}
```  


### 四、Text Style System  

#### 6. `textStyle`: Text Configuration  
**Function**: Controls tooltip text style.  
**Type**: Object  
**Sub-properties**:  
- `color`: Text color (String, default `'#fff'`).  
- `fontWeight`: Font weight (`'normal'` | `'bold'`, default `'normal'`).  
- `fontFamily`: Font family (String, default `'sans-serif'`).  
- `fontSize`: Font size (Number, default `14`).  

**Scenario**: Adapt to high-contrast environments.  

```json
tooltip: {
  textStyle: {
    color: '#2c3e50',
    fontWeight: 'bold',
    fontSize: 16,
    fontFamily: 'Microsoft YaHei'
  }
}
```  


### 五、Animation Control System  

#### 7. `animationCurve`: Animation Easing  
**Function**: Sets tooltip appearance/disappearance animation.  
**Type**: String  
**Default**: `'easeOutCubic'`  
**Options**: `'linear'`, `'easeInOut'`, etc. (CSS easing curves).  
**Scenario**: Customize animation effects.  

```json
tooltip: {
  animationCurve: 'easeInOutQuad'
}
```  

#### 8. `animationFrame`: Animation Duration  
**Function**: Controls animation duration (ms).  
**Type**: Number  
**Default**: `0` (no animation).  
**Scenario**: Smooth transition effects.  

```json
tooltip: {
  animationFrame: 300  // 300ms animation
}
```  


### 六、Comprehensive Practical Example  
**Scenario**: E-commerce data comparison - Huawei vs. Apple phones across dimensions.  

```json
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

**Effect Explanation**:  
- Semi-transparent white background with red dashed indicators.  
- Dark gray text for readability.  
- 200ms elastic animation for lively interactions.  


### Conclusion  
That wraps up our in-depth guide to tooltips! Use these properties like building blocks to create professional, design-driven interactive systems. In practice, prioritize data display needs first, then design tooltip visual hierarchy with the "background-color → text-color → indicator" triad. Let your charts truly tell data stories! 📊
