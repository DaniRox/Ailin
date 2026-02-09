<script>
    import Text from './../components/Text.svelte';
    import imgTitle from "../images/Dress_Code.png";

    const evento = {
        titulo: "Ailín XV",
        ubicacion: "Av. Presidente Illia 10248, Tortuguitas",
        descripcion: "¡No te pierdas esta noche memorable! Inicio: 21:00 hs.",
        // Fecha y hora de inicio: 14 de Marzo de 2026, 21:00
        inicio: new Date("2026-03-14T21:00:00") 
        // ELIMINADO: La propiedad 'fin' para evitar errores de agendamiento
    };

    // Formato Google: AAAAMMDDTHHMMSS
    const formatoGoogle = (fecha) => {
        return fecha.toISOString().replace(/[-:]/g, '').split('.')[0];
    };

    // Formato Outlook: AAAA-MM-DDTHH:MM:SS
    const formatoOutlook = (fecha) => {
        return fecha.toISOString().slice(0, 19);
    };

    const codificar = (texto) => encodeURIComponent(texto);
    
    // CORRECCIÓN: Usamos 'evento.inicio' para el inicio Y para el final.
    // Esto fuerza a que el evento se agende solo en ese día y hora específica.
    const googleCalendarUrl = `https://www.google.com/calendar/render?action=TEMPLATE&text=${codificar(evento.titulo)}&dates=${formatoGoogle(evento.inicio)}/${formatoGoogle(evento.inicio)}&details=${codificar(evento.descripcion)}&location=${codificar(evento.ubicacion)}`;
    
    const outlookCalendarUrl = `https://outlook.live.com/calendar/0/deeplink/compose?path=/calendar/action/compose&subject=${codificar(evento.titulo)}&startdt=${formatoOutlook(evento.inicio)}&enddt=${formatoOutlook(evento.inicio)}&body=${codificar(evento.descripcion)}&location=${codificar(evento.ubicacion)}`;
    
    const appleCalendarUrl = "https://tu-sitio.com/evento.ics"; 

    function getCalendarUrl() {
        if (/iPad|iPhone|iPod/.test(navigator.userAgent) && !window.MSStream) {
            return appleCalendarUrl;
        } else if (navigator.userAgent.includes("Windows") || navigator.userAgent.includes("Macintosh")) {
            return outlookCalendarUrl;
        } else {
            return googleCalendarUrl;
        }
    }

    const calendarUrl = getCalendarUrl();
</script>


<style>
    .Agendar {
        background-color: var(--seasShell);
        box-shadow: 5px 0px 45px 0px rgb(152, 139, 121, 0.8) inset;
        width: 100%;
        padding: 7rem 10%;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 4rem;
    }
    .title {
        height: 5rem;
        margin-bottom: -3.5rem;
    }
    @media (min-width: 430px) {
        .Agendar {
            padding: 8rem 20%;
        }
        .title {
            height: 6.5rem;
        }
    }
    @media (min-width: 768px) {
        .Agendar {
            padding: 10rem 20%;
        }
        .title {
            height: 7rem;
        }
    }
    @media (min-width: 1024px) {
        .Agendar {
            padding: 8rem 25%;
        }
    }
</style>


<div class="Agendar">
    <Text 
        buttonText="Agendar fecha"
        buttonStyleClass="button-default"
        buttonUrl={calendarUrl}
        buttonNewTab={true} 
    >
    No dejes pasar esta fecha especial.
    <br>
    Sincronizá el evento en tu calendario y asegurá tu lugar en esta noche inolvidable.
    </Text>

    <img src={imgTitle} alt="Titulo DressCode" class="title">
    <Text 
        buttonStyleClass="button-none"
    >
        Para esta noche tan especial, queremos verte brillar. Pedimos que asistan con vestimenta elegante.
        <br>
        Aviso importante: El color verde está oficialmente vetado en todas sus variantes. Ailín ya tiene todo el brillo reservado para ella, así que ¡por favor, dejen ese color en el placard!
        <br><br>
        ¡Esperamos verlos radiantes y listos para disfrutar!
    </Text>
</div>