<template>
  <div id="menus">
    <h1> Collapsible menus </h1>

   <div class="content">
      <div class="group">
            <h2>For icons</h2>
            <div class="group-content">
                <RoundMenu />
              <VerticalMenu />
              <HorizontalMenu />
            </div>
      </div>
      <div class="group">
            <h2>For lists and links</h2>
            <div class="group-content">
              <select-list/>

              <DropMenu />
            </div>
      </div>
   </div>
  </div>
</template>
<script>
import HorizontalMenu from '../components/HorizontalMenu.vue'
import VerticalMenu from '../components/VerticalMenu.vue'
import RoundMenu from '../components/RoundMenu.vue'
import DropMenu from '../components/DropMenu.vue'
import SelectList from '../components/SelectList.vue'



export default {
  name : 'Menus',
  components : {
    VerticalMenu,
    HorizontalMenu,
    RoundMenu,
    DropMenu,
    SelectList
  }
}
</script>


<style >
  .content {
    display: flex;
    width: 100%;
    flex-direction: row ;
    justify-content: center;
    align-items: stretch;
    height: 100%;
  }
  .group {
    padding: 1rem 2rem;
    
  }
  .group-content {
    padding: 1rem 2rem;
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    align-items: center;
  }
  .group-content > * {
    margin-top:1rem;
  }
  @media (max-width: 845px) {
    .content {
    display: flex;
    flex-direction: column;
    justify-content: stretch;
    align-items: center;
    height: 100%;
    
    }
    .group-content {
    padding: 1rem 2rem;
    display: flex;
    flex-direction: row;
    justify-content: space-evenly;
    align-items: center;
  }
  .group-content > * {
    margin:0 1rem;
  }
  }
</style>
