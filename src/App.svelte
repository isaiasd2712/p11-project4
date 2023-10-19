<script>
  import Header from "./lib/Header.svelte"
  import MovieList from "./lib/MovieList.svelte"
  import Categorias from "./lib/Categorias.svelte"
</script>
<Header />
<MovieList url= 'https://api.themoviedb.org/3/movie/popular?language=es-ES&page=1'/>
<MovieList url= 'https://api.themoviedb.org/3/movie/now_playing?language=en-US&page=1'/>
<Categorias/>
