<template>
    <b-col cols="12">
        <h2>Resultados</h2>
        <div class="text-center mx-auto">
            <span v-if="esIterable">
                <b-spinner
                    :style="spinnerProps"
                    :class="spinnerClasses"
                    v-for="variante of variantes"
                    :key="variante"
                    :variant="variante"
                    type="grow"
                ></b-spinner>
            </span>
            <span v-else>
                <b-spinner
                    :style="spinnerProps"
                    :class="spinnerClasses"
                    :variant="variante"
                    type="grow"
                ></b-spinner>
            </span>
            
        </div>
    </b-col>
</template>

<script>
export default {
    name: 'Resultado',
    props: {
        esIterable: Boolean,
        variante: String,
        variantes: Array
    },
    data() {
        return {
            spinnerProps: {"width": "3rem", "height": "3rem"},
            spinnerClasses: ['ml-2', 'mb-2']
        }
    },
}
</script>