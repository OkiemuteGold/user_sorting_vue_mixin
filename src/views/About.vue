<template>
    <div class="about">
        <h1>Understanding Vue Mixins</h1>
        <p>
            Sorting users by name, age, status, and date created. Using mixins,
            and returning active and inactive users.
        </p>

        <h3>Modifications:</h3>

        <ul>
            <li>
                Users' data stored in users.js in the data folder and imported
                to components where needed.
            </li>
            <li>Other (CSS) styles</li>
        </ul>

        <p>
            <span class="subtitle">Link: </span>
            <a
                href="https://medium.com/irrelevant-code/understanding-vue-mixins-and-some-practice-with-a-vue-cli-project-1dbb3c414f4d"
            >
                Understanding Vue Mixins, and some practice with a vue-cli
                project
            </a>
            <br />
            <span class="subtitle">Author: </span>
            <span>Evan Winston.</span>
        </p>
    </div>
</template>

<style scoped>
.about {
    padding: 20px 50px;
    max-width: 700px;
    margin: auto;
    text-align: left;
}
h1 {
    margin-bottom: 20px;
    text-align: center;
}

p {
    line-height: 30px;
    margin-bottom: 20px;
}
p a {
    text-decoration: none;
    font-size: 14px;
    transition: 0.4s ease;
}
p a:hover {
    text-decoration: underline;
}

p span {
    font-size: 14px;
}

.subtitle {
    font-weight: 600;
    font-size: 16px;
}

ul {
    margin: 20px auto;
    padding: 0 20px 0 30px;
}
ul li {
    margin-bottom: 20px;
    list-style-type: circle;
}
ul li::marker {
    color: #008000;
}
</style>
