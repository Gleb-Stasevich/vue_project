<template>
    <section class="about-us">
        <div class="about-us__container">
            <div class="about-us__description">
                <h3 class="about-us__title section-name">About us</h3>
                <span class="about-us__sub-title">Lorem Ipsum is simply dummy text of the printing and typesetting industry.
                    Lorem
                    Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a
                    galley of
                    type and scrambled it to make a type specimen book. It has survived not only five centuries, but also
                    the leap
                    into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the
                    release
                    of Letraset.
                </span>
                <div class="btns">
                    <blue-btn>Read more</blue-btn>
                    <white-btn>Contact us</white-btn>
                </div>
            </div>
            <div class="about-us__video">
                <iframe width="532" height="301" src="https://www.youtube.com/embed/Upex8hM6wRs"
                    title="YouTube video player" frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share"
                    allowfullscreen></iframe>
            </div>
        </div>
    </section>
</template>

<script>

export default {
    name: 'my-about-us'
};

</script>

<style lang="scss" scoped>
$grey: #808080;

.about-us {
    background-image: url('@/../public/img/about_us-background.png');
    background-repeat: no-repeat;
    background-color: white;

    &__container {
        padding: 90px 0px;
        max-width: 1167px;
        margin: auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
    }

    &__description {
        max-width: 595px;

    }

    &__sub-title {
        padding-top: 16px;
        font-size: 16px;
        line-height: 26px;
        color: $grey;
    }
}

@media(max-width:1250px) {
    .about-us {

        &__container {
            flex-direction: column;
        }

        &__description {
            text-align: center;
            margin: auto;
        }

        &__title {}

        &__sub-title {
            display: block;
            padding-top: 20px;
        }

        &__video {
            padding-top: 40px;

            iframe {
                width: 620px;
                height: 301px;
            }
        }
    }

    .btns {
        display: block;
    }

}

@media(max-width:768px) {
    .about-us__video iframe {
        width: 520px;
        height: 290px;
    }
}

@media(max-width:576px) {
    .about-us__video iframe {
        width: 304px;
        height: 181px;
    }
}

@media(max-width:476px) {

    .btns>a {
        display: block;
        margin: auto;
        width: 300px;
    }

    .btns>a:last-child {
        margin-top: 20px;
    }
}
</style>