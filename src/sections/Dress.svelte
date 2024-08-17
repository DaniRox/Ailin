<script>
	import Text from './../components/Text.svelte';
    import imgTitle from "../images/titleDress.png";
    import imgIcon from "../images/dress.png";
</script>


<style>
    .Dress {
        background-color: var(--timberwolf);
        width: 100%;
        padding: 4rem 10%;
        display: flex;
        flex-direction: column;
        align-items: center;
    }
    img {
        height: 4.5rem;
        margin-bottom: 0.5rem;
    }
    .dressIcon {
        height: 20rem;
    }
    @media (min-width: 768px) {
        img {
            margin-bottom: 0.7rem;
        }
        .Dress {
            padding: 5rem 20%;
        }
    }
    @media (min-width: 1024px) {
        .Dress {
            padding: 6rem 25%;
        }
        .dressIcon {
            height: 9rem;
        }
    }
</style>


<div class="Dress">
    <img src={imgTitle} alt="Titulo DressCode">
    <Text 
        text="Elegante" 
        buttonStyleClass="button-none"
        />
    <img src={imgIcon} alt="icono" class="dressIcon">
</div>