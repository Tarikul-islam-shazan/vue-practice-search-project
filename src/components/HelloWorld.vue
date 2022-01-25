<script>
import { ref } from 'vue'
import SearchResults from './SearchResults.vue';

export default{
  components: {
    SearchResults,
  },
  /**
  * @author tarikul
  * @param void
  * @return {String}
  */
  setup() {
    const query = ref("");
    const reset = (evt) => {
      query.value = "";
    }
    return {
      query,
      reset,
    };
  },
};
</script>

<template>
  <div>
    <h2>Search Product</h2>
    <input type="text" placeholder="serch here" v-model='query'/>
    <br/>
    <button @click="reset">Reset</button>
    <search-results :query='query'/>
  </div>
</template>


<style>
  input[type='text'] {
    margin-bottom: 20px;
    padding: 10px;
  }
</style>
