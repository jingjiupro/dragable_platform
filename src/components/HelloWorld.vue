<template>
  <div class="hello">
    <draggable :list="list" ghost-class="ghost" :force-fallback="true" chosen-class="chosenClass" animation="300"
      @start="onStart" @end="onEnd">
      <template #item="{ element }">
        <div class="item">
          {{ element.name }}
        </div>
      </template>
    </draggable>
  </div>
</template>

<script lang="ts" setup>
import { ref, reactive } from "vue";
import draggable from "vuedraggable";
const list = ref([
  { name: "www.itxst.com", id: 0 },
  { name: "www.baidu.com", id: 1 },
  { name: "www.google.com", id: 2 },
])
const onStart = () => {
  console.log("start")
}

const onEnd = () => {
  console.log("end")
}
</script>

<style scoped lang="scss">
.item {
  cursor: move;
}
</style>
