<template>
    <form class="free-trial-form" @submit.prevent="checkForm" novalidate>
        <Input
            placeholder="First Name"
            type="text"
            :model-value="name"
            @update:model-value="name = $event"
            autofocus
        />
        <p v-if="nameIsEmpty" class="free-trial-form__error-message">
            {{ errors[0] }}
        </p>

        <Input
            placeholder="Last Name"
            type="text"
            :model-value="lastName"
            @update:model-value="lastName = $event"
        />
        <p v-if="lastNameIsEmpty" class="free-trial-form__error-message">
            {{ errors[1] }}
        </p>

        <Input
            placeholder="Email Address"
            type="email"
            :model-value="email"
            @update:model-value="email = $event"
        />
        <p v-if="emailIsNotValid" class="free-trial-form__error-message">
            {{ errors[2] }}
        </p>

        <Input
            placeholder="Password"
            type="password"
            :model-value="password"
            @update:model-value="password = $event"
        />
        <p v-if="passwordIsEmpty" class="free-trial-form__error-message">
            {{ errors[3] }}
        </p>

        <Button
            disabled="!formIsValid"
            text="Claim your free trial"
            type="submit"
        />
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

    data() {
        return {
            errors: [
                'First Name cannot be empty',
                'Last Name cannot be empty',
                'Looks like this is not an email',
                'Password cannot be empty',
            ],
            name: null,
            lastName: null,
            email: null,
            password: null,
            emailIsNotValid: false,
            nameIsEmpty: false,
            lastNameIsEmpty: false,
            passwordIsEmpty: false,
            regex: /^(([^<>()[\]\\.,;:\s@"]+(\.[^<>()[\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,}))$/,
        }
    },

    // passar valor pro input original informando pra mudar o CSS
    // apresentar as mensagens de erro quando bater com as regras

    methods: {
        checkForm() {
            if (!this.validEmail(this.email)) {
                this.emailIsNotValid = true
            }
            if (!this.nameIsValid) {
                this.nameIsEmpty = true
            }
            // if (this.lastName === null) {
            //     this.lastNameIsEmpty = true
            // }
            // if (this.password === null) {
            //     this.passwordIsEmpty = true
            // }
        },
        validEmail(email) {
            return this.regex.test(email)
        },
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

    .free-trial-form__error-message {
        text-align: right;
        font-size: 0.6rem;
        margin-top: 5px;
        font-style: italic;
        color: $primary-red;
        font-weight: $semi-bold;
    }
}
</style>
