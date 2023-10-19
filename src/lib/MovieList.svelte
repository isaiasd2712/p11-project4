<script>
    import { onMount } from "svelte"
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

<div>
{#each movies as movie }
    <img alt= "Cover" src= {`https://image.tmdb.org/t/p/original/${movie.poster_path}`}>
{/each}
</div>


<style>
    div{
        display: flex;
        flex-wrap: wrap;
        gap: 20px;
       
    }
    img{
        height: 250px;
        width: 175px;
        object-fit: cover;
        border-radius: 5px;
        cursor: pointer;
    }
</style>