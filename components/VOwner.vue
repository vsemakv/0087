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
    @media screen and (min-width: 1024px){
        display: flex;
    }
    &__main { 
        display: flex;

        width: 100%;
        @media screen and (min-width: 1024px){
            width: 50%;
        }
        & > img { 
            border-radius: 50%;
            width: 25.358vw;
            height: 25.358vw;
            position: relative;
            z-index: 2;

            @media screen and (min-width: 1024px){
                width: 12.109vw;
                height: 12.109vw;
            }
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

                @media screen and (min-width: 1024px){
                    font-size: 1.563vw;
                    line-height: 1.953vw;
                }
            }
            & > p:nth-child(2) { 
                font-weight: 400;
                font-size: 2.454vw;
                line-height: 4.090vw;
                color: #808080;
                
                @media screen and (min-width: 1024px){
                    font-size: 1.172vw;
                    line-height: 1.953vw;
                }
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
            

            @media screen and (min-width: 1024px){
                top: 6vw;
                left: -7.8vw;

                width: 35.547vw;
                height: 5.273vw;
                padding: 0.336vw 0vw;

                display: flex;
                justify-content: center;
                align-items: center;
            }

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

                @media screen and (min-width: 1024px){
                    font-size: 1.367vw;
                    line-height: 1.953vw;
                    padding-left: 4.395vw;
                    width: 19.629vw;
                }
            }
        }
    }
    &__srvices { 
        padding-left: 26.585vw;
        color: #333333;

        @media screen and (min-width: 1024px){
            padding-left: 3vw;
            width: 50%;
        }
        &-title { 
            text-align: right;
            padding-right: 4.908vw;
            margin-bottom: 2.454vw;
            font-weight: 400;
            font-size: 2.658vw;
            line-height: 3.067vw;

            @media screen and (min-width: 1024px){
                font-size: 1.270vw;
                line-height: 1.465vw;
                margin-bottom: 0.781vw;
                padding-right: 2.458vw;
            }
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
                @media screen and (min-width: 1024px){
                    height: 0.098vw;
                }
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
                @media screen and (min-width: 1024px){
                    height: 0.098vw;
                }
            }

            @media screen and (min-width: 1024px){
                padding: 1.563vw 0vw;
            }
        }
        &-item {
            padding-right: 8.180vw;

            display: flex;
            align-items: center;
            justify-content: space-between;

            @media screen and (min-width: 1024px){
                padding-right: 3.809vw;
            }

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

                    @media screen and (min-width: 1024px){
                        width: 21.387vw;
                        height: 2.344vw; 
                        border-radius: 0vw 0.293vw 0.293vw 0vw ;
                    }
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

                    @media screen and (min-width: 1024px){
                        width: 5.273vw;
                        height: 2.344vw; 
                        border-radius: 0vw 0.293vw 0.293vw 0vw ;
                    }
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

                    @media screen and (min-width: 1024px){
                        width: 3.516vw;
                        height: 2.344vw; 
                        border-radius: 0vw 0.293vw 0.293vw 0vw ;
                    }
                }
            }
            & > p { 
                font-weight: 400;
                font-size: 2.658vw;
                line-height: 5.317vw;
                position: relative;
                padding-left: 1.227vw;
                z-index: 2;

                @media screen and (min-width: 1024px){
                    font-size: 1.270vw;
                    line-height: 2.539vw;
                    padding-left: 0.586vw;
                }
            }
            & > span { 
                font-weight: 700;
                font-size: 2.658vw;
                line-height: 3.067vw;

                @media screen and (min-width: 1024px){
                    font-size: 1.270vw;
                    line-height: 1.465vw;
                }
            }
        }
        &-total { 
            margin-top: 1.636vw;
            padding-right: 8.180vw;

            display: flex;
            align-items: center;
            justify-content: space-between;

            @media screen and (min-width: 1024px){
                margin-top: 0.879vw;
                padding-right: 3.809vw;
            }

            & > p { 
                font-weight: 700;
                font-size: 3.272vw;
                line-height: 5.317vw;

                @media screen and (min-width: 1024px){
                   font-size: 1.563vw;
                   line-height: 2.539vw;
                }
            }
        }
    }
}
</style>