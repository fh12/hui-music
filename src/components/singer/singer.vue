<template>
    <div class="singer" ref="singer">
    </div>
</template>
<script>
import {getSingerList} from 'api/singer'
import {ERR_OK} from 'api/config'

export default {
  data() {
    return {
      singers: []
    }
  },
  created() {
    this._getSingerList()
  },
  methods: {
    _getSingerList() {
      getSingerList().then((res) => {
        if (res.code === ERR_OK) {
          // this.singers = this._normalizeSinger(res.data.list)
          console.log(res.data.list)
        }
      })
    }
  }
}
</script>
<style scoped lang="stylus" rel="stylesheet/stylus">
.singer
 position: fixed
 top: 88px
 bottom: 0
 width: 100%
</style>
