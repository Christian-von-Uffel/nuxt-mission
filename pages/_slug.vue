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
    async asyncData() {
        const planet = await fetch("https://api.nuxtjs.dev/planets/mars").then((res) => res.json())
        return { planet }
    }
}
</script>