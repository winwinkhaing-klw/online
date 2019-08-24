<template>
 <div class="navbar navbar-expand-lg  navbar-dark bg-primary">
    
  <!-- <nav class="navbar navbar-expand-lg fixed-top navbar-primary">  -->
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Online</a>
          <router-link class="nav-link" to="/typography" name="Typography" icon="ti-text">Typography</router-link>
      <button class="navbar-toggler navbar-burger"
              type="button"
              @click="toggleSidebar"
              :aria-expanded="$sidebar.showSidebar"
              aria-label="Toggle navigation">
        <span class="navbar-toggler-bar"></span>
        <span class="navbar-toggler-bar"></span>
        <span class="navbar-toggler-bar"></span>
      </button>
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav ml-auto">
          
          <li class="nav-item">
            <a href="#" class="nav-link">
              <i class="ti-panel"></i>
              <p>Stats</p>
            </a>
          </li>
          <drop-down class="nav-item"
                     title="Categories"
                     title-classes="nav-link"
                     icon="ti-menu">
            <a class="dropdown-item" href="#">Course 1</a>
            <a class="dropdown-item" href="#">Course 2</a>
            <a class="dropdown-item" href="#">Course 3</a>
            <a class="dropdown-item" href="#">Course 4</a>
            <a class="dropdown-item" href="#">Another Course</a>
          </drop-down>
          <li class="nav-item">    
           <router-link class="nav-link" to="/stats" name="User Profile" icon="ti-user">Profile</router-link>
          </li>
        </ul>
      </div>
      <div class="collapse navbar-collapse">
        <ul class="navbar-nav ml-auto">
          
          <li class="nav-item">
            <a href="#" class="nav-link">
              <i class="ti-panel"></i>
              <p>Stats</p>
            </a>
          </li>
          <drop-down class="nav-item"
                     title="Categories"
                     title-classes="nav-link"
                     icon="ti-menu">
            <a class="dropdown-item" href="#">Category 1 1</a>
            <a class="dropdown-item" href="#">Category 2</a>
            <a class="dropdown-item" href="#">Category 3</a>
            <a class="dropdown-item" href="#">Category 4</a>
            <a class="dropdown-item" href="#">Another Category</a>
          </drop-down>
          <li class="nav-item">    
           <router-link class="nav-link" to="/stats" name="User Profile" icon="ti-user">Profile</router-link>
          </li>
        </ul>
      </div>
    </div>
 </div>
</template>
<script>
export default {
  computed: {
    routeName() {
      const { name } = this.$route;
      return this.capitalizeFirstLetter(name);
    }
  },
  data() {
    return {
      activeNotifications: false
    };
  },
  methods: {
    capitalizeFirstLetter(string) {
      return string.charAt(0).toUpperCase() + string.slice(1);
    },
    toggleNotificationDropDown() {
      this.activeNotifications = !this.activeNotifications;
    },
    closeDropDown() {
      this.activeNotifications = false;
    },
    toggleSidebar() {
      this.$sidebar.displaySidebar(!this.$sidebar.showSidebar);
    },
    hideSidebar() {
      this.$sidebar.displaySidebar(false);
    }
  }
};
</script>
<style>
</style>
