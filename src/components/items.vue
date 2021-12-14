<template>
  <div class="wrapper">
    <div class="items">
      <dl>
        <dt>
          <input type="checkbox" v-model="checkedList1"><label> item 1</label><input type="number" max="1000" min="0" v-model="itemNumber1" placeholder="number of squares"><input type="color" class="colourSquare" v-model="itemColour1">
        </dt>
        <dt>
          <input type="checkbox" v-model="checkedList2"><label> item 2</label><input type="number" max="1000" min="0" v-model="itemNumber2" placeholder="number of squares"><input type="color" class="colourSquare" v-model="itemColour2">
        </dt>
        <dt>
          <input type="checkbox" v-model="checkedList3"><label> item 3</label><input type="number" max="1000" min="0" v-model="itemNumber3" placeholder="number of squares"><input type="color" class="colourSquare" v-model="itemColour3">
        </dt>
        <dt>
          <input type="checkbox" v-model="checkedList4"><label> item 4</label><input type="number" max="1000" min="0" v-model="itemNumber4" placeholder="number of squares"><input type="color" class="colourSquare" v-model="itemColour4">
        </dt>
      </dl>
    </div>
    <div class="showItems">
      <div class="list"></div>
      <span v-show="checkedList1" v-for="item in Number(itemNumber1)" :key="item" class="itemList"><div class="myList" :style="{background:itemColour1}">{{item}}</div></span><br>
      <span v-show="checkedList2" v-for="item in Number(itemNumber2)" :key="item" class="itemList"><div class="myList" :style="{background:itemColour2}">{{item}}</div></span><br>
      <span v-show="checkedList3" v-for="item in Number(itemNumber3)" :key="item" class="itemList"><div class="myList" :style="{background:itemColour3}">{{item}}</div></span><br>
      <span v-show="checkedList4" v-for="item in Number(itemNumber4)" :key="item" class="itemList"><div class="myList" :style="{background:itemColour4}">{{item}}</div></span><br>
    </div>
  </div>
</template>

<script>
export default {
  name: 'items',
  data(){
    return{
      itemNumber1:20,
      itemNumber2:46,
      itemNumber3:15,
      itemNumber4:2,
      checkedList1:false,
      checkedList2:false,
      checkedList3:false,
      checkedList4:false,
      itemColour1:'#da1616',
      itemColour2:'#00ff40',
      itemColour3:'#ffae00',
      itemColour4:'#da1616',
      numberItems:[1,2,3,4]
    }
  },
  props:{
    hasChekedList1:{
      type:Boolean
    },hasChekedList2:{
      type:Boolean
    },hasChekedList3:{
      type:Boolean
    },hasChekedList4:{
      type:Boolean
    }
  },watch:{
    hasChekedList1:function (){
      if(this.hasChekedList1===true){
      this.checkedList1=true
      this.checkedList2=true
      this.checkedList3=true
      this.checkedList4=true}
      if(this.hasChekedList1===false){
        this.checkedList1=false
        this.checkedList2=false
        this.checkedList3=false
        this.checkedList4=false
      }
    },hasChekedList2:function (){
      if(this.hasChekedList2===true){
        this.checkedList1=true
        this.checkedList2=true
        this.checkedList3=true
        this.checkedList4=true}
      if(this.hasChekedList2===false){
        this.checkedList1=false
        this.checkedList2=false
        this.checkedList3=false
        this.checkedList4=false
      }
    },hasChekedList3:function (){
      if(this.hasChekedList3===true){
        this.checkedList1=true
        this.checkedList2=true
        this.checkedList3=true
        this.checkedList4=true}
      if(this.hasChekedList3===false){
        this.checkedList1=false
        this.checkedList2=false
        this.checkedList3=false
        this.checkedList4=false
      }
    },hasChekedList4:function (){
      if(this.hasChekedList4===true){
        this.checkedList1=true
        this.checkedList2=true
        this.checkedList3=true
        this.checkedList4=true}
      if(this.hasChekedList4===false){
        this.checkedList1=false
        this.checkedList2=false
        this.checkedList3=false
        this.checkedList4=false
      }
    },
  },
  mounted() {
    const inputs = document.querySelectorAll('input[type=number]')
    Array.from(inputs).forEach(input => {
      const min = +input.min;
      const max = +input.max;

      input.addEventListener('input', () => {
        const value = +input.value;
        if (value > max) {
          input.value = max
        } else if (value < min) {
          input.value = min
        }
      })
      })
  }
}
</script>

<style scoped>
.wrapper{
  display: flex;
}
.items{
  width: 50%;
  border: solid 2px gray;
  margin-left: 100px;
}
.showItems{
  width: 50%;
  border: 2px solid olivedrab;
  margin-left: 15px;
  /*margin-top: 15px;*/
  height: 100%;
  padding-top: 10px;
}
.myList{
  display: inline-block;
  border: 2px solid gray;
  margin-right: 2px;
  font-size: 0;
  width: 10px;
  height: 10px;
  background-color: black;
}
.itemList{
}
input[type='checkbox']{
  transform: scale(1.3);
}
.colourSquare{
  border:none;
  width: 30px;
  height: 30px;
  background:none;
  margin-left: 5px;
  transition: all .5s ease;

}
.colourSquare:hover{
  background: deepskyblue;
  border-radius: 20px;
}
input[type='number']{
  height: 30px;
  font-size: 20px;
  width: 200px;
}
@media (max-width: 600px) {
  input[type='number']{
    height: 20px;
    font-size: 10px;
    width: 20px;
  }
  .colourSquare{
    width: 20px;
    height: 20px;
  }
}
</style>
