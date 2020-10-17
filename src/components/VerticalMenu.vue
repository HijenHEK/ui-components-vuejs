<template>
    <div id="VerticalMenu">
        <div class="bars btn-square" id="bars1" 
                :class="{'above' : VerticalMenuActive}"
                @click='VerticalMenuActive = !VerticalMenuActive'>

                    <font-awesome-icon icon="times"  v-if="VerticalMenuActive"/>
                    <font-awesome-icon icon="bars"  v-else/>

        </div>
        <div class="menu-item btn-square" :class="{'active above' : VerticalMenuActive}">
            <div>
                a
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-square" :class="{'active above' : VerticalMenuActive}">
            <div>
                b
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-square" :class="{'active above' : VerticalMenuActive}">
            <div>
                c
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-square" :class="{'active above' : VerticalMenuActive}">
            <div>
                d
                <!--  add icon and link or action here -->
            </div>
        </div>        
        
            
        
    </div>
</template>

<script>
export default {
    name : 'VerticalMenu',
    data() {
        return {
            VerticalMenuActive : false ,
        }
    },
    methods :{
        
    }
}
</script>

<style lang="css" scoped>
    
    #VerticalMenu {
        /* --width:auto ; */
        
        --btn-width : 2rem ;
        --btn-height : 2rem ;
        --color1: #2318c9;
        --color2: #e0e0e0;
        --color3: rgba(38, 146, 38, 0.171);
        --box-shadow: 0 0 5px 1px var(--color3);


        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        /* width: var(--width); */
        /* margin: 0 0 3rem 3rem; */
        

    }
    .btn-square {
        height: var(--btn-width);
        width: var(--btn-height);
        background-color: var(--color1);
        color: var(--color2);
        display: flex;
        align-items: center;
        justify-content: center;
        cursor: pointer;
        
        
    }
    .btn-square:hover {
        opacity: 1; 
        transition: opacity 0.1s ease-in;
        transform: translateY(1px);
    }
    .bars {
        z-index: 10;
        box-shadow: var(--box-shadow);

    }
    .menu-item {
            position: absolute;
            left: calc(50% - calc(var(--btn-width)/2) );
            top: calc(50% - calc(var(--btn-height)/2));
            transition: all 0.5s 0s ease-in-out;
            z-index: 5;
            opacity: 0.95;
    }

   
    .active:nth-child(2) {
        transform: translateY(110%);
    }
    
    .active:nth-child(3) {
        transform: translateY(220%);
    }
    
    .active:nth-child(4) {
        transform: translateY(330%);
    }
    
    .active:nth-child(5) {
        transform : translateY(440%);
    }
    
    .above {
        z-index: 999;
    }
  
</style>
