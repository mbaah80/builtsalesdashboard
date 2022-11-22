<template>
     <nav id="sidebarMenu" class="col-md-3 col-lg-2 d-md-block bg-light sidebar collapse">
      <div class="sidebar-sticky pt-3 p-4">
        <ul class="nav flex-column">
          <li class="nav-item">
            <a class="nav-link active" href="#">
              <i class="fa fa-pie-chart" aria-hidden="true"></i>
              Dashboard <span class="sr-only">(current)</span>
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              <i class="fa fa-signal" aria-hidden="true"></i>
              Statistics
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              <i class="fa fa-usd" aria-hidden="true"></i>
              Payment
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              <i class="fa fa-exchange" aria-hidden="true"></i>
              Transactions
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              <span data-feather="bar-chart-2"></span>
              <i class="fa fa-shopping-bag" aria-hidden="true"></i> Products
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              <i class="fa fa-users" aria-hidden="true"></i>
              Customer
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              <i class="fa fa-comments" aria-hidden="true"></i>
              Messages
            </a>
          </li>
        </ul>
        <ul class="nav flex-column mb-2 logout">
          <li class="nav-item mt-auto">
            <a class="nav-link" href="#">
              <i class="fa fa-cog" aria-hidden="true"></i>
              Settings
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">
              <i class="fa fa-sign-out" aria-hidden="true"></i>
              Logout
            </a>
          </li>
        </ul>
      </div>
    </nav>
</template>

<style scoped>
 .active{
  background-color: #184bfe;
  color: #fff !important;
  border: 1px solid #ededed;
  border-radius: 7px;
  /* margin-top: 25%;
  margin-bottom: 25%; */
}
.nav-link{
  color: #9497a0;
  padding: 15px;
}
#sidebarMenu{
  background-color: #fff !important;
  border-right: 1px solid #e5e5e7;
  padding: 1rem;
  position: relative;
  height: 100%;
  width: 100%;
  z-index: 1;
  position: fixed;

}
.logout{
  position: fixed;
  bottom: 0;
}
</style>