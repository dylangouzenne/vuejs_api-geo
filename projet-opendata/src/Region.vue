<template>
    <div>
      <h4>Région</h4>

      <table v-for="r in region"> 
        <tr> 
          <td>{{ r.nom }}</td>
          <td>{{ r.code }}</td>
        </tr>   
      </table> 
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
    $
      .ajax("https://geo.api.gouv.fr/departements?fields=nom,code,codeRegion")

  		.done(function (d) {
        this.region = d
        // console.log(d);
      }.bind(this))
      
  }
  
  
}
</script>