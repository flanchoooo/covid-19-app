<template>
    <div>
        <base-header class="header pb-8 pt-5 pt-lg-8 d-flex align-items-center"
                     style="min-height: 400px; background-image:  background-size: cover; background-position: center top;">
            <!-- Mask -->
            <span class="mask bg-gradient-success opacity-8"></span>
            <!-- Header container -->
            <div class="container-fluid d-flex align-items-center">
                <div class="row">
                    <div class="col-lg-7 col-md-10">
                    </div>
                </div>
            </div>
        </base-header>

        <div class="container-fluid mt--7">
            <div class="row">
                <div class="col-xl-10">
                    <card shadow type="secondary">
                        <div slot="header" class="bg-white border-0">
                            <div class="row align-items-center">
                                <div class="col-8">
                                    <h3 class="mb-0">Company Profile</h3>
                                </div>
                                <div class="col-4 text-right">
                                  <h1>{{description}}</h1>
                                </div>
                            </div>
                        </div>
                        <template>
                            <form @submit.prevent="companyRegistration">
                                <div class="pl-lg-4">
                                    <div class="row">
                                        <div class="col-lg-6">
                                            <base-input alternative=""
                                                        label="Company Name"
                                                        placeholder="Company Name"
                                                        input-classes="form-control-alternative"
                                                        v-model="name"
                                                        required="required"
                                            />
                                        </div>
                                    </div>
                                </div>
                                <!-- Address -->
                                <div class="col-lg-6">
                                    <base-button type="primary" class="primary my-4">Submit</base-button>
                                </div>
                            </form>
                        </template>
                    </card>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                </div>
            </div>
        </div>
    </div>
</template>




<script>
    import axios from 'axios'
  export default {
    name: 'company-registrations',
      data() {
          return {
                  name: '',
              description: 'rest',

          }
      },
      methods: {
        companyRegistration() {
            axios.post("http://144.91.64.120:35600/api/companies", {
                          name: this.name,
                          longitute: 0,
                          latitute: 0,
                      }).then((response) => {
                          if(response.data.status !== 200){
                              let message = this.name + " " + "company profile successfully created.";
                              console.log(response)
                              alert(message);
                          }else {
                              let description = response.data.description;
                              console.log(response)
                              alert(description)

                          }}) .catch(function (error) {
                            console.log(error);
                            alert("Service is unavaliable please try again later.");
            });
                  },
              },
  };
</script>
<style></style>
