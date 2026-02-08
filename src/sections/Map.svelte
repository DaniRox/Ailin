<script>
	import Text from './../components/Text.svelte';
    import imgTitle from "../images/Cena_Fiesta.png";
    import rosas from "../images/rosas2.png";
</script>


<style>
    .title {
        height: 5rem;
        margin-bottom: -3.5rem;
        align-self: center;
    }
    .Ubicacion {
        width: 100%;
        background-color: var(--seasShell);
        box-shadow: 5px 0px 45px 0px rgb(152, 139, 121, 0.8) inset;
        padding: 7rem 10% 2rem;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        align-self: center;
        gap: 4rem;
    }
    iframe {
        width: 100%;
        height: 16rem;
        margin: 2rem;
        border-radius: 1rem;
    }
    .text {
        color: var(--onyx);
        text-align: center;
        font-size: 1.2rem;
        font-weight: 500;
        margin-bottom: 3rem;
        line-height: 1.2rem;
        align-self: center;
    }
    .rosas {
        max-width: none;
        width: 45rem;    
        margin-left: -5rem;
        height: auto;
        left: 0;
        position: relative;
        margin-top: -8rem;
        bottom: -6rem;
        z-index: 20;
    }

    @media (min-width: 430px) {
        .title {
            height: 6.5rem;
        }
        .Ubicacion {
            padding: 8rem 20% 2rem;
        }
        .rosas {
            width: 50rem;
            margin-left: -9rem;   
        }

    }
    @media (min-width: 768px) {
        .title {
            height: 7rem;
        }
        .Ubicacion {
            padding: 10rem 20% 2rem;
        }
        .rosas {
            width: 60rem;
            align-self: center;
            margin-left: 0rem; 
        }
    }
    @media (min-width: 1024px) {
        .Ubicacion {
            padding: 8rem 25% 2rem;
        }
        .rosas {
            width: 65rem;
            align-self: center;
            margin-left: 0rem; 
        }
    }
</style>


<div class="Ubicacion">
    <img src={imgTitle} alt="Titulo Cena y Fiesta" class="title">

    <Text 
        buttonText="ver mapa"
        buttonStyleClass="button-default"
        buttonUrl="https://maps.app.goo.gl/wmfqFpVKNurW99mE9"
        buttonNewTab={true} 
    >
    El escenario elegido para esta noche memorable...
    <br><br>
        Av. Presidente Illia 10248, Tortuguitas. 
        Inicio: 21:00 hs | Fin: 05:00 hs
    <br><br>
        ¡La fiesta arranca en punto y no queremos que te pierdas el comienzo!
    </Text>

    <Text 
        buttonText="confirmar ahora"
        buttonStyleClass="button-default"
        buttonUrl="https://forms.gle/u136ajgCFZXTq73h8"
        buttonNewTab={true} 
    >
        ¡Con vos la fiesta es completa!
        <br>
        Avisanos si nos acompañás. Tu confirmación es vital para recibirte como te mereces.
        <br><br>
        ¡Estamos ansiosos por celebrar junto a vos!
        
    </Text>

    <img src={rosas} alt="Rosas Rococo" class="rosas">
</div>