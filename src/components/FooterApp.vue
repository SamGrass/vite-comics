<script>
    export default {
        name: "FooterApp",
        data() {
            return {
                shopItems: [
                    {
                        image: 'buy-comics-digital-comics.png',
                        text: 'DIGITAL COMICS'
                    },
                    {
                        image: 'buy-comics-merchandise.png',
                        text: 'DC MERCHANDISE'
                    },
                    {
                        image: 'buy-comics-shop-locator.png',
                        text: 'SUBSCRIPTION'
                    },
                    {
                        image: 'buy-comics-subscriptions.png',
                        text: 'COMIC SHOP LOCATOR'
                    },
                    {
                        image: 'buy-dc-power-visa.svg',
                        text: 'DC POWER VISA'
                    },
                ],
                usefulLinks: [
                    {
                        title: 'DC COMICS',
                        links: [
                            'Characters',
                            'Comics',
                            'Movies',
                            'TV',
                            'Games',
                            'Videos',
                            'News'
                        ]
                    },
                    {
                        title: 'SHOP',
                        links: [
                            'Shop DC',
                            'Shop DC Collectibles'
                        ]
                    },
                    {
                        title: 'DC',
                        links: [
                            'Terms Of Use',
                            'Privacy policy (New)',
                            'Ad Choices',
                            'Advertising',
                            'Jobs',
                            'Subscriptions',
                            'Talent Workshops',
                            'CPSC Certificates',
                            'Ratings',
                            'Shop Help',
                            'Contact Us'
                        ]
                    },
                    {
                        title: 'SITES',
                        links: [
                            'DC',
                            'MAD Magazine',
                            'DC Kids',
                            'DC Universe',
                            'DC Power Visa',
                        ]
                    },
                ],
                socials: [
                    'footer-facebook.png',
                    'footer-periscope.png',
                    'footer-pinterest.png',
                    'footer-twitter.png',
                    'footer-youtube.png'
                ]
            }
        },
        methods: {
            getImagePath: function (imgPath) {
                return new URL(imgPath, import.meta.url).href;
            }
        }
    }
</script>

<template>
    <footer class="">
        <!-- link acquisti -->
        <div class="shop">
            <div class="container shop-container">
                <ul>
                    <li v-for="(item, index) in shopItems" :key="index">
                        <a href="#!">
                            <div class="image-container">
                                <img :src="getImagePath(`../assets/${item.image}`)" :alt="item.text">
                            </div>
                            <div class="shop-text">
                                {{item.text}}
                            </div>
                        </a>  
                    </li>
                </ul>
            </div>
        </div>
        <!-- link footer -->
        <div class="useful-links">
            <div class="container flex-column">
                <div class="link-list" v-for="(item, index) in usefulLinks" :key="index">
                    <h3>{{ item.title }}</h3>
                    <ul>
                        <li v-for="(link, index) in item.links" :key="index">
                            <a href="#!">{{ link }}</a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
        <!-- socials -->
        <div class="socials">
            <div class="container">
                <!-- sign up sx-->
                <a href="#!" class="btn-sign-up">
                    SIGN-UP NOW!
                </a>

                <!-- socials dx-->
                <div class="social-icons">
                    <h3>FOLLOW US</h3>
                    <ul>
                        <li v-for="(social, index) in socials" :key="index" >
                            <a href="#!">
                                <img :src="getImagePath(`../assets/${social}`)" :alt="social">
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
    
</template>

<style lang="scss" scoped>
    @use '../styles/partials/variables' as *;
    @use '../styles/partials/mixins' as *;

    footer {
        color: #fff;

        .shop {
            padding: 1rem 0;
            background-color: $primary;

            .shop-container {
                padding: 0 3rem;
                
                ul {
                    @include flex-center();
                    justify-content: space-between;

                    li a {
                        @include flex-center();

                        .image-container {
                            transform: scale(50%);

                            img {
                                display: block;
                            }
                        }

                        .shop-text {
                            font-size: 0.8rem;
                            color: #fff;
                        }
                    }   
                }
                
                
            }
        }

        .useful-links {
            padding: 2rem 0;
            background-image: url(../assets/dc-logo-bg.png), url(../assets/footer-bg.jpg);
            background-repeat: no-repeat;
            background-size: auto, cover;
            background-position: bottom 40% right 10%, 0;

            .flex-column {
                background-repeat: no-repeat;
                display: flex;
                flex-direction: column;
                flex-wrap: wrap;
                max-height: 400px;

                h3 {
                    margin: 0.5rem 0;
                }

                a {
                    color: #ffffff7e;
                    font-size: 0.8rem;
                    margin-top: 0.2rem;

                    &:hover {
                        color: #fff;
                    }
                }
            }         
        }

        .socials {
            padding: 1rem 0;
            background-color: #303030;
            
            .container {
                @include flex-center('vertical');
                justify-content: space-between;

                a {
                    display: block
                }
                .social-icons {
                    @include flex-center();
                    gap: 1rem;
                    color: $primary;

                    ul {
                        @include flex-center();
                        gap: 0.5rem;
                    }
                }
            }
        }
    }
    


    
</style>

