<template>
    <div class="results">
        <h2> Your Reaction Time: {{ score }} ms!</h2>
        <h1>{{ rank }}</h1>
    </div>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null,
        }
    },
    mounted() {
        if (this.score < 300) {
            this.rank = '⚡Lightning has nothing on you!⚡';
        } else if (this.score < 400) {
            this.rank = ' 👏Pro clicker!👏';
        } else if (this.score < 600) {
            this.rank = 'Average reaction 🙆';
        } else {
            this.rank = 'Sloooow..🐌';
        }
    }
}
</script>

<style>
.results {
    margin: 20px auto;
    padding: 20px;
    border: 2px solid rgb(100, 117, 230);
    border-radius: 10px;
    width: 450px;
    background-color: #f9f9f9;
}
</style>