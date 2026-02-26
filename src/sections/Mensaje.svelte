<script>
	import Text from './../components/Text.svelte';
    import Button from '../components/Button.svelte';
    
    export let buttonText = "enviar mensaje";
    export let buttonUrl = "https://forms.gle/MzKdJghFNTjvfGAm9";
    export let buttonNewTab = true;
    export let buttonStyleClass = "button-secondary";

    import rosa9 from "../images/9.png";
    import rosa10 from "../images/10.png";
</script>


<style>
    .Mensaje {
        width: 100%;
        background-color: var(--softLinen);
        box-shadow: 5px 0px 45px 0px rgb(119, 136, 91, 0.8) inset;
        padding: 7rem 10%;
        display: flex;
        align-items: center;
        justify-content: center;
    }
    img {
        height: 4.4rem;
        margin-bottom: 0.5rem;
    }
    .rosasArriba {
        width: 100%;
        position: absolute;
        z-index: 15;
        display: flex;
        align-items: center;
        justify-content: space-between;
        transform: rotate(180deg);
    }
    .rosasAbajo {
        width: 100%;
        position: absolute;
        z-index: 15;
        display: flex;
        flex-direction: row-reverse;
        align-items: center;
        justify-content: space-between;
        bottom: 0;
    }
    .rosas {
        width: 100%;
        height: 27rem;
        position: absolute;
        display: flex;
        flex-direction: column;
    }
    .rosa9 {
        width: 7.5rem;
        height: auto;
    }

    .rosa10 {
        width: 8rem;
        height: auto;
    }
    @media (min-width: 430px) {
        img {
            margin-bottom: 0.7rem;
        }
        .Mensaje {
            padding: 8rem 20%;
        }
        .rosas {
            height: 30rem;
        }
        .rosa9 {
            width: 8.5rem;
            height: auto;
        }

        .rosa10 {
            width: 9rem;
            height: auto;
        }
    }
    @media (min-width: 768px) {
        img {
            margin-bottom: 0.7rem;
        }
        .Mensaje {
            padding: 8rem 20%;
        }
        .rosa9 {
            width: 9.5rem;
            height: auto;
        }

        .rosa10 {
            width: 10rem;
            height: auto;
        }
    }
    @media (min-width: 1024px) {
        .Mensaje {
            padding: 8rem 25%;
        }
        .rosas {
            height: 30rem;
        }
        .rosa9 {
            width: 11rem;
            height: auto;
        }

        .rosa10 {
            width: 11.5rem;
            height: auto;
        }
    }
</style>


<div class="Mensaje">
    <Text 
        buttonStyleClass="button-none"
    >
    ¿Querés dejarle un mensaje de cariño a Ailín? Escribí tus buenos deseos; ella estará encantada de leerlos y guardarlos como recuerdo.
    </Text>

    <Button text={buttonText} styleClass={buttonStyleClass} url={buttonUrl} newTab={buttonNewTab}/>

    <div class="rosas">
        <div class="rosasArriba">
            <img src={ rosa9 } alt="" class="rosa9">
            <img src={ rosa10 } alt="" class="rosa10">
        </div>
        <div class="rosasAbajo">
            <img src={ rosa10 } alt="" class="rosa9">
            <img src={ rosa9 } alt="" class="rosa10">
        </div>
    </div>
    
</div>