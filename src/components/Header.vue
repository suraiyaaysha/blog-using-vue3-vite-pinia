<template>
    <!--Main Menu/Navbar Area Start -->
  <header class="navbar">
      <!-- NOTE -->
      <!-- If user logged in add "afterLoginMenu" class or Remove it -->
      <!-- NOTE -->
      <nav class="navbar navbar-expand-lg" aria-label="Dark offcanvas navbar">
          <div class="container">
            <router-link class="navbar-brand text-white" to="/">
              <!-- <img alt="Vue logo" class="logo" src="@/assets/logo.svg" width="125" height="125" /> -->
              <!-- <img class="img-fluid" src="assets/img/logo.png" alt="Uncloud"> -->
              BlogGo
            </router-link>
            <button class="navbar-toggler" type="button" data-bs-toggle="offcanvas" data-bs-target="#offcanvasNavbarDark" aria-controls="offcanvasNavbarDark">
              <span class="iconify" data-icon="heroicons-outline:menu"></span>
            </button>

              <div class="offcanvas offcanvas-end" tabindex="-1" id="offcanvasNavbarDark" aria-labelledby="offcanvasNavbarDarkLabel">
              <div class="offcanvas-header">
                  <h5 class="offcanvas-title" id="offcanvasNavbarDarkLabel">Menu</h5>
                  <button type="button" class="btn-close" data-bs-dismiss="offcanvas" aria-label="Close"><span class="iconify" data-icon="akar-icons:cross"></span></button>
              </div>
              <div class="offcanvas-body">
                  <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                      <li class="nav-item">
                        <RouterLink to="/" class="nav-link">Posts</RouterLink>
                      </li>
                      <li class="nav-item">
                          <RouterLink to="/authors" class="nav-link">Authors</RouterLink>
                      </li>
                      <li class="nav-item signInMenu">
                          <a class="nav-link theme-btn" href="#">Login</a>
                      </li>
                      <li class="nav-item dropdown userAccountMenu nav-round-menu">
                          <a class="nav-link dropdown-toggle" href="#" id="userAccountMenuDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                          <!-- <img src="assets/img/account-settings-avatar.png" alt="User"> -->
                            Profile
                          </a>
                          <ul class="dropdown-menu dropdown-menu-end" aria-labelledby="userAccountMenuDropdown">
                          <li><a class="dropdown-item" href="#">Profile</a></li>
                          <li><a class="dropdown-item" href="#">Logout</a></li>
                          </ul>
                      </li>
                  </ul>
              </div>
            </div>
          </div>
      </nav>
  </header>
  <!--Main Menu/Navbar Area Start -->
</template>

<script>
export default {
    name: 'Header'

}
</script>

<style>
.navbar {
    display: block;
}
</style>