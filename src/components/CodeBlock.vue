<template>
<pre v-highlightjs><code class="javascript">{{code}}</code></pre>
</template>

<script>
    export default {
        name: "CodeBlock",
        props: [
            'lines',
        ],
        computed: {
            code: function() {
                return this.squash(this.lines);

            }
        },
        methods: {
            squash: function(lines) {
                if (Array.isArray(lines)) {
                    var first = lines.shift();
                    lines.unshift(first);

                    if (typeof first === 'string') {
                        return lines.join("\r\n");
                    }
                }

                return JSON.stringify(lines, null, 2);
            }
        }
    }
</script>
