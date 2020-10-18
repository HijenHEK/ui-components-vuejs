<template>
    <div id="navTwo">
        <div class="left">
              <div class="brand">
                HEK
            </div>  
            <div class="toggler" @click="collapse = !collapse">
                <font-awesome-icon
                class="icon"
                
                
                :icon="collapse ? 'times' : 'bars'"/>
        </div>  
        </div>

        

        <div class="right">
            
            <div :class="collapse ? 'menu above' : 'nav'" >
                <div class="nav-item" :class="{'active' : active == 1}" @click="active = 1">Home</div>
                <div class="nav-item" :class="{'active' : active == 2}" @click="active = 2">Blog</div>
                <div class="nav-item" :class="{'active' : active == 3}" @click="active = 3">Store</div>
                <div class="nav-item" :class="{'active' : active == 4}" @click="active = 4">About</div>
                <div class="nav-item" :class="{'active' : active == 5}" @click="active = 5">Contact</div>
            </div>
            
            
        </div>   
          
    </div>
</template>


<script>
export default {
    data() {
        return {
            collapse : false,
            active : 1 ,
        }
    },
}
</script>

<style lang="css" scoped>
    #navTwo {
        --height : 3rem ;
        --width : 100% ;
        --color1: rgb(31, 82, 112);
        --color2: rgb(161, 151, 201);
        --color3: rgb(243, 220, 210);
        --padding : 1rem 5rem ;
        --nav-padding-collapse : 1rem 2rem ;
        --nav-item-padding: 1rem 0.5rem;
        --menu-right: 0 ;
        --box-shadow: 0 0 5px 1px var(--color2);


        height: var(--height);
        width: var(--width);
        display: flex;
        justify-content: space-between;
        align-items: center;
        padding: 1rem 5rem;
        background-color: var(--color1);
        color: var(--color3);
        box-shadow: var(--box-shadow);
        
    }
    
    #navTwo * {
        cursor: pointer;
        transition: all 0.2s ease-in-out;
        -webkit-tap-highlight-color: transparent;
    }
    #navTwo *:active {
        outline: none;
        outline-style: none;
    }
    .left {
        display: flex;
        align-items: center;
    }
    .right {
        display: flex;
        align-items: center;
        position: relative;
        

    }
    
        .toggler {
            
            width: var(--height);
            height: var(--height);
            display: none;
            align-items: center;
            justify-content: center;

        }
        .toggler:hover  {
            background-color: var(--color2);
            color: var(--color1);
            
        }

        .menu , .nav {
            display: flex;
            align-items: center;
        }
        
        .nav-item{
            padding: var(--nav-item-padding);
            width: 100%;
        }
        .nav-item:hover {
            background-color: var(--color2);
            color: var(--color1);
        }
        .nav-item:active {
            background-color: var(--color3);
            color: var(--color2);
            transition: all 0s ease-in-out !important;
        }
        .nav-item.active {
            background-color: var(--color3);
            color: var(--color2);
            transition: all 0s ease-in-out !important;
        }
    .above {
        z-index: 999;
    }
  
        
    @media (max-width: 900px) {
        #navTwo {
        min-height: var(--height);
        height: unset;
        transition: all 0.2s ease-in-out;

        padding:0;

        flex-direction: column;
        
        }
        .toggler {
            display: flex;
        }
        


        .nav {
            visibility: hidden;
            height: 0;
            opacity: 0;
            transition: height 0s 0s ease-in-out !important;
        }
        .menu {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
        }
        
        
        .left {
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: var(--nav-padding-collapse);
            padding-top: 0 ;
            padding-bottom: 0 ;
        }
        .right {
            width: 100%;
            padding: var(--nav-padding-collapse);
            padding-bottom: 0 ;
            padding-top: 0 ;
            

        }
        .nav-item {
            max-width: 5rem;
        }
        
    }

</style>