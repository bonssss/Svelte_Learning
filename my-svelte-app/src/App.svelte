<script>
import FeedbackList from './components/feedbackList.svelte';
import FeedBackStat from './components/FeedBackStat.svelte';
import FeedBackForm from './components/FeedBackForm.svelte';
import RatingSelect from './components/RatingSelect.svelte';
  
  let feedback =[


  {
    id:1,
    rating:10,
    text:'This is feedback item 1'
  },
  {
    id:2,
    rating:9,
    text:'This is feedback item 2'
  },

  {
    id:3,
    rating:8,
    text:'This is feedback item 3'
  }
  ]

  $: count = feedback.length;
  $: average = feedback.reduce((acc, item) => acc + item.rating, 0) / feedback.length;

  const deleteFeedback = (event) => {
    const itemId = event.detail;
    feedback = feedback.filter((item) => item.id !== itemId);
  };
  
</script>

<main class="container">
<RatingSelect />
<FeedBackForm />
  <FeedBackStat {count} {average} />
  <FeedbackList {feedback} on:delete={deleteFeedback} />

</main>

