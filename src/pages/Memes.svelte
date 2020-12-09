<script>
    export let padlet_name;
    export let padlet_user;
    export let query_name;
    let page_query_name = window.location.search;
    import {onMount} from "svelte";
    let posts = [];
    if (query_name === page_query_name){
        onMount(async()=>{
        fetch("https://9bu70x.deta.dev/v1/padlet/?padlet_username=" +padlet_user +"&padlet_name="+padlet_name)
        .then(myres=>myres.json())
        .then((myjson)=>{console.log(myjson.posts); posts = myjson.posts})
    })
    }
    let a = "caner";
    function splitattachemte(attachname) {
        let url_array = attachname.split("/")
        return (url_array[url_array.length-1])
    }
</script>

<h1 class="title">
   I meme della 2B
</h1>
<div class="container">
    {#if query_name == page_query_name}
    {#each posts as post}
    <div class="ext_post_container">
        <div class="post_container">
            {#if post.subject!= ""}
            <h3>{post.subject}</h3>
            {/if}
        {#if post.attachment_type == "image/jpeg"}
        <picture>
            <img src={post.attachment} alt="img" height="200">
        </picture>
        {:else}
        <a href={post.attachment}>{splitattachemte(post.attachment)}</a>
        {/if}
        </div>
    </div>
        {:else}
        <h3>Loading...</h3>
        
    {/each}
        {:else}
        <h1>404 error, page not found</h1>
    {/if}
    
</div>

<style>
    a {
        color: #292929;
    }
    .title {
        padding-left: 0px;
        color: #555555;
    }
    .container{
        padding: 20px;
        display: grid;
        color: #555555;
        
    }
    @media (max-width: 799px) {
        .container{
            grid-template-columns: auto;
        }
    }
    @media (min-width:800px) and (max-width: 1399px) {
        .container{
            grid-template-columns: auto auto;
        }
    }
    @media (min-width: 1400px) {
        .container{
            grid-template-columns: auto auto auto;
        }
    }
    .post_container {
        border: 2px solid #808080;
    padding: 20px;
    }
    .ext_post_container {
        padding: 10px;
    }
</style>