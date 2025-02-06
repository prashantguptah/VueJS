<template>


<div :style="styleObject">Hello Vue</div>
</template>


<script>

export default{
    name: "PracticeComponent",
    data(){
        return {
            styleObject:{
                color: "blue",
                fontsize: 20
            }
        }
    }
}


</script>