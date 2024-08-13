<script>
	import Text from './../components/Text.svelte';

	const googleCalendarUrl = "https://www.google.com/calendar/render?action=TEMPLATE&text=Fiesta%20More%20XV&dates=20241102T210000Z/20241102T210000Z&details=Detalles%20del%20evento&location=Dirección%20del%20evento";
	const outlookCalendarUrl = "https://outlook.live.com/calendar/0/deeplink/compose?path=/calendar/action/compose&subject=Fiesta%20More%20XV&startdt=2024-11-02T21:00:00&body=Detalles%20del%20evento&location=Dirección%20del%20evento";
	const appleCalendarUrl = "https://tu-sitio.com/evento.ics"; // Reemplaza con el enlace al archivo .ics

	function getCalendarUrl() {
		if (/iPad|iPhone|iPod/.test(navigator.userAgent) && !window.MSStream) {
			// Dispositivo iOS
			return appleCalendarUrl;
		} else if (navigator.userAgent.includes("Windows") || navigator.userAgent.includes("Macintosh")) {
			// Desktop
			return outlookCalendarUrl;
		} else {
			// Otros dispositivos (Android, etc.)
			return googleCalendarUrl;
		}
	}

    const calendarUrl = getCalendarUrl();
</script>


<style>
    .Agendar {
        background-color: var(--timberwolf);
        width: 100%;
        padding: 4rem 10%;
    }
    @media (min-width: 768px) {
        .Agendar {
            padding: 5rem 20%;
        }
    }
    @media (min-width: 1024px) {
        .Agendar {
            padding: 6rem 25%;
        }
    }
</style>


<div class="Agendar">
    <Text 
        text="No te olvides de esta fecha tan especial. Hacé clic en el botón de abajo para agregar el evento a tu calendario y asegurar que no te pierdas este feliz momento." 
        buttonText="Agendar"
        buttonStyleClass="button-secondary"
        buttonUrl={calendarUrl}
        buttonNewTab={true} 
    />
</div>