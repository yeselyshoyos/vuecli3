<template>
  <nav id="nav" class="navbar navbar-expand-lg navbar-dark bg-dark">
      <div class="container-fluid">
          <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNav" aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
          </button>
          <div class="collapse navbar-collapse justify-content-center" id="navbarNav">
              <ul class="navbar-nav">
                  <li class="nav-item">
                    <router-link class="nav-link"  to="/">Inicio</router-link>
                  </li>
                  <li class="nav-item">
                    <router-link class="nav-link" to="/about">Nosotros</router-link>
                  </li>
                  <li class="nav-item">
                    <router-link class="nav-link" to="/books">Libros</router-link>
                  </li>
                  <li class="nav-item">
                    <router-link class="nav-link" to="/users">Usuarios</router-link>
                  </li>
                  <li class="nav-item">
                    <a class="nav-link disabled">Disabled</a>
                  </li>
              </ul>
          </div>
      </div>
  </nav>
  <div id="nav">
  </div>
  <router-view/>
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
  color: #ffffff;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
