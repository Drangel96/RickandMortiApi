<script>
	export let datos;
</script>


<li id="buscadorPer"
class= "bg-gray-200 col-span-1 flex flex-col divide-y divide-gray-200 rounded-lg bg-white text-center shadow"
>
<a href="/aboute">
    <div class="flex flex-1 flex-col p-8">
        <img class="mx-auto h-32 w-32 flex-shrink-0 rounded-full" src={datos['image']} alt="" />

        <h3 class="mt-6 text-sm font-medium text-gray-900">{datos['name']}</h3>

        <dl class="mt-1 flex flex-grow flex-col justify-between">
            <dd class="text-sm text-gray-500">{datos['location']['name']}</dd>
            <dd class="mt-3">
                <span
                    class="inline-flex items-center rounded-full bg-green-50 px-4 py-2 text-xs font-medium text-green-700 ring-1 ring-inset ring-green-600/20"
                    >{datos['species']}</span
                >
            </dd>
        </dl>

    </div> 

    <div>
        <div class="-mt-px flex divide-x divide-gray-200">
            <div class="flex w-0 flex-1">
                <a
                    href="mailto:janecooper@example.com"
                    class="relative -mr-px inline-flex w-0 flex-1 items-center justify-center gap-x-3 rounded-bl-lg border border-transparent py-4 text-sm font-semibold text-gray-900"
                    >Creado:
                    {datos['created']}
                </a>
            </div>
        </div>
    </div>
</a>
</li>

