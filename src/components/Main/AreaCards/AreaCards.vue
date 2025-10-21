<template>
    <div id="AreaCards">
        <header id="headerCards">
            <span id="title">
                OUR CREATIONS
            </span>
            <Button v-show="!toggleButton">
                See All
            </Button>
        </header>
        <ul id="cards">
            <Card
                v-for="item in dataCard"
                :key="item.id"
                :src="item.src"
                :text="item.text"
            />
        </ul>
        <Button v-show="toggleButton">
            See All
        </Button>
    </div>
</template>

<script>
    
    import Button from './Button/Button.vue';
    import Card from './Card/Card.vue';

    export default {
        name: "AreaCards",
        components: {
            Button,
            Card
        },
        data() {
            return {
                dataCard: [
                    {
                        id: 1,
                        src: "image-deep-earth.jpg",
                        text: "PLANET COLLECTION"
                    },
                    {
                        id: 2,
                        src: "image-night-arcade.jpg",
                        text: "ARCADE COLLECTION"
                    },
                    {
                        id: 3,
                        src: "image-soccer-team.jpg",
                        text: "SPORTS COLLECTION"
                    },
                    {
                        id: 4,
                        src: "image-grid.jpg",
                        text: "RACE COLLECTION"
                    },
                    {
                        id: 5,
                        src: "image-from-above.jpg",
                        text: "ROAD COLLECTION"
                    },
                    {
                        id: 6,
                        src: "image-pocket-borealis.jpg",
                        text: "NIGHT COLLECTION"
                    },
                    {
                        id: 7,
                        src: "image-curiosity.jpg",
                        text: "NASA COLLECTION"
                    },
                    {
                        id: 8,
                        src: "image-fisheye.jpg",
                        text: "360 COLLECTION"
                    }
                ],
                toggleButton: false,
                mediaQuerieList: matchMedia("(max-width: 616px)")
            }
        },
        methods: {
            toggleButtonResponsive(mediaQuerieList) {
                if(mediaQuerieList.matches) {
                    this.toggleButton = true;
                } else {
                    this.toggleButton = false;
                }
            }
        },
        mounted() {
            this.toggleButtonResponsive(this.mediaQuerieList);

            this.mediaQuerieList.addEventListener('change', this.toggleButtonResponsive);
        }
    }

</script>

<style scoped>

    div#AreaCards {
        margin: 7rem 0;

        flex-direction: column;
        justify-content: center;
    }
    
    div#AreaCards,
    header#headerCards
    {
        width: 100%;

        display: flex;
        align-items: center;
    }

    header#headerCards {
        justify-content: space-between;

        margin-bottom: 60px;
    }

    span#title {
        font-family: "Josefin Sans";
        font-size: 2.5rem;
    }

    ul#cards {
        display: grid;
        grid-template: auto auto / 25% 25% 25% 25%;

        width: 100%;
    }

    @media screen and (max-width: 984px) {
        ul#cards {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
    }

    @media screen and (max-width: 616px) {
        div#AreaCards {
            margin: 5rem 0;
        }

        header#headerCards {
            justify-content: center;
        }

        span#title {
            text-align: center;
        }

        ul#cards {
            margin-bottom: 20px;
        }
    }

</style>