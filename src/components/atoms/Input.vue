<template>
    <input
        class="input-tag--error"
        :placeholder="placeholder"
        :type="type"
        :value="modelValue"
        @input="$emit('update:modelValue', $event.target.value)"
    />
</template>

<script>
export default {
    props: {
        placeholder: String,
        type: String,
        modelValue: String,
    },
}
</script>

<style lang="scss" scoped>
.input-tag,
.input-tag--error {
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

.input-tag--error {
    border: 2px solid $primary-red;
    background-image: url('~@/assets/img/icon-error.svg');
    background-position: right;
    background-position-x: 95%;
    background-repeat: no-repeat;

    &:focus {
        border: 2px solid $primary-red;
    }
}
</style>
