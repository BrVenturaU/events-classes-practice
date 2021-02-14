<template>

    <div>
        <b-row class="mb-5">
            <b-col cols="12" class="mx-auto">
                <h2>Formulario</h2>
                <b-form inline autocomplete="off" class="justify-content-center">
                    <b-form-checkbox 
                        v-model="esIterable"
                        switch
                        :class="margenesFormulario">
                        Iterar: <b>{{ esIterable ? "Si" : "No" }}</b>
                    </b-form-checkbox>
                    <b-form-group
                        label-for="texto"
                        :class="margenesFormulario"
                        >
                        <b-form-input
                            v-model="texto"
                            @keyup="captura"
                            id="texto"
                            type="text"
                            placeholder="Escribe lo que quieras..."
                            required
                        ></b-form-input>
                    </b-form-group>
                    <b-button variant="info" @click="limpiar">Limpiar</b-button>
                </b-form>
            </b-col>
        </b-row>

        <b-row>
            <Resultado :esIterable="esIterable" :variante="variante" :variantes="variantes" /> 
        </b-row>
    </div>
</template>

<script>
import Resultado from '@/components/Resultado.vue'

export default {
    name:'Formulario',
    components:{
        Resultado
    },
    data() {
        return {
            texto:'',
            variante: '',
            variantes: [],
            esIterable: true,
            margenesFormulario: ['mb-3', 'mr-3']
        }
    },
    methods: {
        captura(e){
            this.texto = e.target.value;
            let keyCode = e.keyCode;
            console.log(e.key);
            console.log(keyCode);
            if(keyCode >= 65 && keyCode <= 90){
                console.log(`Letra: ${evaluarLetra(/^[a-zA-Z]+$/, e.key)}.`);
                this.variantes.push("success");
                this.variante = "success";
            }
            else if((keyCode >= 48 && keyCode <= 57) || (keyCode >= 96 && keyCode <= 105)){
                console.log(`Número: ${evaluarLetra(/^\d+$/, e.key)}.`);
                this.variantes.push("danger");
                this.variante = "danger";
            }
            else{
                console.log("Otra cosa.");
                this.variantes.push("warning");
                this.variante = "warning";
            }
        },
        limpiar(){
            this.variante = "";
            this.variantes = [];
            this.texto = "";
        }
    },
}

function evaluarLetra(expresionRegular,texto){
    return expresionRegular.test(texto);
}
</script>

<style scoped>

</style>