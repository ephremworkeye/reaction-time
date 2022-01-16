<template>
<h1>{{}}</h1>
<div class="block" v-if="showBlock" @click="stopTimer">
    Click me
</div>
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
        }, this.delay);
    },
    methods: {
        startTimer() {
            this.timer = setInterval(() => {
                this.reactionTime += 10
            }, 10);
        },
        stopTimer() {
            clearInterval(this.timer)
            this.$emit('end', this.reactionTime)
        }
    }

   
}
</script>

<style>

.block {
    margin: 40px auto;
    background: rgb(2, 47, 135);
    color: white;
    padding: 100px 50px;
    text-align: center;
    width: 300px;
    border-radius: 10px;
    cursor: pointer;
}
</style>