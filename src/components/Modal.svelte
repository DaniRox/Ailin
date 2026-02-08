<script>
    export let isOpen = false; // Recibe si está abierto o cerrado
    export let close = () => {}; // Recibe la función para cerrar

    // Cerrar si se hace clic fuera del contenido (en el fondo oscuro)
    function handleBackgroundClick(e) {
        if (e.target === e.currentTarget) {
            close();
        }
    }
</script>

{#if isOpen}
    <div class="modal-overlay" on:click={handleBackgroundClick}>
        <div class="modal-content">
            <button class="close-button" on:click={close}>&times;</button>
            <slot />
            <!-- Aquí va el contenido específico del regalo -->
        </div>
    </div>
{/if}

<style>
    .modal-overlay {
        position: fixed;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        padding: 2rem 0;
        background: rgba(0, 0, 0, 0.6); /* Fondo semitransparente */
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 1000;
    }

    .modal-content {
        background-color: var(--seasShell);
        padding: 2rem;
        border-radius: 10px;
        max-width: 90%;
        width: 400px;
        position: relative;
        box-shadow: 0 4px 15px rgba(0,0,0,0.3);
        color: var(--onyx);
    }

    .close-button {
        position: absolute;
        top: 10px;
        right: 15px;
        font-size: 1.9rem;
        background: none;
        border: none;
        cursor: pointer;
        color: #666;
    }
</style>