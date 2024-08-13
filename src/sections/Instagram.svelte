<script>
	import Text from './../components/Text.svelte';
    import imgTitle from "../images/titleInstagram.png";
    import Button from '../components/Button.svelte';

    export let buttonText = "ir a instagram";
    export let buttonUrl = "https://www.instagram.com/morexv.eventus.2024?igsh=MTZ0ZnFmbzFtZDR4NQ==";
    export let buttonNewTab = true;
    export let buttonStyleClass = "button-default";
</script>


<style>
    .Instagram {
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
    .card {
        width: 80%;
        background-color: var(--timberwolf);
        padding: 2rem;
        margin: 1rem 10%;
        border-radius: 1rem;
        margin-bottom: 2rem;
        display: flex;
        flex-direction: column;
    }
    h3 {
        font-size: 1rem;
        font-weight: 400;
        line-height: 1.4rem;
        padding-bottom: 0.8rem;
    }
    p {
        font-size: 0.8rem;
        font-weight: 400;
        line-height: 1.2rem;
        padding-bottom: 0.8rem;
    }
    @media (min-width: 768px) {
        img {
            margin-bottom: 0.7rem;
        }
        .Instagram {
            padding: 5rem 20%;
        }
        .card {
            width: 60%;
        }
    }
    @media (min-width: 1024px) {
        .Instagram {
            padding: 6rem 25%;
        }
    }
</style>


<div class="Instagram">    
    <img src={imgTitle} alt="Titulo: Instagram">
    <Text
        text="¡Unite a la Fiesta en Instagram!" 
        buttonStyleClass="button-none"
        />
    <Text text="Para que la celebración sea aún más especial, creamos un perfil en Instagram dedicado al gran evento.
        " buttonStyleClass="button-none"/>
    <div class="card">
        <p>Seguínos en @MoreXV.eventus.2024 para:</p>
        <p>Conocer los Detalles: Mantenete al tanto de toda la información importante y actualizaciones sobre la fiesta.</p>
        <p>Interacción Previa: Participá en encuestas, juegos y actividades emocionantes antes del gran día.</p>
        <p>Fotos del Evento: Reviví los momentos más destacados y descubrí las fotos de la fiesta después del evento.</p>
        <p>¡No te lo pierdas! Conéctate con nosotros en Instagram y prepárate para disfrutar de una experiencia inolvidable." </p>
    </div>
    <Button text={buttonText} styleClass={buttonStyleClass} url={buttonUrl} newTab={buttonNewTab}/>
</div>