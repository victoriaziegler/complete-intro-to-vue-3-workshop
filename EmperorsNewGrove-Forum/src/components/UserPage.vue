<script>
export default {
    data: () => ({
        userList: []
    }),
    methods: {
        async fetchUsers() {
            this.userList = await fetch('https://jsonplaceholder.typicode.com/users').then(response => response.json())
        }
    }
}
</script>

<template>
    <h1>Users</h1>
    <button @click="fetchUsers">Fetch Users</button>
    <div class="user-grid">
        <ul v-for="user in userList" :key="`user-${user.id}`">
            <li class="user-item">{{ user.name }}: {{ user.company.name }}</li>
        </ul>
    </div>
</template>

<style>
.user-grid {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    border: 5px dotted palevioletred
}

.user-item {
    padding: 10px;
    border: 1px solid black;
}
</style>