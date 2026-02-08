<script>
    import imgBackground from "../images/fondo_rallas.jpg";
    import tagAilin from "../images/tag_ailin.png";
</script>


<style>
    .Hero {
        height: 90vh;
        overflow: hidden;
    }
    .shadow {
        width: 100%;
        height: 100%;
        position: relative;
        background-color: transparent;
        box-shadow: 2px 0px 31px 0px rgba(12,17,12,0.51) inset;
        z-index: 15;
    }
    .div-img {
        overflow: hidden;
        justify-content: center;
        z-index: 1;
    }
    .background {
        max-width: 100rem;
    }
    .tag {
        height: 17rem;
        margin-top: -3rem;
        z-index: 10;
    }
    .text {
        width: 100%;
        height: 100%;
        top: -1rem;
        position: absolute;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    @media (min-width: 430px) {
        .Hero {
            height: 90vh;
        }
        .div-img {
            overflow: hidden;
            position: relative;
        }
        .tag {
            height: 26rem;
        }

    }
    @media (min-width: 768px) {
        .Hero {
            height: 90vh;
        }
        .tag {
            height: 30rem;
        }
    }
    @media (min-width: 1024px) {
        .Hero {
            height: 90vh;
        }
        .tag {
            height: 35rem;
        }
    }
</style>


<div class="Hero">
    <div class="shadow">
        <div class="div-img">
            <img src={ imgBackground } alt="" class="background">  
        </div>

        <div class="text">
            <img src={ tagAilin } alt="" class="tag">
        </div>
    </div>
</div>