<template>
    <p class="terms-services-warning">
        {{ text }}
        <a :href="urlLink" class="terms-services-warning__link">{{
            textLink
        }}</a>
    </p>
</template>

<script>
export default {
    props: {
        text: String,
        textLink: String,
        urlLink: String,
    },
}
</script>

<style lang="scss" scoped>
.terms-services-warning {
    font-size: 0.7rem;
    color: $neutral-grayish-blue;
    font-weight: $semi-bold;

    .terms-services-warning__link {
        font-weight: $bold;
        color: $primary-red;
        text-decoration: none;
        transition: opacity 0.4s;

        &:hover {
            opacity: 0.5;
        }
    }
}
</style>
