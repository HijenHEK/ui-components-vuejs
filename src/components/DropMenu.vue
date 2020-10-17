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

<style lang="css">
    #dropMenu {
        position: relative;
    }
    .menu-toggeler {
        display: flex;
        justify-content: flex-end;
        padding: 1rem;
        font-size: 1.5rem;
        transition: all 0.3s ease-in ;
        border-top-right-radius: 10px;
        border-top-left-radius: 10px;

    }
    .icon:hover {
                cursor: pointer;

        transform: scale(1.05);
    }

    .menu {
        background-color: rgba(38, 146, 38, 0.616);
        height: 0;
        overflow: hidden;
        position: absolute;
        right: 0;
        visibility: hidden;
        opacity: 0;
        transition: all 0.3s ease-in ;
        border-bottom-right-radius: 10px;
        border-bottom-left-radius: 10px;
        color : white


    }
    .active {
        
        height: unset;
        opacity: 1;
        visibility: visible;
        transition: all 0.3s ease-in ;
    }
    .toggler-active {
        background-color: rgba(38, 146, 38, 0.171);
        transition: all 0.3s ease-in ;


    }
    .menu-item {
        width: 10rem;
        padding: 1rem 0;
                transition: all 0.3s ease-in ;

    }
    .menu-item:hover {
       background-color: white;
       color: rgba(38, 146, 38, 0.616);
       cursor: pointer;
               transition: all 0.3s ease-in ;

    }

    .above {
        z-index: 999;
    }
</style>