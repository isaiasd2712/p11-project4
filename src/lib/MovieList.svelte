<script>
    const url = 
        'https://api.themoviedb.org/3/movie/popular?language=es-ES&page=1'
    const options = {
    method: 'GET',
    headers: {
        accept: 'application/json',
        Authorization: 'Bearer eyJhbGciOiJIUzI1NiJ9.eyJhdWQiOiJlYjgxOGQ3OTBlNGM5Yjk3OTE3ZTYwYzNmZTEyNDg1YyIsInN1YiI6IjY1MmU1YzFhY2FlZjJkMDExY2M2YjhjMCIsInNjb3BlcyI6WyJhcGlfcmVhZCJdLCJ2ZXJzaW9uIjoxfQ.sAD1CNXRs8zjfVeGuw2hlE0sVU164QtqTo_VsoGA4lU'
  }
};

    let movies= [];

    fetch(url , options)
        .then(response => response.json())
        .then(data => movies = data.results)
        .catch(err => console.error(err));
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
        justify-content: center;
        gap: 15px;
    }
    img{
        height: 151px;
        width: 275px;
        object-fit: cover;
    }
</style>