<template lang="pug">
  div#app
    div#g1
      github-lawn(:data="data")
      div test 1
    div#g2
      github-lawn(:data="data2")
      div test 2
</template>

<script>
import GithubLawn from './components/GithubLawn'

export default {
  name: 'app',
  data () {
    return {
      data: [
        1, 0, 6, 1, 8, 0, 4, 0, 3, 11, 5, 10, 1, 2
      ],
      data2: [
        6, 2, 4, 0, 5, 5, 3, 2, 0, 3, 1, 7, 11, 0, 5
      ]
    }
  },
  components: {
    GithubLawn
  }
}
</script>

<style lang="stylus">
#g1
  background #888
  padding 20px
  margin-bottom 20px
</style>
