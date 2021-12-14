<template>
    <div class="showItems">
      <div class="list">list 1</div>
      <span v-show="checkedList" v-for="item in Number(itemNumber)" :key="item" class="itemList"><div class="myList" :style="{background:itemColour}">{{item}}</div></span>
    </div>
</template>

<script>
export default {
  name: 'itemList',
  data(){
    return{
      itemNumber:0,
      itemColour:''
    }
  },
  props:{
    checkedList:{
      type:Boolean,
    }
  },
  methods:{
    showList:{
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.wrapper{
  display: flex;
}
.items{
  border: 2px solid gray;
  width: 50%;
}
.showItems{
  width: 50%;
  border: 2px solid olivedrab;
}
.myList{
  display: inline-block;
  border: 2px solid gray;
  margin-right: 2px;
  font-size: 0;
  width: 10px;
  height: 10px;
}
</style>
