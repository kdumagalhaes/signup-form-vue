<template>
    <Input
        placeholder="um"
        type="name"
        autofocus
        :style="{ marginBottom: '100px' }"
    />
    <Input placeholder="dois" type="name" :style="{ marginBottom: '20px' }" />
    <Input placeholder="tres" type="name" />
</template>

<script>
// atoms
import { Input } from '@/components/atoms'

export default {
    name: 'App',
    components: {
        Input,
    },
}
</script>
