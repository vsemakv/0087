<template lang="pug">
        .comment
            .comment__title
                p.comment__owner  {{ name }}  
                .comment__date 
                    span {{ day }}
            .comment__content
                p.comment__content-text {{ comment }}
</template>

<script>
    export default {
        props: {
            name: {
                type: String,
                default: null
            },
            day: {
                type: String,
                default: null
            },
            comment: {
                type: String,
                default: null
            }
        },
    }
</script>

<style lang="scss" scoped>
.comment { 
    margin-bottom: 3.272vw;

    &__title { 
        display: flex;

        @media screen and (min-width: 1024px){
            
        }
    }
    &__owner { 
        margin-right: 1.636vw;

        color: #333333;
        font-weight: 700;
        font-size: 2.863vw;
        line-height: 3.885vw;

        @media screen and (min-width: 1024px){
            margin-right: 0.781vw;
            font-size: 1.367vw;
            line-height: 1.855vw;
        }
    }
    &__date {
        display: flex;
        justify-content: space-between;
        align-items: center;

        & > span { 
            color: #808080;
            font-weight: 400;
            font-size: 2.249vw;
            line-height: 3.885vw;

            @media screen and (min-width: 1024px){
                font-size: 1.074vw;
                line-height: 1.855vw;
            }
        }
    }
    &__content {
        margin-top: 2.454vw;

        background: #F2FBFF;
        border: 0.204vw solid #C4CBCF;
        box-shadow: 0vw 0.818vw 2.045vw rgba(128, 128, 128, 0.1);
        padding: 4.090vw;
        position: relative;

        @media screen and (min-width: 1024px){
            margin-top: 1.3vw;
            border: 0.098vw solid #C4CBCF;
            box-shadow: 0vw 0.418vw 1.045vw rgba(128, 128, 128, 0.1);
            padding: 2vw;
        }

        &::after { 
            content: "";
            display: block;
            position: absolute;
            width: 0;
            height: 0;
            border-style: solid;
            border-width: 1.840vw 0 0 1.840vw;
            border-color: transparent transparent transparent #F2FBFF;
            left: 4.139vw;
            top: -1.636vw;

            @media screen and (min-width: 1024px){
                border-width: 1.970vw 0 0 1.970vw;
                left: 2.079vw;
                top: -0.976vw;
            }
        }
        &::before { 
            content: "";
            display: block;
            position: absolute;
            width: 0;
            height: 0;
            border-style: solid;
            border-width: 2.249vw 0 0 2.147vw;
            border-color: transparent transparent transparent #C4CBCF;
            left: 3.885vw;
            top: -2.249vw;

            @media screen and (min-width: 1024px){
                border-width: 1.240vw 0 0 1.240vw;
                left: 1.979vw;
                top: -1.216vw;
            }
        }

        &-text { 
            color: #333333;
            font-weight: 400;
            font-size: 2.863vw;
            line-height: 3.885vw;

            @media screen and (min-width: 1024px){
                font-size: 1.367vw;
                line-height: 1.855vw;
            }
        }
    }
}
</style>