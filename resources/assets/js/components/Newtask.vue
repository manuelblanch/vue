<template>
    <div class="new">
        <button v-on:click="toggleText()">ToggleText</button>
        <p v-if="showText">{{ text }}</p>
        <p>{{ reverseText }}</p>
        <hr />
        <ul>
            <li v-for="user in users" v-on:click="showUser()">
                {{ user }}
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                text: '',
                showText: false,
                users: ['Task1', 'Task2', 'Task3']
            }
        },
        methods: {
            toggleText() {
                this.showText = !this.showText;
            },
            showUser(user) {
                console.log(user);
            }
        }
    }
</script>
