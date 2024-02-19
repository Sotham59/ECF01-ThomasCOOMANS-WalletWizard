<script setup>
import { defineEmits, reactive } from 'vue';

const emits = defineEmits(['ajoutDepense2'])

const depense2 = reactive({
    name:'',
    desc: '',
    montant:0
})

const submitHandler = () =>{
    emits('ajoutDepense2',{
        ...depense2
    })
    depense2.name = '';
    depense2.desc = '';
    depense2.montant ='';
}

</script>

<template>
    <div class="formu">
    <form action="#" @submit.prevent="submitHandler">
        <div>
            <label for="name">Titre:</label>
            <input type="text" name="name" id="name" v-model="depense2.name" required>
        </div>
        <div>
            <label for="desc">Description:</label>
            <input type="text" name="desc" id="desc" v-model="depense2.desc" required>
        </div>
        <div>
            <label for="montant">Montant:</label>
            <input type="number" name="montant" id="montant" v-model="depense2.montant" required min="0">
        </div>

        <button>Ajouter</button>
    </form>
</div>

</template>

<style scoped>

div{
    display: flex;
    flex-direction: column;
    align-items: center;
}

label{
    margin-bottom: 0.25rem;
    font-size: 1.25rem;
    color: #efefef;
}
input{
    margin-bottom: 0.75rem;
    height: 1.25rem;
    font-size: 1rem;
}

button{
    font-size: 1.25rem;
    cursor: pointer;
    color:rgb(40, 40, 40) ;
    padding: 0.25rem;
    background-color: #efefef;
    border: none;
    transition: scale 200ms ease-in;
    border-radius: 0.25rem;
}
button:hover{
    scale: 1.2;
}
</style>
