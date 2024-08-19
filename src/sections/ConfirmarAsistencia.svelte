<script>
	import Text from './../components/Text.svelte';
    
</script>


<style>
    .Confirmar {
        width: 100%;
        padding: 2rem 10% 4rem;
    }
    @media (min-width: 768px) {
        .Confirmar {
            padding: 2rem 20% 5rem;
        }
    }
    @media (min-width: 1024px) {
        .Confirmar {
            padding: 2rem 25% 6rem;
        }
    }
</style>


<div class="Confirmar">
    <Text 
        text="Tu presencia es muy importante para mi. Por favor, confirma tu asistencia llenando el siguiente formulario. ¡Estoy ansiosa de celebrar con vos!" 
        buttonText="confirmar asitencia"
        buttonStyleClass="button-default"
        buttonUrl="https://forms.gle/LjnvsKy1PiRbNTBo8"
        buttonNewTab={true} 
        />
</div>