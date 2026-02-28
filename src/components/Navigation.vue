<template>
    <header class="site-header">
        <div class="club-banner">
            <h1>Entente Sportive Thaon-Cheniménil</h1>
        </div>

        <div class="nav-wrapper card">
            <Menubar :model="items">
                <template #item="{ item, props, hasSubmenu }">
                    <router-link v-if="item.route" v-slot="{ href, navigate }" :to="item.route" custom>
                        <a v-ripple :href="href" v-bind="props.action" @click="navigate">
                            <span :class="item.icon" />
                            <span>{{ item.label }}</span>
                        </a>
                    </router-link>
                    <a v-else v-ripple :href="item.url" :target="item.target" v-bind="props.action">
                        <span :class="item.icon" />
                        <span>{{ item.label }}</span>
                        <span v-if="hasSubmenu" class="pi pi-fw pi-angle-down" />
                    </a>
                </template>
            </Menubar>
        </div>
    </header>
</template>

<script setup>
import { ref } from "vue";

const items = ref([
    {
        label: 'Accueil',
        icon: 'pi pi-home',
        route: '/'
    },
    {
        label: 'Equipes',
        icon: 'pi pi-users',
        route: '/equipes'
    },
    {
        label: 'Joueurs',
        icon: 'pi pi-user',
        route: '/joueurs'
    },
    {
        label: 'Informations pratiques',
        icon: 'pi pi-info-circle',
        route: '/infos'
    }
]);
</script>

<style scoped>
.site-header {
    background: #31313d;
    color: #ffffff;
}

.club-banner {
    min-height: 120px;
    padding: 1rem clamp(1rem, 3vw, 2rem);
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 1rem;
}

.club-banner h1 {
    margin: 0;
    font-size: clamp(1.35rem, 3vw, 2.45rem);
    line-height: 1.15;
    text-align: center;
}

.nav-wrapper {
    width: 100%;
}

.nav-wrapper :deep(.p-menubar) {
    border: none;
    border-radius: 0;
    background: #31313d;
    justify-content: center;
}

.nav-wrapper :deep(.p-menubar-root-list) {
    gap: 0.5rem;
}

.nav-wrapper :deep(.p-menubar-item-link),
.nav-wrapper :deep(.p-menubar-item-link .p-menubar-item-label),
.nav-wrapper :deep(.p-menubar-item-link .pi) {
    color: #ffffff;
}

.nav-wrapper :deep(.p-menubar-item-link:hover),
.nav-wrapper :deep(.p-menubar-item-link:focus-visible) {
    background: rgba(255, 255, 255, 0.12);
}

@media (max-width: 768px) {
    .club-banner {
        flex-direction: column;
        text-align: center;
    }
}
</style>
