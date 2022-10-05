<template>
  <q-page class="flex flex-center">

      <q-scroll-area class="col" style="height: 800px; max-width: 300px;">
        <div v-for="n in 100" :key="n" class="q-py-xs">
          Lorem ipsum dolor sit amet, consectetur adipisicing
          elit, sed do eiusmod tempor incididunt ut labore et
          dolore magna aliqua.
        </div>
      </q-scroll-area>


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

