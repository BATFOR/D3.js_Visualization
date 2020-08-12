此代码基于前端可视化框架[d3.js](https://github.com/xswei/d3js_doc)。
d3个人感觉和JQuery很像，主要对DOM进行数据绑定且进行相关操作。在学习D3之前，除了对HTML、css、js有相关应用了解外，还需对[SVG](https://www.runoob.com/svg/svg-rect.html)进行相关了解。d3中大部分函数库都是对数据进行处理
，然后将这这些处理了数据应用到画图展示上。  

#### 力向导图 ####
**使用d3 v5版**  
**参考：** 此代码主要参考[https://github.com/zhaoluo123/vue-d3-force](https://github.com/zhaoluo123/vue-d3-force)，去除了其中的vue模块，将d3版本从v3提升到v5。  

力向导图可视，主要采用d3中力学仿真([**forceSimulation**](https://github.com/xswei/d3-force/blob/master/README.md#forceSimulation))模块，这个模块主要功能就是对数据不断进行仿真（可以根据需求添加多个具体的仿真模型，通过force函数），它会将每次仿真结果直接
以属性的方式直接加入（更新）到用户传入的**节点对象和边对象数据**中，比如会添加节点的x,y坐标等，每次仿真都会触发tick事件。而开发者需要做的就是在tick事件中进行图形的绘制渲染。   
另外，[选择器(selection)](https://github.com/xswei/d3-selection/blob/master/README.md#selection)模块是d3中最常用的模块，和jQuery选择器一样，可对页面元素进行获取、属性更改、数据绑定等操作。

**功能：** 
1. 节点之间多关系绘制，节点自我关系绘制
2. 节点拖动放缩
3. 节点隐藏、解除固定（初始全部固定、拖动节点会触发当前节点固定）、删除（只编写函数接口）功能
