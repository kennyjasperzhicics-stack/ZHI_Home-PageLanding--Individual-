<template>
    <section id="sectionFacts">
        <img
            id="imageFacts"
            src="../../../assets/desktop/image-interactive.jpg"
            alt="image interactive"
        />
        <article id="articleFacts">
            <div id="messageFacts">
            <h1 id="title">
                The Fashion of the Future 
            </h1>
            <p id="paragraph">
                Founded in 2011, AuraStyle has been a pioneer in producing world-class clothing, 
                catering to some of the most renowned models and fashion icons across the globe. 
                With a commitment to quality, innovation, and timeless style, 
                AuraStyle has earned a reputation for combining cutting-edge designs with impeccable craftsmanship.
                From runways to global fashion campaigns, the brand continuously redefines elegance and sets new standards in the world of fashion.
            </p>
            </div>
        </article>
    </section>
</template>

<script>
    export default {
        name: "SectionFacts",
        components: {

        },
        data() {
        return {
            showBarText: true,
            mediaQuerieList: matchMedia("(max-width: 830px)"),
        }
        },
        methods: {
            showBr(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.showBarText = false;
                } else {
                    this.showBarText = true;
                }
            }
        },
        mounted() {
            this.showBr(this.mediaQuerieList);

            this.mediaQuerieList.addEventListener('change', this.showBr);
        }
    }
</script>

<style scoped>
    section#sectionFacts {
        display: flex;

        margin-top: 7rem;

        width: 100%;
        height: 30rem;

        position: relative;
    }
    
    img#imageFacts {
        width: 45rem;
    }

    div#messageFacts {
        background-color: var(--white);

        width: 36rem;

        padding-left: 5rem;
        padding-top: 5rem;

        position: absolute;
        right: 0;
        bottom: 0;
    }

    h1#title {
        font-family: "Josefin Sans", Helvetica, sans-serif;
        font-size: 3rem;
        font-weight: normal;

        margin-bottom: 2rem;
    }

    p#paragraph {
        color: var(--very-dark-gray);

        font-family: Atala, Helvetica, sans-serif;
        font-weight: bold;
        font-size: 15px;

        line-height: 1.7rem;
    }

    @media screen and (max-width: 830px) {
        img#imageFacts {
            width: 100%;

            margin-bottom: 3rem;
        }

        section#sectionFacts {
            flex-direction: column;
            justify-content: center;
            align-items: center;

            height: auto;
        }

        div#messageFacts {
            position: static;

            padding-left: 0;
            padding-top: 0;

            width: 100%;
        }

        h1#title,
        p#paragraph
        {
            text-align: center;
        }
    }

    @media screen and (max-width: 616px) {
        section#sectionFacts {
            margin-top: 5rem;
        }
    }

    @media screen and (max-width: 518px) {
    h1#title {
        font-size: 2rem;
        }

    p#paragraph {
        font-size: 14px;
        }
    }
</style>