<template>
    <div>
    <b-container>
        <b-row>
            <b-col>
                <b-card
                        title="John Doe"
                        img-src="https://picsum.photos/600/300/?image=25"
                        img-alt="Image"
                        img-top
                        tag="article"
                        style="max-width: 20rem;"
                        class="mb-2"
                >
                    <b-card-text>
                        Some quick example text to build on the card title and make up the bulk of the card's content.
                    </b-card-text>

                    <b-button href="https://fr.wikipedia.org/wiki/John_Doe" variant="primary">Know more about me</b-button>
                </b-card>
            </b-col>
            <b-col><b-card
                    title="Johnny Doe"
                    img-src="https://picsum.photos/600/300/?image=25"
                    img-alt="Image"
                    img-top
                    tag="article"
                    style="max-width: 20rem;"
                    class="mb-2"
            >
                <b-card-text>
                    Some quick example text to build on the card title and make up the bulk of the card's content.
                </b-card-text>

                <b-button href="https://fr.wikipedia.org/wiki/John_Doe" variant="success">Know more about me</b-button>
            </b-card></b-col>
            <b-col><b-card
                    title="Janne Doe"
                    img-src="https://picsum.photos/600/300/?image=25"
                    img-alt="Image"
                    img-top
                    tag="article"
                    style="max-width: 20rem;"
                    class="mb-2"
            >
                <b-card-text>
                    Some quick example text to build on the card title and make up the bulk of the card's content.
                </b-card-text>

                <b-button href="https://fr.wikipedia.org/wiki/John_Doe" variant="dark">Know more about me</b-button>
            </b-card></b-col>
        </b-row>
    </b-container>
    </div>
</template>

<script>
    export default {
        name: "team"
    }
</script>

<style scoped>

</style>
