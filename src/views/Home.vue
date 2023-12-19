<template>
  <div v-if="ready" class="w-full h-fit grid p-12 gap-8">
    <img src="../assets/images/ieLogo.png" alt="Insurance Express Logo" class="w-[300px]">

    <div class="w-full h-fit grid items-center relative">
      <p class="font-semibold text-custom-gray text-[26px]">Welcome to the Gameify Dashboard!</p>

       <!-- Time -->
       <p class="text-[20px] text-custom-red right-0 absolute">
        {{ formattedTime }}
      </p>
      
      
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
      
      
   <!-- Triangle Leaderboard -->
<div class="flex items-center justify-center bg-gray-100">
  <div class="w-full max-w-md p-6 bg-white rounded-lg shadow-md">
    <p class="text-2xl font-semibold text-center text-custom-red">Triangle Leaderboard</p>

    <div class="mt-4">
      <!-- Centered #1 Player Info -->
      <div class="flex flex-col items-center justify-center">
        <img src="../assets/images/playerLogo.jpg" alt="" class="w-24 h-24 object-cover rounded-full">
        <p class="text-lg truncate text-center"><span class="font-bold">#1</span> Jordan Rochelle</p>
      </div>

      <div class="mt-4 grid grid-cols-2 gap-4">
        <!-- #2 Player Info -->
        <div class="flex flex-col items-center">
          <img src="../assets/images/playerLogo.jpg" alt="" class="w-12 h-12 object-cover rounded-full">
          <p class="mt-2 text-lg truncate"><span class="font-bold">#2</span> Player Name</p>
        </div>
        <!-- #3 Player Info -->
        <div class="flex flex-col items-center">
          <img src="../assets/images/playerLogo.jpg" alt="" class="w-12 h-12 object-cover rounded-full">
          <p class="mt-2 text-lg truncate"><span class="font-bold">#3</span> Player Name</p>
        </div>
      </div>
    </div>
  </div>
</div>






      <!-- Leaderboard 2 -->
      <div class="w-full h-fit grid gap-4">
        <p class="font-medium text-[20px] text-custom-red">Leaderboard</p>
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
    <BottomScroll/>
  </div>
</template>

<script>
import { Icon } from '@iconify/vue';
import BottomScroll from '../components/bottomScroll.vue';
import { format } from 'date-fns';

export default {
  name: "Home",
  data() {
  return {
    ready: false,
    currentTime: new Date(),
    increment: 0,
    leaderboard1: [
      {
        image: "playerLogo.png",
        name: "Liam Johnson",
        score: 1500
      },
      {
        image: "playerLogo.png",
        name: "Sophia Smith",
        score: 1200
      },
      {
        image: "playerLogo.png",
        name: "Noah Williams",
        score: 1100
      },
      {
        image: "playerLogo.png",
        name: "Emma Brown",
        score: 1700
      },
      {
        image: "playerLogo.png",
        name: "Oliver Davis",
        score: 1300
      },
      {
        image: "playerLogo.png",
        name: "Ava Garcia",
        score: 1400
      },
      {
        image: "playerLogo.png",
        name: "Elijah Martinez",
        score: 1600
      },
      {
        image: "playerLogo.png",
        name: "Charlotte Rodriguez",
        score: 1800
      },
      {
        image: "playerLogo.png",
        name: "William Hernandez",
        score: 1250
      },
      {
        image: "playerLogo.png",
        name: "Amelia Lopez",
        score: 1350
      }
    ],
    leaderboard2: [
      {
        image: "playerLogo.png",
        name: "James Wilson",
        score: 1900
      },
      {
        image: "playerLogo.png",
        name: "Isabella Gonzalez",
        score: 2000
      },
      {
        image: "playerLogo.png",
        name: "Benjamin Perez",
        score: 1750
      },
      {
        image: "playerLogo.png",
        name: "Mia Carter",
        score: 1850
      },
      {
        image: "playerLogo.png",
        name: "Lucas Taylor",
        score: 1650
      },
      {
        image: "playerLogo.png",
        name: "Harper Flores",
        score: 1550
      },
      {
        image: "playerLogo.png",
        name: "Mason Lee",
        score: 1450
      },
      {
        image: "playerLogo.png",
        name: "Evelyn Scott",
        score: 2050
      },
      {
        image: "playerLogo.png",
        name: "Alexander King",
        score: 1950
      },
      {
        image: "playerLogo.png",
        name: "Abigail Martinez",
        score: 1700
      }
    ],
    leaderboard3: [
      {
        image: "playerLogo.png",
        name: "Daniel Nguyen",
        score: 2200
      },
      {
        image: "playerLogo.png",
        name: "Sofia Cooper",
        score: 2100
      },
      {
        image: "playerLogo.png",
        name: "Logan Rivera",
        score: 2300
      },
      {
        image: "playerLogo.png",
        name: "Madison Price",
        score: 2400
      },
      {
        image: "playerLogo.png",
        name: "Jack Morris",
        score: 2250
      },
      {
        image: "playerLogo.png",
        name: "Ella Turner",
        score: 2150
      },
      {
        image: "playerLogo.png",
        name: "Ryan Cooper",
        score: 2350
      },
      {
        image: "playerLogo.png",
        name: "Chloe Reed",
        score: 2300
      },
      {
        image: "playerLogo.png",
        name: "Carter Phillips",
        score: 2275
      },
      {
        image: "playerLogo.png",
        name: "Grace Baker",
        score: 2225
      }
    ]
  };
},

async mounted() {
    this.ready = true;
    this.updateCurrentTime(); // Call the method to start updating current time
  },
  
  watch: {
    increment: async function (value) {
      this.currentTime = new Date();
    }
  },
  methods: {
    count() {
      this.increment = this.increment + 1;

      setTimeout(() => {
        this.count();
      }, 10000);
    },
    // Function to update current time
    updateCurrentTime() {
      setInterval(() => {
        this.currentTime = new Date(); // Update current time
      }, 1000); // Update every 1000ms (1 second)
    },
  },
  computed: {
    formattedTime() {
      return format(this.currentTime, 'MMM do yyyy hh:mm:ss a');
    },
  },
  components: {
    Icon,
    BottomScroll,
  }
}
</script>




