<template>
  <q-page class="flex flex-center">
  <div class="row items-start">
    <div class="column q-gutter-sm">
      <q-input outlined v-model="text"></q-input>
      <q-btn @click="add" color="primary" label="Primary" />
      <q-btn color="primary" label="Primary" />
      <q-btn color="primary" label="Primary" />
    </div> 
    <div>      
        <q-tree class="col-12 col-sm-6"
          :nodes="simple"
          node-key="label"
          tick-strategy="leaf"
          v-model:selected="selected"
          v-model:ticked="ticked"
        >
        </q-tree>     
    </div>
    <div>
      <q-scroll-area style="height: 200px; max-width: 300px;">
        <div v-for="n in 100" :key="n" class="q-py-xs">
          Lorem ipsum dolor sit amet, consectetur adipisicing
          elit, sed do eiusmod tempor incididunt ut labore et
          dolore magna aliqua.
        </div>
      </q-scroll-area>
    </div>
  </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue';

const selected = ref('Pleasant surroundings');
const ticked = ref([ 'Quality ingredients', 'Good table presentation' ]);


const simple= ref(
  [
    {
      label: 'Satisfied customers',
      children: [{label:'dfzejqf'},{label:'dfzerqjf'},{label:'dfjrzeqf'},{label:'dfjzgeqf'}],
    }
  ]
);

const text=ref("ok");
const count = ref(0);

const min = -5;
const max = 5;


function add() {
  simple.value.push({label: text.value});
  text.value="";
}


</script>

