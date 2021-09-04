<template>
    <div class="list-members">
        <ul>
            <li v-for="member in members" :key="member.id" class="border border-1 border-indigo-600 m-2 p-2">
                <h1>{{member.id}}</h1>
                <p>{{member.name}}</p>
                <p>{{member.pass}}</p>
            </li>
        </ul>
    </div>
</template>

<script>
    export default {
        name: 'ListMembers',
        props: {
            members: {
                type: Array,
                required: true
            }
        }
        // data: function(){
        //     return {
        //         members: [
        //             {id:1, name:'John', pass:'123'},
        //             {id:2, name:'Mary', pass:'456'},
        //             {id:3, name:'Peter', pass:'789'},
        //             {id:4, name:'John', pass:'123'},
        //         ],
        //     };
        // },
    }
</script>