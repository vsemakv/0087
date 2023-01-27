<template lang="pug">
        .comment
            .comment__title
                p.comment__owner  {{ name }}  
                .comment__date 
                    span {{ day }} 
                    span {{ month }} 
                    span {{ year }} 
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
            month: {
                type: String,
                default: null
            },
            year: {
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
    }
    &__owner { 
        margin-right: 1.636vw;

        color: #333333;
        font-weight: 700;
        font-size: 2.863vw;
        line-height: 3.885vw;
    }
    &__date {
        & > span { 
            color: #808080;
            font-weight: 400;
            font-size: 2.249vw;
            line-height: 3.885vw;
        }
    }
    &__content {
        margin-top: 2.454vw;

        background: #F2FBFF;
        border: 0.204vw solid #C4CBCF;
        box-shadow: 0vw 0.818vw 2.045vw rgba(128, 128, 128, 0.1);
        padding: 4.090vw;
        position: relative;

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
        }

        &-text { 
            color: #333333;
            font-weight: 400;
            font-size: 2.863vw;
            line-height: 3.885vw;
        }
    }
}
</style>