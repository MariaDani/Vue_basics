<template>
    <button class="btn">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'my-random-button'
}
</script>

<style scoped>
    .btn {
        margin-top: -180px;
        margin-left: 110px;
        margin-bottom: 20px;

        border-radius: 50%;
        border: 1px solid #800000;
        background: linear-gradient(to bottom right, #ff6600 0%, #990000 100%);
        box-shadow: #800000 5px 5px;

        width: 150px;
        height: 150px;

        color: white;
        font-family: sans-serif;
        font-weight: 800;
        font-size: 30px;
        text-transform: uppercase;
    }

    
    @media(max-width: 768px) {
        .btn {
            margin-left: 90px;
        }
    }

    @media(max-width: 480px) {
        .btn {
            width: 110px;
            height: 110px;  
            font-size: 15px;
            margin-top: -230px;
        }
    }
</style>