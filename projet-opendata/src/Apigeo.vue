<template>
    <div id="apiGeo">
        <h2>{{ msg }}</h2>
        
        <form method="POST" action="">
            
            <label>Région
                <region></region>
            </label>

            <label>Département
                <departement></departement>
            </label>

        </form>  
    </div>
</template>

<script>

import region from './Region'
import departement from './Departement'

export default {
    name: "apiGeo",
    data () {
        return {
        msg: "Welcome to API Geo"
        }
    },
    components: {
        region,
        departement
    }
}
</script>

<style>

    #apiGeo{
        text-align: center;
    }

    h2{
        margin:1em;
    }


</style>