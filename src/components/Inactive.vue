<template>
    <div>
        <h2>Inactive Users</h2>
        <ul>
            <li>
                <span><strong>NAME</strong></span>
                <span><strong>CREATED</strong></span>
            </li>
            <li v-for="(user, index) in sortedUsers" :key="index">
                <span>{{ user.name }}</span>
                <span>{{ user.created }}</span>
            </li>
        </ul>
    </div>
</template>

<script>
import { filterUsers } from "./../mixins/filterUsers.js";

export default {
    mixins: [filterUsers],

    data() {
        return {
            status: 0,
        };
    },
};
</script>

<style scoped>
h2 {
    margin: 10px 0 0;
    padding: 1rem 0;
}
div {
    margin-bottom: 2rem;
    border: 0.5px solid #ccc;
}
ul {
    list-style-type: none;
    padding-bottom: 20px;
}
ul li {
    display: block;
    line-height: 24px;
}
ul li:first-child {
    margin-bottom: 0.5rem;
    padding: 1rem 0;
}
ul li span {
    display: inline-block;
    width: 50%;
    padding: 0.1rem 0;
}
</style>