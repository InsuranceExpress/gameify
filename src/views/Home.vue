<template>
  <div v-if="ready" class="w-full h-fit grid p-12 gap-8">
    <img src="../assets/images/ieLogo.png" alt="Insurance Express Logo" class="w-[300px]">

    <div class="w-full h-fit grid items-center relative">
      <p class="font-semibold text-custom-gray text-[26px]">Welcome to the Gameify Dashboard!</p>

      <!-- Time -->
      <p class="text-[20px] text-custom-red right-0 absolute">{{moment(time).format('ddd MMM Do Y hh:mm a')}}</p>
    </div>

    <div class="w-full h-fit grid grid-cols-3 gap-12">
      <!-- Leaderboard 1 -->
      <div class="w-full h-fit grid gap-4">
        <p class="font-medium text-[20px] text-custom-red">General Leaderboard</p>
        <div class="w-full h-fit max-h-[500px] overflow-y-scroll grid border-[1px] border-custom-gray border-opacity-20 rounded-[4px]">
          <!-- Headers -->
          <div class="w-full h-[42px] flex items-center ">
            <!-- Number Icon -->
            <div class="w-[10%] h-full grid">
              <Icon icon="solar:hashtag-bold-duotone" height="24px" class="m-auto" />
            </div>
  
            <div class="w-[55%] h-full grid items-center px-2">
              <p class="text-[20px] truncate"></p>
            </div>
  
            <div class="w-[35%] h-full grid items-center px-2">
              <p class="text-[20px] truncate">Count</p>
            </div>
          </div>


          <div v-for="(agent, index) in leaderboard1" :key="index" class="w-full h-[74px] flex items-center  ">
            <!-- Number Icon -->
            <div class="w-[10%] h-full grid">
              <Icon :icon="'fa6-solid:'+(index+1)" height="24px" class="m-auto" />
            </div>
  
            <!-- Agent Information -->
            <div class="w-[55%] h-full flex gap-2 items-center px-2">
              <!-- Logo -->
              <div class="w-[50px] h-[50px] rounded-full relative overflow-clip border ">
                <img src="../assets/images/playerLogo.jpg" alt="" class=" object-cover w-[50px] h-[50px]">
              </div>
              
              <!-- Name -->
              <div class="grid">
                <p class="text-[18px] truncate">Jordan Rochelle</p>
              </div>
            </div>
  
            <div class="w-[35%] h-full grid items-center px-2">
              <p class="text-[18px] truncate text-custom-red">48</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import moment from 'moment';
import { Icon } from '@iconify/vue';

export default {
  name: "Home",
  data(){
    return{
      ready: false,
      time: "",
      increment: 0,
      leaderboard1: [
        {
          image: "playerLogo.png",
          image: "Liam Johnson",
          image: 1500
        },
        {
          image: "playerLogo.png",
          image: "Sophia Smith",
          image: 1200
        },
        {
          image: "playerLogo.png",
          image: "Noah Williams",
          image: 1100
        },
        {
          image: "playerLogo.png",
          image: "Emma Brown",
          image: 1700
        },
        {
          image: "playerLogo.png",
          image: "Oliver Davis",
          image: 1300
        },
        {
          image: "playerLogo.png",
          image: "Ava Garcia",
          image: 1400
        },
        {
          image: "playerLogo.png",
          image: "Elijah Martinez",
          image: 1600
        },
        {
          image: "playerLogo.png",
          image: "Charlotte Rodriguez",
          image: 1800
        },
        {
          image: "playerLogo.png",
          image: "William Hernandez",
          image: 1250
        },
        {
          image: "playerLogo.png",
          image: "Amelia Lopez",
          image: 1350
        }
      ],
      leaderboard2: [
        {
          image: "playerLogo.png",
          image: "James Wilson",
          image: 1900
        },
        {
          image: "playerLogo.png",
          image: "Isabella Gonzalez",
          image: 2000
        },
        {
          image: "playerLogo.png",
          image: "Benjamin Perez",
          image: 1750
        },
        {
          image: "playerLogo.png",
          image: "Mia Carter",
          image: 1850
        },
        {
          image: "playerLogo.png",
          image: "Lucas Taylor",
          image: 1650
        },
        {
          image: "playerLogo.png",
          image: "Harper Flores",
          image: 1550
        },
        {
          image: "playerLogo.png",
          image: "Mason Lee",
          image: 1450
        },
        {
          image: "playerLogo.png",
          image: "Evelyn Scott",
          image: 2050
        },
        {
          image: "playerLogo.png",
          image: "Alexander King",
          image: 1950
        },
        {
          image: "playerLogo.png",
          image: "Abigail Martinez",
          image: 1700
        }
      ],
      leaderboard3: [
        {
          image: "playerLogo.png",
          image: "Daniel Nguyen",
          image: 2200
        },
        {
          image: "playerLogo.png",
          image: "Sofia Cooper",
          image: 2100
        },
        {
          image: "playerLogo.png",
          image: "Logan Rivera",
          image: 2300
        },
        {
          image: "playerLogo.png",
          image: "Madison Price",
          image: 2400
        },
        {
          image: "playerLogo.png",
          image: "Jack Morris",
          image: 2250
        },
        {
          image: "playerLogo.png",
          image: "Ella Turner",
          image: 2150
        },
        {
          image: "playerLogo.png",
          image: "Ryan Cooper",
          image: 2350
        },
        {
          image: "playerLogo.png",
          image: "Chloe Reed",
          image: 2300
        },
        {
          image: "playerLogo.png",
          image: "Carter Phillips",
          image: 2275
        },
        {
          image: "playerLogo.png",
          image: "Grace Baker",
          image: 2225
        }
      ]
    }
  },
  async mounted(){
    this.moment = moment

    this.time = new Date()
    this.count()
    this.ready = true
  },
  watch: {
    increment: async function(value){
      this.time = new Date()
    }
  },
  methods: {
    count(){
      this.increment = this.increment + 1

      setTimeout(() => {
        this.count()
      }, 10000)
    }
  },
  components: {
    Icon
  }
}
</script>
