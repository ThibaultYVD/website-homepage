<template>
    <ul class="list-container">
        <li v-for="item in items" :key="item.name" class="list-item">
            <a :href="item.url" target="_blank">
                <img :src="item.imageUrl" alt="Logo" class="item-logo" />
                <span>{{ item.name }}</span>
            </a>
        </li>
    </ul>
</template>

<script>
export default {
    name: "QuicklinksList",
    props: {
        items: {
            type: Array,
            required: true,
        },
    },
};
</script>

<style scoped>
.list-container {
    list-style: none;
    padding: 0;
    margin: 0;
}

.list-item {
    display: flex;
    align-items: center;
    margin-bottom: 10px;
    border-radius: 10px;
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.25);
    padding: 5px;
}

.list-item a {
    display: flex;
    align-items: center;
    gap: 10px;
    text-decoration: none;
    color: inherit;
    font-size: 1rem;
    border-radius: 10px;
    box-shadow: 0px 0px 5px 0px rgba(0, 0, 0, 0.5);
}

.item-logo {
    width: 30px;
    height: 30px;
    object-fit: contain;
    border-radius: 5px;
}
</style>