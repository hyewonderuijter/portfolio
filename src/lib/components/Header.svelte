<script>
    import { page } from '$app/stores';
</script>
<header>
    <nav>
        <ul>
            <li>
                <a 
                    href="/" 
                    class:active={$page.url.pathname === '/'}
                >
                    Home
                </a>
            </li>
            <li>
                <a 
                    href="/work" 
                    class:active={$page.url.pathname === '/work'}
                >
                    Blog
                </a>
            </li>
            <li>
                <a 
                    href="/contact" 
                    class:active={$page.url.pathname === '/contact'}
                >
                    Contact
                </a>
            </li>
        </ul>
    </nav>
</header>