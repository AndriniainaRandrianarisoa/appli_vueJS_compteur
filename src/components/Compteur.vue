<template>
    <div>
        <h1>Mon super Compteur</h1>
        <p @click="increment" >Vous avez cliqué {{ total }} fois</p>
        <p>le Total general depuis VueX est {{ totalGeneral }} </p>
        <p>Le double du total est de {{ double }} </p>
    </div>
</template>

<script>
export default {
    name: "Compteur",
    data() {
        return {
            total:0
        }
    }, 
    computed: {
        totalGeneral() {
            return this.$store.state.totalFromVueX 
        },
        double() {
            return this.$store.getters.doubleDuTotal
        }
    },

    methods: {
        increment() {
            this.total+=1;
            this.$store.commit("setTotalFromVueX" , this.totalGeneral += 1)
        }
    } 
}
</script>

<style scoped></style>

