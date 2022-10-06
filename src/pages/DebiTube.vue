<template>
  <q-page class="flex flex-center">
  <div class="row items-start q-gutter-md">
    <q-card class="shadow-10 q-card--bordered" style="height:800px">
    <div style="margin:10px">
      <div class="col column q-gutter-sm" >
        <q-input outlined v-model="text" @keydown="onKey"></q-input>
        <q-btn @click="add" color="primary" label="Primary" />
        <q-btn color="primary" label="Primary" />
        <q-btn color="primary" label="Primary" />
      </div>
    </div>
    </q-card>
    <div class="col">
    <q-card class="shadow-10 q-card--bordered" style="height:800px">
    <div style="margin:10px">
     <q-scroll-area style="height: 780px;width: 400px;">
        <q-tree class="col-12 col-sm-6"
          :nodes="simple"
          node-key="label"
          tick-strategy="leaf"
          v-model:selected="selected"
          v-model:ticked="ticked"
        >
        </q-tree>
      </q-scroll-area> 
      </div>
      </q-card>   
    </div>
  </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue';

const selected = ref('Pleasant surroundings');
const ticked = ref([ 'Quality ingredients', 'Good table presentation' ]);


const simple= ref([]);

const text=ref("ok");
const count = ref(0);

const min = -5;
const max = 5;


function add() {
  simple.value.push({label: text.value});
  text.value="";
}

 function onKey (evt) {
        if(evt.keyCode === 13)
        {
        simple.value.push({label: text.value});
        text.value="";
        }
 }


</script>

