<template>
    <div>
        <p v-if="esta_trabalhando">Estou trabalhando no momento.</p>
        <p v-else>Estou em busca de novas oportunidades.</p>
        <p>Utilizo as seguintes tecnologias para back-end:</p>
        <ul>
            <li v-for="(technology, index) in backend_technologies" :key="index">{{ technology }}</li>
        </ul>
        <p>Utilizo as seguintes tecnologias para front-end:</p>
        <ul>
            <li v-for="technology in frontend_technologies" :key="technology.id">
                {{ technology.language }}
            </li>
        </ul>
        <div>
            <button @click="showEmail">{{ textoBotao }}</button>
        </div>
        <p v-show="mostrar_email">Mande uma mensagem para: {{ email }}</p>
        <p>Para acessar meu portifólio basta clicar <a v-bind:href="link_portifolio" target="_blank">aqui</a></p>
        <Picture />
    </div>
</template>

<script>
    import Picture from './Picture.vue';

    export default {
        name: 'Info',
        data() {
            return {
                esta_trabalhando: true,
                email: 'carlos@atendimento.com.br',
                mostrar_email: false,
                textoBotao: 'Mostrar e-mail',
                link_portifolio: 'https://google.com.br',
                backend_technologies: ['JavaScript', 'PHP', 'Python'],
                frontend_technologies: [
                    {id: 1, language: 'HTML'},
                    {id: 2, language: 'CSS'},
                    {id: 3, language: 'Vue'}
                ]
            }
        },
        components: {
            Picture
        },
        methods: {
            showEmail() {
                this.mostrar_email = !this.mostrar_email
                if (!this.mostrar_email) {
                    this.textoBotao = 'Mostrar e-mail'
                } else {
                    this.textoBotao = 'Ocultar e-mail'
                }
            }
        }
    }
</script>