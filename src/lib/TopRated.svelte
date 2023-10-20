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
</script>
<p> Top Rated </p>
<div>
    
{#each movies as movie }

    <img alt= "Cover" src= {`https://image.tmdb.org/t/p/original/${movie.poster_path}`}/>
   
{/each}
</div>


<style>
    p{
        color:white;
        font-weight: bold;
        font-size: larger;
        font-family: Graphik,-apple-system,BlinkMacSystemFont,"Segoe UI","Helvetica Neue",Arial,sans-serif,"Apple Color Emoji","Segoe UI Emoji","Segoe UI Symbol","Noto Color Emoji";
        padding-top: 20px;
    }
    div{
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
    }
</style>