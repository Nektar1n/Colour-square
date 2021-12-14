<template>
  <div id="app">
    <div class="wrapper">
      <div class="itemsLists">
        <div class="allTitle"><div class="showBtn" @click="showItem1()" id="show1">❯</div><div class="titles"></div>
        <input type="checkbox" class="customCheckbox" v-model="hasChekedList1">List 1</div><div class="listTitle">List 1</div>
        <items v-show="hasShowItem1" :hasChekedList1="hasChekedList1"></items>
        <div class="allTitle"><div class="showBtn" @click="showItem2()" id="show2">❯</div><div class="titles"></div>
          <input type="checkbox" class="customCheckbox" v-model="hasChekedList2">List 2</div><div class="listTitle">List 2</div>
        <items v-show="hasShowItem2" :hasChekedList2="hasChekedList2"/>
        <div class="allTitle"><div class="showBtn" @click="showItem3()" id="show3">❯</div><div class="titles"></div>
          <input type="checkbox" class="customCheckbox" v-model="hasChekedList3">List 3</div><div class="listTitle">List 3</div>
        <items v-show="hasShowItem3" :hasChekedList3="hasChekedList3"/>
        <div class="allTitle"><div class="showBtn" @click="showItem4()" id="show4">❯</div><div class="titles"></div>
          <input type="checkbox" class="customCheckbox" v-model="hasChekedList4">List 4</div><div class="listTitle">List 4</div>
        <items v-show="hasShowItem4" :hasChekedList4="hasChekedList4"/>
      </div>
    </div>
  </div>
</template>

<script>
import items from "@/components/items";

export default {
  name: 'App',
  components: {
    items
  },
  data(){
    return{
      itemList:[1,2,3,4],
      hasChekedList1:false,
      hasChekedList2:false,
      hasChekedList3:false,
      hasChekedList4:false,
      hasShowItem1:true,
      hasShowItem2:true,
      hasShowItem3:true,
      hasShowItem4:true
    }
  },methods:{
    showItem1(){
      if (this.hasShowItem1){
        this.hasShowItem1=false
        document.getElementById('show1').style='transform: rotate(360deg)'
      }else {this.hasShowItem1=true
      document.getElementById('show1').style='transform: rotate(90deg)'}
    },
    showItem2(){
      if (this.hasShowItem2){
        this.hasShowItem2=false
        document.getElementById('show2').style='transform: rotate(360deg)'
      }else {this.hasShowItem2=true
        document.getElementById('show2').style='transform: rotate(90deg)'}
    },
    showItem3(){
      if (this.hasShowItem3){
        this.hasShowItem3=false
        document.getElementById('show3').style='transform: rotate(360deg)'
      }else {this.hasShowItem3=true
        document.getElementById('show3').style='transform: rotate(90deg)'}
    },showItem4(){
      if (this.hasShowItem4){
        this.hasShowItem4=false
        document.getElementById('show4').style='transform: rotate(360deg)'
      }else {this.hasShowItem4=true
        document.getElementById('show4').style='transform: rotate(90deg)'}
    }
  }
}
</script>

<style>
#app{
  margin: 10%;
}

.listTitle{
  position: relative;
  left: 55%;
  bottom: 20px;
  font-size: 20px;
}
.titles{
  position: relative;
  top: 20px;
}
input[type='checkbox']{
  transform: scale(1.5);
}
.allTitle{
  display: flex;
  width: 300px;
  font-size: 20px;
}
.showBtn{
  margin-right: 10px;
}
.customCheckbox{
  margin-right: 15px;
  margin-top: 5px;
}
.itemsLists{
  border: solid 2px gray;
  padding: 10px;
}
.showBtn{
  cursor: pointer;
  transform: rotate(90deg);
}

</style>

