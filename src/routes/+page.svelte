<script lang="ts">
    import banner from '$lib/assets/banner.png';
</script>

<style>
    .page {
        width: 100%;
    }

    .section {
        width: 100%;
        height: 100vh;
        display: block;
    }

    .banner {
        background-size: cover;
        background-position: center;
        background-repeat: no-repeat;
    }

    .sea {
        background-color: var(--sea);
        color: var(--white);
    }

    .sand {
        background-color: var(--sand);
        color: var(--dark);
    }

    .orange {
        background-color: var(--orange);
        color: var(--dark);
    }
</style>

<div class="page">
    <section
            class="section banner"
            style:background-image={`url(${banner})`}
    ></section>

    <section class="section orange">g</section>
    <section class="section sea">g</section>
</div>