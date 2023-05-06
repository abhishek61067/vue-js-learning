<template>
    <!-- attribute binding -->
    <div :class="c">
    <!-- Above line is similar to 
        <div class="class"> --> 
I am binded in attribute
    </div>
</template>

<script>
    export default {
        data(){
            return{
                i:"id",
                c:"class",
            }
        }
    }
</script>

<style scoped>
.class{
    color:blue;
}
#id{
    color:purple;
}
</style>