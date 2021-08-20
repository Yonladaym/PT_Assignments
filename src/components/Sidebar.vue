<template>
  <div v-show="showSidebar" id="menu" class="flex  h-screen w-2/5 sm:w-4/5">
   <a href="" @click.prevent="closeButton()"
          ><img src="../assets/Icon/close.svg" alt="" id="close-button"
        /></a>
    <div
      id="menu-content"
      class="h-full w-full flex justify-center text-2xl md:text-sm"
    >
      <ol>
        <li><a href="#">01 Home</a></li>
        <li><a href="#">02 About Programming</a></li>
        <li><a href="#">03 Business Tech</a></li>
        <li><a href="#">04 Innovation</a></li>
        <li><a href="#">05 Could</a></li>
        <li><a href="#">06 Blog</a></li>
        <li><a href="#">07 Career</a></li>
        <li><a href="#">08 Get In Touch</a></li>
      </ol>
    </div>
  </div>
</template>

<script>
import {ref} from 'vue'
export default {
  setup(){
    let showSidebar = ref(true);
    function closeButton(){
      showSidebar.value = false;
      
    }
    return {closeButton, showSidebar}
  }
};
</script>

<style>
#menu {
  background-image: url("../assets/Menu/bg-menu.png");
  background-repeat: no-repeat;
  /* background-position: center; */
  background-size: cover;
  position: fixed;
  z-index: 1;
  right: 0;
  top: 0;
  overflow: hidden;
}
#menu-content {
  position: relative;
  top: 6%;
  right: 0;
}
li {
  color: grey;
  padding: 0.5rem;
}
li a:hover {
  color: white;
}
#close-button {
  position: absolute;
  right: 10%;
  top: 2%;
  margin-right: 1.25rem;
}
</style>
