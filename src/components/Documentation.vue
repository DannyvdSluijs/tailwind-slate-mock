<template>
    <div class="">
        <documentation-block v-for="(item) in items" v-bind:key="item.title" :item="item"/>
    </div>
</template>

<script>
    import DocumentationBlock from "./DocumentationBlock";

    export default {
        name: "Documentation",
        components: {
            DocumentationBlock
        },
        data: function() {
            return {
                items: [
                    {
                        title: "Introduction",
                        explanation: [
                            "Welcome to the Kittn API! You can use our API to access Kittn API endpoints, which can get information on various cats, kittens, and breeds in our database.",
                            "We have language bindings in Shell, Ruby, Python, and JavaScript! You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.",
                            "This example API documentation page was created with Slate. Feel free to edit it and use it as a base for your own API's documentation.",
                        ]

                    },
                    {
                        title: "Authentication",
                        explanation: [
                            "Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our developer portal.",
                            "Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:",
                            "Authorization: meowmeowmeow"
                        ],
                        example: {
                            request: {
                                header: "To authorize, use this code:",
                                code: [
                                    "const kittn = require('kittn');",
                                    "let api = kittn.authorize('meowmeowmeow');"
                                ],
                                footer: "Make sure to replace meowmeowmeow with your API key.",
                            },
                        }
                    },
                    {
                        title: "Kittens",
                        explanation: [
                            {type: "title", content: "Get all Kittens"},
                            "This endpoint retrieves all kittens",
                            {type: "header", content: "HTTP Request"},
                            {type: "highlight", content: "GET http://example.com/api/kittens"},
                            {type: "header", content:"Query Parameters"},
                            "Parameter Default Description",
                            "include_cats false If set to true, the result will also include cats",
                            "available true If set to false, the result will include kittens that have already been adopted",
                            "Remember -- a happy kitten is an authenticated kitten"

                        ],
                        example: {
                            request: {
                                code: [
                                    "const kittn = require('kittn');",
                                    "",
                                    "let api = kittn.authorize('meowmeowmeow');",
                                    "let kittens = api.kittens.get();",
                                ],
                            },
                            response: {
                                header: "The above command returns JSON structured like this:",
                                code: [

                                        {
                                            "id": 1,
                                            "name": "Fluffums",
                                            "breed": "calico",
                                            "fluffiness": 6,
                                            "cuteness": 7
                                        },
                                        {
                                            "id": 2,
                                            "name": "Max",
                                            "breed": "unknown",
                                            "fluffiness": 5,
                                            "cuteness": 10
                                        }

                                ],
                            }
                        }
                    },
                ]
            }
        }
    }
</script>
