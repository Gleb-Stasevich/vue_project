<template>
    <section class="frameworks">
        <h3 class="frameworks__title section-name">Frameworks</h3>
        <div v-for="framework in frameworks" :key="framework.id" class="frameworks__list">
            <div class="framework">
                <div class="framework__image">
                    <img :key="framework.id" :src="framework.img" alt="">
                </div>
                <div class="framework__description">
                    <div class="framework__name">{{ framework.name }}</div>
                    <div class="framework__text">{{ framework.text }}</div>
                    <div class="framework__btns btns">
                        <blue-btn>Read More</blue-btn>
                        <white-btn>Webinar</white-btn>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: 'my-frameworks',
    props: {
        frameworks: {
            type: Array,
            required: true,
            default: () => []
        }
    },

    mounted() {
        const currentTarget = document.querySelectorAll('.frameworks__list')[1];
        const currentFramework = currentTarget.firstElementChild;
        const currentDescription = currentTarget.querySelector('.framework__description');
        currentDescription.style.paddingLeft = 11 + 'px';
        currentFramework.prepend(currentDescription);
    }
}

</script>

<style lang="scss" scoped>
$dark: #3D3D3D;
$grey: #808080;

.frameworks {

    &__title {
        text-align: center;
        padding: 45px 0px;
    }

    &__list {
        max-width: 1196px;
        margin: auto;
        background: white;
    }
}

.framework {

    display: flex;
    flex-wrap: wrap;
    justify-content: space-between;
    align-items: flex-start;

    &__image img {
        max-width: 535px;
        width: 100%;
    }

    &__description {
        padding: 23px 0px 27px 0px;
        max-width: 588px;
    }

    &__name {
        font-weight: 700;
        font-size: 24px;
        line-height: 30px;
        color: $dark;
    }

    &__text {
        height: 187px;
        padding-top: 9px;
        font-weight: 400;
        font-size: 16px;
        line-height: 26px;
        color: $grey;
    }

    &__btns {
        padding-top: 29px;
    }
}

.frameworks__list:not(:nth-child(2)) {
    padding-top: 45px;
}

@media(max-width: 1250px) {
    .frameworks {

        &__list {
            margin: auto;
            text-align: center;
        }
    }

    .framework {

        &__image,
        &__description {
            margin: auto;
        }

        &__text {
            height: auto;
            padding: 0px 15px;
        }

        &__btns a {
            margin: auto;
        }
    }

    .framework:first-child {
        padding-top: 45px;
    }
}

@media(max-width: 476px) {

    .framework__btns {
        display: flex;
        flex-direction: column;
    }

    .framework__btns a {
        display: block;
        width: 300px;
        margin: auto;
    }

    .framework__btns a:last-child {
        margin-top: 20px;
    }
}
</style>