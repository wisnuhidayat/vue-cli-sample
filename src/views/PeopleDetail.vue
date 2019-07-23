<template>
  <div>
    <h1>{{ people.name }}</h1>
    <h2>Gender: {{ people.gender }}</h2>
    <h2>Age: {{ people.age }}</h2>
    <h2>
      <router-link to="/films">
        Films
      </router-link>
    </h2>

    <router-link to="/people">
      Back to People List
    </router-link>
  </div>
</template>

<script>
const URL_API = 'https://ghibliapi.herokuapp.com/people'

export default {
  name: 'PeopleDetail',
  data () {
    return {
      people: {
        name: ''
      }
    }
  },
  mounted () {
    const filmId = this.getParamsId()
    fetch(`${URL_API}/${filmId}`)
      .then(res => res.json())
      .then(data => {
        this.people = data
      })
  },
  methods: {
    getParamsId () {
      return this.$route.params.id
    }
  }
}
</script>

<style lang="less" scoped>
</style>
