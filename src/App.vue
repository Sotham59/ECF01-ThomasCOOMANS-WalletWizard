<script setup>
import Formulaire from './components/Formulaire.vue';
import Formulaire2 from './components/Formulaire2.vue';
import Card from './components/Card.vue';
import Card2 from './components/Card2.vue';
import { ref, computed } from 'vue';

const depenses = ref([])
const depense2 = ref([])

const total = computed(() => {
    const map = depenses.value.map((x) => x.montant)
    const totaldepense = map.reduce((a, c) => a + c, 0)
    return totaldepense
})

const total2 = computed(() => {
    const map2 = depense2.value.map((x) => x.montant)
    const totalCredit = map2.reduce((a, b) => a + b, 0)
    return totalCredit
})

const solde = computed(() => {
    const soldee = total2.value - total.value
    return soldee
})
</script>

<template>
    <div class="title">
        <h1>Wallet Wizard</h1>
    </div>
    <h3>Solde du compte: {{ solde }}€</h3>
    <div class="display">
        <span>Total des débit: {{ total }} €</span>
        <span>Total des crédit: {{ total2 }} €</span>
    </div>

    <div class="container-flex">
        <div class="debit">
            <h3>Ajouter un débit:</h3>

            <Formulaire @ajout-depense="depenses.push($event)"></Formulaire>
            <Card v-for="(c, i) in depenses" :dep="c" @supp-dep="depenses.splice(i, 1)"></Card>
        </div>
        <div class="credit">
            <h3>Ajouter un crédit:</h3>
            <Formulaire2 @ajout-depense2="depense2.push($event)"></Formulaire2>
            <Card2 v-for="(d, i) in depense2" :dep2="d" @suppDep2="depense2.splice(i, 1)"></Card2>
        </div>
    </div>
</template>

<style scoped>
h1 {
    background-color: rgb(40, 40, 40);
    font-size: 2.5rem;
    font-family: monospace;
    padding-block: 1rem;
    color: rgb(250, 5, 5);
}

.display {
    display: flex;
    justify-content: space-around;
    margin-top: 2.5rem;
}

h3 {
    font-size: 1.75rem;
    color: #efefef;
}

span {
    color: #efefef;
    font-size: 1.25rem;
}

.container-flex {
    display: grid;
    grid-template-columns: 1fr 1fr;
}
</style>
