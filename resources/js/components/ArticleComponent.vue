<template>
    <div class="container">
        <div class="row justify-content-center">
            <div class="col-md-8">
                <div class="card">
                    <div class="card-header"><h3>Article Compoment</h3></div>

                    <div class="card-body">
                        Article component mounted.
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        data() {
            return {
                articles: [],
                article: {
                    id: '',
                    title: '',
                    body: ''
                },
                article_id: '',
                pagination: {},
                edit: false
            }
        }, 

        created() {
            this.fetchArticles();
        },

        methods: {
            fetchArticles() {
                fetch('api/articles')
                    .then(res => res.json())
                    .then(res => {
                        console.log(res.data);
                    })
            }
        }
    }
</script>
