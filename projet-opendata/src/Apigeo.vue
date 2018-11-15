<template>
    <div id="apiGeo">
        <h2>{{ msg }}</h2>
        <region></region>   
    </div>
</template>

<script>

import region from './Region'

export default {
    name: "apiGeo",
    data () {
        return {
        msg: "Welcome to API Geo"
        }
    },
    components: {
        region
    }
}
</script>