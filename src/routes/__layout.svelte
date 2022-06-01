<script lang="ts">
    import "carbon-components-svelte/css/all.css";
    import {Theme} from 'carbon-components-svelte'

    let theme = "g80"; // "white" | "g10" | "g80" | "g90" | "g100"
</script>

<Theme bind:theme/>

<slot/>