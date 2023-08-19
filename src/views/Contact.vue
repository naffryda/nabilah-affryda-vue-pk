<template>
  <v-content>
    <div class="staticHero">
      <v-img max-height="400" src="../assets/images/cloud.jpg">
        <v-row align="end" class="lightbox white--text pa-2 fill-height">
          <v-col>
            <v-container>
              <div class="headline">Contact Us</div>
            </v-container>
          </v-col>
        </v-row>
      </v-img>
    </div>
    <div class="block">
      <v-container>
        <v-row justify="center" align="center">
          <v-col cols="12" sm="8">
            <v-form
              ref="form"
              v-model="valid"
              lazy-validation
              id="contact-form"
              v-on:submit.prevent="submit"
            >
              <div class="col-12 form-group">
                <label class="col-form-label col-form-label-lg"
                  >Name <span class="text-danger">*</span></label
                >
                <v-spacer></v-spacer>
                <v-text-field
                  type="text"
                  :rules="nameRules"
                  v-model.trim="$v.name.$model"
                  class="form-control form-control-lg"
                />
              </div>
              <div class="col-12 form-group">
                <label class="col-form-label col-form-label-lg"
                  >Email <span class="text-danger">*</span></label
                ><v-spacer></v-spacer>
                <v-text-field
                  type="email"
                  v-model.trim="$v.email.$model"
                  :rules="emailRules"
                  class="form-control form-control-lg"
                />
              </div>
              <div class="col-12 form-group">
                <label class="col-form-label col-form-label-lg"
                  >Message <span class="text-danger">*</span></label
                ><v-spacer></v-spacer>
                <v-text-field
                  type="text"
                  class="form-control form-control-lg"
                  v-model.trim="$v.message.$model"
                  :rules="messageRules"
                />
              </div>
              <div class="col-12 form-group text-center">
                <button class="btn btn-vue btn-lg col-4 mr-4">Submit</button>
                <button class="btn btn-reset btn-lg col-4" @click="reset">
                  Reset Form
                </button>
              </div>
            </v-form>
          </v-col>
        </v-row>
      </v-container>
    </div>
    <div class="googlemap" justify="center" align="center">
      <iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d16705.802661855836!2d-0.14290489950731525!3d51.50711704027593!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47d8a00baf21de75%3A0x52963a5addd52a99!2sLondon!5e0!3m2!1sen!2suk!4v1577041400110!5m2!1sen!2suk"
        width="90%"
        height="450"
      ></iframe>
    </div>
  </v-content>
</template>

<script>
import { required, email } from "vuelidate/lib/validators";
export default {
  name: "Contact",
  data: function () {
    return {
      valid: true,
      name: "",
      nameRules: [
        (v) => !!v || "Name is required",
        (v) => (v && v.length <= 10) || "Name must be less than 10 characters",
      ],
      email: "",
      emailRules: [
        (v) => !!v || "E-mail is required",
        (v) => /.+@.+\..+/.test(v) || "E-mail must be valid",
      ],
      message: "",
      messageRules: [
        (v) => !!v || "Message is required",
        (v) =>
          (v && v.length <= 10) || "Message must be less than 10 characters",
      ],
    };
  },

  validations: {
    name: { required },
    email: { required, email },
    message: { required },
  },
  methods: {
    reset() {
      this.$refs.form.reset();
    },

    submit: function () {
      this.$v.$touch();
      if (this.$v.$pendding || this.$v.$error) return;

      alert("Data Submitted");
      this.$v.$reset();
      this.resetData();
    },
  },
};
</script>
<style>
.btn-vue {
  background: #53b985;
  color: #31485d;
  font-weight: bold;
}
.btn-reset {
  background: lightgray;
  color: #31485d;
  font-weight: bold;
}
</style>
