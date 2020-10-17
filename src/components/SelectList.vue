<template>
    <div id="SelectList" >
        
            <div class="select" :class="{'active' : listOpen}">
                <div v-text="selectedItem" class="selected" @click="listOpen = !listOpen"/>
                <div class="btn" @click="listOpen = !listOpen">
                <font-awesome-icon :icon="listOpen ? 'arrow-up' : 'arrow-down'" />
 
                </div>
                
            </div>
            <div class="list" :class="{'active above' : listOpen}">
                <div class="item" 
                v-for="(el,index) in unselectedItems" 
                :key="index" v-text="el"
                    @click="selectedItem = el;listOpen = !listOpen;"
                />
            </div>


    </div>
</template>

<script>
export default {
    name: 'ColorItem',

    data() {
        return {
            selectedItem : 'option0' ,
            combos : ['option1','option2','option3', 'option4','option5'],
            listOpen : false
        }
    },
    computed: {
        unselectedItems () {
            return this.combos.filter(el => el != this.selectedItem)
        }
    },
}
</script>

<style lang="css" scoped>
* {
    transition: all 0.3s ease-in-out;

}
#SelectList {
        --height : 3rem ;
        --width : 15rem ;
        --color1: rgba(35, 142, 49, 0.623);
        --color2: rgba(35, 142, 49, 0.808);
        --color3: rgba(255, 255, 255, 0.808);
        --item-padding: 1rem 2rem;
        
        --border: 2px solid var(--color1);
        --border-radius: 1rem;


    display: flex;
    flex-direction: column;  
    position: relative;
    height: var(--height);
        


}

.select {
    display: flex;
    width: var(--width);
    justify-content: space-between;
    align-items: center;
    border: var(--border);
    border-radius: var(--border-radius);
    height: var(--height);
            

}
.select .selected {
    padding: 1rem 2rem;
    text-align: center;
    flex: 1;
    color: var(--color2);
    cursor: pointer;

}

.btn {
    padding: 1rem;
        cursor: pointer;

}
.list {
    position: absolute;
    visibility: collapse;
    left:50%;
    top:100%;
    transform: translate(-50%,0);
    opacity: 0;
    width: 100%;
    border-top: none !important;


}
.item{
    padding: var(--item-padding);
    color: var(--color3);
}
.item:last-child {
    border-bottom-left-radius: var(--border-radius);
    border-bottom-right-radius: var(--border-radius);
}
.item:hover{
    background-color: var(--color1);
    color: var(--color3);
    transform: scale(1.02);
    cursor: pointer;
}

.list.active {
    visibility: visible;
    opacity: 1;
    border: 2px solid var(--color1);
    background-color: var(--color1);
    
    border-bottom-left-radius: var(--border-radius);
    border-bottom-right-radius: var(--border-radius);
}
.select.active {
    border-radius: 0 !important;
    border-top-left-radius: var(--border-radius) !important ;
    border-top-right-radius: var(--border-radius) !important;
        

}
.above {
        z-index: 999;
    }
  
</style>