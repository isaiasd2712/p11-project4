<script>
    import { onMount } from "svelte";
    export let url; 
        
    const options = {
    method: 'GET',
    headers: {
        accept: 'application/json',
        Authorization: 
            'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJlYjgxOGQ3OTBlNGM5Yjk3OTE3ZTYwYzNmZTEyNDg1YyIsInN1YiI6IjY1MmU1YzFhY2FlZjJkMDExY2M2YjhjMCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.sAD1CNXRs8zjfVeGuw2hlE0sVU164QtqTo_VsoGA4lU'
  }
};
    
    let movies= [];

    onMount(() => 
        fetch(url , options)
            .then((response) => response.json())
            .then((data) => (movies = data.results))
            .catch((err) => console.error(err))
    );
    let containerslider;
    let scrollValue = 0;

    const right = () => {
        if (containerslider) {
      scrollValue += 100;
      containerslider.scroll({ left: scrollValue, behavior: "smooth" });
    }
    };
    const left = () => {
        if (containerslider) {
      scrollValue -= 100;
      containerslider.scroll({ left: scrollValue, behavior: "smooth" });
    }
    };
</script>

<button on:click={left} class="left"></button>
<button on:click={right} class="right"></button>

<section>
<p> New Arrival </p>


<div bind:this={containerslider}>

    
{#each movies as movie }

    <img alt= "Cover" src= {`https://image.tmdb.org/t/p/original/${movie.poster_path}`}/>
   
{/each}
</div>


</section>

<style>
    section{
        margin-left: 40px;
    }
    p{
        color:white;
        font-weight: bold;
        font-size: larger;
        font-family: Graphik,-apple-system,BlinkMacSystemFont,"Segoe UI","Helvetica Neue",Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
        padding-top: 20px;
    }
    div{
        width: 95%;
        display: flex;
        justify-content: start;
        flex-wrap: nowrap;
        gap: 20px;
        overflow-x: scroll;
        overflow-y: hidden;
        padding-top: 20px;
        

       
    }
    img{
        height: 250px;
        width: 175px;
        object-fit: cover;
        border-radius: 5px;
        cursor: pointer;
        margin-top: 20px;
    }
    button{
        position: absolute;

    }
    .left{
        height: 24px;
        width: 24px;
        background: url(./src/assets/Btn-option.png);
        left: 0;
        transform: rotate(90deg);
        border: 0;
        background-repeat: no-repeat;
    }
    .right{
        height: 20px;
        width: 24px;
        background: url(./src/assets/Btn-option.png);
        right: 0;
        transform: rotate(-90deg);
        border: 0;
        background-repeat: no-repeat;
    }
    
</style>
    

