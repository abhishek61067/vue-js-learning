<template>
    <div>
        <div class="h2 text-primary">Emit:</div>
    </div>
</template>

<script>
    export default {
        data(){
            return{
            emits: "testEmitDataOption"
            }     
        },
        emits:"response",
        created(){
            console.log("emitvuecreated test");
            console.log(this.emits);
            this.$emit("response", "This one is coming using emit");
        }
    }
</script>

<style lang="scss" scoped>

</style>