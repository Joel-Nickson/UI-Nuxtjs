<template>
    <form @submit="onSubmit">
        <div>
            <label for="name">Name</label>
            <input v-model="name" id="name" name="name" placeholder="Enter Name">
        </div>
        <div>
            <label for="password">Password</label>
            <input v-model="password" id="password" name="password" placeholder="Enter Password">
        </div>
        <button type="submit" class="bg-indigo-600 shadow-sm p-4 rounded-sm">Add</button>
    </form>
</template>

<script lang='ts'>
import Vue from 'vue'
export default Vue.extend({
    data() {
        return {
            name: '',
            password: ''
        };
    },
    methods: {
        async onSubmit(event: { preventDefault: () => void; }) { 
            event.preventDefault();
            const result = await this.$axios.$post('http://localhost:8000/api/', {
                name: this.name,
                pass: this.password
            });

        }
    }
});

</script>