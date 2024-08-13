<script>
    import imgBackground from "../images/fondo-hero-s.jpg";
    import textFooter from "../images/text-footer.png";
</script>


<style>
    .Hero {
        height: 41rem;
        position: relative;
    }
    .div-img {
        overflow: hidden;
        display: flex;
        justify-content: center;
        height: 100%;
        transform: rotate(180deg);
    }
    .img {
        max-width: max-content;
    }
    .textFooter {
        height: 7rem;
        margin: 0.5rem 0;
    }
    .text {
        width: 100%;
        height: 100%;
        top: 0;
        position: absolute;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    @media (min-width: 650px) {
        .Hero {
            overflow: hidden;
        }
        .div-img {
            overflow: hidden;
            position: relative;
        }
        .img {
            width: 100%;
            max-width: none;
            position: inherit;
            height: min-content;
        }
        
        .textFooter {
            height: 10rem;
            margin: 0.6rem 0;
        }
    }
    @media (min-width: 1024px) {
        .Hero {
            height: 33rem;
        }
        .img {
            top: -8rem;
        }
        .textFooter {
            height: 12rem;
            margin: 0.9rem 0;
        }
    }
</style>


<div class="Hero">
    <div class="div-img">
        <img src={ imgBackground } alt="" class="img">  
    </div>
    <div class="img">   
    </div>
    <div class="text">
        <img src={ textFooter } alt="" class="textFooter">
    </div>
</div>