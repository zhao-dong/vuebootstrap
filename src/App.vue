<template>
  <div id="app">
    <b-navbar toggleable="lg" type="dark" variant="info">
    <b-navbar-brand href="#">NavBar</b-navbar-brand>

    <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

    <b-collapse id="nav-collapse" is-nav>
      <b-navbar-nav>
        <b-nav-item href="#">Link</b-nav-item>
        <b-nav-item href="#" disabled>Disabled</b-nav-item>
      </b-navbar-nav>

      <!-- Right aligned nav items -->
      <b-navbar-nav class="ml-auto">
        <b-nav-form>
          <b-form-input size="sm" class="mr-sm-2" placeholder="Search"></b-form-input>
          <b-button size="sm" class="my-2 my-sm-0" type="submit">Search</b-button>
        </b-nav-form>

        <b-nav-item-dropdown text="Lang" right>
          <b-dropdown-item href="#">EN</b-dropdown-item>
          <b-dropdown-item href="#">ES</b-dropdown-item>
          <b-dropdown-item href="#">RU</b-dropdown-item>
          <b-dropdown-item href="#">FA</b-dropdown-item>
        </b-nav-item-dropdown>

        <b-nav-item-dropdown right>
          <!-- Using 'button-content' slot -->
          <template v-slot:button-content>
            <em>User</em>
          </template>
          <b-dropdown-item href="#">Profile</b-dropdown-item>
          <b-dropdown-item href="#">Sign Out</b-dropdown-item>
        </b-nav-item-dropdown>
      </b-navbar-nav>
    </b-collapse>
  </b-navbar>
  <b-row align-h="center" class="mt-5">
    <b-col cols="5">
      <b-card
        title="Card Title"
        img-src="https://picsum.photos/600/300/?image=25"
        img-alt="Image"
        img-top
        tag="article"
        style="max-width: 20rem;"
        class="mb-2"
      >
        <b-card-text>
          Some quick example text to build on the card title and make up the bulk of the card's content.
        </b-card-text>
        <b-button href="#" variant="primary">Go somewhere</b-button>
      </b-card>
    </b-col>
  </b-row>
  <b-card
    title="Card Title"
    img-src="https://picsum.photos/600/300/?image=25"
    img-alt="Image"
    img-top
    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <b-card-text>
      Some quick example text to build on the card title and make up the bulk of the card's content.
    </b-card-text>

    <b-button href="#" variant="primary">Go somewhere</b-button>
  </b-card>
    <b-container class="bv-example-row">
      <b-row>
        <b-col>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</b-col>
        <b-col cols="8">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</b-col>
        <b-col>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</b-col>
      </b-row>
      <hr>
      <b-row>
        <b-col md="4">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</b-col>
        <b-col md="4" offset-md="4">Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</b-col>
      </b-row>
      <hr>
      <b-row>
        <b-col sm>col-sm</b-col>
        <b-col sm>col-sm</b-col>
        <b-col sm>col-sm</b-col>
      </b-row>
      <hr>
      <b-row align-v="center" class="height">
        <b-col>One of three columns</b-col>
        <b-col>One of three columns</b-col>
        <b-col>One of three columns</b-col>
      </b-row>
      <hr>
      <b-row align-h="center">
        <b-col cols="4">
          <b-button size="lg" variant="success" @click="handleClick">My Button</b-button>
        </b-col>
        <b-col cols="4">
          <b-alert v-model="showDismissibleAlert" variant="danger" dismissible>
            Dismissible Alert!
          </b-alert>
        </b-col>
      </b-row>
      <hr>
      <b-row>
        <b-form @submit="onSubmit" @reset="onReset" v-if="show">
          <b-form-group
            id="input-group-1"
            label="Email address:"
            label-for="input-1"
            description="We'll never share your email with anyone else."
          >
            <b-form-input
              id="input-1"
              v-model="form.email"
              type="email"
              required
              placeholder="Enter email"
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-2" label="Your Name:" label-for="input-2">
            <b-form-input
              id="input-2"
              v-model="form.name"
              required
              placeholder="Enter name"
            ></b-form-input>
          </b-form-group>

          <b-form-group id="input-group-3" label="Food:" label-for="input-3">
            <b-form-select
              id="input-3"
              v-model="form.food"
              :options="foods"
              required
            ></b-form-select>
          </b-form-group>

          <b-form-group id="input-group-4">
            <b-form-checkbox-group v-model="form.checked" id="checkboxes-4">
              <b-form-checkbox value="me">Check me out</b-form-checkbox>
              <b-form-checkbox value="that">Check that out</b-form-checkbox>
            </b-form-checkbox-group>
          </b-form-group>
          <div class="d-flex justify-content-between">
            <div>
              <b-button type="submit" variant="primary">Submit</b-button>
              <b-button type="reset" variant="danger">Reset</b-button>
            </div>
            <div>
              <a href="#">Forgot Password</a>
            </div>
          </div>
        </b-form>
      </b-row>
      <hr>
      <b-row  align-h="center">
        <b-button v-b-modal.modal-1>Launch demo modal</b-button>
        <b-button v-b-popover.hover.top="'I am popover directive content!'" title="Popover Title">
          Hover Me
        </b-button>
      </b-row>
      <hr>
      <b-row>
        <b-table striped hover :items="items"></b-table>
      </b-row>
    </b-container>
    <b-modal id="modal-1" title="BootstrapVue">
      <p class="my-4">Hello from modal!</p>
    </b-modal>
  </div>
</template>

<script>
export default {
  name: 'App',
  data () {
    return {
      form: {
        email: '',
        name: '',
        food: null,
        checked: []
      },
      show: true,
      foods: [{ text: 'Select One', value: null }, 'Carrots', 'Beans', 'Tomatoes', 'Corn'],
      showDismissibleAlert: false,
      items: [
        { age: 40, first_name: 'Dickerson', last_name: 'Macdonald' },
        { age: 21, first_name: 'Larsen', last_name: 'Shaw' },
        { age: 89, first_name: 'Geneva', last_name: 'Wilson' },
        { age: 38, first_name: 'Jami', last_name: 'Carney' }
      ]
    }
  },
  methods: {
    handleClick () {
      console.log('handleClick')
      this.showDismissibleAlert = true
    },
    onSubmit (evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
    },
    onReset (evt) {
      evt.preventDefault()
      // Reset our form values
      this.form.email = ''
      this.form.name = ''
      this.form.food = null
      this.form.checked = []
      // Trick to reset/clear native browser form validation state
      this.show = false
      this.$nextTick(() => {
        this.show = true
      })
    }
  }
}
</script>

<style>
  body {
    background: lightgrey !important;
  }
  .height {
    min-height: 10rem;
    background: lightgrey
  }
</style>
