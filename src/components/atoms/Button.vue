<template>
    <button class="button-tag" :type="type">{{ text }}</button>
</template>

<script>
export default {
    props: {
        text: String,
        type: String,
    },
}
</script>

<style lang="scss" scoped>
.button-tag {
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
    margin-bottom: 15px;

    &:hover {
        box-shadow: 0px 0px 0px 0px rgb(43, 166, 113);
        transform: translateY(4px);
    }
}

@media only screen and (max-width: $mobile) {
    .button-tag {
        font-size: 0.8rem;
    }
}
</style>
