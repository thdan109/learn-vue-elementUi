<template>
  <div class="root">
    <el-container class="container-layout">
      <el-aside class="hidden-sm-only hidden-xs-only" width="200px">
        <!-- Logo -->
        <el-col class="logo">
          <img src="../assets/Banners/logo.png" alt="logo" />
        </el-col>

        <!-- Menu -->
        <el-col>
          <el-menu>
            <el-menu-item
              v-for="(item, index) in navList"
              :key="index"
              :index="index"
            >
              <i :class="item.icon"></i>
              <span>{{ item.title }}</span>
            </el-menu-item>
          </el-menu>
        </el-col>
        <!--End Menu  -->
      </el-aside>

      <el-container>
        <!-- Header -->
        <el-header>
          <el-input
            background-color="#304156"
            class="search-input"
            prefix-icon="el-icon-search"
            placeholder="Search Anything..."
            size="medium"
            v-model="searchInput"
          >
          </el-input>
          <div class="action-header">
            <i class="el-icon-chat-dot-square"></i>
            <i class="el-icon-bell"></i>
            <el-button type="primary"> New patients </el-button>
          </div>
        </el-header>
        <!-- End Header -->

        <!-- Main -->
        <el-main>
          <el-row :gutter="20">
            <!-- Left -->
            <el-col :xl="18" :lg="18" :xs="24">
              <el-row>
                <el-col :span="24">
                  <el-card class="box-card">
                    <el-row>
                      <el-col :xl="21" :lg="21" :xs="24">
                        <h2>Hi, Dr. Joshi</h2>
                        <span id="title-unlock"
                          >Unlock the full potential become</span
                        ><span id="pro"> Pro</span>
                      </el-col>
                      <el-col :xl="3" :lg="3" :xs="24">
                        <el-button>Go Premium</el-button>
                      </el-col>
                    </el-row>
                  </el-card>
                </el-col>
              </el-row>

              <el-row gutter="40">
                <el-col :xl="8" :xs="24" :lg="8">
                  <el-card class="dashboard-card">
                    <el-row type="flex" justify="space-between">
                      <el-col>
                        <img src="../assets/Banners/medicine.png"
                      /></el-col>
                      <el-col>
                        <h1>24</h1>
                        <span>New Patients</span>
                      </el-col>
                      <el-col :span="4">
                        <i
                          style="font-size: 36px; color: blue; margin-top: 20px"
                          class="el-icon-circle-plus"
                        ></i>
                      </el-col>
                    </el-row>
                  </el-card>
                </el-col>
                <el-col :lg="8" :xl="8" :xs="24">
                  <el-card class="dashboard-card">
                    <el-row type="flex" justify="space-between">
                      <el-col> <img src="../assets/Banners/note.png" /></el-col>
                      <el-col>
                        <h1>13</h1>
                        <span>Important Tasks</span>
                      </el-col>
                      <el-col :span="4">
                        <i
                          style="font-size: 36px; color: gray; margin-top: 20px"
                          class="el-icon-circle-plus"
                        ></i>
                      </el-col>
                    </el-row>
                  </el-card>
                </el-col>
                <el-col :lg="8" :xl="8" :xs="24">
                  <el-card class="dashboard-card">
                    <el-row type="flex" justify="space-between">
                      <el-col>
                        <img src="../assets/Banners/gender.png" />
                      </el-col>
                      <el-col>
                        <h1>09</h1>
                        <span>Complex Alerts</span>
                      </el-col>
                      <el-col :span="4">
                        <i
                          style="font-size: 36px; color: gray; margin-top: 20px"
                          class="el-icon-circle-plus"
                        ></i>
                      </el-col>
                    </el-row>
                  </el-card>
                </el-col>
              </el-row>
              <!-- Patient activity -->
              <el-row>
                <el-col :span="24">
                  <el-card class="patient-activity-card">
                    <h1>Patient activity</h1>

                    <el-divider></el-divider>
                    <apexcharts
                      height="300"
                      type="line"
                      :options="options"
                      :series="series"
                    ></apexcharts>
                    <!-- <el-divider></el-divider> -->
                  </el-card>
                </el-col>
              </el-row>

              <el-row>
                <el-col>
                  <el-card class="card-recent-patient">
                    <h3>Recent patient</h3>
                    <el-divider></el-divider>
                    <el-row class="title-recent">
                      <el-col :lg="4" :xl="4">Avatar</el-col>
                      <el-col :lg="5" :xl="5">Name</el-col>
                      <el-col :lg="3" :xl="3">Weight</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">Disease</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">Date</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">Status</el-col>
                    </el-row>
                    <el-row class="info-patient">
                      <el-col :lg="4" :xl="4">
                        <img src="../assets/Banners/men1.png" />
                      </el-col>
                      <el-col :lg="5" :xl="5">Brijanmohan Mallicik</el-col>
                      <el-col :lg="3" :xl="3">70 kg</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">Cardiology</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">12 june</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">Confirmed</el-col>
                    </el-row>
                    <el-row class="info-patient">
                      <el-col :lg="4" :xl="4">
                        <img src="../assets/Banners/men2.png" />
                      </el-col>
                      <el-col :lg="5" :xl="5">Leona Ietta</el-col>
                      <el-col :lg="3" :xl="3">80 kg</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">Pathology</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">12 june</el-col>
                      <el-col class="hidden-xs-only" :lg="4" :xl="4">Cancelled</el-col>
                    </el-row>
                  </el-card>
                </el-col>
              </el-row>
            </el-col>

            <!-- End Left -->
            <!-- Right -->
            <el-col :xl="6" :lg="6" :xs="24">
              <el-row>
                <el-col :span="24">
                  <el-card class="doctor-card">
                    <el-row type="flex">
                      <el-col :span="24" align="center">
                        <img src="../assets/Banners/doctor.jpg" alt="doctor" />
                        <el-col class="info-doctor">
                          <h1>Dc. Joshi</h1>
                          <span>Medicine, NC Hospital</span>
                        </el-col>
                      </el-col>
                    </el-row>
                    <el-divider></el-divider>
                    <el-row
                      type="flex"
                      justify="space-between"
                      style="margin-top: 10px"
                    >
                      <el-col :span="10" align="center">
                        <h3>3,453</h3>
                        <span style="color: gray">Appointments</span>
                      </el-col>
                      <el-col :span="10" align="center">
                        <h3>2,545</h3>
                        <span style="color: gray">Total Patients</span>
                      </el-col>
                    </el-row>
                    <el-divider></el-divider>
                    <el-row
                      type="flex"
                      justify="space-between"
                      style="margin-top: 10px"
                    >
                      <el-col :span="24" align="flex-start">
                        <h3 style="margin-bottom: 5px">126 People</h3>
                        <span style="color: gray">Appointments Limits</span>
                        <el-progress
                          style="margin-top: 5px"
                          :percentage="50"
                          status="warning"
                        ></el-progress>
                      </el-col>
                    </el-row>
                    <el-divider></el-divider>
                    <el-row type="flex" justify="space-between">
                      <el-col :span="10" align="center">
                        <h3>43,453</h3>
                        <span style="color: gray">Consulations</span>
                      </el-col>
                      <el-col :span="10" align="center">
                        <h3>2,145</h3>
                        <span style="color: gray">Return Patients</span>
                      </el-col>
                    </el-row>
                    <el-row
                      style="margin: 20px 20px"
                      type="flex"
                      justify="center"
                    >
                      <el-progress type="circle" :percentage="25"></el-progress>
                    </el-row>
                  </el-card>
                </el-col>
              </el-row>
            </el-col>
            <!-- End right -->
          </el-row>
        </el-main>
        <!-- End Main -->
      </el-container>
    </el-container>
    <div class="session3">
      <div class="child">ádsadsadsa</div>
    </div>
  </div>
</template>
<script>
import VueApexCharts from "vue-apexcharts";

export default {
  components: {
    apexcharts: VueApexCharts,
  },
  data() {
    return {
      searchInput: "",
      navList: [
        { path: "dashboard", title: "Dash Board", icon: "el-icon-s-marketing" },
        { path: "appointments", title: "Appointment", icon: "el-icon-date" },
        { path: "patients", title: "Patients", icon: "el-icon-suitcase-1" },
        { path: "payments", title: "Payments", icon: "el-icon-bank-card" },
        {
          path: "emergency",
          title: "Emergency",
          icon: "el-icon-phone-outline",
        },
        { path: "settings", title: "Settings", icon: "el-icon-setting" },
      ],
      options: {
        chart: {
          id: "vuechart-example",
        },
        xaxis: {
          categories: [
            1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998, 1999, 2000, 2001,
            2002, 2003,
          ],
        },
      },
      series: [
        {
          name: "series-1",
          data: [30, 40, 45, 50, 49, 60, 70, 91, 92, 93, 94, 91, 95],
        },
      ],
    };
  },
};
</script>
<style>
@import url("https://fonts.googleapis.com/css2?family=Libre+Baskerville:wght@700&display=swap");
* {
  margin: 0;
}
 
.root {
  min-height: 100vh;
  font-family: "Libre Baskerville", serif;
}
.container-layout {
  min-height: 100vh;
}
.side-bar {
  background-color: red;
}
.body {
  background-color: blue;
}
.logo {
  text-align: center;
}
.logo img {
  margin: 10px 0;
  width: 120px;
}
.el-menu {
  border-right: none;
}
.el-menu-item {
  background-color: white;
  color: black;
}
.el-menu-item.is-active {
  background-color: #f0ecfd;
  color: #7b62f0;
  font-weight: 800;
}
.el-menu-item i {
  margin-right: 15px !important;
  padding: 9px 7px;
  border-radius: 8px;
}
.el-menu-item.is-active i {
  background-color: #7b62f0;
  color: white;
}
/* Header */
.el-header {
  background-color: #f0ecfd;
  padding: 10px 20px;
  display: flex;
  align-items: center;
}
.el-input .el-input__inner {
  background-color: #f0ecfd;
  margin-left: 15px;
  border: none;
  max-width: 350px;
}
.el-input__prefix {
  font-size: 25px;
}
.action-header {
  display: flex;
  flex-direction: row;
  align-items: center;
}
.action-header i {
  color: #909399;
  font-size: 25px;
  margin: 0 20px;
}
.action-header .el-button {
  margin-left: 10px;
}

/* main */
.el-main {
  background-color: #f0ecfd;
  padding: 30px;
}
.box-card {
  margin-bottom: 20px;
  border-radius: 10px;
}
.box-card h2 {
  margin-bottom: 10px;
}
.box-card #title-unlock {
  color: gray;
}
.box-card #pro {
  font-weight: 900;
  color: blue;
}
.box-card .el-button {
  color: white;
  font-weight: 600;
  background: linear-gradient(to right, #ffb75e, #ed8f03);
  margin-top: 10px;
}
.dashboard-card {
  border-radius: 10px;
  margin-bottom: 20px;
}
.dashboard-card h1 {
  font-size: 40px;
}
.dashboard-card span {
  color: rgb(172, 172, 172);
  font-size: 18px;
}
.dashboard-card img {
  width: 80px;
}
.patient-activity-card {
  border-radius: 10px;
  margin-bottom: 20px;
}
.card-recent-patient {
  border-radius: 10px;
   margin-bottom: 20px;
}
.card-recent-patient img {
  width: 40px;
}
.card-recent-patient .title-recent {
  color: gray;
  font-weight: 900;
  margin-bottom: 15px;
  display: flex;
  align-items: center;
}
.card-recent-patient .info-patient {
  display: flex;
  align-items: center;
  font-weight: 900;
}
.doctor-card {
  border-radius: 10px;
}
.doctor-card img {
  width: 180px;
}
.info-doctor h1 {
  font-size: 26px;
}
.info-doctor span {
  font-size: 18px;
  color: gray;
}
</style>
