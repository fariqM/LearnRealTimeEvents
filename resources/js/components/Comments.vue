<template>
    <div class="container">
        <ul class="comment-list">
            <Comment :key="comment.id" v-for="comment in comments" :comment="comment"></Comment>
        </ul>
    </div>
</template>

<script>
    import {mapGetters} from 'vuex'
    import Comment from './Comment'

    export default {
        name: "Comments",
        components: {Comment},
        mounted() {
            this.$store.dispatch('GET_COMMENTS')


            Pusher.logToConsole = true;

            let pusher = new Pusher('0340a8033793dbdc2f85', {
                cluster: 'ap1',
                encrypted: true
            });


            //Subscribe to the channel we specified in our Adonis Application
            let channel = pusher.subscribe('comment-channel')

            channel.bind('new-comment', (data) => {
                this.$store.commit('ADD_COMMENT', data.comment)
            })
        },
        computed: {
            ...mapGetters([
                'comments'
            ])
        }
    }
</script>

<style scoped>
    .comment-list {
        padding: 1em 0;
        margin-bottom: 15px;
    }

</style>
