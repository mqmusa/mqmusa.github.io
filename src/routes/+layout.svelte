<script lang="ts">
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger, Dropdown, DropdownItem } from 'flowbite-svelte';
    import { Footer, FooterCopyright, FooterIcon, Button } from 'flowbite-svelte';
    import { TwitterSolid, ChevronDownOutline, InstagramSolid, DollarOutline } from 'flowbite-svelte-icons';
    import "../app.css";
    // import Boxes from '$lib/boxes';
    import logo from '$lib/assets/mqm.png';
    import isCustom from '$lib/isCustom';

    import { base } from '$app/paths';

    let nonActiveClass = 'text-gray-700 border-green-300 hover:bg-green-300 hover:text-white md:hover:bg-transparent md:border-0 md:hover:text-green-300 dark:text-gray-400 md:dark:hover:text-white dark:hover:bg-gray-700 dark:hover:text-white md:dark:hover:bg-transparent';
</script>

<Navbar let:NavContainer class="p-0 sm:mx-0 md:mx-0 m-0 bg-green-600 dark:bg-gray-800 text-primary-800 dark:text-green-400 border-0 divide-primary-500 dark:divide-primary-200 w-full">
    <NavContainer class="border-0 mx-0!important  rounded-lg bg-green-600 dark:bg-gray-600">
        <div class="mx-auto flex flex-wrap justify-between items-center container">
            <NavBrand href={base + "/"}>
                <img src={logo} class="my-3 mr-3 h-9 sm:h-12 md:h-16 lg:h-20 2xl:h-24" alt="MQM Logo" />
            </NavBrand>
            <div class="flex md:order-2">
                <a href="{base}/gift">
                    <button type="button" class="text-sm md:text-md lg:text-lg xl:text-xl focus:outline-none text-white bg-red-700 hover:bg-red-800 focus:ring-4 focus:ring-red-300 font-medium rounded-lg px-5 py-2.5 mx-auto my-auto dark:bg-red-600 dark:hover:bg-red-700 dark:focus:ring-red-900">Gift</button>
                </a>
                <NavHamburger />
            </div>
            <NavUl class="order-1 mx-auto mb-10 md:mb-0" classUl="bg-green-900 border-gray-500 md:bg-transparent md:border-0" {nonActiveClass}>
                <NavLi class="text-white" href={base + "/"}>Home</NavLi>
                <NavLi class="text-white cursor-pointer">
                    About<ChevronDownOutline class="w-6 h-6 ms-2 text-red-300 dark:text-white inline" />
                </NavLi>
                <Dropdown class="w-44 z-20">
                    <DropdownItem href="{base}/biography">Biography</DropdownItem>
                    <DropdownItem href="{base}/political_struggle">Political Struggle</DropdownItem>
                    <DropdownItem href="{base}/philosophy">Philosophy</DropdownItem>
                </Dropdown>
                <NavLi href="{base}/books" class="text-white">Books</NavLi>
                <NavLi class="cursor-pointer text-white">
                    Gallery<ChevronDownOutline class="w-6 h-6 ms-2 text-red-300 dark:text-white inline" />
                </NavLi>
                <Dropdown class="w-44 z-20">
                    <DropdownItem href="{base}/images">Images</DropdownItem>
                    <DropdownItem href="{base}/videos">Videos</DropdownItem>
                    <DropdownItem href="{base}/songs">Songs</DropdownItem>
                </Dropdown>
                <NavLi href="{base}/social_media" class="text-white">Social Media</NavLi>
                <NavLi href="{base}/contact" class="text-white">Contact</NavLi>
            </NavUl>
        </div>
    </NavContainer>
</Navbar>

<slot></slot>

<Footer class="mt-10 mb-5">
    <div class="flex space-x-6 rtl:space-x-reverse sm:justify-center sm:mt-0">
        <strong>
            <FooterCopyright href={base} by="Altaf Hussain™" year={2024} />
        </strong>
        <FooterIcon>
            <a href="https://x.com/AltafHussain_90">
                <TwitterSolid class="w-5 h-5 text-gray-500 dark:text-gray-500 hover:text-gray-900 dark:hover:text-white" />   
            </a>
            <a href="https://www.instagram.com/altafhussain_90">
                <InstagramSolid class="w-5 h-5 text-gray-500 dark:text-gray-500 hover:text-gray-900 dark:hover:text-white" />   
            </a>
            <a href="">
                <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512">
                    <!--!Font Awesome Free 6.6.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license/free Copyright 2024 Fonticons, Inc.-->
                    <path d="M448 209.9a210.1 210.1 0 0 1 -122.8-39.3V349.4A162.6 162.6 0 1 1 185 188.3V278.2a74.6 74.6 0 1 0 52.2 71.2V0l88 0a121.2 121.2 0 0 0 1.9 22.2h0A122.2 122.2 0 0 0 381 102.4a121.4 121.4 0 0 0 67 20.1z"/>
                </svg>
            </a>
        </FooterIcon>
    </div>
</Footer>
