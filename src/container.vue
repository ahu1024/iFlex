<template>
  <section>
    <b>{{myFlexObj.title}}</b>: {{myFlexObj.currentValue}};
    <a v-on:click="setCount(5)">单行5个</a>
    <a v-on:click="setCount(15)">多行15个</a>
    <hr>
    <p>{{myFlexObj.info }}：

      <a v-for="(item, index) in myFlexObj.value" :key="index" v-on:click="change(item.name)">{{item.name}} {{item.info}} |</a>

      <span class="f_box" v-bind:style="currentStyle">
        <i v-for="(item, index) in count" :key="index">
         
            <b v-if="index==3" :style="{fontSize:'30px'}">{{item}}</b>
            <b v-else>{{item}}</b>
        </i>
    


      </span>

    </p>
  </section>
</template>

<script>
  export default {
    props: ['flexObj'],
    data: function () {
      return {
        count: 5,
        myFlexObj: this.flexObj
      }
    },
    computed: {
      currentStyle: function () {
        var obj;
        switch (this.myFlexObj.title) {
          case 'flex-direction':
            obj = {
              flexDirection: this.myFlexObj.currentValue
            };
            break;
          case 'flex-wrap':
            obj = {
              flexWrap: this.myFlexObj.currentValue
            };
            break;
          case 'flex-flow':
            obj = {
              flexFlow: this.myFlexObj.currentValue
            };
            break;
          case 'justify-content':
            obj = {
              justifyContent: this.myFlexObj.currentValue
            };
            break;
          case 'align-items':
            obj = {
              alignItems: this.myFlexObj.currentValue
            };
            break;
          case 'align-content':
            obj = {
              alignContent: this.myFlexObj.currentValue
            };
            break;
          default:
            obj = '';
            break;
        }
        return obj;
      }
    },

    methods: {
      setCount: function (num) {
        this.count = num;
      },
      change: function (value) {
        this.myFlexObj.currentValue = value;
      }
    }
  }

</script>
<style lang="scss" scoped>
  $pre: rgb(57, 114, 199);
  $font: gray;
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

  .f_box {
    display: flex;
    display: -webkit-flex;
    flex-flow: row wrap;
    background-color: white;
    border-radius: 7px;
    margin: 10px 0;
    width: auto;
    max-height: 500px;
    min-height: 150px;
    i {
      display: block;
      width: 10%;
      height: 40px;
      margin: 10px;
      background-color: gold;
      text-align: center;
      line-height: 40px;
    }
  }

  p {
    background-color: #f5f5f5;
    padding: 10px;

  }

</style>
