<template>
  <div id="app" class="h-auto bg-gray-800 flex">
    <table-of-content class="fixed top-0 left-0 w-1/6"/>
    <div class="w-1/6"/>
    <documentation class="w-5/6"/>
    <language-selector class="fixed top-0 right-0 w-5/12"/>
  </div>
</template>

<script>
  import TableOfContent from "./components/TableOfContent";
  import Documentation from "./components/Documentation";
  import LanguageSelector from "./components/LanguageSelector";

  export default {
    name: 'app',
    components: {
      TableOfContent,
      Documentation,
      LanguageSelector
    },
  }
</script>
