<template>
    <div v-if="ready" class="ticker-container">
      <div class="ticker-content">
        <div v-for="(agent, index) in combinedLeaderboard" :key="index" class="ticker-item">
          <img src="../assets/images/playerLogo.jpg" alt="Player Logo" class="ticker-img mx-4">
          <strong class="ticker-name">{{ agent.name }}</strong>
          <strong class="ticker-score mr-4">{{ agent.score }}</strong>
        </div>
      </div>
    </div>
  </template>
  <script>
import moment from 'moment';
import { Icon } from '@iconify/vue';

export default {
  name: "BottomScroll",
  data() {
    return {
      ready: false,
      time: "",
      increment: 0,
      leaderboard1: [
        {
          image: "playerLogo.jpg",
          name: "Liam Johnson",
          score: 1500
        },
        {
          image: "playerLogo.jpg",
          name: "Sophia Smith",
          score: 1200
        },
        {
          image: "playerLogo.jpg",
          name: "Noah Williams",
          score: 1100
        },
        {
          image: "playerLogo.jpg",
          name: "Emma Brown",
          score: 1700
        },
        {
          image: "playerLogo.jpg",
          name: "Oliver Davis",
          score: 1300
        },
        {
          image: "playerLogo.jpg",
          name: "Ava Garcia",
          score: 1400
        },
        {
          image: "playerLogo.jpg",
          name: "Elijah Martinez",
          score: 1600
        },
        {
          image: "playerLogo.jpg",
          name: "Charlotte Rodriguez",
          score: 1800
        },
        {
          image: "playerLogo.jpg",
          name: "William Hernandez",
          score: 1250
        },
        {
          image: "playerLogo.jpg",
          name: "Amelia Lopez",
          score: 1350
        }
      ],
      leaderboard2: [
        {
          image: "playerLogo.jpg",
          name: "James Wilson",
          score: 1900
        },
        {
          image: "playerLogo.jpg",
          name: "Isabella Gonzalez",
          score: 2000
        },
        {
          image: "playerLogo.jpg",
          name: "Benjamin Perez",
          score: 1750
        },
        {
          image: "playerLogo.jpg",
          name: "Mia Carter",
          score: 1850
        },
        {
          image: "playerLogo.jpg",
          name: "Lucas Taylor",
          score: 1650
        },
        {
          image: "playerLogo.jpg",
          name: "Harper Flores",
          score: 1550
        },
        {
          image: "playerLogo.jpg",
          name: "Mason Lee",
          score: 1450
        },
        {
          image: "playerLogo.jpg",
          name: "Evelyn Scott",
          score: 2050
        },
        {
          image: "playerLogo.jpg",
          name: "Alexander King",
          score: 1950
        },
        {
          image: "playerLogo.jpg",
          name: "Abigail Martinez",
          score: 1700
        }
      ],
      leaderboard3: [
        {
          image: "playerLogo.jpg",
          name: "Daniel Nguyen",
          score: 2200
        },
        {
          image: "playerLogo.jpg",
          name: "Sofia Cooper",
          score: 2100
        },
        {
          image: "playerLogo.jpg",
          name: "Logan Rivera",
          score: 2300
        },
        {
          image: "playerLogo.jpg",
          name: "Madison Price",
          score: 2400
        },
        {
          image: "playerLogo.jpg",
          name: "Jack Morris",
          score: 2250
        },
        {
          image: "playerLogo.jpg",
          name: "Ella Turner",
          score: 2150
        },
        {
          image: "playerLogo.jpg",
          name: "Ryan Cooper",
          score: 2350
        },
        {
          image: "playerLogo.jpg",
          name: "Chloe Reed",
          score: 2300
        },
        {
          image: "playerLogo.jpg",
          name: "Carter Phillips",
          score: 2275
        },
        {
          image: "playerLogo.jpg",
          name: "Grace Baker",
          score: 2225
        }
      ],
      combinedLeaderboard: [], // Combined leaderboard array
    };
  },
  async mounted() {
    this.moment = moment;
    this.time = new Date();
    this.count();
    this.ready = true;
    this.combineLeaderboards();
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
    },
  
    combineLeaderboards() {
      this.combinedLeaderboard = [...this.leaderboard1, ...this.leaderboard2, ...this.leaderboard3];
    },
  },
  components: {
    Icon,
  },
};
</script>
<style scoped>
.ticker-container {
  position: fixed;
  bottom: 0;
  left: 0;
  width: 100%;
  background: rgb(5,21,74);
  color: white;
  overflow: hidden;
}

.ticker-content {
  display: flex;
  animation: ticker 30s linear infinite;
}

.ticker-item {
  display: flex;
  align-items: center;
  padding: 10px;
  white-space: nowrap;
}

.ticker-img {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  margin-right: 10px;
}

.ticker-name, .ticker-score {
  margin-right: 20px;
}

@keyframes ticker {
  0% { transform: translate3d(100%, 0, 0); }
  100% { transform: translate3d(-100%, 0, 0); }
}
</style>
