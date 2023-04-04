<template>
    <section class="mini-contact">
        <div class="mini-contact__container">
            <div class="mini-contact__block">
                <div class="mini-contact__image">
                    <img src="@/../public/img/contact-1.png" alt="">
                </div>
                <div class="mini-contact__description">
                    <div class="description__title">Setup a Meeting</div>
                    <div class="description__sub-title">Fill out our contact form and<br> have someone get back to you<br>
                        within 24
                        hours.</div>
                    <blue-btn class="description__btn">Schedule a Meeting</blue-btn>
                </div>
            </div>

            <div class="mini-contact__block">
                <div class="mini-contact__image">
                    <img src="@/../public/img/contact-2.png" alt="">
                </div>
                <div class="mini-contact__description">
                    <div class="description__title">Ask a Question</div>
                    <div class="description__sub-title">Have a question? Just fill out<br> our contact us form and we
                        will<br> get
                        back to you.</div>
                    <blue-btn>Ask a Question</blue-btn>
                </div>
            </div>
        </div>
    </section>
</template>

<script>

export default {

};

</script>

<style lang="scss" scoped>
$dark: #3D3D3D;
$grey: #808080;

.mini-contact {

    margin-top: 61px;
    background-color: white;

    &__container {
        max-width: 1216px;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
        margin: auto;
    }

    &__block {
        max-width: 608px;
        display: flex;
        flex-wrap: wrap;
        align-items: center;

    }

    &__image img {
        max-width: 345px;
        width: 100%;
        height: 227px;
    }

    &__description {
        padding-left: 20px;

    }

}

.description {

    &__title {
        font-weight: 700;
        font-size: 24px;
        line-height: 30px;
        color: $dark;
    }

    &__sub-title {
        padding-top: 9px;
        padding-bottom: 21px;
        line-height: 26px;
        color: $grey;
    }

    &__btn {
        padding: 11px 25px 9px 31px !important;
    }
}

@media (max-width: 1250px) {
    .mini-contact {

        &__block {
            margin: auto;
            width: 600px;
        }

        &__block:last-child {
            margin-top: 20px;
        }

    }
}

@media (max-width: 650px) {
    .mini-contact {
        &__description {
            padding-left: 0;
            text-align: center;
        }

        &__container {
            padding-top: 40px;
        }

        &__block {
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        &__block:last-child {
            margin-top: 40px;
            padding-bottom: 40px;
        }

    }
}

.description {

    &__title {
        padding-top: 20px;
    }

}
</style>