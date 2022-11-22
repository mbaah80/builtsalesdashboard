<template>
  <div>
  <Nav/>
<div class="container-fluid">
  <div class="row">
   <Sidebar/>

    <main role="main" class="col-md-9 ml-sm-auto col-lg-10 px-md-4">
    
      <div class="row">
        <div class="col-md-4">
          <div class="card">
            <div class="tableHeader">
             <div class="todaySalesInfo">
              <h6>
                Today  Sales
              </h6>
              <span >
               <h3> $54.4k </h3>
                <small >
                We have sold 123 items
                </small>
              </span>
             </div>
              <v-chart class="todaySales" :option="todaySales" />
            </div>
          
          </div>
        </div>
        <div class="col-md-4">
          <div class="card">
            <div class="tableHeader">
             <div class="todaySalesInfo">
              <h6>
                Today  Revenue
              </h6>
              <span >
               <h3> $8.2k </h3>
                <small >
                Available to payout
                </small>
              </span>
             </div>
              <v-chart class="todaySales" :option="todayRevenue" />
            </div>
          
          </div>
        </div>
        <div class="col-md-4">
          <div class="card">
            <div class="tableHeader">
             <div class="todaySalesInfo">
              <h6>
                In Escrow
              </h6>
              <span >
               <h3> $18.2k </h3>
                <small >
                Available to payout
                </small>
              </span>
             </div>
              <v-chart class="todaySales" :option="escrow" />
            </div>
          
          </div>
        </div>
      </div>
      <div class="row">
        <div class="col-md-8">
          <div class="card">
            <div class="tableHeader">
             <div>
              <h6>
                Total Revenue
              </h6>
              <span class="revenueSection">
               <h3> $54.4k </h3>
                <small class="text-success ml-2">
                 8% than last month <i class="fa fa-long-arrow-up" aria-hidden="true"></i>
                </small>
              </span>
             </div>
              <div class="ml-auto actionBtn">
                <p class="mt-2">
                  <small>Data Updates Every 3 Hours</small>
                </p>
                <button class="btn btn-default btn-small ml-4">View All Orders</button>
              </div>
            </div>
          <v-chart class="chartBar" :option="graphBar" />
          </div>
        </div>
        <div class="col-md-4">
          <div class="card">
            <div class="tableHeader">
             <div>
              <h6>
                Most Sold item
              </h6>
          
             </div>
              <div class="ml-auto actionBtn">
                <button class="btn mostSoldBtn btn-small ml-4"><i class="fa fa-ellipsis-h" aria-hidden="true"></i></button>
              </div>
            </div>
            <v-chart class="chart" :option="option" />
          </div>
        </div>
      </div>

      
      <div class="card ">
        <div class="tableHeader">
          <h6>
            Latest Orders
          </h6>
          <div class="ml-auto actionBtn">
            <small>Data Updates Every 3 Hours</small>
            <button class="btn btn-primary btn-small ml-4">View All Orders</button>
          </div>
        </div>
        <table class="table table-borderless">
        <thead class="thead-light">
          <tr>
            <th scope="col">Products</th>
            <th scope="col">Order ID</th>
            <th scope="col">Date</th>
            <th scope="col">Customer name</th>
            <th scope="col">Status</th>
            <th scope="col">Amount</th>
            <th scope="col">Action</th>
          </tr>
        </thead>
        <tbody>
          <tr>
            <td>
              <img class="productImage" src="https://media.gqmagazine.fr/photos/60ebfe8424ddaa5ec8e0066e/16:9/w_1280,c_limit/iphone13.jpeg" alt="iphone 13"> Iphone 13 pro
            </td>
            <td>#11232</td>
            <td>jun 29, 2022</td>
            <td>Anastasia Hasuna</td>
            <td><span class="badge badge-success">Delivered</span></td>
            <td>$ 1100.00</td>
            <td>
              <button class="actionDetail">...</button>
            </td>
            
          </tr>
          <tr>
            <td>
              <img class="productImage" src="https://www.cnet.com/a/img/resize/5f624f7c63102565c447663f085e95d00cb36953/hub/2015/04/07/b35f1174-696c-4d25-8a4f-fa16a2842338/macbook-air-gold-2015-16.jpg?auto=webp&fit=crop&height=675&width=1200" alt="iphone 13"> Macbook pro
            </td>
            <td>#11232</td>
            <td>jun 28, 2022</td>
            <td>Anastasia Hasuna</td>
            <td><span class="badge badge-warning text-white">Pending</span></td>
            <td>$ 1200.00</td>
            <td>
              <button class="actionDetail">...</button>
            </td>
            
          </tr>
          <tr>
            <td>
              <img class="productImage" src="https://www.apple.com/newsroom/images/product/watch/standard/Apple_delivers-apple-watch-series-6_09152020_big.jpg.large.jpg" alt="iphone 13"> Apple Watch
            </td>
            <td>#11232</td>
            <td>jun 27, 2022</td>
            <td>Induan Kastorika</td>
            <td><span class="badge badge-danger text-white">Cancelled</span></td>
            <td>$ 1200.00</td>
            <td>
              <button class="actionDetail">...</button>
            </td>
            
          </tr>
         
        </tbody>
      </table>
      </div>
    </main>
  </div>
</div>

  </div>
</template>

<script>
import Sidebar from '@/components/sidebar.vue'
import Nav from '@/components/navbar.vue'
import { use } from "echarts/core";
import { CanvasRenderer } from "echarts/renderers";
import { PieChart, BarChart } from "echarts/charts";
import {GridComponent} from "echarts/components";
import {
  TitleComponent,
  TooltipComponent,
  LegendComponent
} from "echarts/components";
import VChart, { THEME_KEY } from "vue-echarts";
use([
  CanvasRenderer,
  PieChart,
  BarChart,
  TitleComponent,
  TooltipComponent,
  LegendComponent,
  GridComponent
]);


export default {
  name: 'Dashboard',
  components: { VChart, Sidebar, Nav },
  props: {
    chartId: {
      type: String,
      default: 'doughnut-chart'
    },
    datasetIdKey: {
      type: String,
      default: 'label'
    },
    width: {
      type: Number,
      default: 400
    },
    height: {
      type: Number,
      default: 100
    },
    cssClasses: {
      default: '',
      type: String
    },
    styles: {
      type: Object,
      default: () => {}
    },
    plugins: {
      type: Object,
      default: () => {}
    }
  },
  data() {
    return {
      todaySales:{
        legend: {
          orient: "horizontal",
          bottom: "bottom",
          data: [
            "Today Sale",
          ]
        },
        series: [
          {
            type: 'pie',
            radius: ['40%','50%'],

            avoidLabelOverlap: false,
            label: {
              show: true,
              position: 'center'
            },
            data: [
              { value: 335, name: "75%" },
            ],
            emphasis: {
              label: {
                show: true,
                fontSize: '40',
                fontWeight: 'bold'
              }
            },
            labelLine: {
              show: false
            },
          }
        ]
      },
      todayRevenue:{
        legend: {
          orient: "horizontal",
          bottom: "bottom",
          data: [
            "Today Revenue",
          ]
        },
        series: [
          {
            type: 'pie',
            radius: ['40%','50%'],
            showBackground: true,

             backgroundStyle: {
              color: 'rgba(180, 180, 180, 0.2)'
            },

            avoidLabelOverlap: false,
            label: {
              show: true,
              position: 'center'
            },
            data: [
              { value: 115 },
              { value: 1200, name: "85%" },
            ],
            emphasis: {
              label: {
                show: true,
                fontSize: '40',
                fontWeight: 'bold'
              }
            },
            labelLine: {
              show: false
            },
          }
        ]
      },
      escrow:{
        legend: {
          orient: "horizontal",
          bottom: "bottom",
          data: [
            "Today Revenue",
          ]
        },
        series: [
          {
            type: 'pie',
            radius: ['40%','50%'],
            showBackground: true,

             backgroundStyle: {
              color: 'rgba(180, 180, 180, 0.2)'
            },

            avoidLabelOverlap: false,
            label: {
              show: true,
              position: 'center'
            },
            data: [
              { value: 115 },
              { value: 115 },
              { value: 115 },
              { value: 1200, name: "60%" },
            ],
            emphasis: {
              label: {
                show: true,
                fontSize: '40',
                fontWeight: 'bold'
              }
            },
            labelLine: {
              show: false
            },
          }
        ]
      },
    
      option:{
        legend: {
          orient: "horizontal",
          bottom: "bottom",
          data: [
            "Jeans",
            "Shirts",
            "Caps",
            "Others",
          ]
        },
        series: [
          {
            type: 'pie',
            radius: ['50%', '60%'],
            avoidLabelOverlap: false,
            label: {
              show: true,
              position: 'center'
            },
            data: [
              { value: 335, name: "Jeans" },
              { value: 310, name: "Shirts" },
              { value: 120, name: "Caps" },
              { value: 135, name: "Others" },
            ],
            emphasis: {
              label: {
                show: true,
                fontSize: '40',
                fontWeight: 'bold'
              }
            },
            labelLine: {
              show: false
            },
          }
        ]
      },
      graphBar:{ 
        xAxis: {
          type: 'category',
          data: ['Jan', 'Feb', 'Mar', 'Apr', 'May', 'Jun', 'Jul', 'Aug', 'Sep']
        },
        yAxis: {
          type: 'value',
          data: ['0', '20k', '50k', '60k', '80k', '100k']

        },
        series: [{
          data: [10, 20, 40, 60, 80, 10, 20, 40, 100],
          type: 'bar',
          showBackground: true,

          backgroundStyle: {
              color: 'rgba(180, 180, 180, 0.2)'
            }
        }]
      }
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card{
  border-radius: 10px;
  margin-top: 30px;
  margin-bottom: 40px;
}
.tableHeader{
  display: flex;
  align-items: center;
  padding: 1rem;
}
.actionBtn{
  display: flex;
  align-items: center;
  justify-content: center;
}
.productImage{
  width: 50px;
  height: 50px;
  border-radius: 14px;
  margin-right: 1rem;
  object-fit: cover;
}
.btn-primary{
  border-radius: 7px;
}
.btn-default{
  border-radius: 7px;
  background-color: #F5F5F5;
  color: #000;
}
.actionDetail{
  background-color: #fff;
  border: none;
  align-items: center;
  text-align: center;
}
.actionDetail:hover{
  background-color: rgb(231, 229, 229);
  border: none;
  border-radius: 7px;
}
.revenueSection{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.mostSoldBtn{
  border: 1px solid #ededed;
  color: #ada9a9;
}
small{
  color: #ada9a9;
}
.chart {
  height: 400px;
  width: 100%;
}
.chartBar{
  height: 360px;
  width: 100%;
}
.todaySales{
  height: 150px;
  width: 30%;
}
.todaySalesInfo{
  width: 70%;
}
</style>
