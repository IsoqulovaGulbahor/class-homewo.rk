<template>
  <div id="list-demo">
    <button class="first-button" @click="add">😉 QO'SHISH 👍</button>
    <button class="second-button" @click="remove">😉OLIB TASHLASH✋</button>
    <transition-group name="list" teg="ul">
      <li v-for="item in items" :key="item.id" class="list-item">
        Item: {{ item + 1 }} - {{ item }} =
      </li>
    </transition-group>
  </div>
</template>
<script>
export default {
  data() {
    return {
      items: [1, 2, 3],
      nextNum: 1,
    };
  },
  methods: {
    randomItem() {
      return Math.floor(Math.random() * this.items.length);
    },
    add() {
      this.items.splice(this.randomItem(), 0, this.nextNum++);
    },
    remove() {
      this.items.splice(this.randomItem(), 1);
    },
  },
};
</script>
<style>
* {
  padding: 0;
  margin: 0;
}
body {
  margin: 100px;
  background-image: url(./Childern.jpg);
}
.list-item {
  margin-left: 425px;
  display: inline-block;
  display: block;
  width: 25%;
   background-color: rgb(147, 245, 252);
  display: flex;
  align-items: center;
  justify-content: center;
}
button {
  margin-left: 250px;
  color: #fff;
  padding: 15px 38px;
  font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
}
.first-button {
  padding: 15px 50px;
  border: 1px solid red;
  border-radius: 50%;
  background-color: red;
}
.second-button {
  border: 1px solid green;
  border-radius: 50%;
  background-color: green;
}
</style>
