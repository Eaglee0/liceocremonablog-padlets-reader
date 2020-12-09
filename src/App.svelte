<script>

  import Home from "./pages/Home.svelte";
  import Memes from "./pages/Memes.svelte";
  let query_name = window.location.search;

</script>



  <nav class="nav">

    <a class="menulink"><a class="test" id="test" href="/padlets">Home</a></a>
  </nav>


<div>
	{#if query_name==""}
		<Home />
		{:else}
		<Memes padlet_user="nicovalespazio" padlet_name="fnsef2dqbbj25udd" query_name="?padlet_username=nicovalespazio&padlet_name=fnsef2dqbbj25udd"/>
	{/if}
</div>


<style>
	
	.nav {
	  background-color: #29292a;
	  padding-right: 50%;
	  padding-left: 50%;
	  padding-bottom: 2%;
	  padding-top: 2%;
	  display: grid;
	  grid-template-columns: auto;
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
  