<script>
	import Text from './../components/Text.svelte';
    import Modal from './../components/Modal.svelte';
    import imgDuplicate from "../images/Duplicate.png";

    let mostrarModal = false;

    function toggleModal() {
        mostrarModal = !mostrarModal;
    }

    async function copiarTexto(texto) {
        try {
            await navigator.clipboard.writeText(texto);
            alert('¡Texto copiado al portapapeles!'); // Opcional: puedes usar un toast en lugar de alert
        } catch (err) {
            console.error('Error al copiar: ', err);
        }
    }
</script>


<style>
    .Regalos {
        width: 100%;
        padding: 7rem 10%;
        display: flex;
        flex-direction: column;
        align-items: center;
        background-color: var(--almondCream);
        box-shadow: 5px 0px 45px 0px rgb(152, 139, 121, 0.8) inset;
    }
    .title{
        color: var(--onyx);
        text-align: center;
        font-size: 1.8rem;
        font-weight: 700;
    }
    .text {
        color: var(--onyx);
        text-align: center;
        font-size: 1.6rem;
        font-weight: 600;
    }
    .text2 {
        margin-bottom: 3rem;
    }
    .text-modal {
        color: var(--onyx);
        text-align: center;
        font-size: 1rem;
        font-weight: 300;
        text-transform: uppercase;
        font-family:'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    }
    .container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 1rem;
    }
    .tag {
        width: 23rem;
        position: absolute;
        z-index: 1;
        padding-left: 2rem;
        padding-bottom: 1.5rem;
    }
    img {
        width: 1.2rem;
    }
    .renglon {
        display: flex;
        flex-direction: row;
        justify-content: center;
        align-items: center;
        gap: 0.5rem;
        padding: 0.3rem 0;
    }
    .card-Regalos{
        width: 3rem;
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        font-size: 2.5rem;
        font-weight: 500;
        gap: 1rem;
        z-index: 2;
    }
    .card-text {
        color: var(--smokyBlack);
        font-size: 0.9rem;
        font-weight: 500;
        text-transform: uppercase;
    }

    .button-secondary {
        font-size: 0.9rem;
        padding: 0.5rem 0.7rem;
        font-weight: 500;
        border-radius: 0.15rem;
        text-transform: uppercase;
        transition: all 0.3s;
        margin-top: 1.6rem;
        background-color: var(--tan);
        color: var(--oldRose);
        box-shadow: 0px 2px 4px 1px rgba(36,30,16,0.60);
    }

    .button-secondary:hover {
        background-color: var(--khakiBeigeHover);
        transform: scale(1.03);
        box-shadow: 0px 2px 6px 3px rgba(36,30,16,0.40);
    }

    .button-secondary:active {
        background-color: var(--btnSecondaryClick);
        transform: scale(0.96);
        box-shadow: 0px 2px 0px 0px rgba(36,30,16,0.40);
    }

    @media (min-width: 430px) {
        .Regalos {
            padding: 8rem 20%;
        }
    }
    @media (min-width: 768px) {
        .Regalos {
            padding: 10rem 20%;
        }
        .tag {
            width: 26rem;
            padding-left: 2rem;
            padding-bottom: 2rem;
        }
        .text-modal {
            font-size: 1.2rem;
        }
        .text {
            font-size: 1.8rem;
        }
        .title{
            font-size: 2rem;
        }
        .card-Regalos{
            width: 4rem;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            font-size: 3.5rem;
            font-weight: 500;
            gap: 1rem;
            z-index: 2;
        }
        .card-text {
            font-size: 1.1rem;
        }
        .button-secondary {
            font-size: 0.9rem;
            font-weight: 500;
            border-radius: 0.3rem;
            text-transform: uppercase;
            transition: all 0.3s;
        }
    }
    @media (min-width: 1024px) {
        .Regalos {
            padding: 8rem 25%;
        }
    }
</style>


<div class="Regalos">
    <Text 
        buttonStyleClass="button-none"
        buttonNewTab={false} 
    >
        El mejor regalo es que compartas este momento con nosotros.
        <br>
        Sin embargo, si deseas hacerle un obsequio económico a Ailín para que ella lo disfrute a su gusto, podés hacerlo aquí de manera fácil y segura.
    </Text>

    <button on:click={toggleModal} class="button-secondary">Enviar regalo</button>
</div>

<Modal 
    isOpen={mostrarModal} 
    close={toggleModal}
>
    <h2 class="title">Datos para el Regalo</h2>
    <br>

    <p class="text-modal">Nombre: Ailin Eluney Benitez</p>

    <div class="renglon">
        <p class="text-modal">Alias: ailin.786.abuela.mp</p>
        <button class="btn-copy" on:click={() => copiarTexto("ailin.786.abuela.mp")} title="Copiar alias">
            <img src={imgDuplicate} alt="img">
        </button>
    </div>


    <br>
    <p class="text">¡Muchas gracias!</p>
</Modal>

    