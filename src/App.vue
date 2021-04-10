<template>
    <div class="app">
        <MainTemplate />
    </div>
</template>

<script>
// templates
import { MainTemplate } from '@/components/templates'

export default {
    name: 'App',
    components: {
        MainTemplate,
    },
}
</script>

<style lang="scss" scoped>
.app {
    width: 100%;
    max-width: $desktop;
    background-color: $primary-red;
    padding: 0 20px 0 20px;
    background-image: url('~@/assets/img/bg-intro-desktop.png');
}
</style>
