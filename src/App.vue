<template>
  <div id="app">
    <h1>Flex</h1>

      <p>本文仅用于学习和巩固 flex 布局的相关概念及知识点. </p>
      <p>Flex 是Flexible Box的缩写，意为”弹性布局”，用来为盒状模型提供最大的灵活性。</p>

      <p>
        <small>
          <i>注意，设为 Flex 布局以后，子元素的float、clear和vertical-align属性将失效。</i>
        </small>
        <pre>.box{
          display: flex; /*任何一个容器都可以指定为 Flex 布局。*/
          display: inline-flex; /*行内元素也可以使用 Flex 布局。*/
          display: -webkit-flex; /* Safari -Webkit 内核的浏览器，必须加上-webkit前缀。*/
          display: -webkit-inline-flex; /* Safari -Webkit 内核的浏览器，必须加上-webkit前缀。*/
        }</pre>
      </p>

      <h3>容器的属性(默认样式 row wrap maxHeight:500px minHeight:150px; width:auto )</h3>
      <Container :flexObj='derectionObj'></Container>
      <Container :flexObj='wrapObj'></Container>
      <Container :flexObj='flowObj'></Container>
      <Container :flexObj='justifyContentObj'></Container>
      <Container :flexObj='alignItemsObj'></Container>
      <Container :flexObj='alignContentObj'></Container>

      <Items></Items>
  </div>
</template>

<script>
  import Container from './container.vue'
  import Items from './items.vue'


  export default {
    name: 'app',
    components: {
      Container,
      Items
    },
    data() {
      return {

        derectionObj: {
          title: 'flex-direction',
          info: '主轴的方向即项目的排列方向',
          currentValue: 'row',
          value: [{
              'name': 'row',
              'info': '主轴上项目从左到右水平排列)'
            },
            {
              'name': 'row-reverse',
              'info': '主轴上项目从右到左水平排列'
            },
            {
              'name': 'column',
              'info': '主轴上项目从上到下垂直排列'
            },
            {
              'name': 'column-reverse',
              'info': '主轴上项目从下到上垂直排列'
            }
          ],
        },

        wrapObj: {
          title: 'flex-wrap',
          info: '如果一条轴线排不下，如何换行',
          currentValue: 'nowrap',
          value: [{
              'name': 'nowrap',
              'info': '默认不换行'
            },
            {
              'name': 'wrap',
              'info': '换行，第一行在上方'
            },
            {
              'name': 'wrap-reverse',
              'info': '换行，第一行在下方'
            }
          ],
        },

        flowObj: {
          title: 'flex-flow',
          info: 'flex-direction属性和flex-wrap属性的简写形式',
          currentValue: 'row nowrap',
          value: [{
            'name': 'row nowrap',
            'info': ''
          }, {
            'name': 'row wrap',
            'info': ''
          }, {
            'name': 'row wrap-reverse',
            'info': ''
          }, {
            'name': 'row-reverse nowrap',
            'info': ''
          }, {
            'name': 'row-reverse wrap',
            'info': ''
          }, {
            'name': 'row-reverse wrap-reverse',
            'info': ''
          }, {
            'name': 'column nowrap',
            'info': ''
          }, {
            'name': 'column wrap',
            'info': ''
          }, {
            'name': 'column wrap-reverse',
            'info': ''
          }, {
            'name': 'column-reverse nowrap',
            'info': ''
          }, {
            'name': 'column-reverse wrap',
            'info': ''
          }, {
            'name': 'column-reverse wrap-reverse',
            'info': ''
          }],
        },

        justifyContentObj: {
          title: 'justify-content',
          info: '项目在主轴上的对齐方式',
          currentValue: 'flex-start',
          value: [{
            'name': 'flex-start',
            'info': '（默认值）：左对齐'
          }, {
            'name': 'flex-end',
            'info': '右对齐'
          }, {
            'name': 'center',
            'info': '居中'
          }, {
            'name': 'space-between',
            'info': '两端对齐，项目之间的间隔都相等。'
          }, {
            'name': 'space-around',
            'info': '每个项目两侧的间隔相等。所以，项目之间的间隔比项目与边框的间隔大一倍。'
          }, ],
        },

        alignItemsObj: {
          title: 'align-items',
          info: '项目在交叉轴上如何对齐',
          currentValue: 'stretch',
          value: [{
            'name': 'stretch',
            'info': '默认值,如果项目未设置高度或设为auto，将占满整个容器的高度'
          }, {
            'name': 'flex-start',
            'info': '交叉轴的起点对齐'
          }, {
            'name': 'flex-end',
            'info': '交叉轴的终点对齐'
          }, {
            'name': 'center',
            'info': '交叉轴的中点对齐'
          }, {
            'name': 'baseline',
            'info': '项目的第一行文字的基线对齐'
          }, ],
        },

        alignContentObj: {
          title: 'align-content',
          info: '多根轴线(多行)的对齐方式。如果项目只有一根轴线（一行），该属性不起作用',
          currentValue: 'stretch',
          value: [{
            'name': 'stretch',
            'info': '默认值,轴线占满整个交叉轴'
          }, {
            'name': 'flex-start',
            'info': '交叉轴的起点对齐'
          }, {
            'name': 'flex-end',
            'info': '交叉轴的终点对齐'
          }, {
            'name': 'center',
            'info': '交叉轴的中点对齐'
          }, {
            'name': 'space-between',
            'info': '与交叉轴两端对齐，轴线之间的间隔平均分布'
          }, {
            'name': 'space-around',
            'info': '每根轴线两侧的间隔都相等。所以，轴线之间的间隔比轴线与边框的间隔大一倍。'
          }, ],
        },

      }
    },
    methods: {}
  }

</script>

<style lang="scss">
  $pre: rgb(57, 114, 199);
  $font: gray;

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale; // text-align: center;
    max-width: 1200px;
    margin: 0 auto;
    margin-top: 60px;
  }

  small {
    color: #666;
  }

  h1,
  h2 {
    color: $font;
    font-weight: normal;
    border-bottom: 2px solid gray;
  }

  pre {
    font-size: 15px;
    background-color: $font;
    border-radius: 7px;
    padding: 10px;
    color: #fff;
    overflow-x: auto;
  }

  p {
    background-color: #f5f5f5;
    padding: 10px;
    a {
      cursor: pointer;
      padding: 2px;
      border-radius: 5px;
      color: gray;
      &:hover {
        background-color: $font;
        color: white;
      }
    }
  }

</style>
