<template>
    <section class="welcome">
        <div class="welcome__container">
            <h1 class="welcome__title">Welcome to Test Page</h1>
            <h2 class="welcome__sub-title">Front-end developer</h2>
        </div>
    </section>
</template>

<script>

export default {
    name: 'my-welcome'
};

</script>

<style lang="scss" scoped>
.welcome {

    &__container {
        display: flex;
        flex-wrap: wrap;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        background-image: url('@/../public/img/welcome-backgrond.png');
        background-attachment: fixed;
        background-repeat: no-repeat;
        height: 662px;
    }

    &__title {
        font-weight: 700;
        font-size: 70px;
        line-height: 88px;
        color: #FFFFFF;
        text-shadow: 0px 5px 5px rgba(0, 0, 0, 0.15);
    }

    &__sub-title {
        font-size: 36px;
        line-height: 45px;
        color: #FFFFFF;
        text-shadow: 0px 5px 5px rgba(0, 0, 0, 0.15);
    }
}

@media (max-width:768px) {
    .welcome {

        &__title {
            font-size: 50px;
        }

        &__sub-title {
            font-size: 30px;
        }
    }

}

@media (max-width:576px) {
    .welcome {


        &__title {
            font-size: 40px;
        }

        &__sub-title {
            font-size: 25px;
        }
    }
}

@media (max-width:476px) {
    .welcome {

        &__container {}

        &__title {
            font-size: 25px;
        }

        &__sub-title {
            font-size: 20px;
        }
    }
}
</style>