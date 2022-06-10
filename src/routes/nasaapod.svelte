<script>
    import { onMount } from 'svelte'
     let mySource='';
    let info='';

    

    onMount(async () => {
        let API_KEY='whyrorqrXEAg69eru0U3QaGuAeBq9da4bQh09YfW'
        let response= await fetch('https://api.nasa.gov/planetary/apod?api_key='+API_KEY)
		let data= await response.json()
        info= data.explanation
        mySource=data.url
	});




</script>

<div class="content">
    
<h1 class="text-3xl hover:text-indigo-800">

    Today's NASA Astronomy Picture of the Day
</h1>

<p><span class="text-indigo-600 hover:underline">Description: </span> <span>{info}</span></p>
<div class="ring-2 ring-offset-2 ring-slate-300 hover:ring-indigo-900 max-w-fit">
<img src="{mySource}" alt="Today APOD">
</div>
</div>

<style>
    .content {
        place-items: center;
    }

    img { height: auto;
    width:100%;

    }
</style>
