<template>
    <div class="aside">
      <div class="aside__content">
        <img v-bind:src="userInfo.avatar" class="user__ph">
        <div class="user__info"><strong>First Name:</strong> {{userInfo.first_name}}</div>
        <div class="user__info"><strong>Last Name:</strong> {{userInfo.last_name}}</div>
        <div class="user__info"><strong>Username:</strong> {{userInfo.username}}</div>
        <div class="user__info"><strong>E-mail:</strong> {{userInfo.email}}</div>
      </div>
    </div>
</template>

<script>
export default {
    props: {
        userInfo: {
            type: Array,
            required: true,
        },
    },
}
</script>

<style scoped>
    .aside {
        margin: 20px;
        display: flex;
        flex-direction: column;
        background-color: beige;
        border-radius: 5px;
        width: 350px;
        min-height: 550px;
        margin-bottom: 100px;
        font-family: sans-serif;
        font-size: 15px;
    }
    .aside__content {
        padding: 10px;
    }
    .user__ph {
        padding-bottom: 30px;
    }
    .user__info {
        padding-bottom: 10px;
    }

    @media(max-width: 768px) {
        .aside {
            width: 300px;
        }
    }

    @media(max-width: 480px) {
        .aside__content {
            padding-top: 0;
        }
        .user__ph {
            width: 250px;
            height: 250px;
        }
    }

</style>