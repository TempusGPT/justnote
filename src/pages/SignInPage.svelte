<script lang="ts">
    import { device } from "@libs/media-query";
    import { auth } from "@libs/server";
</script>

<main class="container">
    <div class="grid">
        {#if device.mobile}
            {@render image()}
            {@render text()}
        {:else}
            {@render text()}
            {@render image()}
        {/if}
    </div>
</main>

{#snippet text()}
    <div class="text">
        <h1>JustNote</h1>
        <p>
            Lorem ipsum dolor sit, amet consectetur adipisicing elit. Dolor, sed eligendi eveniet
            eius minus perferendis corrupti.
        </p>

        <button class="outline" onclick={auth.signIn}>Continue with Google</button>
    </div>
{/snippet}

{#snippet image()}
    <div class="image">
        <img src="/favicon.svg" alt="Vite logo" />
    </div>
{/snippet}

<style>
    main {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100dvh;
    }

    button {
        margin-top: 1.5rem;
    }

    img {
        width: 80%;
        height: auto;
    }

    .text {
        display: flex;
        flex-direction: column;
        align-items: start;
        justify-content: center;
    }

    .image {
        display: flex;
        flex-direction: column;
        align-items: center;
    }
</style>
