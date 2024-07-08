<script>
    export default {
        name: "FooterApp",
        data() {
            return {
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
                ]
            }
        },
    }
</script>

<template>
    <footer class="">
        <!-- link acquisti -->
        <div class="shop">

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
                <div>
                    SIGN-UP NOW!
                </div>

                <!-- socials dx-->
                <div>
                    <h3>FOLLOW US</h3>
                    <ul>
                        <li>twitter</li>
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
            padding: 2.5rem 0;
            background-color: $primary;
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
        }
    }
    


    
</style>

