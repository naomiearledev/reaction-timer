<template>
  <p>Reaction time: {{ scoreSeconds }} seconds</p>
  <p class="rank">Rank: {{ rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            scoreSeconds: this.score / 1000,
            rank: null
        }
    },
    mounted() {
        if (this.score < 250) {
            this.rank = 'Ninja Fingers'
        } else if (this.score < 500) {
            this.rank = 'Rapid Reflexes'
        } else {
            this.rank = 'Snail Pace'
        }
    }
}
</script>

<style>
.rank {
    font-size: 1.4em;
    color: #0faf87;
    font-weight: bold;
}
</style>