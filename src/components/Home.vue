<template>
    <div class="pt-5">
        <div class="text-center">
            <img alt="Lets logo" height="100px" src="../assets/logo.png">
        </div>

        <!-- Simple text binded -->
        <div class="text-center mt-5 col-12">
          <span class="cursor-default" :title="alertTitle">
              <i class="far fa-comments mr-1"></i>
              {{ alertMessage }}
          </span>
        </div>

        <div class="mt-4">
            <!-- Form binded -->
            <form class="col-4 offset-4">
                <div class="form-group">
                    <label for="inputEmail">Email</label>
                    <input type="email" id="inputEmail" class="form-control" placeholder="Digite seu email" v-model="loginForm.email">
                    <small id="emailHelp" class="form-text text-muted">Não iremos compartilhar seu email com ninguém</small>
                </div>

                <div class="form-group">
                    <label for="exampleInputPassword1">Senha</label>
                    <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Digite sua senha" v-model="loginForm.password">
                </div>

                <div class="form-check">
                    <input type="checkbox" class="form-check-input" id="keepConnected" v-model="loginForm.keepConnected">
                    <label class="form-check-label" for="keepConnected">Mantenha-me conectado</label>
                </div>

                <div class="text-right">
                    <button type="submit" class="btn btn-primary mt-2" :disabled="!loginForm.canSignIn">
                        Acessar
                    </button>
                </div>
            </form>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'Home',

        data() {
            return {
                alertMessage: 'Apresentação sobre Vue 2',
                alertTitle: 'Exemplo de título',

                loginForm: {
                    email: '',
                    password: '',
                    keepConnected: false,
                    canSignIn: false,
                },

            }
        }
    }
</script>

<style scoped>
    .cursor-default {
        cursor: default;
    }
</style>
