<template>
    <ul class="list-container">
        <li v-for="item in items" :key="item.name" class="list-item">
            <div class="item-content">
                <a :href="item.appUrl" target="_blank" class="main-link">
                    <div class="logo-container">
                        <img v-if="item.imageUrl !== 'null'" :src="item.imageUrl" :alt="item.name + ' logo'"
                            class="item-logo" />
                        <i v-else class="fa-solid fa-cube placeholder-icon"></i>
                    </div>
                    <div class="item-info">
                        <span class="item-name">{{ item.name }}</span>
                        <div class="tags-container">
                            <span class="tag administrator" v-if="item.forAdministrator">
                                <i class="fa-solid fa-lock"></i>Admin
                            </span>
                            <span class="tag limited" v-if="item.limited">
                                <i class="fa-solid fa-user-group"></i>Limited
                            </span>
                            <span class="tag free-to-use" v-if="item.freeToUse">
                                <i class="fa-solid fa-leaf"></i>Free
                            </span>
                        </div>
                    </div>
                </a>
            </div>
            <div class="actions">
                <a v-if="item.githubUrl" :href="item.githubUrl" target="_blank" class="github-link"
                    title="View on GitHub">
                    <i class="fa-brands fa-github"></i>
                </a>
                <a :href="item.appUrl" target="_blank" class="launch-link" title="Open application">
                    <i class="fa-solid fa-arrow-up-right-from-square"></i>
                </a>
            </div>
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

@import "../assets/styles/components/list.css";

</style>
