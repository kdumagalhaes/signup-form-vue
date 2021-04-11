<template>
    <form class="free-trial-form" @submit.prevent="checkForm" novalidate>
        <input
            class="free-trial-form__input"
            placeholder="First Name"
            type="text"
            name="firstName"
            :model="firstName"
            v-bind:class="[
                nameIsEmpty
                    ? 'free-trial-form__input--error'
                    : 'free-trial-form__input',
            ]"
            autofocus
        />
        <p v-if="nameIsEmpty" class="free-trial-form__error-message">
            {{ errors[0] }}
        </p>

        <input
            class="free-trial-form__input"
            placeholder="Last Name"
            type="text"
            name="lastName"
            :model="lastName"
        />
        <p v-if="lastNameIsEmpty" class="free-trial-form__error-message">
            {{ errors[1] }}
        </p>

        <input
            class="free-trial-form__input"
            placeholder="Email Address"
            type="email"
            name="email"
            :model="email"
            v-bind:class="[
                emailIsNotValid
                    ? 'free-trial-form__input--error'
                    : 'free-trial-form__input',
            ]"
        />
        <p v-if="emailIsNotValid" class="free-trial-form__error-message">
            {{ errors[2] }}
        </p>

        <input
            class="free-trial-form__input"
            placeholder="Password"
            type="password"
            name="password"
            :model="password"
        />
        <p v-if="passwordIsEmpty" class="free-trial-form__error-message">
            {{ errors[3] }}
        </p>

        <button class="free-trial-form__button">Claim your free trial</button>
        <TermsAndServicesWarning
            text="By clicking the button, you are agreeing to our "
            textLink="Terms and Services"
            urlLink="#"
        />
    </form>
</template>

<script>
// atoms
import { TermsAndServicesWarning } from '@/components/atoms'

export default {
    components: {
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
            firstName: null,
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

    methods: {
        checkForm() {
            if (!this.validEmail(this.email)) {
                this.emailIsNotValid = true
            }
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

.free-trial-form__input,
.free-trial-form__input--error {
    width: 100%;
    border: 1px solid $neutral-grayish-blue;
    height: 50px;
    border-radius: $border-radius;
    padding: 0 25px;
    font-weight: $semi-bold;
    margin-top: 20px;

    &:focus {
        border: 1px solid $neutral-dark-blue;
    }
}

.free-trial-form__input--error {
    border: 2px solid $primary-red;
    background-image: url('~@/assets/img/icon-error.svg');
    background-position: right;
    background-position-x: 95%;
    background-repeat: no-repeat;

    &:focus {
        border: 2px solid $primary-red;
    }
}

.free-trial-form__button {
    text-transform: uppercase;
    width: 100%;
    height: 50px;
    border-radius: $border-radius;
    border: none;
    background-color: $primary-green;
    box-shadow: 0px 4px 0px 0px rgb(43, 166, 113);
    transition: box-shadow 0.1s ease 0s, transform 0.1s ease 0s;
    letter-spacing: 1px;
    font-size: 1.1rem;
    font-weight: $semi-bold;
    color: #fff;
    text-align: center;
    margin: 20px 0 15px 0;

    &:hover {
        box-shadow: 0px 0px 0px 0px rgb(43, 166, 113);
        transform: translateY(4px);
    }
}

@media only screen and (max-width: $mobile) {
    .free-trial-form__button {
        font-size: 0.8rem;
    }
}
</style>
