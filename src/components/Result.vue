<template>
    <p>Reaction Time is: {{ score }} ms</p>
    <h2 class="message">{{ message }}</h2>
</template>

<script>
export default {
props: ['score'],
data() {
    return {
        message: null
    }
},
mounted() {
    if (this.score < 300){
        this.message = "You are super fast!!!"
    }else if (this.score < 600){
        this.message = 'Average speed!!!'
    }else {
        this.message = 'Too slow!!!'
    }
}

}
</script>

<style>
    .message {
        font-weight: bold;
        font-size: 2.2rem;
        color: green;
    }
</style>