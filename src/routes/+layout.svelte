<script>
    import "../app.css";
    import logo from '$lib/assets/peterbbq-logo-web.svg'

    let currentYear = new Date().getFullYear()

    const menuItems = [
        {name: "Home", url: "/"},
        {name: "Formules", url: "/formules"},
        {name: "Foto's", url: "/fotos"},
        {name: "Contact", url: "/contact"}
    ]
</script>
  
<header class="container mx-auto flex justify-between px-4 py-1 uppercase items-center">
    <div class="logo"><img src={logo} alt="Logo" class="w-36"></div>

    <nav class="flex list-none gap-8 items-center text-2xl font-bold">
        {#each menuItems as menuItem}
        <li class="px-4 hover:pbred"><a href={menuItem.url}>{menuItem.name}</a></li>
        {/each}
    </nav>
    <a class="text-2xl font-bold uppercase py-4 px-6 border-2 rounded-full leading-none" href={menuItems[3].url}>Contacteren</a>
</header>

<section class="bg-white py-8">
    <slot />
</section>
  






<footer class="container mx-auto w-full px-4 pt-16 pb-4">
    <nav class="flex gap-12 list-none justify-center font-medium montserrat">
        {#each menuItems as menuItem}
        <li class="px-4 hover:pbred"><a href={menuItem.url}>{menuItem.name}</a></li>
        {/each}
    </nav>
    <div class="w-full border-t my-12 border-gray-600"></div>
    <p class="text-center">© {currentYear} Alle rechten voorbehouden - Door <a href="https://www.newfront.be/" rel="nofollow" class="underline">NewFront</a>.</p>
</footer>