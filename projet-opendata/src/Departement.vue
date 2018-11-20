<template>
  <div v-if="departement.length > 0">
    <select name='list_departement'>
      <option v-for="d in departement" v-bind:value="d.code" v-on:click="trie_departement">

        {{ d.nom }}
        {{ d.code }}

      </option>
    </select>
  </div>
</template>

<script>
    import $ from 'jquery'

    export default {

        name: 'departement',

        data: function () {
            return {
                departement : []
            }
        },

        created: function(){
            $.ajax("https://geo.api.gouv.fr/regions/44/departements?fields=nom,code")
            // ---------------------------remplacer 44 par la valleur du code region choisis dans le composant region
            .done(function (d) {
            this.departement = d
            //console.log(d);
            }.bind(this))    
        },

        methods: {
            trie_departement: function(message, event){

            }
        }
    }

</script>

<style>

    select{
        margin:1em;
    }

</style>