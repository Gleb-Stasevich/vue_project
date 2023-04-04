<template>
    <a class="blue-btn" href="#">
        <slot></slot>
    </a>
</template>

<script>

export default {
    name: 'blue-btn'
};

</script>

<style scoped>
a {}

a:hover {
    background: darkblue;
    transition: all 0.4s ease;
}

.blue-btn {
    padding: 10px 60px;
    background: #71A3FF;
    border-radius: 10px;
    color: white;
    transition: all 0.4s ease;
}
</style>