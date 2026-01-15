<template>
    <img src="../assets/postman.jpg" class="block" v-if="showBlock" @click="stopTimer" />
</template>

<script>
export default {
    props: ['delay'],
    data() {
        return {
            showBlock: false,
            timer: null,
            reactionTime: 0,
        }
    },
    mounted() {
        setTimeout(() => {
            this.showBlock = true
            this.startTimer()
        }, this.delay)
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10)
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        },
    },

}
</script>

<style>
.block {
    width: 400px;
    cursor: pointer;
    border: 2px solid rgb(100, 117, 230);
    border-radius: 10px;
}
</style>