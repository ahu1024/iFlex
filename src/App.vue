<template>
  <div id="app">
   <h1>Flex</h1>
    <div>
      
      <p>本文仅用于学习和巩固 flex 布局的相关概念及知识点. </p>
      <p>Flex 是Flexible Box的缩写，意为”弹性布局”，用来为盒状模型提供最大的灵活性。</p>

      <p>
        <small><i>注意，设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效。</i></small>
        <pre>.box{
          display: flex; /*任何一个容器都可以指定为 Flex 布局。*/
          display: inline-flex; /*行内元素也可以使用 Flex 布局。*/
          display: -webkit-flex; /* Safari -Webkit 内核的浏览器，必须加上-webkit前缀。*/
          display: -webkit-inline-flex; /* Safari -Webkit 内核的浏览器，必须加上-webkit前缀。*/
        }</pre>
      </p>

      <h3>容器的属性</h3>

      <a name="flex-direction">flex-direction</a>: {{flex_direction}};<hr>
      <p>主轴的方向即项目的排列方向：
        <a v-on:click="change('flex_direction', 'row')">row(水平左浮动) </a> |
        <a v-on:click="change('flex_direction', 'row-reverse')">row-reverse(水平右浮动倒序) </a>| 
        <a v-on:click="change('flex_direction', 'column')">column(垂直) </a>| 
        <a v-on:click="change('flex_direction', 'column-reverse')">column-reverse(垂直倒序); </a>
        <span class="f_box f_derection"  v-bind:style="{ flexDirection: flex_direction }">
          <i>1</i><i>2</i><i>3</i><i>4</i>
        </span>
      </p>

      <a name="flex-wrap">flex-wrap</a>: {{flex_wrap}};<hr>
      <p>如果一条轴线排不下，如何换行：
        <a v-on:click="change('flex_wrap', 'nowrap')">nowrap (默认不换行)</a>| 
        <a v-on:click="change('flex_wrap', 'wrap')">wrap(换行，第一行在上方)</a> | 
        <a v-on:click="change('flex_wrap', 'wrap-reverse')">wrap-reverse(换行，第一行在下方)</a>
        <span class="f_box"  v-bind:style="{ flexWrap:flex_wrap ,width: '200px'}">
          <i>1</i><i>2</i><i>3</i><i>4</i>
        </span>
      </p>

      <a name="flex-flow">flex-flow</a>: {{flex_flow}};<hr>
      <p>flex-direction属性和flex-wrap属性的简写形式：
        <a v-on:click="change('flex_flow', 'row nowrap')">row nowrap</a> |
        <a v-on:click="change('flex_flow', 'row wrap')">row wrap</a> |
        <a v-on:click="change('flex_flow', 'row wrap-reverse')">row wrap-reverse</a> |
        <a v-on:click="change('flex_flow', 'row-reverse nowrap')">row-reverse nowrap</a> |
        <a v-on:click="change('flex_flow', 'row-reverse wrap')">row-reverse wrap</a> |
        <a v-on:click="change('flex_flow', 'row-reverse wrap-reverse')">row-reverse wrap-reverse</a> |
        <a v-on:click="change('flex_flow', 'column nowrap')">column nowrap</a> |
        <a v-on:click="change('flex_flow', 'column wrap')">column wrap</a> |
        <a v-on:click="change('flex_flow', 'column wrap-reverse')">column wrap-reverse</a> |
        <a v-on:click="change('flex_flow', 'column-reverse nowrap')">column-reverse nowrap</a> |
        <a v-on:click="change('flex_flow', 'column-reverse wrap')">column-reverse wrap</a> |
        <a v-on:click="change('flex_flow', 'column-reverse wrap-reverse')">column-reverse wrap-reverse</a>

        <span class="f_box"  v-bind:style="{ flexFlow:flex_flow ,width: '200px'}">
          <i>1</i><i>2</i><i>3</i><i>4</i>
        </span>
      </p>

      <a name="justify-content">justify-content</a>: {{justify_content}};<hr>
      <p>项目在主轴上的对齐方式：
        <a v-on:click="change('justify_content', 'flex-start')">flex-start(默认值,左对齐) </a> |
        <a v-on:click="change('justify_content', 'flex-end')">flex-end(右对齐) </a> |
        <a v-on:click="change('justify_content', 'center')">center(居中) </a> |
        <a v-on:click="change('justify_content', 'space-between')">space-between(两端对齐，项目之间的间隔都相等。) </a> |
        <a v-on:click="change('justify_content', 'space-around')">space-around(每个项目两侧的间隔相等,项目之间的间隔比项目与边框的间隔大一倍) </a> 

        <span class="f_box"  v-bind:style="{ justifyContent:justify_content ,width: ''}">
          <i>1</i><i>2</i><i>3</i><i>4</i>
        </span>
      </p>

      <a name="align-items">align-items</a>: {{align_items}};  (项目高度为auto) <hr>
      <p>项目在交叉轴上如何对齐：
        <a v-on:click="change('align_items', 'stretch')">stretch(默认值,如果项目未设置高度或设为auto，将占满整个容器的高度) </a> |
        <a v-on:click="change('align_items', 'flex-start')">flex-start(默认值,左对齐) </a> |
        <a v-on:click="change('align_items', 'flex-end')">flex-end(交叉轴的终点对齐) </a> |
        <a v-on:click="change('align_items', 'center')">center(交叉轴的中点对齐) </a> |
        <a v-on:click="change('align_items', 'baseline')">baseline(项目的第一行文字的基线对齐。) </a> 

        <span class="f_box f_ai"  v-bind:style="{ alignItems:align_items , height: '200px'}">
          <i>1</i><i>2</i><i>3</i><i>4</i>
        </span>
      </p>

      <a name="align-content">align-content</a>: {{align_content}};<hr>
      <p>多根轴线的对齐方式。如果项目只有一根轴线，该属性不起作用：
        <a v-on:click="change('align_content', 'stretch')">stretch(默认值,轴线占满整个交叉轴) </a> |
        <a v-on:click="change('align_content', 'flex-start')">flex-start(与交叉轴的起点对齐) </a> |
        <a v-on:click="change('align_content', 'flex-end')">flex-end(与交叉轴的终点对齐) </a> |
        <a v-on:click="change('align_content', 'center')">center(与交叉轴的中点对齐) </a> |
        <a v-on:click="change('align_content', 'space-between')">flex-between(与交叉轴两端对齐，轴线之间的间隔平均分布) </a> |
        <a v-on:click="change('align_content', 'space-around')">flex-around(每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍) </a> 

        <span class="f_box f_ac"  v-bind:style="{ alignContent:align_content , height: '200px', width: '200px', flexFlow: 'row wrap'}">
          <i>1</i><i>2</i><i>3</i><i>4</i>
        </span>
      </p>

      <h3>项目的属性</h3>

      <a name="order">order</a>: 项目的排列顺序。数值越小，排列越靠前，默认为0<hr>
      <p>
        <span class="f_box" >
          <i :style="{ order: 0, width: 'auto', height: 'auto'}"> 1 <br> order: 0 </i>
          <i :style="{ order: 2, width: 'auto', height: 'auto'}"> 2 <br> order: 2 </i>
          <i :style="{ order: 3, width: 'auto', height: 'auto'}"> 3 <br> order: 3 </i>
          <i :style="{ order: 1, width: 'auto', height: 'auto'}"> 4 <br> order: 1 </i>
        </span>
      </p>


      <a name="flex-grow">flex-grow</a>: 项目的放大比例，默认为0，即如果存在剩余空间，也不放大<hr>
      <p>
        <span class="f_box" >
          <i :style="{ flexGrow: 0, width: 'auto', height: 'auto'}"> 1 <br> flex-grow: 0 </i>
          <i :style="{ flexGrow: 2, width: 'auto', height: 'auto'}"> 2 <br> flex-grow: 2 </i>
          <i :style="{ flexGrow: 3, width: 'auto', height: 'auto'}"> 3 <br> flex-grow: 3 </i>
          <i :style="{ flexGrow: 1, width: 'auto', height: 'auto'}"> 4 <br> flex-grow: 1 </i>
        </span>
      </p>

      <a name="flex-shrink">flex-shrink</a>: 项目的缩小比例，默认为1，即如果空间不足，该项目将缩小<hr>
      <p>
        <span class="f_box" :style="{  width: '200px'}">
          <i :style="{ flexShrink: 0, width: 'auto', height: 'auto'}"> 1 <br> flex-shrink: 0 </i>
          <i :style="{ flexShrink: 2, width: 'auto', height: 'auto'}"> 2 <br> flex-shrink: 2 </i>
          <i :style="{ flexShrink: 3, width: 'auto', height: 'auto'}"> 3 <br> flex-shrink: 3 </i>
          <i :style="{ flexShrink: 1, width: 'auto', height: 'auto'}"> 4 <br> flex-shrink: 1 </i>
        </span>
      </p>

      <a name="flex-basis">flex-basis</a>: 在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。<hr>
      <p>
        <span class="f_box">
          <i :style="{ flexBasis: 'auto', width: 'auto', height: 'auto'}"> 1 <br> flex-basis: auto </i>
          <i :style="{ flexBasis: '300px', width: 'auto', height: 'auto'}"> 2 <br> flex-basis: '300px' </i>
          <i :style="{ flexBasis: '200px', width: 'auto', height: 'auto'}"> 3 <br> flex-basis: '200px' </i>
          <i :style="{ flexBasis: '100px', width: 'auto', height: 'auto'}"> 4 <br> flex-basis: '100px' </i>
        </span>
      </p>

      <a name="align-self">align-self</a>: 允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。 <hr>
      <p>
        <span class="f_box" :style="{  height: '200px'}">
          <i :style="{ alignSelf: 'auto', width: 'auto', height: 'auto'}"> 1 <br> align-self: auto (默认) </i>
          <i :style="{ alignSelf: 'flex-start', width: 'auto', height: 'auto'}"> 2 <br> align-self: flex-start </i>
          <i :style="{ alignSelf: 'flex-end', width: 'auto', height: 'auto'}"> 3 <br> align-self: flex-end </i>
          <i :style="{ alignSelf: 'center', width: 'auto', height: 'auto'}"> 4 <br> align-self: center </i>
          <i :style="{ alignSelf: 'baseline', width: 'auto', height: 'auto'}"> 5 <br> align-self: baseline </i>
          <i :style="{ alignSelf: 'stretch', width: 'auto', height: 'auto'}"> 6 <br> align-self: stretch </i>
        </span>
      </p>

      <a name="flex">flex</a>: 默认值为0 1 auto, flex-shrink 和 flex-basis的简写。后两个属性可选。<hr>
      <p>
        <span class="f_box" :style="{  height: '200px'}">
          <i :style="{ flex: '0', width: 'auto', height: 'auto'}"> 1 <br> flex: 0 (默认) </i>
          <i :style="{ flex: '0 1 suto', width: 'auto', height: 'auto'}"> 2 <br> flex: 0 1 auto </i>
          <i :style="{ flex: '0 1 300px', width: 'auto', height: 'auto'}"> 3 <br> flex: 0 1 300px </i>
          <i :style="{ flex: '0 1 200px', width: 'auto', height: 'auto'}"> 4 <br> flex: 0 1 200px </i>
          <i :style="{ flex: '0 1 100px', width: 'auto', height: 'auto'}"> 5 <br> flex: 0 1 100px </i>
        </span>
      </p>
    </div>
    
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      flex_direction: 'row',
      flex_wrap: 'nowrap',
      flex_flow: 'row nowrap',
      justify_content: 'flex-start',
      align_items: 'stretch',
      align_content: 'stretch'
    }
  },
   methods: {
     change: function(el,style){
       switch(el){
          case 'flex_direction': 
          this.flex_direction = style; break;

          case 'flex_wrap': 
          this.flex_wrap = style; break;

          case 'flex_flow': 
          this.flex_flow = style; break;

          case 'justify_content': 
          this.justify_content = style; break;
          
          case 'align_items': 
          this.align_items = style; break;

          case 'align_content': 
          this.align_content = style; break;

          default:;
       }
     }
   }
}
</script>

<style lang="scss">
$pre: rgb(57, 114, 199);
$font: gray; 

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif; 
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  max-width: 1200px;
  margin: 0 auto;
  margin-top: 60px;
}
.f_box{
  display: flex;
  display: -webkit-flex;
  background-color: white;
  border-radius: 7px;
  margin: 10px 0;
  i{
    display: block;
    width: 40px;
    height: 40px;
    margin: 10px;
    background-color: gold;
    text-align: center;
    line-height: 40px;
  }
}
.f_ai i,.f_ac i{
    height: auto;
}

small{
  color: #666;
}

h1, h2 {
  color: $font;
  font-weight: normal;
  border-bottom: 2px solid gray; 
}

pre{
    font-size: 15px;
    background-color: $font;
    border-radius: 7px;
    padding: 10px;
    color: #fff;
    overflow-x: auto;
}

a[name]{
  font-weight: bold;
}

p{
    background-color: #f5f5f5;
    padding: 10px;
    a{
      cursor: pointer;
      padding: 2px;
      border-radius: 5px;
      color: gray;
      &:hover{
        background-color: $font;
        color:  white;
      }
    }
}

</style>
