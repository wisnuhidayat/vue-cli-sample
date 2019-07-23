<template>
  <div>
    <ul class="wrapper">
      <li
        v-for="people in people"
        :key="people.id"
        class="list"
      >
        <router-link
          :to="getDetailUrl(people.id)"
          class="card"
        >
          <img
            src="https://www.w3schools.com/howto/img_avatar.png"
            alt="Avatar"
            style="width:100%"
          >
          <div class="container">
            <h4><b>{{ people.name }} ({{ people.gender }})</b></h4>
            <p>{{ people.age }}</p>
          </div>
        </router-link>
      </li>
    </ul>
  </div>
</template>

<script>
const URL_API = 'https://ghibliapi.herokuapp.com/people'

export default {
  name: 'People',
  data () {
    return {
      people: []
    }
  },
  mounted () {
    fetch(URL_API)
      .then(res => res.json())
      .then(data => {
        this.people = data
      })
  },
  methods: {
    getDetailUrl (id) {
      return '/people/' + id
    }
  }
}
</script>

<style lang="less" scoped>
.wrapper{
  list-style: none;
  padding: 0;
  margin: 2em;

  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: center;
}
.list{
  width: 300px;
}
.card {
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  transition: 0.3s;
  border-radius: 5px; /* 5px rounded corners */
  display: block;
  margin-bottom: 4em;
  text-decoration: none;
  color: #3e3b3b;

  img {
    border-radius: 5px 5px 0 0;
  }
}

/* On mouse-over, add a deeper shadow */
.card:hover {
  box-shadow: 0 8px 16px 0 rgba(0,0,0,0.2);
}

/* Add some padding inside the card container */
.container {
  padding: 2px 16px;
}
</style>
