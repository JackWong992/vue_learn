<template>
  <div class="home">
    hello
    <button @click="handleclick('back')">返回上一页</button>
    <button @click="handleclick('push')">跳转到parent</button>
    <button @click="handleclick('replace')">替换到child</button>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: 'home',
  components: {

  },
  methods: {
    handleclick(type){
      if(type==='back'){
        this.$router.go(-1)
      }else if(type==='push'){
        this.$router.push({
          name: 'argu',
          //查询参数
          params: {
            name: 'wallen'
          }

          // query: {
          //   name: 'wallen'
          // }
        })
      }else if(type==='replace'){
        this.$router.replace('/child')
      }

    }
  }
}
</script>
