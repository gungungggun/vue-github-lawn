<template>
  <div class="github-lawn">
    <ul v-for="week in github">
      <li v-for="d in week" :class="calc(d)"></li>
    </ul>
  </div>
</template>

<script>
import moment from 'moment'

export default {
  name: 'github-lawn',
  props: ['data', 'last'],
  computed: {
    github () {
      let copy = this.data.concat()
      let m = moment(this.last)
      for (let i = 0; i < 6 - m.day(); i++) {
        copy.unshift(null)
      }
      let count = 0
      let data = []
      let week = []

      for (let i = copy.length; i < 53 * 7; i++) {
        copy.push(0)
      }

      copy.reverse().forEach(d => {
        if (count % 7 === 0) {
          week = []
        }
        week.push(d)
        if (count % 7 === 6) {
          data.push(week)
        }
        count++
      })
      console.log(data)
      return data
    },
    max () {
      return Math.max.apply(null, this.data)
    },
    min () {
      return Math.min.apply(null, this.data)
    },
    sumValue () {
      return this.sum(this.data)
    },
    avgValue () {
      return this.sumValue / this.data.length
    },
    medianValue () {
      return this.median(this.data)
    }
  },
  methods: {
    calc (d) {
      if (d > 0) {
        if (d > this.medianValue) {
          if (d > (this.medianValue + this.max) / 2) {
            return 'l5'
          }
          return 'l4'
        } else {
          if (d > (this.medianValue / 2)) {
            return 'l3'
          }
          return 'l2'
        }
      }
      return 'l1'
    },
    sum (arr) {
      let sum = 0
      let ii = arr.length
      for (let i = 0; i < ii; i++) {
        sum += arr[i]
      }
      return sum
    },
    median (arr) {
      let sort = arr.filter(function (x) {
        return (x > 0)
      })
      sort.sort(function (a, b) {
        if (a < b) {
          return -1
        }
        if (a > b) {
          return 1
        }
        return 0
      })
      if (sort.length % 2 === 0) {
        let m1 = sort.length / 2
        let m2 = m1 - 1
        return (sort[m1] + sort[m2]) / 2
      } else {
        return sort[(sort.length - 1) / 2]
      }
    }
  }
}
</script>

<style scoped>
.github-lawn {
  clear:both;
}
.github-lawn ul {
  list-style:none;
  margin:0;
  padding:0;
  float:left;
}
.github-lawn ul li {
  width:10px;
  height:10px;
  background:#f0f0f0;
  margin:1px;
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
