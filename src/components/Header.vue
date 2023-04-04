<template>
    <header>
        <div class="header__container">
            <div @click="checkBurger($event.target)" class="burger">X</div>
            <div class="header__icon">
                <a href="#"><img src="@/../public/img/logo.svg" alt=""></a>
            </div>
            <ul class="nav">
                <li><a name="home">Home</a></li>
                <li><a name="about-us">About us</a></li>
                <li><a name="frameworks">Frameworks</a></li>
                <li><a name="applications">Applications</a></li>
                <li><a name="contact-us">Contact us</a></li>
            </ul>
        </div>
    </header>
</template>

<script>

export default {

    methods: {

        getLinks() {
            const headerLinks = document.querySelector('.nav').querySelectorAll('a');
            for (let link of headerLinks) {
                link.addEventListener('click', () => {
                    this.sendLink(link);
                })
            }
        },
        sendLink(link) {
            this.$emit('scrollToSection', link);
        },
        checkBurger(burger) {
            const nav = document.querySelector('.nav');
            if (nav.classList.contains('open')) {
                nav.classList.remove('open');
            } else {
                nav.classList.add('open');
            };
        }
    },

    mounted() {
        this.getLinks();
    }

}

</script>

<style lang="scss" scoped >
$dark: #3D3D3D;

.header {

    &__container {
        position: fixed;
        background-color: white;
        width: 100%;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
        align-items: center;
        height: 80px;
    }

    &__icon {
        z-index: 6;
        padding-left: 123px;
    }
}

.nav {
    z-index: 5;
    display: flex;
    flex-wrap: wrap;
    align-items: center;

    li {
        padding: 0px 15px;
        text-transform: uppercase;
        font-size: 18px;
        line-height: 21px;
    }

    li:last-child {
        padding-right: 77.86px;
    }

    li>a {
        cursor: pointer;
        color: $dark;
    }
}

.nav.open {
    transform: translateY(0px);
    transition: all 1s ease;
}

.burger {
    z-index: 6;
    cursor: pointer;
    position: absolute;
    top: 29px;
    right: 20px;
    visibility: hidden;
}

@media(max-width: 1100px) {
    .header {

        &__container {
            height: 100px;
            display: flex;
            justify-content: center;
            flex-direction: column;
        }

        &__icon {
            padding: 0;
        }
    }

    .nav {
        margin-top: 20px;

        li:last-child {
            padding-right: 0px;
        }
    }

}

@media(max-width: 768px) {

    .header {

        &__container {
            flex-direction: row;
            height: 80px;
        }

        &__icon {

            margin-top: 10px;

            img {
                display: inline-block;
                margin-top: 10px;
            }
        }
    }

    .burger {
        visibility: visible;
    }

    .nav {
        transform: translateY(-400px);
        width: 100%;
        margin-top: 0;
        flex-direction: column;
        background: white;
        transition: all 1s ease;

        li {
            padding: 10px 0px;
        }
    }
}
</style>