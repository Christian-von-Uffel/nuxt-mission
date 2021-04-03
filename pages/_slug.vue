<template>
    <div>
        {{ $route.params.slug }}
        <pre>
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