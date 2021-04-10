<template>
    <div class="promo-cta">
        <h2 class="promo-cta__text">
            <strong>{{ strong }}</strong
            >{{ text }}
        </h2>
    </div>
</template>

<script>
export default {
    props: {
        text: String,
        strong: String,
    },
}
</script>

<style lang="scss" scoped>
.promo-cta {
    width: 100%;
    background-color: $accent-blue;
    height: 55px;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: $border-radius;
    box-shadow: 0px 8px 0px 0px rgba(0, 0, 0, 0.253);
    font-size: 0.7rem;
    margin-bottom: 30px;

    .promo-cta__text {
        font-weight: $regular;
        color: #fff;
    }
}
</style>
