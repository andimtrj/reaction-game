<template>
    <p>Your reaction time: {{ showScore }}ms </p>
    <h3 v-if="showFast">Kenceng banget ngab! 🔥 </h3>
    <h3>Yah lamban amat! 💩</h3>
</template>

<script>
export default {
    name: 'Result',
    props: ["showScore"],
    data(){
        return{
            showFast: false,
            showSlow: false
        }
    },
    methods: {
        toggleFast() {
            if(this.showScore <= 500){
                this.showFast = true
            }
            else{
                this.showSlow = true
            }
        }
    }
}
</script>

<style scope>
p {
    color: #DDDDDD;
}

</style>