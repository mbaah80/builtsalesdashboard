<template>
      <nav class="navbar  sticky-top  flex-md-nowrap p-0">
      <a class="navbar-brand col-md-3 col-lg-2 mr-0 px-3" href="#">Gogana</a>
      <button class="navbar-toggler position-absolute d-md-none collapsed" type="button" data-toggle="collapse" data-target="#sidebarMenu" aria-controls="sidebarMenu" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <h4 class="mr-auto mt-2">
        Dashboard
      </h4>
      <ul class="navbar-nav px-3">
        <div class="nav-item text-nowrap userDetail">
           
            <div class="input-group mb-3">
            <div class="input-group-prepend">
                <span class="input-group-text" id="basic-addon1"><i class="fa fa-search" aria-hidden="true"></i></span>
            </div>
            <input class="form-control" id="searchForm" type="text" placeholder="Search here..." aria-label="Search">
            </div>
            <span class="notification ml-4 mr-4"><i class="fa fa-bell-o" aria-hidden="true"></i></span>
          <div>
            <span>Alex Mora</span> <br>
            <small>Super Admin</small>
         </div> 
         <img src="https://cdn.flintrehab.com/uploads/2020/08/Personality-Changes-After-Head-Injury-1.jpg" class="profilePic" alt="" srcset="">
        </div>
      </ul>
    </nav>
</template>

<style scoped>
.navbar{
    background-color: #fff !important;
    border-bottom: 1px solid #e5e5e7;
    box-shadow: none !important;
    color: #000 !important;
    padding: 10px !important;
}
.navbar-brand{
    color: #000 !important;
    font-size: 28px;
    font-weight: 600;
    margin-left: 30px;
}
.profilePic{
    border-radius: 50%;
    width: 60px;
    height: 60px;
    margin-left: 10px;
    object-fit: cover;
}
.notification{
    border: 1px solid #e5e5e7;
    color: #6b6b6b;
    border-radius: 50%;
    /* width: 40px;
    height: 40px; */
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 10px;
    margin-right: 10px;
}

.userDetail{
    display: flex;
    align-items: center;

}
#searchForm{
    width: 600px;
    border-top-right-radius: 20px;
    border-bottom-right-radius: 20px;
    border:none;
    background-color: #fafafa;
    margin-top: 12px;
}
.input-group-text{
    border-radius: 20px;
    border:none;
    background-color: #fafafa;
    margin-top: 12px;
}
</style>