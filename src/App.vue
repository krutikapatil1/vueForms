<template>
  <div class="container">
    <form v-if="!dataSubmitted">
      <div class="row">
        <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
          <!-- Exercise 1 -->
          <!-- Create a Signup Form where you retrieve the following Information -->
          <!-- Full Name (First Name + Last Name) -->
          <app-first-last-name v-model="userData.fullName"></app-first-last-name>
          <br />

          <div class="form-group">
            <!-- Mail -->
            <label>Email</label>
            <input type="text" id="email" class="form-control" v-model="userData.email" />
            <!-- Password -->
            <label>Password</label>
            <input type="password" id="password" class="form-control" v-model="userData.password" />
            <!-- Store Data? Yes/No -->
          </div>
          <div class="form-group">
            <label>
              Store Data?
              <label for="yes">
                <input type="radio" id="yes" value="yes" v-model="storeData" /> Yes
              </label>
              <label for="no">
                <input type="radio" id="no" value="no" v-model="storeData" /> No
              </label>
            </label>
          </div>
          <div class="row">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
              <button class="btn btn-primary" @click.prevent="submitData">Submit</button>
            </div>
          </div>

          <!-- Exercise 2 -->
          <!-- Only display the Form if it has NOT been submitted -->
          <!-- Display the Data Summary ONCE the Form HAS been submitted -->

          <!-- Exercise 3 -->
          <!-- Edit the Example from above and create a custom "Full Name" Control -->
          <!-- which still holds the First Name and Last Name Input Field -->
        </div>
      </div>
    </form>
    <hr />
    <div class="row" v-if="dataSubmitted">
      <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
        <div class="panel panel-default">
          <div class="panel-heading">
            <h4>Your Data</h4>
          </div>
          <div class="panel-body">
            <p>Full Name: {{userData.fullName}}</p>
            <p>Mail: {{userData.email}}</p>
            <p>Password: {{userData.password}}</p>
            <p>Store in Database?: {{storeData}}</p>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import FirstandLastName from "./components/FirstandLastName.vue";
export default {
  data() {
    return {
      userData: {
        email: "",
        password: "",
        fullName: "Krutika Patil"
      },
      storeData: "no",
      dataSubmitted: false
    };
  },
  methods: {
    submitData() {
      this.dataSubmitted = true;
    }
  },
  components: {
    "app-first-last-name": FirstandLastName
  }
};
</script>

<style>
</style>
