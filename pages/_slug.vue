<template>
    <div class="mx-auto px-4 py-16">
        <img :src="planet.image" :alt="planet.title" class="max-w-sm rounded-lg shadow-lg overflow-hidden mx-auto">
        <h1 class="text-center text-3xl font-bold mt-12 mb-12">
        {{ planet.title }}
        </h1>
        <pre class="flex flex-wrap max-w-screen-md mx-auto">
            {{$data}}
        </pre>
    </div>
</template>

<script>
export default {
    async asyncData( {params}) {
        const planet = await fetch(`https://api.nuxtjs.dev/planets/${params.slug}`).then((res) => res.json())
        return { planet }
    }
}
</script>