<template>
    <div id="navOne">
        <div class="left">
              <div class="brand">
                HEK
            </div>  
        </div>

        <!-- <div class="mid">
            <input type="search" name="" id="">
        </div> -->

        <div class="right">
            <div class="toggler" @click="collapse = !collapse">
                <font-awesome-icon
                class="icon"
                
                
                :icon="collapse ? 'times' : 'bars'"/>
            </div>
            <div :class="collapse ? 'menu active above' : 'nav'" >
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
    #navOne {
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
    
    #navOne * {
        cursor: pointer;
        transition: all 0.2s ease-in-out;
        -webkit-tap-highlight-color: transparent;
    }
    #navOne *:active {
        outline: none;
        outline-style: none;
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
        #navOne {
        
        padding: var(--nav-padding-collapse);
        
        }
        .toggler {
            display: flex;
        }
        
        .nav {
            visibility: hidden;
            width: 0;
            opacity: 0;
            transition: width 0s 0s ease-in-out !important;
            
        }
        .menu {
            opacity: 0;
            position: absolute;
            flex-direction: column;
            justify-content: center;
            top : var(--height) ;
            right: var(--menu-right) ;
            visibility: collapse;
            height: 0;
            background-color: var(--color1);
            box-shadow: var(--box-shadow);
            
            
        }
        .menu.active {
            visibility: visible !important;
            height: unset !important;
            opacity: 1;
            transition: all 0.3s ease-in;
                    

        }
    }

</style>