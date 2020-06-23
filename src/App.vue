<template>
    <div id="app">
        <div id="nav">
            <b-container>
                <b-row>
                    <b-nav>
                        <b-nav-item>
                            <router-link to="/">Home</router-link>
                        </b-nav-item>
                        <b-nav-item>
                            <router-link to="/about">About</router-link>
                        </b-nav-item>
                    </b-nav>
                </b-row>
            </b-container>
        </div>
        <router-view/>
    </div>
</template>

<style>
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
    }

    #nav {
        padding: 30px;
    }

    #nav a {
        font-weight: bold;
        color: #2c3e50;
    }

    #nav a.router-link-exact-active {
        color: #42b983;
    }
</style>
