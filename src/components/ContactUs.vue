<template>
    <section class="contact-us">
        <h3 class="contact-us__title section-name">Contact Us</h3>
        <div class="contact-us__container">
            <div class="contact-us__top-inputs">
                <div class="contact-us__block">
                    <label for="first">First Name *</label>
                    <br>
                    <my-input id="first" class="elem" placeholder="Enter your First name"></my-input>
                </div>
                <div class="contact-us__block">
                    <label for="second">Last Name *</label>
                    <br>
                    <my-input id="second" class="elem" placeholder="Enter your Last name"></my-input>
                </div>
                <div class="contact-us__block">
                    <label for="third">Company *</label>
                    <br>
                    <my-input id="third" class="elem" placeholder="Enter your company"></my-input>
                </div>
                <div class="contact-us__block">
                    <label for="fourth">Email *</label>
                    <br>
                    <my-input id="fourth" class="elem" placeholder="Enter Your Email"></my-input>
                </div>
            </div>
            <div class="contact-us__bottom-inputs">
                <div class="contact-us__block">
                    <label for="fifth">Job Title *</label>
                    <br>
                    <my-input id="fifth" class="elem" placeholder="Enter job title"></my-input>
                </div>
                <div class="contact-us__block">
                    <label for="sixth">Country</label>
                    <br>
                    <my-input id="sixth" class="elem" placeholder="Enter Your Country"></my-input>
                </div>
                <div class="contact-us__block">
                    <label for="seventh">State *</label>
                    <br>
                    <my-input id="seventh" class="elem" placeholder="Enter your State"></my-input>
                </div>
                <div class="contact-us__block">
                    <label for="eighth">Zip code *</label>
                    <br>
                    <my-input id="eighth" class="elem" placeholder="Enter Your Zip Code"></my-input>
                </div>
            </div>
            <blue-btn class="contact-us__btn">Submit</blue-btn>
        </div>
    </section>
</template>

<script>

export default {
}

</script>

<style lang="scss" scoped>
$dark: #3D3D3D;
$grey: #808080;

.contact-us {
    background: white;
    margin-top: 40px;
    padding-bottom: 59px;

    &__title {
        text-align: center;
        padding: 44px 0px;
    }

    &__container {
        max-width: 1155px;
        margin: auto;
    }

    &__top-inputs,
    &__bottom-inputs {
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }

    &__bottom-inputs {
        padding-top: 15px;
    }

    &__btn {
        margin-top: 50px !important;
    }

}

.contact-us__btn {
    padding-top: 50px;
    display: block;
    width: 200px;
    text-align: center;
    height: 40px;
    margin: auto;
    margin-top: 50px !important;
}

@media(max-width:1250px) {
    .contact-us {

        &__block {
            padding: 15px 15px;
        }

        &__block input {
            width: 550px;
        }

        &__block:nth-child(4) {
            padding-top: 20px;
        }

        &__top-inputs,
        &__bottom-inputs {
            justify-content: center;
            padding: 0;
        }

    }
}

@media(max-width:600px) {
    .contact-us__block input {
        width: 304px;
    }
}
</style>
