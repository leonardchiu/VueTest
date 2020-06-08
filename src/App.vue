<template>
    <div class="container">
        <form>
            <div class="row">
                <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                    <h1>Form</h1>
                    <hr>
                    <app-fullname :value="fullName" @input="fullName = $event"></app-fullname>
                    <div class="form-group">
                      <label for="mail">Mail</label>
                      <input type="text" id="mail" class="form-control" v-model="mail">
                    </div>
                    <div class="form-group">
                      <label for="password">Password</label>
                      <input type="password" id="password" class="form-control" v-model="password">
                    </div>
                    <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3 form-group">
                      <label for="yes">
                      <input type="radio" id="yes" value="Yes" v-model="storeData"> Store Data - Yes
                      </label>
                      <label for="No">
                      <input type="radio" id="No" value="No" v-model="storeData"> Store Data - No
                      </label>
                      <button class="btn btn-primary" @click.prevent="isSubmitted = true">Submit</button>

                    </div>
                    <!-- Exercise 1 -->
                    <!-- Create a Signup Form where you retrieve the following Information -->
                    <!-- Full Name (First Name + Last Name) -->
                    <!-- Mail -->
                    <!-- Password -->
                    <!-- Store Data? Yes/No -->

                    <!-- Exercise 2 -->
                    <!-- Only display the Form if it has NOT been submitted -->
                    <!-- Display the Data Summary ONCE the Form HAS been submitted -->

                    <!-- Exercise 3 -->
                    <!-- Edit the Example from above and create a custom "Full Name" Control -->
                    <!-- which still holds the First Name and Last Name Input Field -->
                </div>
            </div>
        </form>
        <hr>
        <div class="row" v-if="isSubmitted">
            <div class="col-xs-12 col-sm-8 col-sm-offset-2 col-md-6 col-md-offset-3">
                <div class="panel panel-default">
                    <div class="panel-heading">
                        <h4>Your Data</h4>
                    </div>
                    <div class="panel-body">
                        <p>Full Name: {{ fullName }}</p>
                        <p>Mail: {{ mail }}</p>
                        <p>Password: {{ password }}</p>
                        <p>Store in Database?: {{ storeData }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    import fullName from './FullName.vue';

    export default {
      data() {
        return {
          fullName: 'Leonard Chiu',
          mail: '',
          password: '',
          storeData: 'yes',
          isSubmitted: false
        }
      },
      components: {
        appFullname: fullName
      }
    }
</script>

<style>
</style>
