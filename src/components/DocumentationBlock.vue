<template>
    <div>
        <div class="bg-gray-100 w-1/2">
            <h1 class="font-semibold text-3xl border-b border-t border-gray-500 px-6 py-2">{{item.title}}</h1>
        </div>
        <div  class="flex">
            <div class="bg-gray-100 w-1/2">
                <div class="bg-gray-200 px-6 font-hairline pt-4 pb-12">
                    <template v-for="(explanation) in item.explanation">
                        <template v-if="explanation.type === 'title'">
                            <h2 class="font-semibold text-xl pb-2" v-bind:key="explanation">{{explanation.content}}</h2>
                        </template>
                        <template v-if="explanation.type === 'header'">
                            <h3 class="font-semibold pb-2" v-bind:key="explanation">{{explanation.content}}</h3>
                        </template>
                        <template v-if="explanation.type === 'highlight'">
                            <div class="mb-10" v-bind:key="explanation">
                                <span class="font-hairline text-sm bg-gray-300 px-1" >{{explanation.content}}</span>
                            </div>
                        </template>
                        <p class="pb-4" v-bind:key="explanation" v-if="!explanation.hasOwnProperty('type')">
                            {{explanation}}
                        </p>
                    </template>
                </div>
            </div>
            <div class="w-1/2" v-if="item.example">
                <template v-if="item.example.request">
                    <example-explanation v-if="item.example.request.header" :content="item.example.request.header" />
                    <code-block v-if="item.example.request.code" :lines="item.example.request.code" />
                    <example-explanation v-if="item.example.request.footer" :content="item.example.request.footer" />
                </template>
                <template v-if="item.example.response">
                    <example-explanation v-if="item.example.response.header" :content="item.example.response.header" />
                    <code-block v-if="item.example.response.code" :lines="item.example.response.code" />
                    <example-explanation v-if="item.example.response.footer" :content="item.example.response.footer" />
                </template>
            </div>
        </div>
    </div>
</template>

<script>
    import CodeBlock from "./CodeBlock";
    import ExampleExplanation from "./ExampleExplanation";

    export default {
        name: "DocumentationBlock",
        props: [
            'item',
        ],
        components: {
            ExampleExplanation,
            CodeBlock
        }
    }
</script>
