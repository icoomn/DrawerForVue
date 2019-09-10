<template>
  <div id="app">
    <button class="btn open" @click="display = true">点我，打开抽屉</button>
    <drawer title="Hello, I'm drawer" :display.sync="display" :width="drawerWidth">
        <p>1. Hello, world!</p>
        <p>2. Do you like it?</p>
        <button class="btn try" @click="changeWidth">点我试试?</button>
    </drawer>
  </div>
</template>

<script>
import drawer from './components/drawer'

export default {
  name: 'app',
  components: {
    drawer
  },
  data () {
    return {
        display: false,
        drawerWidth: '500px'
    }       
  },
  methods: {
    changeWidth () {
      this.drawerWidth = (this.drawerWidth === '500px') ? '800px' : '500px'
    }
  }
}
</script>

<style lang="scss">
#app {
  margin: 60px;
}
.btn { 
  border: none;
  border-radius: 3px;
  outline: none;
  cursor: pointer;
  letter-spacing: 3px;
  &:hover {
    opacity: .8;
  }
  &.open {
    width: 200px;
    height: 80px;
    font-size: 18px;
    background-color: orange;
    color: #fff;
  }
  &.try {
    width: 100px;
    height: 40px;
    background-color: green;
    color: #fff;
    margin-top: 50px;
  }
}
</style>
