<script setup>
import { useLayout } from '@/layout/composables/layout';
import AppConfigurator from '@/layout/AppConfigurator.vue';

const { toggleDarkMode, isDarkTheme } = useLayout();
</script>

<template>
    <div class="fixed flex gap-4 top-8 right-8">
        <Button :icon="{ 'pi pi-moon': isDarkTheme, 'pi pi-sun': !isDarkTheme }" rounded severity="secondary" type="button" @click="toggleDarkMode"></Button>
        <div class="relative">
            <Button
                v-styleclass="{ selector: '@next', enterFromClass: 'hidden', enterActiveClass: 'animate-scalein', leaveToClass: 'hidden', leaveActiveClass: 'animate-fadeout', hideOnOutsideClick: true }"
                icon="pi pi-palette"
                rounded
                type="button"
            />
            <AppConfigurator />
        </div>
    </div>
</template>
