<template lang="pug">
    .owner  
        .owner__main 
            img(:src="image", :alt="alternate")
            .owner__main-text   
                p {{ name }}
                p {{ profession }}
                .owner__main-desc
                    p {{ description }}
        .owner__srvices
            p.owner__srvices-title Services
            ul.owner__srvices-list
                li.owner__srvices-item 
                    p Manual tour booking
                    span {{ booking }}
                li.owner__srvices-item 
                    p Package tours
                    span {{ tours }}
                li.owner__srvices-item 
                    p Hotels
                    span {{ hotels }}
            .owner__srvices-total 
                p Total 
                p {{ total }}
</template>

<script>
    export default {
        data() {
            return {
                total: null
            }
        },
        mounted () {
            this.total = this.tours + this.hotels + this.booking;
        },
        props: {
            image: {
                type: String,
                default: null
            },
            alternate: { 
                type: String,
                default: null
            },
            name: {
                type: String,
                default: null
            },
            profession: {
                type: String,
                default: null
            },
            description: {
                type: String,
                default: null
            },
            booking: { 
                type: Number,
                default: 0
            },
            tours: { 
                type: Number,
                default: 0
            },
            hotels: { 
                type: Number,
                default: 0
            },
        },
    }
</script>

<style lang="scss" scoped>
.owner { 

    &__main { 
        display: flex;

        width: 100%;

        & > img { 
            border-radius: 50%;
            width: 25.358vw;
            height: 25.358vw;
            position: relative;
            z-index: 2;
        }

        &-text { 
            width: 100%;
            position: relative;
            padding-top: 1.227vw;
            & > p { 
                padding-left: 2.454vw;
            }
            & > p:first-child { 
                font-weight: 700;
                font-size: 3.272vw;
                line-height: 4.090vw;
                color: 33333;
            }
            & > p:nth-child(2) { 
                font-weight: 400;
                font-size: 2.454vw;
                line-height: 4.090vw;
                color: #808080;
            }
        }
        &-desc { 
            position: absolute;
            bottom: 2.045vw;
            right: 0vw;
            overflow: hidden;
            overflow-y: inherit;
            
            padding: 1.636vw 0vw;

            width: 74.642vw;
            height: 11.043vw;
            background: #FFFBC8;
            border: 0.204vw solid #DADADA;
            border-radius: 1.022vw;
            
            & > p { 
                width: 41.104vw;
                padding-left: 10.18vw;
                font-weight: 400;
                font-size: 2.863vw;
                line-height: 4.090vw;
                color: #333333;

                @media screen and (min-width: 580px){
                    padding-left: 14.18vw;
                }
            }
        }
    }
    &__srvices { 
        padding-left: 26.585vw;
        color: #333333;

        &-title { 
            text-align: right;
            padding-right: 4.908vw;
            margin-bottom: 2.454vw;
            font-weight: 400;
            font-size: 2.658vw;
            line-height: 3.067vw;
        }
        &-list { 
            width: 100%;
            position: relative;
            padding: 3.067vw 0vw;
            &::after { 
                position: absolute;
                display: block;
                content: "";
                width: 100%;
                height: 0.204vw;
                background-color: #DADADA;
                bottom: 0vw;
                left: 0vw;
            }
            &::before {
                position: absolute;
                display: block;
                content: "";
                width: 100%;
                height: 0.204vw;
                background-color: #DADADA;
                top: 0vw;
                left: 0vw;
            }
        }
        &-item {
            padding-right: 8.180vw;

            display: flex;
            align-items: center;
            justify-content: space-between;

            &:first-child { 
                position: relative;

                &::before { 
                    content: "";
                    display: block;
                    position: absolute;
                    left: 0vw;
                    top: 0vw;
                    width: 44.785vw;
                    height: 4.908vw;
                    background: #B1E19B;
                    border-radius: 0vw 0.613vw 0.613vw 0vw;

                    z-index: 1;
                }
            }

            &:nth-child(2) { 
                position: relative;

                &::before { 
                    content: "";
                    display: block;
                    position: absolute;
                    left: 0vw;
                    top: 0vw;
                    width: 11.043vw;
                    height: 4.908vw;
                    background: #ACE2F8;
                    border-radius: 0vw 0.613vw  0.613vw  0vw;

                    z-index: 1;
                }
            }

            &:last-child { 
                position: relative;

                &::before { 
                    content: "";
                    display: block;
                    position: absolute;
                    left: 0vw;
                    top: 0vw;
                    width: 7.362vw;
                    height: 4.908vw;
                    background: #ACE2F8;
                    border-radius: 0vw 0.613vw 0.613vw 0vw;

                    z-index: 1;
                }
            }
            & > p { 
                font-weight: 400;
                font-size: 2.658vw;
                line-height: 5.317vw;
                position: relative;
                padding-left: 1.227vw;
                z-index: 2;
            }
            & > span { 
                font-weight: 700;
                font-size: 2.658vw;
                line-height: 3.067vw;
            }
        }
        &-total { 
            margin-top: 1.636vw;
            padding-right: 8.180vw;

            display: flex;
            align-items: center;
            justify-content: space-between;

            & > p { 
                font-weight: 700;
                font-size: 3.272vw;
                line-height: 5.317vw;
            }
        }
    }
}
</style>