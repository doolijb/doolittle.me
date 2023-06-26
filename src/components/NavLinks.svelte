<script>
    import { page } from '$app/stores'; 
</script>

<li>
    <a
        href="/"
        class="text-secondary-600 hover:underline"
        class:underline={$page.url.pathname  == '/index'}
        title="Home"
    >
        Home
    </a>
</li>
<li>
    <a
        href="/baby"
        class="text-secondary-600 hover:underline"
        class:underline={$page.url.pathname  == '/baby'}
        title="Baby Shower"
    >
        Baby Shower
    </a>
</li>
<li>
    <a 
        href="/contact" 
        class="text-secondary-600 hover:underline" 
        class:underline={$page.url.pathname == '/contact'}
        title="Contact"
    >
        Contact
    </a>
</li>