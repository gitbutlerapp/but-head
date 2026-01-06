<script>
  let email = '';
  
  function handleSubscribe() {
    if (email) {
      alert(`Thank you for subscribing with ${email}!`);
      email = '';
    }
  }
</script>

<main>
  <section class="hero">
    <h1>Welcome to but-head</h1>
    <p class="tagline">A simple, elegant landing page built with Svelte</p>
  </section>

  <section class="features">
    <div class="feature">
      <h2>⚡ Fast</h2>
      <p>Built with Vite for lightning-fast development and optimized builds</p>
    </div>
    <div class="feature">
      <h2>🎨 Modern</h2>
      <p>Clean, responsive design that works beautifully on all devices</p>
    </div>
    <div class="feature">
      <h2>🚀 Simple</h2>
      <p>Minimal setup with maximum impact - start building in seconds</p>
    </div>
  </section>

  <section class="cta">
    <h2>Stay Updated</h2>
    <form on:submit|preventDefault={handleSubscribe}>
      <input 
        type="email" 
        bind:value={email}
        placeholder="Enter your email"
        required
      />
      <button type="submit">Subscribe</button>
    </form>
  </section>
</main>

<style>
  main {
    max-width: 1200px;
    margin: 0 auto;
    padding: 2rem;
  }

  .hero {
    text-align: center;
    padding: 4rem 0;
  }

  h1 {
    font-size: 3.5rem;
    margin-bottom: 1rem;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tagline {
    font-size: 1.5rem;
    color: #888;
    margin-bottom: 3rem;
  }

  .features {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
    gap: 2rem;
    margin: 3rem 0;
  }

  .feature {
    padding: 2rem;
    border-radius: 12px;
    background: rgba(255, 255, 255, 0.05);
    border: 1px solid rgba(255, 255, 255, 0.1);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }

  .feature:hover {
    transform: translateY(-5px);
    box-shadow: 0 10px 30px rgba(102, 126, 234, 0.2);
  }

  .feature h2 {
    font-size: 2rem;
    margin-bottom: 1rem;
  }

  .feature p {
    color: #aaa;
    line-height: 1.6;
  }

  .cta {
    text-align: center;
    padding: 4rem 0;
  }

  .cta h2 {
    font-size: 2rem;
    margin-bottom: 2rem;
  }

  form {
    display: flex;
    gap: 1rem;
    max-width: 500px;
    margin: 0 auto;
    flex-wrap: wrap;
    justify-content: center;
  }

  input {
    flex: 1;
    min-width: 250px;
    padding: 0.8rem 1.2rem;
    font-size: 1rem;
    border-radius: 8px;
    border: 1px solid rgba(255, 255, 255, 0.2);
    background: rgba(255, 255, 255, 0.05);
    color: inherit;
    transition: border-color 0.3s ease;
  }

  input:focus {
    outline: none;
    border-color: #667eea;
  }

  button {
    padding: 0.8rem 2rem;
    font-size: 1rem;
    font-weight: 600;
    border-radius: 8px;
    border: none;
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    color: white;
    cursor: pointer;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  button:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
  }

  @media (prefers-color-scheme: light) {
    .feature {
      background: rgba(0, 0, 0, 0.02);
      border: 1px solid rgba(0, 0, 0, 0.1);
    }

    .tagline, .feature p {
      color: #666;
    }

    input {
      background: rgba(0, 0, 0, 0.02);
      border: 1px solid rgba(0, 0, 0, 0.2);
    }
  }
</style>
