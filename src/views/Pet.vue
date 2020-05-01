<template>
    <div>
      <h1>{{ animal.name }}</h1>
      <h2>{{ animal.gender }}</h2>
      <h3>{{ animal.age }}</h3>
    </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  data () {
    return {
      animal: {}
    }
  },
  computed: {
    ...mapState([
      'cats',
      'dogs'
    ])
  },
  mounted () {
    const animal = this[this.$route.params.species][this.$route.params.id]
    this.animal = animal
  }
}
</script>
