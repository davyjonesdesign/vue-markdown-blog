<template>
<div ref="utterancesContainer"></div>
</template>

<script>
export default {
    mounted() {
        const script = document.createElement('script');
        script.src = 'https://utteranc.es/client.js';
        script.setAttribute('repo', 'davyjonesdesign/vue-markdown-blog');
        script.setAttribute('issue-term', 'pathname');
        script.setAttribute('theme', 'preferred-color-scheme');
        script.setAttribute('crossorigin', 'anonymous');
        script.async = true;

        this.$refs.utterancesContainer.appendChild(script);
    },
};
</script>