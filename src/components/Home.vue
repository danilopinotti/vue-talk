<template>
  <div class="pt-5" :class="{'bg-dark': usingDarkTheme}">
      <div class="text-center">
          <img alt="Lets logo" height="100px" src="../assets/logo.png">
      </div>

      <div class="text-center mt-5">
          <span class="alert alert-secondary cursor-default" :title="title">
              <i class="far fa-comments mr-1"></i>
              {{ message }}
          </span>
      </div>

      <div class="text-center mt-5">
          <button class="btn btn-primary" :disabled="!canChangeTheme">
              <i class="far mr-1" :class="{'fa-moon': usingDarkTheme, 'fa-sun': !usingDarkTheme}"></i>
              Trocar tema
          </button>
      </div>
  </div>
</template>

<script>
  export default {
    name: 'Home',

    data() {
        return {
            message: 'Apresentação sobre Vue 2',
            title: 'Exemplo de título',

            usingDarkTheme: false,
            canChangeTheme: false,
        }
    }
  }
</script>

<style scoped>
    .cursor-default {
        cursor: default;
    }
</style>
