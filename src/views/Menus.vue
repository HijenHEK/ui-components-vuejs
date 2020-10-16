<template>
  <div id="menus">
    <h1> Collapsible menus </h1>

   <div class="content">
     <div class="col">
       <h2>For icons</h2>
        <RoundMenu />
        <VerticalMenu />
        <HorizontalMenu />
     </div>
     <div class="col">
       <h2>For lists and links</h2>
        <DropMenu />

     </div>
   </div>
  </div>
</template>
<script>
import HorizontalMenu from '../components/HorizontalMenu.vue'
import VerticalMenu from '../components/VerticalMenu.vue'
import RoundMenu from '../components/RoundMenu.vue'
import DropMenu from '../components/DropMenu.vue'
export default {
  name : 'Menus',
  components : {
    VerticalMenu,
    HorizontalMenu,
    RoundMenu,
    DropMenu
  }
}
</script>


<style lang="css">
  .content {
    display: flex;
    justify-content: stretch;
    align-items: center;
    height: 100%;
  }
  .col {
    padding: 1rem 2rem;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
  }
</style>
