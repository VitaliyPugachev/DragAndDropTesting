<script setup>
import {VueDraggableNext} from 'vue-draggable-next';
import {ref} from "vue";

const list = ref([{name: '123'}, {name: '456'}, {name: '12355'}])
const list2 = ref([{name: 'FFFF'}, {name: 'BBBBB'}, {name: 'CCCCC'}])
const list3 = ref([{name: 'TEST'}])


</script>

<template>
  <main class="main">
      <VueDraggableNext v-model="list"  group="test" @change="console.log" :move="(e) => console.log(e)">
          COL1
          <div
              class="list"
              v-for="(element, index) in list"
              :key="element.name"
          >
              {{ element.name }} {{ index }}
          </div>
      </VueDraggableNext>

      <VueDraggableNext v-model="list2" group="test">
          COL 2
          <div
              class="list2"
              v-for="(element, index) in list2"
              :key="element.name"
          >
              {{ element.name }} {{ index }}
          </div>
      </VueDraggableNext>

      <VueDraggableNext v-model="list3" group="test">
          COL 3
          <div
              class="list1"
              v-for="(element, index) in list3"
              :key="element.name"
          >
              {{ element.name }} {{ index }}
          </div>
      </VueDraggableNext>
  </main>
</template>

<style scoped>
.main {
    display: flex;
    gap: 20px;
}

.list {
    background: #f8f8f8;
}

.list2 {
    background: antiquewhite;
}
</style>
