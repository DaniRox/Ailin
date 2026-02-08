<script>
    import { onMount } from 'svelte';
    import tagContador from "../images/tag_contador.png";

    let dias = 0;
    let horas = 0;
    let minutos = 0;

// Fecha del evento
const eventDate = new Date('2026-03-14T21:00:00');

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
        display: flex;
        flex-direction: column;
        align-items: center;
        width: 100%;
        padding: 7rem 10% 9rem;
        background-color: var(--almondCream);
        box-shadow: 5px 0px 45px 0px rgb(152, 139, 121, 0.8) inset;
    }
    .text {
        color: var(--onyx);
        align-self: center;
        max-width: 30rem;
        text-align: center;
        font-size: 1.2rem;
        font-weight: 500;
        margin-bottom: 3rem;
    }
    .text2 {
        margin-bottom: 3rem;
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
    .card-contador{
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
    @media (min-width: 430px) {
        .Contador {
            padding: 8rem 20% 10;
        }
        .text {
            font-size: 1.3rem;
        }
    }
    @media (min-width: 768px) {
        .Contador {
            padding: 10rem 20% 12;
        }
        .tag {
            width: 26rem;
            padding-left: 2rem;
            padding-bottom: 2rem;
        }
        .text {
            font-size: 1.4rem;
        }
        .card-contador{
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
    }
    @media (min-width: 1024px) {
        .Contador {
            padding: 8rem 25% 10;
        }
    }
</style>


<div class="Contador">
    <p class="text">
        Los momentos pasan,
        pero los recuerdos de este día
        quedarán grabados para siempre
        en el tiempo.</p>
    <p class="text text2">Faltan...</p>
    <div class="container">
        <img src={ tagContador } alt="" class="tag">  
        <div class="dias card-contador">{dias}<p class="card-text">dias</p></div>
        <div class="minutos card-contador">{horas}<p class="card-text">horas</p></div>
        <div class="segundos card-contador">{minutos}<p class="card-text">mins</p></div>
    </div>
</div>