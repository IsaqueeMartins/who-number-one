<script setup>
import { ref, onMounted } from 'vue';

onMounted(() => {
    users.value = [
        { rank: 1, country: 'Brazil', user: 'Isaque Martins', rating: 2998 },
        { rank: 2, country: 'Brazil', user: 'Supi', rating: 2900 },
        { rank: 3, country: 'Brazil', user: 'Krikor Mekhitarian', rating: 2898 },
        { rank: 4, country: 'Norway', user: 'Magnus Carlsen', rating: 2891 },
        { rank: 5, country: 'United States', user: 'Hikaru', rating: 2887 }
    ];
});

const users = ref()
const columns = [
    { field: 'rank', header: 'Rank' },
    { field: 'country', header: 'Country' },
    { field: 'user', header: 'User' },
    { field: 'rating', header: 'Rating' }
];

</script>


<template>
    <div class="card">
        <DataTable :value="users" class="min-width: 20rem max-width: 30rem flex justify-center mt-10 rounded-xs">
            <Column v-for="col of columns" :key="col.field" :field="col.field" :header="col.header"></Column>
        </DataTable>
    </div>
</template>

