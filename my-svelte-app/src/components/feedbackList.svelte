<script>
import {fade,scale} from 'svelte/transition';
import FeedbackItem from './feedbackItem.svelte';
export let feedback = [];

</script>

{#each feedback as fb (fb.id)}
<div in:fade={{duration:200}} out:scale={{duration:200}}>
    <FeedbackItem  item={fb} on:delete />

</div>

    
{/each}

