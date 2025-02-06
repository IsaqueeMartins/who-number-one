<script setup>
import { ref } from "vue";

const items = ref(Array.from({ length: 1000 }, (_, i) => ({ label: `Item #${i}`, value: i })));
const selectedItem = ref();
const filteredItems = ref();
const searchItems = (event) => {
    //in a real application, make a request to a remote url with the query and return filtered results, for demo we filter at client side
    let query = event.query;
    let _filteredItems = [];

    for (let i = 0; i < items.value.length; i++) {
        let item = items.value[i];

        if (item.label.toLowerCase().indexOf(query.toLowerCase()) === 0) {
            _filteredItems.push(item);
        }
    }

    filteredItems.value = _filteredItems;
};
</script>


<template>
    <div class="card flex justify-center">
        <IftaLabel>
            <AutoComplete v-model="selectedItem" :suggestions="filteredItems" @complete="searchItems"
                :virtualScrollerOptions="{ itemSize: 38 }" optionLabel="label" placeholder="Selecione um modo de jogo"
                dropdown />
            <label for="modos">Modos:</label>
        </IftaLabel>
    </div>
</template>
