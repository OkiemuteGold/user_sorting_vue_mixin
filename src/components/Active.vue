<template>
    <div>
        <h2>Active Users</h2>
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
import users from "@/data/users.js";

export default {
    data() {
        return {
            status: 1,
            users,
        };
    },
    methods: {
        filter_active_inactive() {
            if (this.status != null) {
                var status = this.status;
                return this.users.filter(function (users) {
                    return users.status == status;
                });
            } else {
                return this.users;
            }
        },
        sort_by(users, sortProp) {
            return users.sort(function (a, b) {
                if (a[sortProp] > b[sortProp]) return 1;
                if (a[sortProp] < b[sortProp]) return -1;
                return 0;
            });
        },
    },
    computed: {
        sortedUsers() {
            if (!this.sortCriteria) {
                this.sortCriteria == "created_at";
            }
            return this.sort_by(
                this.filter_active_inactive(),
                this.sortCriteria
            );
        },
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