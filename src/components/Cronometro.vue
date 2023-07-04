<template>
    <section>
        <strong class="display">
            {{ tempoDecorrido }}
        </strong>
    </section>
</template>

<script lang="ts">
// Obrigatório colocar o TS caso fizer um script em TypeScript
import { defineComponent } from 'vue'

export default defineComponent({
    name: 'Cronometro',
    props: {
        tempoEmSegundos: {
            type: Number,
            default: 0
        }
    },
    computed: {
        tempoDecorrido(): string {
            return new Date(this.tempoEmSegundos * 1000).toISOString().substr(11, 8)
        }
    },
})
</script>

<style>
.display {
    color: var(--texto-primario);

}
</style>