<script>
	import Text from './../components/Text.svelte';
    import imgInsta from "../images/instagram.png";
    import Button from '../components/Button.svelte';
    import tagInsta from "../images/tag-insta.png";

    export let buttonText = "ir a instagram";
    export let buttonUrl = "https://www.instagram.com/eventus.invitacionesdigitales/";
    export let buttonNewTab = true;
    export let buttonStyleClass = "button-default";
</script>


<style>
    .Instagram {
        width: 100%;
        padding: 7rem 10%;
        color: var(--onyx);
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    img {
        height: 2rem;
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
    p {
        font-size: 0.9rem;
        font-weight: 400;
        line-height: 1.2rem;
        padding-bottom: 0.8rem;
        z-index: 8;
    }
    .tag-insta {
        width: 12.5rem;
        height: auto;
        padding: 5rem 0 3rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
    }
    .insta {
        width: 17rem;
        height: auto;
        position: absolute;
        z-index: 5;
    }
    @media (min-width: 430px) {
        p {
            font-size: 1rem;
            font-weight: 400;
            line-height: 1.2rem;
            padding-bottom: 0.8rem;
            z-index: 8;
        }
        .tag-insta {
            width: 14rem;
            height: auto;
            padding: 5rem 0 3rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .insta {
            width: 19rem;
            height: auto;
            position: absolute;
            z-index: 5;
        }
    }
    @media (min-width: 768px) {
        img {
            margin-bottom: 0.7rem;
        }
        p {
            font-size: 1.1rem;
        }
        .Instagram {
            padding: 5rem 20%;
        }
        .card {
            width: 60%;
        }
        .tag-insta {
            width: 14rem;
            height: auto;
            padding: 5rem 0 3rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
        }
        .insta {
            width: 19rem;
            height: auto;
            position: absolute;
            z-index: 5;
        }
    }
    @media (min-width: 1024px) {
        .Instagram {
            padding: 6rem 25%;
        }
    }
</style>


<div class="Instagram">    
    <img src={imgInsta} alt="Logo Instagram">
    <Text
        buttonStyleClass="button-none"
    >
        ¡La emoción comienza antes de la fiesta!
        <br>
        Seguí la cuenta oficial de los XV de Ailín y participá de encuestas, juegos y anticipos exclusivos. 
        <br>
        No te quedes afuera de la diversión previa.
    </Text>

    <div class="tag-insta">
        <img src={ tagInsta } alt="" class="insta">
        <p>Cómo participar:</p>
        <p>1. Seguí la cuenta y activa las notificaciones para estar al día con las novedades.</p>
        <p>2. Respondé a las historias y jugá a las encuestas para interactuar con la festejada.</p>
        <p>3. El día del evento, compartí tus fotos y videos usando el hashtag #Los15deAilin</p>
    </div>

    <Button text={buttonText} styleClass={buttonStyleClass} url={buttonUrl} newTab={buttonNewTab}/>
</div>