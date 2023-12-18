
<script>
    //Se genera un vinculo de las librerias sobre los componentes de la pagina 
	import Personaje from '$lib/components/Personaje.svelte';
    import Dato from '$lib/components/Dato.svelte';

	//1.- se crea una variable para almacenar los datos de los personajes obtenidos 
	let personajes = [];
    //2.- se crea un espacio para guardar la url de la appi que se utiliza para obtener los datos de los personajes 
	const urlPersonajes = 'https://rickandmortyapi.com/api/character?page=4';

    //3.- la funcion asincrona nos ayuda a generar la solicitud a la API y obtener los datos de los personajes 
	async function descargarPersonajes(url) {

        //4.- Solicitud a la Api:  realizar la solicitud HTTP a la URL  especificada en el parámetro url de la función. 
        // La función fetch devuelve una promesa que se resuelve con la respuesta de la solicitud.
		const respuesta = await fetch(url);

        //5.-Verificación de respuesta,  Si la respuesta es exitosa, se procede a procesar los datos.
		if (respuesta.ok) {

            //6.-Procesamiento de los datos se da una pausa a que se obtengan los datos con await y despues convierte los datos obtenidos a JSON y lo guarda a la variable contenido 
			const contenido = await respuesta.json();
            //asigna el arreglo de personajes obtenido de la respuesta a la variable personajes
			personajes = contenido['results'];
		}
	}
    //7.- Se llama ala funcion , pasando la url como argumento 
	descargarPersonajes(urlPersonajes);

    export let data;
</script> 


<div class="py-10">
	<header>
		<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
			<h1 class="text-3xl font-bold leading-tight tracking-tight text-gray-900">Rick and Morty API </h1>
		</div>
	</header>

</div>

<!-- each sirve para recorrer arrays -->
<ul class="divide-y divide-gray-100">

</ul>


<ul id="buscador" role="list" class="grid grid-cols-1 gap-6 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 py-8">

    {#each data.summaries as {slug, title} }
        <button>{title}</button>
    {/each}



</ul>

<Dato />

