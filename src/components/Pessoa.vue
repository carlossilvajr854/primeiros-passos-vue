<template>
    <div>
        <h2>Está é a descrição da pessoa: {{ nome }}</h2>
        <Info :email="email" :esta_trabalhando="true" />
        <Form />
    </div>
</template>

<script>
    import Info from "./Info.vue";
    import Form from "./Form.vue";

    export default {
        name: "Pessoa",
        data() {
            return {
                nome: "Carlos",
                email: "carlossilva@hannahtech.com.br",
            };
        },
        components: {
            Info,
            Form,
        },
    };
</script>
