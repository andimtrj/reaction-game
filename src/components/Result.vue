<template>
    <p>Your reaction time: {{ showScore }}ms </p>
    <h3 v-if="showFast">Kenceng banget ngab! 🔥 </h3>
    <h3 v-else>Yah lamban amat! 💩</h3>
</template>

<script>
export default {
    name: 'Result',
    props: ["showScore"],
    data(){
        return{
            showFast: false,
        }
    },
    mounted(){
        this.toggleFast();
    },
    methods: {
        toggleFast() {
            if(this.showScore <= 500){
                this.showFast = true
            }
        }
    }
}
</script>

<style scope>
p {
    color: #DDDDDD;
}

h3 {
    color: #DDDDDD;
}

</style>