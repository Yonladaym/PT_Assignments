<template>
  <div>
    <div
      class="w-full flex justify-between bg-black  bg-opacity-10 h-1/6 px-10 py-4 fixed"
    >
      <img src="../assets/logo.svg" alt="" />

      <div class="flex items-center justify-around w-1/6 sm:w-2/6 text-gray-500">
        <a v-bind:class="{changeColor:isColor}" @click.prevent="clickColor()" href="">EN</a>
        <a v-bind:class="{changeColor:!isColor}" @click.prevent="clickColor()" href="">TH</a>
        <img
          id="toggle"
          @click="clickSidebar()"
          src="../assets/toggle.svg"
          alt=""
        />
      </div>
    </div>
    <Sidebar v-show="openSidebar"></Sidebar>
  </div>
</template>

<script>
import Sidebar from "./Sidebar.vue";
import { ref } from "vue";
export default {
  setup() {
    let openSidebar = ref(false);
    function clickSidebar() {
      openSidebar.value = true;
    }
    let isColor = ref(true);
    function clickColor(){
        isColor.value = !isColor.value
    }
    return { clickSidebar, openSidebar, clickColor, isColor};
  },
  components: {
    Sidebar,
  },
};
</script>

<style>
#toggle {
  cursor: pointer;
}
.changeColor{
    color: white;
    border-bottom: 1px solid red;
}
</style>
