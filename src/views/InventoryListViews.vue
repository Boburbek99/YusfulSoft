<template>
    <div class="table-block">
        <Table :inventoryData="stores.inventories" />
    </div>
</template>
<script setup>

import { onBeforeMount, ref } from 'vue';
import Table from '@/components/Table.vue';
import { useInventoryStore } from '@/stores/inventory';
let stores = useInventoryStore()

onBeforeMount(async () => {
    await stores.fetchInventories();
});

</script>
<style scoped></style>