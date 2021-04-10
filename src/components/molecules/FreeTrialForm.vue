<template>
    <form class="free-trial-form">
        <Input placeholder="First Name" type="text" />
        <Input placeholder="Last Name" type="text" />
        <Input placeholder="Email Address" type="email" />
        <Input placeholder="Password" type="password" />
        <Button text="Claim your free trial" />
        <TermsAndServicesWarning
            text="By clicking the button, you are agreeing to our "
            textLink="Terms and Services"
            urlLink="#"
        />
    </form>
</template>

<script>
// atoms
import { Input, Button, TermsAndServicesWarning } from '@/components/atoms'

export default {
    components: {
        Input,
        Button,
        TermsAndServicesWarning,
    },
}
</script>

<style lang="scss" scoped>
.free-trial-form {
    width: 100%;
    max-width: 500px;
    background-color: #fff;
    padding: 35px;
    border-radius: $border-radius;
    box-shadow: 0px 8px 0px 0px rgba(0, 0, 0, 0.253);
}
</style>
