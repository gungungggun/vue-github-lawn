<template>
  <div id="app">
    <github-lawn :data="data" :last="last"></github-lawn>
  </div>
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
      last: '2017-8-11'
    }
  },
  components: {
    GithubLawn
  }
}
</script>
