<template>
    <div id="SelectList" >
        
            <div class="select" :class="{'active' : listOpen}">
                <div v-text="selectedItem" class="selected" @click="listOpen = !listOpen"/>
                <div class="btn" @click="listOpen = !listOpen">
                <font-awesome-icon :icon="listOpen ? 'arrow-up' : 'arrow-down'" />
 
                </div>
                
            </div>
            <div class="list" :class="{'active' : listOpen}">
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

<style>
* {
    transition: all 0.3s ease-in-out;

}
#SelectList {
    display: flex;
    flex-direction: column;  
    position: relative;
    height: 3rem;
        


}

.select {
    display: flex;
    width: 15rem;
    justify-content: space-between;
    align-items: center;
    border: 2px solid rgba(35, 142, 49, 0.808);
    border-radius: 1rem;
    height: 3rem;
            

}
.select .selected {
    padding: 1rem 2rem;
    text-align: center;
    flex: 1;
    color: rgba(35, 142, 49, 0.808);
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
    padding: 1rem 2rem;
}
.item:last-child {
    border-bottom-left-radius: 1rem;
    border-bottom-right-radius: 1rem;
}
.item:hover{
    background-color: rgba(35, 142, 49, 0.808);
    color: rgba(255, 255, 255, 0.808);
    transform: scale(1.02);
    cursor: pointer;
}

.list.active {
    visibility: visible;
    opacity: 1;
    border: 2px solid rgba(35, 142, 49, 0.808);
    
    border-bottom-left-radius: 1rem;
    border-bottom-right-radius: 1rem;
}
.select.active {
    border-radius: 0 !important;
    border-top-left-radius: 1rem !important ;
    border-top-right-radius: 1rem !important;
        

}
</style>