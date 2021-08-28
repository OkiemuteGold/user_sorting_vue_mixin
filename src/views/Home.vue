<template>
    <div class="home">
        <div class="users">
            <AllUsers />
            <Active />
            <Inactive />
        </div>
    </div>
</template>

<script>
import AllUsers from "../components/AllUsers.vue";
import Active from "../components/Active.vue";
import Inactive from "../components/Inactive.vue";

export default {
    name: "Home",
    components: {
        AllUsers,
        Active,
        Inactive,
    },
};
</script>

<style>
.users > * {
    float: left;
    width: 46%;
    padding: 1rem 3rem;
    margin: 0 2%;
    text-align: left;
    border: 0.5px solid #ccc;
}
</style>
