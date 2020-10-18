<template>
    <div id="NavBars" >
        <div class="responsive">
                    <h2 >resize window to test responsivness for under 900px width</h2>
        </div>
        <NavOne />
        <NavTwo />
    </div>
</template>


<script>
import NavOne from '../components/NavOne.vue'
import NavTwo from '../components/NavTwo.vue'
export default {
    
    components : {
        NavOne,
        NavTwo
    },
   
    
}
</script>


<style lang="css" scoped>
    h2 {
        margin: 2rem 0;
    }
    
    
    @media (max-width: 900px) {
    .responsive {
            display: none;
        }
    }

</style>