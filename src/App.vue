<script setup>
  import {createApp} from 'vue'
  import vueDraggableNested from 'vue-draggable-nested-tree'
</script>

<template>
 
  <div id="appl">

  <Tree :data="tree2data" draggable="draggable" cross-tree="cross-tree">
    <div slot-scope="{data, store}">
      <template v-if="!data.isDragPlaceHolder"><b v-if="data.children &amp;&amp; data.children.length" @click="store.toggleOpen(data)">{{data.open ? '-' : '+'}}&nbsp;</b><span>{{data.text}}</span></template>
    </div>
  </Tree>


  <Tree class="tree3" :data="tree3data" draggable="draggable" cross-tree="cross-tree">
    <div slot-scope="{data, store}">
      <template v-if="!data.isDragPlaceHolder"><b v-if="data.children &amp;&amp; data.children.length" @click="store.toggleOpen(data)">{{data.open ? '-' : '+'}}&nbsp;</b><span>{{data.text}}</span></template>
    </div>
  </Tree>


  </div>
</template>

<style scoped>
  .logo {
    
  }
  #app {
    padding: 50px;
  }
  .he-tree{
    border: 1px solid #ccc;
    padding: 20px;
    float: left;
    min-width: 300px;
    margin-right: 30px;
  }
  .tree-node{
  }
  .tree-node-inner{
    padding: 5px;
    border: 1px solid #ccc;
    cursor: pointer;
  }
  .draggable-placeholder{
  }
  .draggable-placeholder-inner{
    border: 1px dashed #0088F8;
    box-sizing: border-box;
    background: rgba(0, 136, 249, 0.09);
    color: #0088f9;
    text-align: center;
    padding: 0;
    display: flex;
    align-items: center;
  }
  .tree3{

  }
  .tree-node-inner{
      border: none;
      padding: 0px;
    }
    .tree-node-inner-back:hover{
      background: #ddd;
    }
  .tree4{

  }
  .tree-node-inner{
      border: none;
      border-bottom: 1px solid #ccc;
      padding: 5px 10px;
      backgroud: #ccc;
    }
    .draggable-placeholder-inner{
      background-color: orangered;
    }
</style>

<script>
const app = createApp({
  el: '#appl',
    components: {Tree: vueDraggableNested.DraggableTree},
    data: {
      tree1data: [
          {text: 'node 1'},
          {text: 'node 2'},
          {text: 'node 3 undraggable', draggable: false},
          {text: 'node 4'},
          {text: 'node 4 undroppable', droppable: false},
          {text: 'node 5', children: [
            {text: 'node 1'},
            {text: 'node 2', children: [
              {text: 'node 3'},
              {text: 'node 4'},
            ]},
            {text: 'node 2 undroppable', droppable: false, children: [
              {text: 'node 3'},
              {text: 'node 4'},
            ]},
            {text: 'node 2', children: [
              {text: 'node 3'},
              {text: 'node 4 undroppable', droppable: false},
            ]},
            {text: 'node 3'},
            {text: 'node 4'},
            {text: 'node 3'},
            {text: 'node 4'},
            {text: 'node 3'},
            {text: 'node 4'},
            {text: 'node 3'},
            {text: 'node 4'},
          ]},
        ],
        tree2data: [
          {text: 'node 1'},
          {text: 'node 2'},
          {text: 'node 3'},
          {text: 'node 4'},
        ],
        tree3data: [
            {text: 'node 1'},
            {text: 'node 2'},
            {text: 'node 3 undraggable', draggable: false},
            {text: 'node 4'},
            {text: 'node 4 undroppable', droppable: false},
            {text: 'node 5', children: [
              {text: 'node 1'},
              {text: 'node 2', children: [
                {text: 'node 3'},
                {text: 'node 4'},
              ]},
              {text: 'node 2 undroppable', droppable: false, children: [
                {text: 'node 3'},
                {text: 'node 4'},
              ]},
              {text: 'node 2', children: [
                {text: 'node 3'},
                {text: 'node 4 undroppable', droppable: false},
              ]},
              {text: 'node 3'},
              {text: 'node 4'},
              {text: 'node 3'},
              {text: 'node 4'},
              {text: 'node 3'},
              {text: 'node 4'},
              {text: 'node 3'},
              {text: 'node 4'},
            ]},
          ],
        tree4data: [
            {text: 'node 1'},
            {text: 'node 2'},
            {text: 'node 3 undraggable', draggable: false},
            {text: 'node 4'},
            {text: 'node 4 undroppable', droppable: false},
            {text: 'node 5', children: [
              {text: 'node 1'},
              {text: 'node 2', children: [
                {text: 'node 3'},
                {text: 'node 4'},
              ]},
              {text: 'node 2 undroppable', droppable: false, children: [
                {text: 'node 3'},
                {text: 'node 4'},
              ]},
              {text: 'node 2', children: [
                {text: 'node 3'},
                {text: 'node 4 undroppable', droppable: false},
              ]},
              {text: 'node 3'},
              {text: 'node 4'},
              {text: 'node 3'},
              {text: 'node 4'},
              {text: 'node 3'},
              {text: 'node 4'},
              {text: 'node 3'},
              {text: 'node 4'},
            ]},
          ],
    },
    methods: {
      // hook: isNodeDroppable
      maxDroppableLevel2(node, nodeVm, store){
        return node.level <= 2
      },
    },

})

app
  // new Vue({
    
  // })
</script>