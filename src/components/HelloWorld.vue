<template>
  <div class="hello">
    <el-divider content-position="left">已选择</el-divider>
    <draggable v-model="selectedApp" group="app" item-key="quickEntryName" class="app-list" animation="500">
      <template #item="{ element }">
        <div class="app-item dialog-item">
          <div class="item-div already-item-div">
            <span class="icon-name">{{ element.quickEntryName }}</span>
          </div>
        </div>
      </template>
    </draggable>
    <el-divider content-position="left">全部</el-divider>
    <draggable v-model="allApp" group="app" item-key="quickEntryName" class="app-list" animation="500" @start="onStart"
      @end="onEnd">
      <template #item="{ element }">
        <div class="app-item dialog-item">
          <div class="item-div already-item-div">
            <span class="icon-name">{{ element.quickEntryName }}</span>
          </div>
        </div>
      </template>
    </draggable>
  </div>
</template>

<script lang="ts" setup>
import { ref } from "vue";
import draggable from "vuedraggable";
const selectedApp = ref([
  { quickEntryName: "菜单1" },
  { quickEntryName: "菜单2" },
  { quickEntryName: "菜单3" },
  { quickEntryName: "菜单4" },
  { quickEntryName: "菜单5" },
])

const allApp = ref([
  { quickEntryName: "菜单6" },
  { quickEntryName: "菜单7" },
  { quickEntryName: "菜单8" },
  { quickEntryName: "菜单9" },
  { quickEntryName: "菜单10" },
  { quickEntryName: "菜单11" },
  { quickEntryName: "菜单12" },
  { quickEntryName: "菜单13" },
  { quickEntryName: "菜单14" },
])

const onStart = () => {
  console.log("start")
}

const onEnd = () => {
  console.log("end")
}
</script>

<style scoped lang="scss">
.hello {
  width: 50%;
  margin: 0 auto;
}

.app-list {
  display: flex;
  flex-wrap: wrap;

  .app-item {
    margin-bottom: 15px;

    .item-div {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      cursor: cursor;
      width: 98px;
      margin: 10px;
      padding: 18px 0;
      border: 1px solid gray;
      border-radius: 5px;
      -webkit-user-select: none;
      -moz-user-select: none;
      -ms-user-select: none;
      user-select: none;

      &:hover {
        background: #ffffff;
        box-shadow: 0px 0px 6px rgba(0, 0, 0, 0.12);
        border-radius: 4px 4px 4px 4px;
      }

      .icon-name {
        font-size: 14px;
        color: #2d2e3b;
        margin-top: 6px;
      }
    }

    .already-item-div {
      position: relative;

      .already-remove {
        color: #ff3434;
        position: absolute;
        right: 14px;
        top: 0px;
        font-size: 20px;
      }
    }
  }
}
</style>
