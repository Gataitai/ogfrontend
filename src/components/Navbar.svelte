<script lang="ts">
    import logo from '$lib/assets/cubulan.png';

    let menuOpen = $state(false);

    function toggleMenu() {
        menuOpen = !menuOpen;
    }

    function closeMenu() {
        menuOpen = false;
    }
</script>

<style>
    .navbar {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        box-sizing: border-box;
        padding: 2rem 10rem 0 10rem;
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-family: 'Poppins', sans-serif;
        color: var(--white);
        z-index: 50;
    }

    .left {
        display: flex;
        align-items: center;
        gap: 2.5rem;
    }

    .right {
        display: flex;
        align-items: center;
        gap: 1.5rem;
    }

    a {
        color: var(--white);
        text-decoration: none;
        white-space: nowrap;
    }

    a:hover {
        color: var(--sand);
    }

    .logo {
        display: flex;
        align-items: center;
        height: 3rem;
    }

    .logo img {
        height: 100%;
        width: auto;
        object-fit: contain;
        display: block;
    }

    .cta {
        background: var(--orange);
        color: var(--dark);
        padding: 0.6rem 1.2rem;
        border-radius: 999px;
        font-weight: 600;
    }

    .cta:hover {
        background-color: var(--sea);
        color: var(--white);
    }

    .burger {
        display: none;
        background: transparent;
        border: none;
        cursor: pointer;
        width: 2.2rem;
        height: 2.2rem;
        padding: 0;
        flex-direction: column;
        justify-content: center;
        gap: 0.35rem;
    }

    .burger span {
        display: block;
        width: 100%;
        height: 3px;
        background: var(--white);
        border-radius: 999px;
    }

    .modal-backdrop {
        position: fixed;
        inset: 0;
        background: rgba(15, 23, 42, 0.96);
        z-index: 100;
        display: flex;
        justify-content: center;
        align-items: center;
        padding: 2rem;
    }

    .modal {
        width: min(100%, 12rem);
        display: flex;
        flex-direction: column;
        gap: 1rem;
        text-align: center;
    }

    .modal a {
        font-size: 1.5rem;
    }

    .modal .cta {
        display: inline-block;
        text-align: center;
        margin-top: 0.5rem;
    }

    .close {
        position: absolute;
        top: 1.5rem;
        right: 1.5rem;
        background: transparent;
        border: none;
        color: var(--white);
        font-size: 2rem;
        cursor: pointer;
        line-height: 1;
    }

    @media (max-width: 1000px) {
        .navbar {
            padding: 0 4rem;
        }
    }

    @media (max-width: 800px) {
        .navbar {
            min-height: 5.5rem;
            padding: 1rem 2rem;
        }

        .left {
            gap: 0;
        }

        .left a:not(.logo),
        .right {
            display: none;
        }

        .burger {
            display: flex;
        }
    }

    @media (max-width: 500px) {
        .navbar {
            padding: 1rem;
        }

        .modal a {
            font-size: 1.2rem;
        }
    }
</style>

<nav class="navbar">
    <div class="left">
        <a class="logo" href="/" onclick={closeMenu}>
            <img src={logo} alt="logo" />
        </a>

        <a href="/">Home</a>
        <a href="/about">About</a>
        <a href="/programme">Programme</a>
        <a href="/impact">Impact</a>
        <a href="/contact">Contact</a>
    </div>

    <div class="right">
        <a href="/login">Login</a>
        <a class="cta" href="/signup">Join Now</a>
    </div>

    <button
            class="burger"
            type="button"
            aria-label="Open menu"
            aria-expanded={menuOpen}
            onclick={toggleMenu}
    >
        <span></span>
        <span></span>
        <span></span>
    </button>
</nav>

{#if menuOpen}
    <div class="modal-backdrop">
        <button
                class="close"
                type="button"
                aria-label="Close menu"
                onclick={closeMenu}
        >
            ×
        </button>

        <div class="modal">
            <a href="/" onclick={closeMenu}>Home</a>
            <a href="/about" onclick={closeMenu}>About</a>
            <a href="/programme" onclick={closeMenu}>Programme</a>
            <a href="/impact" onclick={closeMenu}>Impact</a>
            <a href="/contact" onclick={closeMenu}>Contact</a>
            <a href="/login" onclick={closeMenu}>Login</a>
            <a class="cta" href="/signup" onclick={closeMenu}>Join Now</a>
        </div>
    </div>
{/if}