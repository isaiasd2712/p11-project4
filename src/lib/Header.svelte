<script>
    import Logo from "./Logo.svelte";
    import Button from "./Button.svelte";
    import imagen from "../assets/Btn-option.png";
</script>
<header>
    <Logo />
    <nav>
        <a href="https//">Inicio</a>
        <a href="https//">Peliculas</a>
        <a href="https//">Series</a>
        <a href="https//">Colecciones</a>
        <a href="https//">Festivales</a>
        <a href="https//">Más</a>
        <img src={imagen} alt="imagen de busqueda">
        
    </nav>
   

    <Button></Button>
</header>

<style>
    
    header {
        width: 95%;
        display: flex;
        justify-content: flex-start;
        align-items: center;
        margin: 20px 40px;
        gap: 20px;
        color: white;
    }
    nav {
        display: flex;
        justify-content: flex-start;
        align-items: center;
        gap: 10px;
    }
    a {
        color: white;
        text-decoration: none;
        list-style: none;
        transition: text-shadow 0.4s ease;
    }
    a:hover{
        color: #00ff7b;
        transition: color 0.4s;
        text-shadow: 0 0 30px rgba(255, 255, 255);
         

    }
    img{
        width: 15px;
        height: 10px;
        cursor:pointer;
    }
    
</style>