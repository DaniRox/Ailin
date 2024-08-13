<script>
	import Text from './../components/Text.svelte';
    
    import imgTitle from "../images/titleMensaje.png";
</script>


<style>
    .Mensaje {
        width: 100%;
        padding: 4rem 10%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    img {
        height: 4.4rem;
        margin-bottom: 0.5rem;
    }
    @media (min-width: 768px) {
        img {
            margin-bottom: 0.7rem;
        }
        .Mensaje {
            padding: 5rem 20%;
        }
    }
    @media (min-width: 1024px) {
        .Mensaje {
            padding: 6rem 25%;
        }
    }
</style>


<div class="Mensaje">
    <img src={imgTitle} alt="Titulo Deja un Mensaje">
    <Text 
        text="Compartí tus buenos deseos y mensajes especiales para mi. Estaré encantada de leerlos y guardarlos como un precioso recuerdo." 
        buttonText="enviar mensaje"
        buttonStyleClass="button-default"
        buttonUrl="https://forms.gle/37V2FYBQfcm19dtt5"
        buttonNewTab={true} 
    />
</div>