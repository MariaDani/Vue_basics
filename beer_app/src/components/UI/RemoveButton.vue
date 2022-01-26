<template>
    <button class="btn-remove">
        <slot></slot>
    </button>
</template>

<script>
export default {
    name: 'my-remove-btn',
}
</script>

<style scoped>
    .btn-remove {
        position: absolute;
        margin-top: -65px;
        margin-left: 340px;
        background-color: #691919cb;
        border: none;
        border-radius: 5px;
        color: white;
        width: 60px;
        height: 40px;
        text-transform: lowercase;
    }

    
    @media(max-width: 768px) {
        .btn-remove {
            position: relative;
            margin-left: 0;
            margin-top: 5px;
        }
    }



</style>