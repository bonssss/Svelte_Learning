<script>
export let count
export let average

</script>

<div class="feedback-stats">
  <p>Feedback ({count})</p>
  <p>Average Rating: {average.toFixed(1)}</p>
</div>

<style>
    .feedback-stats{
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 20px;
    }
</style>