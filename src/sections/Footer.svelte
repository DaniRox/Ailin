<script>
    import imgBackground from "../images/fondo_rallas.jpg";
    import textFooter from "../images/Los_esperamos.png";
    
    import rosa9 from "../images/9.png";
    import rosa10 from "../images/10.png";
</script>


<style>
    .Footer {
        height: 15rem;
        overflow: hidden;
        display: flex;
        align-items: flex-end;
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
        height: 7rem;
        z-index: 20;
    }
    .text {
        width: 100%;
        padding-bottom: 2rem;
        position: absolute;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        align-self: center;
    }

    .rosa9 {
        width: 7.5rem;
        height: auto;
    }

    .rosa10 {
        width: 8rem;
        height: auto;
    }
    .rosas {
        width: 100%;
        position: absolute;
        z-index: 15;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-between;
    }

    @media (min-width: 430px) {
        .Footer {
            height: 26rem;
        }
        .div-img {
            overflow: hidden;
            position: relative;
        }
        .tag {
            height: 8rem;
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
        .Footer {
            height: 28rem;
        }
        .tag {
            height: 9rem;
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
        .Footer {
            height: 30rem;
        }
        .tag {
            height: 14rem;
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


<div class="Footer">
    <div class="div-img">
        <img src={ imgBackground } alt="" class="background">  
    </div>
    <div class="text">
        <img src={ textFooter } alt="" class="tag">
    </div>

    <div class="rosas">
        <img src={ rosa9 } alt="" class="rosa9">
        <img src={ rosa10 } alt="" class="rosa10">
    </div>
</div>