<template>
    <TermsAndServicesWarning
        text="By clicking the button, you are agreeing to our "
        textLink="Terms & Services"
        urlLink="#"
    />
</template>

<script>
// atoms
import { TermsAndServicesWarning } from '@/components/atoms'

export default {
    name: 'App',
    components: {
        TermsAndServicesWarning,
    },
}
</script>
