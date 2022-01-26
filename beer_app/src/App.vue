<template>
  <div class="app">
    <div class="usr_btn">
      <user-info 
      :userInfo="userInfo"
      />

      <my-random-button
      @click="fetchBeer"
    > Press</my-random-button>
    </div>
    
    <beer-list 
      :beerInfo="beerInfo"
      v-if="beerInfo.length > 0"
      @remove="removeItem"
    />
    <div v-else class="alter_el">Wanna some beer? Press the button!</div>

  </div>
</template>

<script>

  import axios from 'axios';
  import UserInfo from './components/UserInfo.vue'
  import BeerList from './components/BeerList.vue'

  export default {
    components: {
      UserInfo,
      BeerList,
    },
    data() {
      return {
        userInfo: [],
        beerInfo: [],
      }
    },
    methods: {
      async fetchUser() {
        try {
          const responseUser = await axios.get('https://random-data-api.com/api/users/random_user');
          this.userInfo = responseUser.data;
        } catch (e) {
          alert('Error!');
        }
      },

      async fetchBeer() {
        try {
          const responseBeer = await axios.get('https://random-data-api.com/api/beer/random_beer');
          this.beerInfo.push(responseBeer.data);
        } catch (e) {
          alert('Error!');
        }
      },

      removeItem(beerItem) {
        this.beerInfo = this.beerInfo.filter(item => item.id !== beerItem.id);
      },
    },

    mounted() {
      this.fetchUser();
    },
  }
</script>

<style scoped>
  .app {
    display: flex;
    flex-direction: row;
    max-width: 850px;
    margin-right: auto;
    margin-left: auto;
    border-radius: 5px;
  }
  .alter_el {
    margin-right: 20px;
    margin-top: 20px;
    margin-bottom: 20px;
    background-color: bisque;
    width: 450px;
    padding-top: 20px;
    color: coral;
    font-size: 30px;
    text-align: center;
    font-weight: 800;
    border-radius: 5px;
  }

  .usr_btn {
    display: flex;
    flex-direction: column;
  }

  
  @media(max-width: 768px) {
    .app {
      max-width: 760px;
    }

    .alter_el {
      width: 350px;
      margin-right: 20px;
    }
  }

  @media(max-width: 480px) {
    .app {
      flex-direction: column;
      max-width: 480px;
    }

    .alter_el {
      width: 300px;
      margin-left: 20px;
      padding-bottom: 10px;
      margin-top: 10px;
    }
  }

</style>