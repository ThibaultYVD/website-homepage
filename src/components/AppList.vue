<template>
    <ul class="list-container">
        <li v-for="item in items" :key="item.name" class="list-item">
            <a :href="item.appUrl" target="_blank">
                <img :src="item.imageUrl" alt="Logo" class="item-logo" />
                <span>{{ item.name }}</span>
            </a>
            <label class="administrator-tag" v-if="item.forAdministrator">Admin</label>
            <a v-if="item.githubUrl" :href="item.githubUrl" target="_blank">
                <i class="fa-brands fa-github"></i>
            </a>
        </li>
    </ul>
</template>

<script>
export default {
    name: "AppList",
    props: {
        items: {
            type: Array,
            required: true,
        },
    },
};

</script>

<style scoped>
li {
    display: flex;
    justify-content: space-between;
}

.list-container {
    list-style: none;
    display: flex;
    flex-direction: column;
    gap: 10px;
    padding: 0;
    margin: 0;
}

.list-item {
    display: flex;
    align-items: center;
    gap: 10px;
    box-shadow: 0px 2px 5px 0px rgba(0, 0, 0, 0.2);
    border-radius: 10px;
    padding: 4px 8px;
}

.list-item a {
    display: flex;
    align-items: center;
    gap: 4px;
    text-decoration: none;
    color: inherit;
    font-size: 1rem;
    border-radius: 5px;
    padding: 4px 8px;

}

span {
    font-weight: bold;
    border-bottom: 1px lightgrey solid;
}

i {
    font-size: 25px;
}

.item-logo {
    width: 20px;
    height: 20px;
    object-fit: contain;
    border-radius: 5px;
}

.administrator-tag {
    background-color: darksalmon;
    color: black;
    font-style: italic;
    font-size: 12px;
    padding: 2px 5px;
    border-radius: 5px;
    float: right;
}

.list-item a:hover {
    background-color: rgb(235, 235, 235);

}
</style>