<template>
<q-layout class="bg-blue-grey-1" view="hhh Lpr Lff">
 <q-page-container>
   <q-page class="row items-center justify-center">
       <div class="row full-width">
           <div class="col-md-8 offset-md-2 col-xs-12 q-pr-md q-pt-sm">
            <q-card class="bg-white text-black">
                <div class="row">
                    <!-- <div class="col-md-6 col-xs-12">
                        <div class="row q-pt-md q-pb-md bg-teal-5">
                          <div class="col-md-8 offset-2 col-xs-8">
                            <q-img spinner-color="white" placeholder-src="statics/nyoba.png" src="statics/nyoba.png"></q-img>
                          </div>
                        </div>
                    </div> -->
                    <q-card-section class="section text-blue-grey-14">
                     <div class="text-h4">Registrasi</div>
                    </q-card-section>
                    <div class="col-md-12 col-xs-12 q-pt-md">
                      <div class="q-pa-md">

    <q-form
      @submit="onSubmit"
      @reset="onReset"
      class="q-gutter-md"
    >
      <q-input
        filled
        v-model="username"
        label="Username"
        hint="Username"
        lazy-rules
        :rules="[ val => val && val.length > 0 || 'Data tidak boleh kosong']"
      />

      <q-input
        filled
        type="Password"
        v-model="password"
        label="Password"
        hint="Password"
        lazy-rules
         :rules="[ val => val && val.length > 0 || 'Data tidak boleh kosong']"
      />

         <q-input
        filled
        v-model="email"
        label="Email"
        hint="Email"
        lazy-rules
         :rules="[ val => val && val.length > 0 || 'Data tidak boleh kosong']"
      />

         <q-input
        filled
        v-model="notelp"
        label="No Telepon"
        hint="No Telepon"
        lazy-rules
         :rules="[ val => val && val.length > 0 || 'Data tidak boleh kosong']"
      />

       <div>
        <q-btn label="Login"  to="/auth/login" type="submit" color="primary"/>
        <q-btn label="Registrasi" color="primary" flat class="q-ml-sm" />
      </div>
    </q-form>

                      </div>
                    </div>
                </div>
            </q-card>
           </div>
       </div>
   </q-page>
</q-page-container>
</q-layout>
</template>

<script>
export default {
  name: 'Registrasi',
  data () {
    return {
      username: null,
      password: null,
      email: null,
      notelp: null,
      accept: false
    }
  },

  methods: {
    onSubmit () {
      if (this.accept !== true) {
        this.$q.notify({
          color: 'red-5',
          textColor: 'white',
          icon: 'warning',
          message: 'You need to accept the license and terms first'
        })
      } else {
        this.$q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: 'Submitted'
        })
      }
    },

    onReset () {
      this.name = null
      this.age = null
      this.accept = false
    }
  }
}

</script>

<style scoped>

</style>
