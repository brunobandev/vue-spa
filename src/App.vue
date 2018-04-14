<template>
    <div id="app">
        <nav class="navbar is-spaced has-shadow">
            <div class="container">
                <div class="navbar-brand">
                    <a class="navbar-item" href="https://bulma.io">
                        devoluntários
                    </a>
                    <div class="navbar-burger burger" data-target="navbarExampleTransparentExample">
                        <span></span>
                        <span></span>
                        <span></span>
                    </div>
                </div>

                <div id="navbarExampleTransparentExample" class="navbar-menu">
                    <div class="navbar-start">
                        <a class="navbar-item" href="https://bulma.io/">
                            Home
                        </a>
                        <div class="navbar-item has-dropdown is-hoverable">
                            <a class="navbar-link" href="/documentation/overview/start/">
                                Docs
                            </a>
                            <div class="navbar-dropdown is-boxed">
                                <a class="navbar-item" href="#">
                                    Item 1
                                </a>
                                <a class="navbar-item" href="#">
                                    Item 2
                                </a>
                                <hr class="navbar-divider">
                                <a class="navbar-item" href="#">
                                    Item 3
                                </a>
                            </div>
                        </div>
                    </div>

                    <div class="navbar-end">
                        <div class="navbar-item">
                            <div class="field is-grouped">
                                <p class="control">
                                    <a class="bd-tw-button button" data-social-network="Twitter" data-social-action="tweet" data-social-target="http://localhost:4000" target="_blank" href="https://twitter.com/intent/tweet?text=Bulma: a modern CSS framework based on Flexbox&amp;hashtags=bulmaio&amp;url=http://localhost:4000&amp;via=jgthms">
                                        <span class="icon">
                                            <i class="fab fa-twitter"></i>
                                        </span>
                                        <span>
                                            Tweet
                                        </span>
                                    </a>
                                </p>
                                <p class="control">
                                    <a class="button is-primary" href="https://github.com/jgthms/bulma/releases/download/0.6.2/bulma-0.6.2.zip">
                                        <span class="icon">
                                            <i class="fab fa-discord"></i>
                                        </span>
                                        <span>Conectar Discord</span>
                                    </a>
                                </p>
                            </div>
                        </div>

                        <div class="navbar-item has-dropdown is-hoverable">
                            <a class="navbar-link">
                                Right
                            </a>
                            <div class="navbar-dropdown is-right">
                                <a class="navbar-item">Overview</a>
                                <a class="navbar-item">Elements</a>
                                <a class="navbar-item">Components</a>
                                <hr class="navbar-divider">
                                <div class="navbar-item">Version 0.6.2</div>
                            </div>
                        </div>

                    </div>

                </div>
            </div>
        </nav>

        <section class="hero is-primary">
            <div class="hero-body">
                <div class="container">
                    <h1 class="title">
                        Primary title
                    </h1>
                    <h2 class="subtitle">
                        Primary subtitle
                    </h2>
                </div>
            </div>
        </section>

        <section class="section">
            <div class="container">
                <div class="columns">
                    <div class="column is-one-fifth">
                        <aside class="menu">
                            <p class="menu-label">
                                General
                            </p>
                            <ul class="menu-list">
                                <li><a>Dashboard</a></li>
                                <li><a>Customers</a></li>
                            </ul>
                            <p class="menu-label">
                                Administration
                            </p>
                            <ul class="menu-list">
                                <li><a>Team Settings</a></li>
                                <li>
                                    <a class="is-active">Manage Your Team</a>
                                    <ul>
                                        <li><a>Members</a></li>
                                        <li><a>Plugins</a></li>
                                        <li><a>Add a member</a></li>
                                    </ul>
                                </li>
                                <li><a>Invitations</a></li>
                                <li><a>Cloud Storage Environment Settings</a></li>
                                <li><a>Authentication</a></li>
                            </ul>
                            <p class="menu-label">
                                Transactions
                            </p>
                            <ul class="menu-list">
                                <li><a>Payments</a></li>
                                <li><a>Transfers</a></li>
                                <li><a>Balance</a></li>
                            </ul>
                        </aside>
                    </div>
                    <div class="column">
                        <router-view></router-view>
                    </div>
                </div>
            </div>
        </section>

        <!-- 
        <main>
            <aside class="sidebar">
                <router-link v-for="post in posts" active-class="is-active" class="link" :to="{ name: 'post', params: { id: post.id } }">
                    {{ post.title }}
                </router-link>
            </aside>
        </main>
        -->
    </div>
</template>
<script>
import axios from 'axios'
export default {
  data () {
    return { 
      posts: null,
      endpoint: 'https://jsonplaceholder.typicode.com/posts/',
    }
  },

  created() {
    this.getAllPosts();
  },

  methods: {
    getAllPosts() {
      axios.get(this.endpoint)
        .then(response => {
          this.posts = response.data
        })
        .catch(error => {
          console.log('--------------- error --------------');
          console.log(error)
        })
    }
  }
}
</script>