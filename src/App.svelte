<script>

  import Home from "./pages/Home.svelte";
  import Memes from "./pages/Memes.svelte";
  let query_name = window.location.search;

</script>



  <nav class="nav">

	<a class="menulink" href="/">Home</a>
	<a class="menulink" href="/padlets">Padlets</a>
  </nav>


<div>
	{#if query_name==""}
		<Home />
		{:else}
		<Memes padlet_user="nicovalespazio" padlet_name="fnsef2dqbbj25udd" query_name="?padlet_name=fnsef2dqbbj25udd"/>
	{/if}
</div>


<style>
	
	.nav {
	  background-color: #29292a;
	  padding-right: 50%;
	  padding-left: 50%;
	  padding-bottom: 1.5%;
	  padding-top: 1.5%;
	  display: grid;
	  grid-template-columns: auto auto;
	}
	a {
		color: white;
		padding: 20px;
	  border: 0;
	}
	a:hover {
		background-color: #151515;
	}

  

  </style>
  