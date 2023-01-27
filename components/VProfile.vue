<template lang="pug">
    .profile    
        .container
            .profile__owner(v-for="owner in owners" :key="owners.id") 
                VOwner(
                    :image="owner.image"
                    :alternate="owner.alternate"
                    :name="owner.name"
                    :profession="owner.profession"
                    :description="owner.description"
                    :booking="owner.booking"
                    :tours="owner.tours"
                    :hotels="owner.hotels"
                )
            .profile__info 
                .profile__info-text 
                    p Latest reviews 
                    a(href="#") All reviews
                .profile__info-stats
                    span 131
                    span 14
            .profile__review
                .profile__review-comments(v-for="commentator in commentators" :key="commentator.id")
                    VComment(
                        :name="commentator.name"
                        :day="commentator.day" 
                        :month="commentator.month" 
                        :year="commentator.year" 
                        :comment="commentator.comment"
                    )
        .profile__form
            textarea(type='text' v-model="comment" require).profile__form-input  
            button(@click.prevent="addComment" :disabled="isEmpty" ).profile__form-button Send a comment
</template>

<script>
import VComment from '@/components/VComment.vue';
import VOwner from '@/components/VOwner.vue';
    export default {
        components: {
            VComment,VOwner
        },
        data() {
            return {
                commentators: [
                    {
                        id: 0,
                        name: "Samuel Jackson",
                        comment: "Hey Eva! You're cool. Nice pic!",
                        day: "13",
                        month: "Apr",
                        year: "2022"
                    },
                    {
                        id: 1,
                        name: "Angela Deimon",
                        comment: "Thanks for your services! We really liked the ocean view room. We hope to cooperate in the near future. We are sure you will do everything to make our next holiday fantastic.",
                        day: "10",
                        month: "Apr",
                        year: "2022"
                    },
                    {
                        id: 2,
                        name: "Ronald Harris",
                        comment: "Eva, hello! There is such a question: How can I contact you if I am abroad in roaming?",
                        day: "8",
                        month: "Apr",
                        year: "2022"
                    },
                ],
                owners: [
                    {
                        id: 0,
                        image: require("@/assets/images/avatars/girl.png"),
                        name: "Eva Jonson",
                        alternate: "Eva's photo avatar",
                        profession: "Sales Manager",
                        description: `I will find the best offers for you. My services are absolutely free.`,
                        booking: 11,
                        tours: 3,
                        hotels: 1
                    }
                ],
                keysPressed: {},
                comment:'',
                isEmpty: true,
            }
        },
        watch: { 
            comment(){
                if(this.comment.length !== 0){
                    this.isEmpty = false
                }else {
                    this.isEmpty = true
                }
            }
        },
        methods: {
            addComment() { 
                const date = new Date();
                const formattedDate = date.toLocaleDateString('en-GB', {
                    day: 'numeric', month: 'short', year: 'numeric'
                });
                let newComment = {
                    name: "You",
                    day: formattedDate,
                    comment: this.comment,
                }

                this.commentators = JSON.parse(localStorage.getItem("commentators"));
                
                this.commentators.unshift(newComment)

                localStorage.setItem("commentators", JSON.stringify(this.commentators));

                this.comment = ""
            },
        },
        mounted() {
            document.addEventListener('keydown', (event) => {
                this.keysPressed[event.key] = true;

                if (this.keysPressed['Control'] && event.key == 'Enter') {
                    this.addComment();
                }
            });

            document.addEventListener('keyup', (event) => {
                delete this.keysPressed[event.key];
            });


            if (!localStorage.getItem("commentators")) { 
                localStorage.setItem("commentators", JSON.stringify(this.commentators));
                this.commentators = JSON.parse(localStorage.getItem("commentators"));
            } else {
                this.commentators = JSON.parse(localStorage.getItem("commentators"));
            }
        }
    }
</script>

<style lang="scss" scoped>
.profile { 

    &__info { 
        margin: 2.658vw 0vw;

        display: flex;
        justify-content: space-between;
        align-items: center;

        &-text { 
            display: flex;
            justify-content: space-between;
            align-items: center;

            & > p { 
                margin-right: 2.658vw;
                font-weight: 700;
                font-size: 3.272vw;
                line-height: 3.272vw;
            }
            & > a { 
                font-weight: 400;
                font-size: 2.863vw;
                line-height: 3.272vw;
                text-decoration-line: underline;
                color: #005DA1;
            }
        }
        &-stats { 
            & > span { 
                font-weight: 400;
                font-size: 2.454vw;
                line-height: 2.863vw;

                &:nth-child(1){
                    margin-right: 8.180vw;
                    position: relative;

                    &::after { 
                        content: url("@/assets/images/svg/like.svg");
                        display: block;
                        position: absolute;
                        left: -3.476vw;
                        top: 0.2vw;
                        width: 2.454vw;
                        height: 2.198vw;

                        @media screen and (max-width: 400px){
                            left: -4.476vw;
                            top: 0vw;
                        }
                    }
                }
                &:nth-child(2){
                    position: relative;

                    &::after { 
                        content: url("@/assets/images/svg/comment.svg");
                        display: block;
                        position: absolute;
                        left: -3.476vw;
                        top: 0.2vw;
                        width: 3.272vw;
                        height: 3.272vw;

                        @media screen and (max-width: 400px){
                            left: -4.476vw;
                            top: 0vw;
                        }
                    }
                }
            }
        }
    }
    &__review { 
        height: 100%;
        overflow-y: scroll;
        padding-bottom: 182px;
    }
    &__form {
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;

        background-color: #F2F2F2;
        min-height: 39.059vw;
        width: 100%;

        position: fixed;
        bottom: 0vw;

        @media screen and (min-width: 580px){
            min-height: 29.059vw;
        }

        &-input {
            border: 0.204vw solid #000000;
            border-radius: 0.204vw;
            width: 91.411vw;
            height: 12.883vw;
            font-size: 4.908vw;
            padding-left: 2.045vw;

            @media screen and (min-width: 580px){
                width: 87.411vw;
                height: 10.883vw;
                font-size: 2.908vw;
            }
        }

        &-button { 
            padding: 2.658vw 9.816vw;
            margin-top: 4.703vw;

            background: #FDD639;
            border-radius: 4.703vw;
            border: none;

            font-weight: 700;
            font-size: 3.272vw;
            line-height: 4.294vw;
            color: #333333;

            @media screen and (min-width: 580px){
                padding: 1.658vw 8.816vw;
            }
        }
    }
}
</style>