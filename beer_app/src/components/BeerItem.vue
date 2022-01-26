<template>
    <div class="beer__info">
        <div class="beer__info-item"><strong>Brand:</strong> {{beerItem.brand}}</div>
        <div class="beer__info-item"><strong>Name:</strong> {{beerItem.name}}</div>
        <div class="beer__info-item"><strong>Style:</strong> {{beerItem.style}}</div>
        <div class="beer__info-item"><strong>Alcohol:</strong> {{beerItem.alcohol}}</div>
        <div class="item__btns">
          <my-remove-btn
            @click="this.$emit('remove', beerItem)"
          >Delete</my-remove-btn>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        beerItem: {
            type: Object,
            required: true,
        }
    }
}
</script>

<style scoped>
  .beer__info {
        border: 1px solid brown;
        border-radius: 5px;
        padding: 5px;
        margin-bottom: 10px;
        font-family: sans-serif;
        font-size: 15px;
        width: 410px;
    }
    .beer__info-item {
        padding-bottom: 5px;
    }


  @media(max-width: 768px) {
    .beer__info {
        width: 250px;
    }
  }
</style>