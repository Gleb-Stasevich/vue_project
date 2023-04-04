<template>
    <section class="applications">
        <h3 class="applications__title section-name">Applications</h3>
        <div class="applications__container">
            <div class="applications__top">
                <div class="application" v-for="application in applications" :key="application.id">
                    <div class="application__content" v-if="application.id <= 4">
                        <div class="application__image">
                            <img :src="application.img" alt="">
                        </div>
                        <div class="application__app-number">
                            <span>{{ application.name }}</span>
                        </div>
                    </div>
                </div>
            </div>
            <div class="applications__bottom">
                <div class="application" v-for="application in applications" :key="application.id">
                    <div class="application__content" v-if="application.id > 4">
                        <div class="application__image">
                            <img :src="application.img" alt="">
                        </div>
                        <div class="application__app-number">
                            <span>{{ application.name }}</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {
    props: {
        applications: {
            type: Array,
            required: true,
            default: () => []
        }
    },
    mounted() {
        const applications = document.querySelectorAll('.application');
        for (let application of applications) {
            if (!application.querySelector('.application__content')) {
                application.remove();
            }
        }
    }
};

</script>

<style lang="scss" scoped>
.applications {

    padding-bottom: 60px;

    &__title {
        padding: 45px 0px;
        text-align: center;
    }

    &__container {
        max-width: 1196px;
        margin: auto;
    }

    &__top,
    &__bottom {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
    }

    &__bottom {
        padding-top: 83px;
    }
}

.application {

    width: 227px;
    height: 124px;
    margin: 0px 15px;

    &__app-number {
        display: flex;
        flex-wrap: wrap;
        justify-content: center;
        align-items: center;
        height: 38px;
        background-color: #3D3D3D;
        color: white;
        line-height: 20px;

    }
}

@media (max-width: 1044px) {
    .application:nth-child(4) {
        margin-top: 80px;
    }
}

@media (max-width: 787px) {

    .application:nth-child(3) {
        margin-top: 80px;
    }

    .application:nth-child(4) {
        margin-top: 80px;
    }
}

@media (max-width: 530px) {
    .application {
        margin: auto;
        width: auto;
        height: auto;
        padding: 0px 15px;
        margin-top: 20px;
        margin-bottom: 20px;

        &:nth-child(3) {
            margin-top: 20px !important;
        }

        &:nth-child(4) {
            margin-top: 20px !important;
        }
    }

    .applications__bottom {
        padding-top: 0;
    }
}
</style>