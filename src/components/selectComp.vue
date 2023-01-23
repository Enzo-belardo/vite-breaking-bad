<script>
import { store } from '../store.js'

export default{
    name: 'selectComp',
    component:{},
    data() {
        return {
            store,
            selectOutput:""
        }
    },
    methods: {},
  created() {},
    
}

</script>

<template>
    <div>
      <select class="form-select form-select-lg mb-3" aria-label=".form-select-lg example"  v-model="selectOutput" @change="$emit('changeType', selectOutput)">
       <option selected>Seleziona i tipi </option>
       <option value="Alien">Alien</option>
       <option value="Laval">Laval</option>
       <option value="Vylon">Vylon</option>
       <option value="Inzektor">Inzektor</option>
       <option value="Umi">Umi</option>
       <option value="Gusto">Gusto</option>
     </select>
  </div>
</template>
<style lang="scss" >

</style>
