<template>
    <div id="VerticalMenu">
        <div class="bars btn-square" id="bars1" 
            :class="{'above' : HorizontalMenuActive}"

            @click='HorizontalMenuActive = !HorizontalMenuActive'>
                    <font-awesome-icon icon="times"  v-if="HorizontalMenuActive"/>
                                    <font-awesome-icon icon="bars"  v-else/>

        </div>
        <div class="menu-item btn-square" :class="{'active above' : HorizontalMenuActive}">
            <div>
                a
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-square" :class="{'active above' : HorizontalMenuActive}">
            <div>
                b
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-square" :class="{'active above' : HorizontalMenuActive}">
            <div>
                c
                <!--  add icon and link or action here -->
            </div>
        </div>
        <div class="menu-item btn-square" :class="{'active above' : HorizontalMenuActive}">
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
            HorizontalMenuActive : false ,
        }
    },
}
</script>

<style lang="css" scoped>
    
    /* ps : change the width to 10px in three places
        #vartical menu width 10px
        .btn-square width 10px
        .menu-item left: calc(50% - 5px ); //half for horizontal padding
        //same for height
     */

    #VerticalMenu {
        --btn-width : 5rem ;
        --btn-height : 2rem ;

        --color1: #c96818;
        --color2: #e0e0e0;
        --color3: #aeb6cc;
        --box-shadow: 0 0 5px 1px var(--color3);

        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
        /* width: 5rem; */
        /* margin: 0 0 3rem 3rem;   */
        

    }
    .btn-square {
        
        height: var(--btn-height);
        width: var(--btn-width);
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
            opacity: 0.9;


    }

   
    .active:nth-child(2) {
        transform: translateX(110%);
    }
    
    .active:nth-child(3) {
        transform: translateX(220%);
    }
    
    .active:nth-child(4) {
        transform: translateX(330%);
    }
    
    .active:nth-child(5) {
        transform : translateX(440%);
    }
    
  .above {
        z-index: 999;
    }
</style>
