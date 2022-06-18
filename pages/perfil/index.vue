<template>
  <v-main>
      <!-- Login -->
         <v-container 
         v-if="!this.$auth.loggedIn"
         fluid 
         fill-height>
            <v-layout align-center justify-center>
               <v-flex xs12 sm8 md4>
                  <v-card class="elevation-12">
                     <v-toolbar dark color="primary">
                        <v-toolbar-title>Iniciar Sesion</v-toolbar-title>
                     </v-toolbar>
                     <v-card-text>
                     <v-form>
                            <v-text-field
                              v-model="email"
                              name="email"
                              label="Correo"
                              type="text"
                              placeholder="Correo"
                              required
                           ></v-text-field>
                           
                            <v-text-field
                              v-model="password"
                              name="password"
                              label="Contraseña"
                              type="password"
                              placeholder="Contraseña"
                              required
                           ></v-text-field>
                           <v-btn 
                           type="button" 
                           class="mt-4" 
                           color="primary"  
                           @click="login()">Iniciar Sesion</v-btn>
                      </v-form>
                     </v-card-text>
                  </v-card>
                
               </v-flex>
            </v-layout>
         </v-container>

         <!-- Sign Up -->
         <v-container>
             <v-layout align-center justify-center>
               <v-flex xs12 sm8 md4>
                  <v-card class="elevation-12">
                     <v-toolbar dark color="primary">
                        <v-toolbar-title>Registrar</v-toolbar-title>
                     </v-toolbar>
                     <v-card-text>
                     <v-form>

                         <v-text-field
                              v-model="username"
                              name="email"
                              label="Nombre"
                              type="text"
                              placeholder="Nombre"
                              required
                           ></v-text-field>

                            <v-text-field
                              v-model="email"
                              name="email"
                              label="Correo"
                              type="text"
                              placeholder="Correo"
                              required
                           ></v-text-field>
                           
                            <v-text-field
                              v-model="password"
                              name="password"
                              label="Contraseña"
                              type="password"
                              placeholder="Contraseña"
                              required
                           ></v-text-field>
                           <v-btn 
                           type="button" 
                           class="mt-4" 
                           color="primary"  
                           @click="registrar()">Registrar</v-btn>
                      </v-form>
                     </v-card-text>
                  </v-card>
                
               </v-flex>
            </v-layout>
         </v-container>
      </v-main>
</template>

<script>
export default {
    auth: 'guest',
    data(){
        return {
            err: null,
            username: '',
            email: '',
            password: '',
        }
    },
    methods: {
        async login() {
            try{
                await this.$auth.loginWith('local',{
                    data: {identifier: this.email, password: this.password},
                })
            }catch(e){
                if(e.response) this.err = e.response.data.error.message
            }
        },
        async registrar() {
            try{
                this.$axios.setToken(false)
                await this.$axios.post('auth/local/register',{
                    username: this.username,
                    email: this.email,
                    password: this.password,
                })
            }catch(e){
                if(e.response) this.err = e.response.data.error.message
            }
        }
  }

}
</script>

<style>

</style>