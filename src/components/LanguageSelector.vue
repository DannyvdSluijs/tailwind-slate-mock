<template>
    <div class="flex items-center justify-start text-white bg-black">

        <a class="px-2 text-sm font-semibold" href="#"
            v-for="language in languages"
            v-bind:key="language"
            v-bind:class="{'bg-gray-800': isActiveLanguage(language)}"
            v-on:click="setActiveLanguage(language)"
        >
            {{language}}
        </a>
    </div>
</template>

<script>
    export default {
        name: "LanguageSelector",
        data: function() {
            return {
                activeLanguage: 'javascript',
                languages: [
                    'shell',
                    'ruby',
                    'python',
                    'javascript',
                ]
            }
        },
        methods: {
            isActiveLanguage: function (language) {
                return this.activeLanguage === language
            },
            setActiveLanguage: function (language) {
                this.activeLanguage = language
            }
        }
    }
</script>

<style scoped>

</style>
