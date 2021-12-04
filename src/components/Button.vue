<template>
    <button v-on:click = "onClick()" :style="{background: color , color: textColor}" class="btn">{{ text }}</button>
</template>

<script>
export default {
    name : 'Button',
    props : {
        text : String,
        color : String,
        textColor : String
    },
    methods : {
        onClick() {
            console.log("Click");
        }
    }
    
}
</script>