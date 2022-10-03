<template>
  <q-page class="flex flex-center">
  <div class="row items-start">
    <div class="column q-gutter-sm">
      <q-btn color="primary" label="Primary" />
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
        v-model:expanded="expanded"
      />
    </div>
  </div>
  </q-page>
</template>

<script setup>
import { ref } from 'vue';

const selected = ref('Pleasant surroundings');
const ticked = ref([ 'Quality ingredients', 'Good table presentation' ]);
const  expanded = ref([ 'Satisfied customers', 'Good service (disabled node)', 'Pleasant surroundings' ]);

const simple= ref([
        {
          label: 'Satisfied customers',
          children: [
            {
              label: 'Good food',
              children: [
                { label: 'Quality ingredients' },
                { label: 'Good recipe' }
              ]
            },
            {
              label: 'Good service (disabled node)',
              disabled: true,
              children: [
                { label: 'Prompt attention' },
                { label: 'Professional waiter' }
              ]
            },
            {
              label: 'Pleasant surroundings',
              children: [
                { label: 'Happy atmosphere' },
                { label: 'Good table presentation' },
                { label: 'Pleasing decor' }
              ]
            }
          ]
        }
      ]);



const count = ref(0);

const min = -5;
const max = 5;

</script>
