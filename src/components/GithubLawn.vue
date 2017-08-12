<template>
  <div class="github-lawn">
    <ul>
      <li class="l1"></li>
      <li class="l3"></li>
      <li class="l3"></li>
      <li class="l1"></li>
      <li class="l4"></li>
      <li class="l5"></li>
      <li class="l1"></li>
    </ul>
    <ul>
      <li class="l2"></li>
      <li class="l4"></li>
      <li class="l1"></li>
      <li class="l2"></li>
      <li class="l5"></li>
      <li class="l3"></li>
      <li class="l1"></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'github-lawn',
  data () {
    return {
      msg: 'first'
    }
  }
}
</script>

<style scoped>
.github-lawn {
}
.github-lawn ul {
  list-style:none;
  display:inline-block;
  margin:0;
  padding:0;
}
.github-lawn ul li {
  width:10px;
  height:10px;
  background:#f0f0f0;
  margin-bottom:1px;
}
.github-lawn ul li:last-child {
  margin-bottom:0;
}
.github-lawn ul li.l1 {
  background:#f0f0f0;
}
.github-lawn ul li.l2 {
  background:#c6e48b;
}
.github-lawn ul li.l3 {
  background:#7bc96f;
}
.github-lawn ul li.l4 {
  background:#239a3b;
}
.github-lawn ul li.l5 {
  background:#196127;
}
</style>
