<template>
    <div class="componente">
        <h2>As Informações de Usuário</h2>
        <p>Vários detalhes...</p>
        <p>idade:{{idade}}</p>
        <p><strong>{{inverterr()}}</strong></p>
        <button @click="reiniciarNome">Reiniciar</button>
        <button @click="reiniciarFn()">Reiniciar(callback)</button>
    </div>
</template>

<script>
import barramento from '@/barramento'
export default {
    props:{
        nome: {
            type: String,
             default: "anomino"
        },
        idade: Number,
       reiniciarFn: Function

    },

    methods: {
        inverterr(){
            return this.nome.split('').reverse().join('')
        },
        reiniciarNome(){
            this.nome = 'pedro'
            this.$emit("nomeMudou",this.nome)
        }
    },

    created() {
            barramento.quandoIdadeMudar(idade =>{
                this.idade = idade
            })
    }

}
</script>

<style scoped>
    .componente {
        flex: 1;
        background-color: #ec485f;
        color: #fff;
    }
</style>
