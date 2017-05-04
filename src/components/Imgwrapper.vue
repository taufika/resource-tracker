<template lang="pug">
    .img-wrapper(ref="theWrapper")
        img(v-bind:src="imageUrl" ref="theImage")
</template>

<script>

export default {
    name: "Imgwrapper",
    props: ["imageUrl"],
    mounted(){

        var comp = this;

        this.$nextTick(function(){
            var parentWidth = comp.$refs.theWrapper.clientWidth;
            var imgWidth = comp.$refs.theImage.clientWidth;

            if( imgWidth < parentWidth ){
                comp.$refs.theImage.className += " portrait";
            }
        });
    }
}

</script>

<style lang="scss">

    .img-wrapper{
        overflow: hidden;
        position: relative;

        img{
            height: 100%;
            position: relative;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);

            &.portrait{
                height: auto;
                width: 100%;
            }
        }
    }
</style>