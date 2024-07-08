<script>
    export default {
        name: "HeaderApp",
        data() {
            return {
                links: [
                    {
                        text: 'CHARACTERS',
                        url: '#!',
                        active: true
                    },
                    {
                        text: 'COMICS',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'MOVIES',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'TV',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'GAMES',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'COLLECTIBLES',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'VIDEOS',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'FANS',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'NEWS',
                        url: '#!',
                        active: false
                    },
                    {
                        text: 'SHOP',
                        url: '#!',
                        active: false
                    }
                ]
            }
        },
    }
</script>

<template>
    <div>   
        <header class="container">
            <!-- img sx -->
            <div class="image-container">
                <img src="../assets/dc-logo.png" alt="">
            </div>
            <!-- nav dx -->
            <nav>
                <ul>
                    <li v-for="(link, index) in links" :key="index">
                        <a :class="link.active ? 'active' : ''" :href="link.url">{{ link.text }}</a>
                    </li>
                    
                </ul>
            </nav>
        </header>
    </div>
    <div class="jumbotron"></div>
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;
    
    .container {
        height: 6.5rem;
        padding: 0.5rem 0.2rem 0;
        @include flex-center('vertical');
        justify-content: space-between;

        .image-container {
            width: 5rem;

            img {
                display: block;
            }
        }

        nav {
            height: 100%;

            ul {
                @include flex-center;
                gap: 1rem;
                height: 100%;

                li {
                    height: 100%;

                    a   {
                        display: block;
                        height: 100%;
                        font-size: 0.9rem;
                        font-weight: 500;
                        @include flex-center('vertical');
                        transition: all 50ms ease;


                        &.active,
                        &:hover {
                            border-bottom: 3px solid $primary;
                            color: $primary;
                        }
                    }   
                }    
            }
        }           
    }

    .jumbotron {
        height: 400px;
        background-image: url(../assets/jumbotron.jpg);

    }
</style>