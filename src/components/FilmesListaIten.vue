<template>
    <!--<input type="text" :value="titulo" :placeholder="$attrs.placeholder">-->
    <li class="list-group-item">
        <span>{{ filme.titulo }} | {{ filme.ano }}</span>
        <button class="btn btn-success float-right" @click="selecionar(event)">Editar</button>
    </li>
</template>

<script>
export default {
    // NÃO HERDA OS VALORES DO PAI MAIS CRIA OS ATRIBUTOS NON PRPS $attrs
    // inheritAttrs: false,
    props: {
        // filmeTitulo: String,
        /*
        titulo: {
            type: String,
            required: true,
            // default () {
            //    return [] ou {}
            // },
            // default: 'Vingadores Guerra Infinita',
            // validator (x) {
            //    return x.includes('Marvel')
            // },
        },
        ano: {
            type: Number,
            required: true,
        },
        */
       filme: {
           type: Object,
           required: true,
       },
    },
    methods: {
        selecionar () {
            this.$emit('selecionarFilme', this.filme)
        },
    },
    computed: {
        filmeTituloConcatenado () {
            return `Filme: ${this.titulo}`
        }
    },
    created () {
        // console.log('Filme: ' + this.titulo)
        // console.log('Filme: ' + this.$attrs)
    },
}
</script>>
