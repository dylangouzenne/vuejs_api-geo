<template>
  <div v-if="region.length > 0" >
    <select name='list_region'>
      <option v-for="r in region" v-bind:value='r.code'>
       
        {{ r.nom }}
        {{ r.code }}
         
      </option>
    </select>
  </div>
</template>

<script>
  import $ from 'jquery'
  export default {
    
    name: 'region',
    
    data: function () {
      return {
        region : []
      }
    },
    
    created : function(){
      $region = $.ajax("https://geo.api.gouv.fr/regions?fields=nom,code")
      .done(function (d) {
        this.region = d
        //console.log(d);
      }.bind(this))   
    }
  }
</script>