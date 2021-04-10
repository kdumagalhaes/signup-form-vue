<template>
    <input class="input-tag" :placeholder="placeholder" :type="type" />
</template>

<script>
export default {
    props: {
        placeholder: String,
        type: String,
    },
}
</script>

<style lang="scss" scoped>
.input-tag {
    width: 100%;
    border: 1px solid $neutral-grayish-blue;
    height: 50px;
    border-radius: 5px;
    padding: 0 25px;
    margin-bottom: 20px;
    font-weight: $semi-bold;

    &:focus {
        border: 1px solid $neutral-dark-blue;
    }
}
</style>
