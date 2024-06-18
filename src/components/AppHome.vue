<template>
    <div class="container">
        <div class="row">
            <div class=" d-flex gap-2 flex-wrap">
                <div v-for="character in characters" :key="character">
                    <div class="card col-3">
                        <div class="card-title text-warning">{{ character.name }}</div>
                        <div class="card-body">{{ character.description }}</div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import axios from 'axios'


export default {

    data() {
        return {
            characters: [],

        }
    },
    methods: {

        fetchCharacters() {

            axios.get('http://127.0.0.1:8000/api/characters', {

            })
                .then((res) => {

                    console.log(res.data.characters)
                    this.characters = res.data.characters
                    
                })

        }
    },
    created() {
        this.fetchCharacters()
    },
}
</script>

<script>
</script>