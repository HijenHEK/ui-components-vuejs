<template>
    <div id="RoundMenu">
        <div class="bars btn-circle" id="bars1" 
        :class="{'above' : RoundMenuActive}"
        @click='RoundMenuActive = !RoundMenuActive'>
                <font-awesome-icon icon="times"  v-if="RoundMenuActive"/>
                                <font-awesome-icon icon="bars"  v-else/>

        </div>
        <div class="menu-item btn-circle" :class="{'active above' : RoundMenuActive}">
            <div>
                a
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-circle" :class="{'active above' : RoundMenuActive}">
            <div>
                a
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-circle" :class="{'active above' : RoundMenuActive}">
            <div>
                a
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-circle" :class="{'active above' : RoundMenuActive}"><div>
                a
                <!--  add icon and link or action here -->
            </div>
        </div>        
        
            
        
    </div>
</template>

<script>
export default {
    name : 'RoundMenu',
    data() {
        return {
            RoundMenuActive : false ,
        }
    },
}
</script>

<style lang="css" scoped>
    
    #RoundMenu {
        /* --width:4rem ; */
        --btn-width : 2rem ;
        --btn-height : 2rem ;

        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        /* width: var(--width);
        margin: 0 0 3rem 3rem; */
        

    }
    .btn-circle {
        height: var(--btn-width);
        width: var(--btn-width);
        border-radius: 100%;
        background-color: #252525;
        color: #e0e0e0;
        box-shadow: 0 0 5px #aeb6cc;
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
    }
    .btn-circle:hover {
        opacity: 1; 
        transition: opacity 0.1s ease-in;
        transform: translateY(1px);
    }
    .bars {
        z-index: 10;
    }
    .menu-item {
            position: absolute;
            left: calc(50% - calc(var(--btn-width)/2) );
            top: calc(50% - calc(var(--btn-height)/2));
            border-radius: 100%;
            transition: all 0.5s 0s ease-in-out;
            z-index: 5;
                    box-shadow: 0 0 5px #aeb6cc;

    }


    /* adjust rotation deg % with number of element and positioning 
    translateX represent distance between menu item and menu toggler */
   
    .active:nth-child(2) {
        transform: rotate(45deg) translateX(50px);
    }
    .active:nth-child(2) > div {
        transform: rotate(-45deg);
    }
    .active:nth-child(3) {
        transform: rotate(90deg) translateX(50px);
    }
    .active:nth-child(3) > div {
        transform: rotate(-90deg);
    }
    .active:nth-child(4) {
        transform: rotate(135deg) translateX(50px);
    }
     .active:nth-child(4) > div {
        transform: rotate(-135deg);
    }
    .active:nth-child(5) {
        transform : rotate(180deg) translateX(50px);
    }
    
    .active:nth-child(5) > div {
        transform : rotate(180deg);
    }


    .above {
        z-index: 999;
    }
  
</style>
