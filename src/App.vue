<script>
import { RouterLink, RouterView } from 'vue-router'
import HelloWorld from './components/HelloWorld.vue'
 
export default {
  components: {
    HelloWorld,
    RouterLink,
    RouterView
  },
  data () {
    return {
      msg: "Test message",
      headingClass: "main-heading",
      type: "A",
      books: ['book1', 'book2', 'book3', 'book4'],
      users: [
        {
          name: 'User1',
          age: 23,
          books: 3
        },
        {
          name: 'User2',
          age: 15,
          books: 6
        },
        {
          name: 'User3',
          age: 40,
          books: 5
        },
        {
          name: 'User4',
          age: 25,
          books: 0
        },
        {
          name: 'User5',
          age: 35,
          books: 11
        },
      ],
      count: 0
    }
  },
  mounted () {
    console.log (this.msg)
    this.msg = "Update message"
    console.log (this.count)
    this.increment()
  },
  methods: {
    increment () {
      this.count++
    }
  }

}
 
</script>

<template>
      

<!-- <button @click="console.log('click')">Click on me!</button> -->




  <header>
    <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" />


    <h3 v-if="type ==='A'"></h3>

<h3 v-else-if="type ==='B'"></h3>

<h3 v-else-if="type ==='C'"></h3>

<h3 v-else>Not A/B/C</h3>

<h2 v-show="type ==='B'">Выбран вариант B</h2>
<h2 v-show="type ==='C'">Выбран вариант C</h2>
<h2 v-show="type ==='A'">Выбран вариант A</h2>

<ul>
  <li v-for="(book, index) in books" :key="index">{{book}}</li>
</ul>

<ol>
  <li v-for="(user, index) in users" :key="index" :class= "{'red-text':user.books === 0 || user.books > 10}">
  {{ user.name}} has {{ user.books}} books
</li>
</ol>


    <div>
<!-- <button @click="increment">Counter</button> -->
<button @click="count++">Прибавить</button>
<button @click="count--">Убавить</button>
<p v-show="count > 10 || count < -10">Вы превысили порог +-10</p>
<p>{{ count }}</p>
</div>



    <!-- <div class="wrapper">

      <h1 :class="headingClass">{{msg.split('').reverse().join('') }}</h1>

      

      <HelloWorld msg="You did it!" />

      <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
      </nav>
    </div> -->
  </header>

  <RouterView />
</template>

<style scoped>
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

nav {
  width: 100%;
  font-size: 12px;
  text-align: center;
  margin-top: 2rem;
}

nav a.router-link-exact-active {
  color: var(--color-text);
}

nav a.router-link-exact-active:hover {
  background-color: transparent;
}

nav a {
  display: inline-block;
  padding: 0 1rem;
  border-left: 1px solid var(--color-border);
}

nav a:first-of-type {
  border: 0;
}

/* @media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  nav {
    text-align: left;
    margin-left: -1rem;
    font-size: 1rem;

    padding: 1rem 0;
    margin-top: 1rem;
  }
} */



ul {
  border: 2px solid #41B883;
  border-radius: 5px;
  margin: 20px 0px;
}

ol {
  border: 2px solid #41B883;
  border-radius: 5px;
  margin: 20px 0px;
}

button {
  background-color: #34495E;
  color: white;
  border-radius: 3px;
  margin: 0px 5px 0px 5px;
  width: 150px;
  height: 25px;
  font-size: 15px;
}

p {
  border: 2px solid #34495E;
  border-radius: 5px;
  margin: 20px 0px;
  text-align: center;
}

.red-text {
  color: red;
}

h2 {
  border: 2px solid #41B883;
  border-radius: 5px;
  margin: 20px 0px;
  text-align: center;
}

</style>
