<template>
    <div v-if="this.$store.state.data.notes.length != 0">
        <fab color="black" iconType="edit"></fab>
        <card cardType="note" :currentNote="note" :key="note.id" :color="note.color" v-for="note in this.$store.state.data.notes" :content="note.content" :title="note.title"></card>
    </div>
    <div v-else>
        <fab color="black" iconType="edit"></fab>
        <placeholder text="No notes" icon="note"></placeholder>
    </div>
</template>

<script>
import Placeholder from './Placeholder.vue'
import Card from '../components/Card.vue'
import Fab from '../components/Fab.vue'
import { colors } from '../colors.js'

export default {
    name: 'notes',
    components: {
        Card, Fab, Placeholder
    },
    mounted() {
        var notes = this.$store.state.data.notes
        if (notes.length != 0) {
            if (notes[notes.length - 1]['title'] === '' && notes[notes.length - 1]['content'] === '') {
                this.$store.commit('NOTE_pop')
            }
        }
    }
}    
</script>

<style scoped>
.container {
    padding-top: 2em;
}
</style>
