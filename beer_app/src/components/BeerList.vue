<template>
    <div class="main">
      <div class="main__content">
        <transition-group name='beer-list'>
          <beer-item
          :beerItem="beerItem"
          v-for="beerItem in beerInfo"
          :key="beerItem.id"
          @remove="$emit('remove', beerItem)"
        />
        </transition-group>
      </div>
    </div>
</template>

<script>
import BeerItem from './BeerItem.vue'

export default {
    components: { 
        BeerItem,
    },
    props: {
        beerInfo: {
            type: Array,
            required: true,
        }
    },
    
}
</script>

<style scoped>
    .main {
        display: flex;
        flex-direction: column;
        background-color: bisque;
        border-radius: 5px;
        margin-top: 20px;
        margin-bottom: 20px;
        max-width: 450px;
        height: auto;
    }
    .main__content {
        padding: 10px;
    }

    .beer-list-item {
            display: inline-block;
            margin-right: 10px;
        }
    .beer-list-enter-active,
    .beer-list-leave-active {
            transition: all 0.4s ease;
        }
    .beer-list-enter-from,
    .beer-list-leave-to {
            opacity: 0;
            transform: translateX(130px);
        }


    @media(max-width: 768px) {
        .main {
            width: 350px;
            margin-right: 20px;
        }
    }

    @media(max-width: 480px) {
        .main {
            margin-top: 10px;
            width: 300px;
            margin-left: 20px;
        }
    }

</style>