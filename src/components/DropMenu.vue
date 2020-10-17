<template>
    <div id="dropMenu" :class="{'above' : active}">
        <div class="menu-toggeler" 
            :class="{'toggler-active' : active}"
            >
            <font-awesome-icon
                class="icon"
                @click="active = !active"
                icon="times"  v-if="active"/>
            <font-awesome-icon
                class="icon"
                @click="active = !active"
                icon="bars"  v-else/>
        </div>
        <div class="menu" :class="{'active' : active}">
            <div class="menu-item">Home</div>
            <div class="menu-item">Store</div>
            <div class="menu-item">Blog</div>
            <div class="menu-item">About</div>
            <div class="menu-item">Contact</div>
            
        </div>
    </div>
</template>

<script>


    
export default {
    data() {
        return {
            active : false 
        }
    },
}
</script>

<style lang="css" scoped>
    #dropMenu {
        --toggler-font-size : 1.5rem ;
        --border-radius : 1rem ;
        --color1: rgba(38, 146, 38, 0.616);
        --color2: rgba(255, 255, 255, 1);
        --color3: rgba(38, 146, 38, 0.171);

        --menu-right: 0;
        --menu-item-padding: 1rem 0;

        --menu-item-width : 10rem ;
        --toggler-width: 3rem;
        --toggler-height: 3rem;
        position: relative;
        
    }
    .menu-toggeler {
        display: flex;
        justify-content: center;
        align-items: center;
        width: var(--toggler-width);
        height: var(--toggler-height);
        font-size: var(--toggler-font-size);
        transition: all 0.3s ease-in ;
        border-top-right-radius: var(--border-radius);
        border-top-left-radius: var(--border-radius);

    }
    .icon:hover {
                cursor: pointer;

        transform: scale(1.05);
    }

    .menu {
        background-color: var(--color1);
        height: 0;
        overflow: hidden;
        position: absolute;
        right: 0;
        visibility: hidden;
        opacity: 0;
        transition: all 0.3s ease-in ;
        border-bottom-right-radius: var(--border-radius);
        border-bottom-left-radius: var(--border-radius);
        color : var(--color2)


    }
    .active {
        
        height: unset;
        opacity: 1;
        visibility: visible;
        transition: all 0.3s ease-in ;
    }
    .toggler-active {

        background-color: var(--color3);
        transition: all 0.3s ease-in ;


    }
    .menu-item {
        width: var(--menu-item-width);
        padding: var(--menu-item-padding);
        transition: all 0.3s ease-in ;

    }
    .menu-item:hover {
       background-color: var(--color2);
       color: var(--color1);
       cursor: pointer;
        transition: all 0.3s ease-in ;

    }

    .above {
        z-index: 999;
    }
</style>