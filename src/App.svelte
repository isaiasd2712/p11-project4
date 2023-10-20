<script>
  import Header from "./lib/Header.svelte"
  import MovieList from "./lib/MovieList.svelte"
  import Categorias from "./lib/Categorias.svelte"
  import TopRated from "./lib/TopRated.svelte"
  import UpComing from "./lib/UpComing.svelte"
</script>
<Header />
<UpComing url= 'https://api.themoviedb.org/3/movie/upcoming'/>
<MovieList url= 'https://api.themoviedb.org/3/movie/popular?language=es-ES&page=1'/>
<Categorias url= 'https://api.themoviedb.org/3/movie/now_playing'/>
<TopRated url= 'https://api.themoviedb.org/3/movie/top_rated
'/>
