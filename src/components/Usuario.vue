<template>
    <div class="container">
        <h1>Componente Usuário</h1>
        <p>Esse é um componente muito legal!</p>
        <p><strong>{{nome}}</strong></p>
        <p> a idade é:{{idade}}</p>
        <button @click="alterarNome" class="btn btn-primary">Alterar nome</button>
        <hr>
        <div class="componentes">
            <app-usuario-info
             :nome="nome"
             :idade="idade"
             @nomeMudou="nome = $event "
             :reiniciarFn="reiniciarNome"
             />
            <app-usuario-editar
            :idade="idade"/>
           
        </div>
    </div>
</template>

<script>
import AppUsuarioInfo from './UsuarioInfo'
import AppUsuarioEditar from './UsuarioEditar'


export default {
    components: { AppUsuarioInfo, AppUsuarioEditar },
     data() {
         return {
             nome: "Eduardo",
             idade: 23
            
         }
     },
     methods: {
        
         alterarNome(){
             this.nome = 'Eduardo santana'
         },

         reiniciarNome(){
             this.nome = "santana santos"
         }
     },
}
</script>

<style scoped>
    .container {
        background-color: #27363b;
        color: #fff;
        padding: 10px;
    }

    .container hr {
        margin: 20px 10px;
    }

    .componentes {
        display: flex;
    }

    .componentes > * {
        margin: 10px;
    }
</style>
