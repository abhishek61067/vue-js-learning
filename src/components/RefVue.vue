<template>
    <div>
        <div class="text-primary h2">Ref vs class( or you may also use id)</div>
<p  id="template__p">hello</p>
<p  class="template__p--class">hello</p>
<p ref="c">hello</p>
    </div>
</template>

<script>
    export default {
        mounted(){
            alert("mounted function will execute after document is ready");
            alert("when you change something inside mounted in editor, template will rerender in browsers and mounted function will run as well");
                            this.$refs.c.textContent = "changed using ref"
                                        document.querySelector("#template__p").innerHTML = "changed using vanilla js targeting id"
                                        document.querySelector(".template__p--class").innerHTML = "changed using vanilla js targeting class"


        }
            }
</script>

<style lang="scss" scoped>

</style>