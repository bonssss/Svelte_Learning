<script>
  function submitForm(event) {
    event.preventDefault();
  }
</script>

<section class="contact" id="contact">
  <div class="contact-grid">
    <div class="contact-copy">
      <span class="eyebrow">Contact</span>
      <h2>Ready to launch your next trade?</h2>
      <p>
        Get in touch to explore premium insights, portfolio intelligence, and tailored strategy support.
      </p>

      <div class="contact-info">
        <div>
          <span>Email</span>
          <a href="mailto:hello@stellarpulse.io">hello@stellarpulse.io</a>
        </div>
        <div>
          <span>Phone</span>
          <a href="tel:+18005551234">+1 800 755 4520</a>
        </div>
      </div>
    </div>

    <form class="contact-form" on:submit={submitForm}>
      <label>
        <span>Name</span>
        <input type="text" placeholder="Your full name" required />
      </label>
      <label>
        <span>Email</span>
        <input type="email" placeholder="you@example.com" required />
      </label>
      <label>
        <span>Tell us more</span>
        <textarea placeholder="Describe your goals or questions" rows="6" required></textarea>
      </label>
      <button type="submit">Launch a Conversation</button>
    </form>
  </div>
</section>
