<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps(['dep2'])
const emits = defineEmits(['suppDep2'])

const supp = () =>{
    emits('suppDep2')
}

</script>

<template>
    <div class="card">

        <div>
            <h2>{{ dep2.name }}</h2>
            <p>{{ dep2.desc }}</p>
            <p class="debit">{{ dep2.montant }} €</p>
        </div>
        <button @click="supp">Supprimer</button>

    </div>


</template>

<style scoped>
    .card{
    display: inline-flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    height: 14rem;
    width: 14rem;
    background-color: rgba(40, 202, 43, 0.7);
    border-radius: 1.5rem;
    margin:1rem ;
    color: #efefef;
}

h2{
    font-size: 1.75rem;
}

p{
    font-size: 1.25rem;
}

button{
    font-size: 1rem;
    cursor: pointer;
    color:rgb(40, 40, 40) ;
    padding: 0.25rem;
    border: none;
    border-radius: 0.25rem;
    transition: scale 200ms ease-in;
}

button:hover{
    scale: 1.2
}


</style>
