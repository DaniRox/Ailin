<script>
    import { onMount } from 'svelte';

let dias = 0;
let horas = 0;
let minutos = 0;

// Fecha del evento
const eventDate = new Date('2024-11-02T21:00:00');

// Función para calcular el tiempo restante
function calcularTiempoRestante() {
    const ahora = new Date();
    const tiempoRestante = eventDate - ahora;

    if (tiempoRestante > 0) {
        dias = Math.floor(tiempoRestante / (1000 * 60 * 60 * 24));
        horas = Math.floor((tiempoRestante % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
        minutos = Math.floor((tiempoRestante % (1000 * 60 * 60)) / (1000 * 60));
    } else {
        dias = 0;
        horas = 0;
        minutos = 0;
    }
}

// Actualizar el contador cada minuto
onMount(() => {
    calcularTiempoRestante();
    const intervalo = setInterval(calcularTiempoRestante, 60000); // Actualiza cada minuto

    // Limpiar intervalo cuando se destruya el componente
    return () => clearInterval(intervalo);
});
</script>


<style>
    .Contador {
        width: 100%;
        padding: 4rem 10%;
    }
    .title {
        color: var(--smokyBlack);
        text-align: center;
        font-size: 1.3rem;
        font-weight: 400;
        margin-bottom: 3rem;
    }
    .container {
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap: 2rem;
    }
    .card-contador{
        color: var(--smokyBlack);
        width: 8rem;
        height: 8rem;
        background-color: var(--mistyRose);
        display: flex;
        justify-content: center;
        align-items: center;
        flex-direction: column;
        border-radius: 0.6rem;
        font-size: 1.5rem;
        font-weight: 500;
        gap: 1.2rem;
        box-shadow: 0px 2px 7px 2px rgba(36,30,16,0.40);
    }
    .card-text {
        color: var(--smokyBlack);
        font-size: 0.9rem;
        font-weight: 500;
        text-transform: uppercase;
    }
    @media (min-width: 768px) {
        .Contador {
            padding: 5rem 20%;
        }
        .container {
            gap: 2.5rem;
        }
    }
    @media (min-width: 1024px) {
        .Contador {
            padding: 6rem 25%;
        }
        .card-contador{
            width: 8rem;
            height: 10rem;
        }
        .container {
            gap: 3rem;
        }
    }
</style>


<div class="Contador">
    <p class="title">Faltan...</p>
    <div class="container">
        <div class="dias card-contador">{dias}<p class="card-text">dias</p></div>
        <div class="minutos card-contador">{horas}<p class="card-text">horas</p></div>
        <div class="segundos card-contador">{minutos}<p class="card-text">minutos</p></div>
    </div>
</div>