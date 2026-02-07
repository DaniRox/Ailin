<script>
    import Button from "./Button.svelte";
    import { createEventDispatcher } from 'svelte'; // Importamos esto

    export let buttonText = "click";
    export let buttonUrl = "#";
    export let buttonNewTab = false;
    export let buttonStyleClass = "button-default";

    const dispatch = createEventDispatcher();

    // Función que maneja el clic
    function handleClick(event) {
        // Si NO hay URL (o está vacía), significa que queremos abrir el modal
        // Si hay URL, dejamos que el botón actúe como enlace normal
        if (!buttonUrl || buttonUrl === '#') {
            event.preventDefault(); // Evita que el enlace recargue la página
            dispatch('click'); // Envía el evento 'click' al padre
        }
    }
</script>


<style>
    div {
        display: flex;
        flex-direction: column;
        align-items: center;
        align-self: center;
            max-width: 30rem;
    }
    p {
        color: var(--onyx);
        text-align: center;
        font-size: 1.1rem;
        font-weight: 500;
        line-height: 1.4rem;
        padding-bottom: 0.4rem;
    }
    @media (min-width: 430px) {
        p {
            font-size: 1.2rem;
        }
    }
</style>


<div>
    <p><slot /></p>
    <Button 
        text={buttonText} 
        styleClass={buttonStyleClass} 
        url={buttonUrl} 
        newTab={buttonNewTab}
        on:click={handleClick}
    />
</div>