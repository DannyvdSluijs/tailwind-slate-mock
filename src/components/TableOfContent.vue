<template>
    <div class="text-white">
        <div>
            <img src="/img/logo.png" />
        </div>
        <div class="py-2 px-5 ">
            <div class="flex border-b items-center pb-1">
                <svg class="fill-current h-4 w-4" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20"><path d="M12.9 14.32a8 8 0 1 1 1.41-1.41l5.35 5.33-1.42 1.42-5.33-5.34zM8 14A6 6 0 1 0 8 2a6 6 0 0 0 0 12z"/></svg>
                <input class="bg-gray-800 outline-none ml-2" placeholder="Search">
            </div>
        </div>
        <div class="leading-loose">
            <ul>
                <li>
                    <a href="#"
                       class="px-5 font-semibold text-sm tracking-wide inline-block w-full"
                       v-on:click="setActive('introduction')"
                       v-bind:class="{ 'bg-blue-700': isActive('introduction') }"
                    >
                        Introduction
                    </a>
                </li>
                <li>
                    <a href="#"
                       class="px-5 font-semibold text-sm tracking-wide inline-block w-full"
                       v-on:click="setActive('authentication')"
                       v-bind:class="{ 'bg-blue-700': isActive('authentication') }"
                    >
                        Authentication
                    </a>
                </li>
                <li>
                    <a href="#"
                       class="px-5 font-semibold text-sm tracking-wide inline-block w-full"
                       v-on:click="setActive('kittens')"
                       v-bind:class="{ 'bg-blue-700': isActive('kittens') }"
                    >
                        Kittens
                    </a>
                    <ul class="bg-black">
                        <li>
                            <a href="#"
                               class="pl-8 font-semibold text-sm tracking-wide inline-block w-full"
                               v-on:click="setActive('getAllKittens')"
                               v-bind:class="{ 'bg-blue-700': isActive('getAllKittens') }"
                            >
                                Get All Kittens
                            </a>
                        </li>
                        <li>
                            <a href="#"
                               class="pl-8 font-semibold text-sm tracking-wide inline-block w-full"
                               v-on:click="setActive('getOneKitten')"
                               v-bind:class="{ 'bg-blue-700': isActive('getOneKitten') }"
                            >
                                Get a Specific Kittens
                            </a>
                        </li>
                        <li>
                            <a href="#"
                               class="pl-8 font-semibold text-sm tracking-wide inline-block w-full"
                               v-on:click="setActive('deleteOneKitten')"
                               v-bind:class="{ 'bg-blue-700': isActive('deleteOneKitten') }"
                            >
                                Delete a Specific Kittens
                            </a>
                        </li>
                    </ul>
                </li>

                <li>
                    <a href="#"
                       class="px-5 font-semibold text-sm tracking-wide inline-block w-full"
                       v-on:click="setActive('errors')"
                       v-bind:class="{ 'bg-blue-700': isActive('errors') }"
                    >
                        Errors
                    </a>
                </li>
            </ul>
        </div>
        <p class="text-xs border-t border-dashed mt-2 pt-2 px-5">
            Sign Up for a Developer Key
            Documentation Powered by Slate
        </p>
    </div>
</template>

<script>
    export default {
        name: "TableOfContent",
        data: function () {
            return {
                activeItem: "introduction"
            }
        },
        methods: {
            isActive: function (menuItem) {
                return this.activeItem === menuItem
            },
            setActive: function (menuItem) {
                this.activeItem = menuItem
            }
        }
    }
</script>

