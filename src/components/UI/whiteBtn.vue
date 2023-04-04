<template>
    <a class="white-btn" href="#">
        <slot></slot>
    </a>
</template>

<script>

export default {
    name: 'white-btn'
};

</script>

<style lang="scss" scoped>
$dark: #3D3D3D;

a {
    margin-left: 25px;
    transition: all 0.4s ease;
}

a:hover {
    background: darkblue;
    color: white;
    border: 1px solid darkblue;
    transition: all 0.4s ease;
}

.white-btn {
    padding: 10px 60px;
    border: 1px solid #71A3FF;
    border-radius: 10px;
    color: $dark;
}
</style>