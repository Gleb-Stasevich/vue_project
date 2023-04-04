<template>
    <footer class="footer">
        <span class="footer__text">©2015-2022 Success Craft</span>
    </footer>
</template>

<script>

export default {
};

</script>

<style lang="scss" scoped>
$dark: #3D3D3D;

.footer {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 125px;
    background: $dark;

    &__text {
        line-height: 16px;
        color: #FFFFFF;
    }
}
</style>