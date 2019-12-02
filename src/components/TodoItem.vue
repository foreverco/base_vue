<template>
  <li @mouseenter="getBg(true)" @mouseleave="getBg(false)" :style="{'background':bgColor}">
    <label>
      <input type="checkbox" v-model="item.complete" />
      <span>{{item.name}}</span>
    </label>
    <button class="btn btn-danger" v-show="isShow" @click="delItem">删除</button>
  </li>
</template>

<script>
export default {
  props: {
    item: Object,
    index: Number,
    deltodoLists: Function
  },
  data() {
    return {
      bgColor: "white",
      isShow: false
    };
  },
  methods: {
    getBg(isEnter) {
      if (isEnter) {
        this.bgColor = "#999";
        this.isShow = true;
      } else {
        this.bgColor = "white";
        this.isShow = false;
      }
    },
    delItem() {
      const { deltodoLists, index, item } = this;
      if (window.confirm(`确定删除${item.name}的评论吗？`)) {
        deltodoLists(index);
      }
    }
  }
};
</script>
<style>
/*item*/
li {
  list-style: none;
  height: 36px;
  line-height: 36px;
  padding: 0 5px;
  border-bottom: 1px solid #ddd;
}

li label {
  float: left;
  cursor: pointer;
}

li label li input {
  vertical-align: middle;
  margin-right: 6px;
  position: relative;
  top: -1px;
}

li button {
  float: right;
  display: none;
  margin-top: 3px;
}

li:before {
  content: initial;
}

li:last-child {
  border-bottom: none;
}
</style>