<template>
    <div class="block" v-if="showBlock"> CLICK ME FAST!</div>
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            clicked: false,
        }
    },
    mounted() {
        console.log(`Block component mounted.`);
        setTimeout(() => {
            this.showBlock = true;
            console.log(`Current delay: ${this.delay} ms.`);
        }, this.delay);
    },
    updated() {
        console.log(`Block component updated.`);
    },
    unmounted() {
        console.log(`Block component unmounted.`);
    },

}
</script>

<style>
.block {
    width: 200px;
    border-radius: 20px;
    background-color: rgb(100, 117, 230);
    color: white;
    font-size: 20px;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
    cursor: pointer;
}
</style>