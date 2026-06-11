<script>
  let openIndex = 0;

  const faqs = [
    {
      question: 'What makes Stellar Pulse different?',
      answer:
        'Our platform uses adaptive AI signals and market context to deliver insights that evolve with every trading session.'
    },
    {
      question: 'Can I use the system with my own strategies?',
      answer:
        'Yes. You can overlay our signals, automate alerts, and trade alongside your existing workflow.'
    },
    {
      question: 'How do I access live portfolio insights?',
      answer:
        'Simply sign up, connect your account, and start viewing live analytics, risk metrics, and signal summaries in minutes.'
    }
  ];

  function toggle(index) {
    openIndex = openIndex === index ? -1 : index;
  }
</script>

<section class="faq" id="faq">
  <div class="faq-inner">
    <span class="eyebrow">FAQ</span>
    <h2>Answers to common questions</h2>
    <div class="faq-list">
      {#each faqs as item, index}
        <article class="faq-item {openIndex === index ? 'open' : ''}">
          <button type="button" class="faq-question" on:click={() => toggle(index)}>
            <span>{item.question}</span>
            <span class="faq-icon">{openIndex === index ? '−' : '+'}</span>
          </button>
          <div class="faq-answer" aria-hidden={openIndex !== index}>
            <p>{item.answer}</p>
          </div>
        </article>
      {/each}
    </div>
  </div>
</section>
