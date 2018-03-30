<template>
  <div>
      <h3>项目的属性(默认样式 row wrap maxHeight:500px minHeight:100px; width:auto )</h3>

      <b>order</b>: 项目的排列顺序。数值越小，排列越靠前，默认为0
      <hr>
      <p>
        <span class="f_box">
          <i :style="{ order: 0, width: 'auto', height: 'auto'}"> 1
            <br> order: 0 </i>
          <i :style="{ order: 2, width: 'auto', height: 'auto'}"> 2
            <br> order: 2 </i>
          <i :style="{ order: 3, width: 'auto', height: 'auto'}"> 3
            <br> order: 3 </i>
          <i :style="{ order: 1, width: 'auto', height: 'auto'}"> 4
            <br> order: 1 </i>
        </span>
      </p>


      <b>flex-grow</b>: 项目的放大比例，默认为0，即如果存在剩余空间，也不放大
      <hr>
      <p>
        <span class="f_box">
          <i :style="{ flexGrow: 0, width: 'auto', height: 'auto'}"> 1
            <br> flex-grow: 0 </i>
          <i :style="{ flexGrow: 2, width: 'auto', height: 'auto'}"> 2
            <br> flex-grow: 2 </i>
          <i :style="{ flexGrow: 3, width: 'auto', height: 'auto'}"> 3
            <br> flex-grow: 3 </i>
          <i :style="{ flexGrow: 1, width: 'auto', height: 'auto'}"> 4
            <br> flex-grow: 1 </i>
        </span>
      </p>

      <b>flex-shrink</b>: 项目的缩小比例，默认为1，即如果空间不足，该项目将缩小
      <hr>
      <p>
        <span class="f_box" :style="{ width: '200px', flexFlow: 'row nowrap'}">
          <i :style="{ flexShrink: 0, width: 'auto', height: 'auto'}"> 1
            <br> flex-shrink: 0 </i>
          <i :style="{ flexShrink: 2, width: 'auto', height: 'auto'}"> 2
            <br> flex-shrink: 2 </i>
          <i :style="{ flexShrink: 3, width: 'auto', height: 'auto'}"> 3
            <br> flex-shrink: 3 </i>
          <i :style="{ flexShrink: 1, width: 'auto', height: 'auto'}"> 4
            <br> flex-shrink: 1 </i>
        </span>
      </p>

      <b>flex-basis</b>: 在分配多余空间之前，项目占据的主轴空间（main size）。浏览器根据这个属性，计算主轴是否有多余空间。它的默认值为auto，即项目的本来大小。
      <hr>
      <p>
        <span class="f_box">
          <i :style="{ flexBasis: 'auto', width: 'auto', height: 'auto'}"> 1
            <br> flex-basis: auto </i>
          <i :style="{ flexBasis: '300px', width: 'auto', height: 'auto'}"> 2
            <br> flex-basis: '300px' </i>
          <i :style="{ flexBasis: '200px', width: 'auto', height: 'auto'}"> 3
            <br> flex-basis: '200px' </i>
          <i :style="{ flexBasis: '100px', width: 'auto', height: 'auto'}"> 4
            <br> flex-basis: '100px' </i>
        </span>
      </p>

      <b>align-self</b>: 允许单个项目有与其他项目不一样的对齐方式，可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch。
      <hr>
      <p>
        <span class="f_box">
          <i :style="{ alignSelf: 'auto', width: 'auto', height: 'auto'}"> 1
            <br> align-self: auto (默认) </i>
          <i :style="{ alignSelf: 'flex-start', width: 'auto', height: 'auto'}"> 2
            <br> align-self: flex-start </i>
          <i :style="{ alignSelf: 'flex-end', width: 'auto', height: 'auto'}"> 3
            <br> align-self: flex-end </i>
          <i :style="{ alignSelf: 'center', width: 'auto', height: 'auto'}"> 4
            <br> align-self: center </i>
          <i :style="{ alignSelf: 'baseline', width: 'auto', height: 'auto'}"> 5
            <br> align-self: baseline </i>
          <i :style="{ alignSelf: 'stretch', width: 'auto', height: 'auto'}"> 6
            <br> align-self: stretch </i>
        </span>
      </p>

      <b>flex</b>: 默认值为0 1 auto, flex-shrink 和 flex-basis的简写。后两个属性可选。
      <hr>
      <p>
        <span class="f_box">
          <i :style="{ flex: '0', width: 'auto', height: 'auto'}"> 1
            <br> flex: 0 (默认) </i>
          <i :style="{ flex: '0 1 suto', width: 'auto', height: 'auto'}"> 2
            <br> flex: 0 1 auto </i>
          <i :style="{ flex: '0 1 300px', width: 'auto', height: 'auto'}"> 3
            <br> flex: 0 1 300px </i>
          <i :style="{ flex: '0 1 200px', width: 'auto', height: 'auto'}"> 4
            <br> flex: 0 1 200px </i>
          <i :style="{ flex: '0 1 100px', width: 'auto', height: 'auto'}"> 5
            <br> flex: 0 1 100px </i>
        </span>
      </p>
    </div>
</template>
<script>
export default {
  
}
</script>
<style lang="scss" scoped>

  .f_box {
    display: flex;
    display: -webkit-flex;
    flex-flow: row wrap;
    background-color: white;
    border-radius: 7px;
    margin: 10px 0;
    width: auto;
    max-height: 500px;
    height: 100px;
    i {
      display: block;
      width: 10%;
      height: 40px;
      margin: 5px;
      padding: 5px;
      background-color: gold;
      text-align: center;
    }
  }
</style>
