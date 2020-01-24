<template>
    <div class="pt-5">
        <div class="text-center">
            <img alt="Lets logo" height="100px" src="../assets/logo.png">
        </div>

        <div class="mt-5 mx-auto card p-4 w-25 very-rounded">
            <!-- Simple text binded -->
            <div class="text-center col-12">
              <span class="cursor-default text-secondary font-weight-bold h5" :title="welcomeTitle">
                  {{ welcomeMessage }}
              </span>
              <hr>
            </div>

            <!-- Form binded -->
            <form>
                <div class="form-group">
                    <input type="email" class="form-control" placeholder="Digite seu email"
                           v-model="loginForm.email">
                    <small id="emailHelp" class="form-text text-muted">Não iremos compartilhar seu email com
                        ninguém</small>
                </div>

                <div class="form-group">
                    <input type="password" class="form-control"
                           placeholder="Digite sua senha" v-model="loginForm.password">
                </div>

                <div class="form-check small">
                    <input type="checkbox" class="form-check-input" id="keepConnected"
                           v-model="loginForm.keepConnected">
                    <label class="form-check-label text-muted align-middle" for="keepConnected">Mantenha-me conectado</label>
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
                welcomeMessage: 'Seja bem-vindo de volta!',
                welcomeTitle: 'Fazer login na plataforma',

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

    .very-rounded {
        border-radius: 30px;
    }
</style>
