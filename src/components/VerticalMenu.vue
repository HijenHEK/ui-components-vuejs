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
        --font-size : 2rem ;
        --padding : 1rem ;
        --btn-width : 100% ;
        --btn-height : var(--btn-width) ;        
        --color1: #2318c9;
        --color2: #e0e0e0;
        --color3: rgba(38, 146, 38, 0.171);
        --box-shadow: 0 0 5px 1px var(--color3);
        
        --spacing : calc(var(--btn-width) * 0.1);
        /* --font-size : calc(var(--btn-width) * 0.5) ; */
        --item-opacity : 0.98 ;
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        font-size: var(--font-size);
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
        padding: var(--padding);
        
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
            opacity: var(--item-opacity);
            opacity: 0;
            width: 100%;
    }

   .active {
       opacity: 1;
   }
     .active:nth-child(2) {
        transform: translateY(calc(100% + var(--spacing)));
    }
    
    .active:nth-child(3) {
        transform: translateY(calc(200% + 2*var(--spacing)));
    }
    
    .active:nth-child(4) {
        transform: translateY(calc(300% + 3*var(--spacing)));
    }
    
    .active:nth-child(5) {
        transform : translateY(calc(400% + 4*var(--spacing)));
    }
    
    .above {
        z-index: 999;
    }
</style>
