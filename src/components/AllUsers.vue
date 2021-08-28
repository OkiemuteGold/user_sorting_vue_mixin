<template>
    <div>
        <h2>All Users</h2>

        <div class="radio-btns">
            <p>Sort by:</p>
            <div
                class="radio-btn-filter"
                v-for="(prop, index) in userProperties"
                :key="index"
            >
                <span v-if="prop != 'image'">
                    <input
                        type="radio"
                        :id="prop"
                        :value="prop"
                        v-model="sortCriteria"
                    />
                    <label :for="prop">{{ prop }}</label>
                </span>
            </div>
        </div>

        <ul>
            <User
                v-for="(user, index) in sortedUsers"
                :key="index"
                :user="user"
            />
        </ul>
    </div>
</template>

<script>
import User from "./User.vue";

import users from "@/data/users.js";
export default {
    components: {
        User,
    },
    data() {
        return {
            users,
            sortCriteria: "",
        };
    },
    methods: {
        sort_by(users, sortProp) {
            return users.sort(function (a, b) {
                if (a[sortProp] > b[sortProp]) {
                    return 1;
                }
                if (a[sortProp] < b[sortProp]) {
                    return -1;
                }
                return 0;
            });
        },
    },
    computed: {
        sortedUsers() {
            if (!this.sortCriteria) {
                this.sortCriteria == "created_at";
            }
            return this.sort_by(this.users, this.sortCriteria);
        },
        userProperties() {
            let arr = [];
            for (let prop in this.users[0]) {
                arr.push(prop);
            }
            return arr;
        },
    },
};
</script>

<style scoped>
h2 {
    margin: 10px 0 0;
    padding: 1rem;
}
ul {
    list-style-type: none;
    padding: 0;
}
ul li {
    display: block;
}
li {
    display: inline-block;
    margin: 0 10px;
}
.radio-btns {
    padding: 1rem;
}
.radio-btn-filter {
    display: inline-block;
    padding-top: 0.5rem;
    padding-right: 0.5rem;
}
</style>