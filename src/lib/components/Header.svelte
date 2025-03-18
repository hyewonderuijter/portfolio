<!--src/lib/components/Header.svelte-->
<script>
    import { page } from '$app/stores';

    let isMenuOpen = false;
    
    function toggleMenu() {
        isMenuOpen = !isMenuOpen; // Menu Toggle
    }
</script>

<header>
    <div class="container">
        <button on:click={() => window.location.href = '/'}>
            <img src="/portfolio-logo.png" alt="logo of portfolio website" class="logo-img">
        </button>
        
        <button 
            class="menu-overlay-bg {isMenuOpen ? 'visible' : ''}" 
            on:click={toggleMenu} 
            on:keydown={(e) => e.key === 'Enter' && toggleMenu()} 
            aria-label="Close menu overlay"
        ></button>
        <button 
            class="menu-icon" 
            on:click={toggleMenu} 
            aria-expanded={isMenuOpen} 
            aria-label={isMenuOpen ? 'Close menu' : 'Open menu'}
        >
            {#if isMenuOpen}
            <img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/delete-sign.png" alt="delete-sign" class="menu-close-icon">
            {:else}
            <img width="30" height="30" src="https://img.icons8.com/ios-filled/30/menu--v1.png" alt="menu--v3"class="menu-open-icon">
            {/if}
        </button>

        <button 
            class="overlay {isMenuOpen ? 'open' : ''}" 
            on:click={toggleMenu} 
            aria-expanded={isMenuOpen} 
            aria-label="Toggle menu"
        >
            <a href="/">Home</a>
            <a href="/work" class:active={$page.url.pathname === '/work'}>Work</a>
            <a href="/contact" class:active={$page.url.pathname === '/contact'}>Contact</a>
            <div class="social-icons">
                <a href="https://www.linkedin.com/in/hyewonim"><img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/linkedin.png" alt="linkedin" class="social-icon-img"/></a>
                <a href="https://github.com/hyewonderuijter"><img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/github.png" alt="github" class="social-icon-img"/></a>
                <a href="mailto:hyewon.im@icloud.com"><img width="30" height="30" src="https://img.icons8.com/ios-glyphs/30/new-post.png" alt="new-post" class="social-icon-img"/></a>
            </div>
        </button>

        <div class="big-screen-nav">
            <a href="/" class:active={$page.url.pathname === '/' || $page.url.pathname === ''}>Home</a>
            <a href="/work" class:active={$page.url.pathname === '/work'}>Work</a>
            <a href="/contact" class:active={$page.url.pathname === '/contact'}>Contact</a>
        </div>
        
    </div>
</header>

<style>
    .logo-img {
        width: 5rem;
        border-radius: 10px;
        cursor: pointer;
    }

    header {
        padding: 2rem 0;
        width: 100vw;
        overflow: hidden;
        overflow-x: none;
        background-color: #FCF8F6;
        z-index: 10; /* 다른 요소보다 앞에 배치 */
    }

    .container {
        display: flex;
        flex-direction: row;
        justify-content: space-between;
        align-items: center;
        max-width: 80vw;
        margin: 0 auto;
    }

    
    .big-screen-nav {
        display: flex;
        flex-direction: row;
        gap: 2rem;
        list-style: none;
    }

    a {
        text-decoration: none;
        color: #463F3C;
        position: relative;
    }

    a::after {
        content: '';
        position: absolute;
        left: 0;
        bottom: -5px;
        width: 0;
        height: 2px;
        background-color: #ADA29E;
        transition: width 0.3s ease-in-out;
    }

    a:hover::after,
    a:focus::after,
    a.active::after {
        width: 100%;
    }

    button {
        border: 0;
        background: transparent;
    }
/* Menu icon is Invisible if the screensize is big enough */
    .menu-icon, .overlay, .menu-overlay-bg {
        display: none;
    }

    /* ======================== */
    /* ======================== */
    /*       Media Query        */
    /* ======================== */
    /* ======================== */

    @media (max-width: 768px) {
            /* Logo Image Size */
                .logo-img {
                    width: 3.5rem;
                }

            /* Navigation bar - Invisible */
                .big-screen-nav {
                    display: none;
                }

            /* Menu Icon */
                .menu-icon {
                    display: block;
                    width: 30px;  
                    background: none;
                    border: none;
                    padding: 0;

                    cursor: pointer;
                }

                .menu-icon img {
                    display: block;
                    margin: 0;
                    padding: 0;
                }

                button {
                    border: none;
                    background: transparent;
                }

                .menu-open-icon {
                    cursor: pointer;
                    display: block;
                    width: 30px;
                    border-bottom: none;
                    
                }

                .menu-close-icon {
                    display: block;
                    width: 30px;
                    cursor: pointer;
                    position: relative;
                    z-index: 1001;
                }

                /* Menu - Overlay Effect */

                .menu-overlay-bg {
                    position: fixed;
                    top: 0;
                    left: 0;
                    width: 100vw;
                    height: 100vh;
                    background: rgba(0, 0, 0, 0.5);
                    backdrop-filter: blur(10px); /* Blur Effect */
                    opacity: 0;
                    visibility: hidden;
                    transition: opacity 0.3s ease-in-out, visibility 0.3s ease-in-out;
                    z-index: 998;
                }

                .menu-overlay-bg.visible {
                    opacity: 1;
                    visibility: visible;
                }

                .overlay {
                    position: fixed;
                    top: 0;
                    right: -100%;  /* Initially position the overlay outside of the screen on the right */
                    width: 70%;
                    height: 100%;
                    background-color: rgba(252, 248, 246, 0.9);
                    z-index: 999;
                    display: flex;
                    justify-content: center;
                    align-items: center;
                    flex-direction: column;
                    text-align: center;
                    opacity: 0;  /* Initially hidden */
                    transition: right 0.5s ease-in-out, opacity 0.5s ease-in-out; /* Apply smooth transition for right and opacity */
                }

                /* Menu items */
                .overlay a {
                    padding: 1.5em;
                    font-size: 1.5rem;
                    color: #2c2522;
                    display: block;
                    opacity: 0;  /* Initially invisible */
                    transform: translateX(50px);  /* Position items slightly to the right */
                    transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out; /* Smooth transition for opacity and position */
                }

                /* When the menu is open */
                .overlay.open {
                    right: 0;  /* Move the overlay to the visible area */
                    opacity: 1;  /* Make it visible */
                }

                .overlay.open a {
                    opacity: 1;  /* Make menu items visible */
                    transform: translateX(0);  /* Move items to their normal position */
                }

                a:hover::after,
                a:focus::after,
                a.active::after {
                    width: 0; /* Remove hovering effect in mobile screen */
                }

                .social-icons {
                    display: flex;
                    flex-direction: row;
                    margin: 0 auto;
                    gap: 1.4rem;
                }

                .social-icon-img {
                    max-width: 30px;
                    height: auto;
                }

                .social-icons,
                .social-icons a,
                .social-icons img {
                    margin: 0;
                    padding: 0;
                    margin-top: 3rem;
                }
            }
</style>