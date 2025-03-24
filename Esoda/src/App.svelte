<script lang="ts">
  import svelteLogo from './assets/svelte.svg'
  import viteLogo from '/vite.svg'
  import Counter from './lib/Counter.svelte'
  import Test from './lib/Test.svelte'
</script>

<main>
  <div class="title">
    <h1>Welcome to Esoda AI</h1>
  </div>
  <div>
    <a href="https://vite.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>
  <!-- Testing this file -->
  <Test />
  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a href="https://github.com/sveltejs/kit#readme" target="_blank" rel="noreferrer">SvelteKit</a>, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">
    Feel free to learn more
  </p>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>

<!-- Claude Edits
App.svelte file
<script lang="ts">
  // Define types for our data structures
  interface Feature {
    id: number;
    title: string;
    description: string;
    icon: string;
  }

  interface Testimonial {
    id: number;
    name: string;
    role: string;
    content: string;
    avatar: string;
  }

  // Sample data
  const features: Feature[] = [
    {
      id: 1,
      title: "Intuitive Design",
      description: "Clean interfaces designed with the user experience in mind.",
      icon: "✨"
    },
    {
      id: 2,
      title: "Fast Performance",
      description: "Optimized code ensures your applications run smoothly.",
      icon: "⚡"
    },
    {
      id: 3,
      title: "Responsive Layout",
      description: "Perfect viewing experience across all devices.",
      icon: "📱"
    }
  ];

  const testimonials: Testimonial[] = [
    {
      id: 1,
      name: "Alex Johnson",
      role: "Product Manager",
      content: "This product has transformed how our team collaborates. The interface is intuitive and the performance is outstanding.",
      avatar: "/api/placeholder/50/50"
    },
    {
      id: 2,
      name: "Sam Rivera",
      role: "UX Designer",
      content: "I've never worked with a more responsive and well-designed platform. It's made my workflow so much more efficient.",
      avatar: "/api/placeholder/50/50"
    }
  ];

  // Navigation state
  let isMenuOpen: boolean = false;
  const toggleMenu = () => {
    isMenuOpen = !isMenuOpen;
  };

  // Form handling
  let email: string = "";
  const handleSubmit = () => {
    alert(`Thank you for subscribing with: ${email}`);
    email = "";
  };
</script>

<main>
  <header>
    <div class="container">
      <nav>
        <div class="logo">
          <span>Nova</span>
        </div>
        <div class="nav-toggle" on:click={toggleMenu}>
          <span></span>
          <span></span>
          <span></span>
        </div>
        <ul class={isMenuOpen ? 'nav-links active' : 'nav-links'}>
          <li><a href="#features">Features</a></li>
          <li><a href="#testimonials">Testimonials</a></li>
          <li><a href="#pricing">Pricing</a></li>
          <li><a href="#contact" class="btn-primary">Get Started</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <section class="hero">
    <div class="container">
      <div class="hero-content">
        <h1>Transform Your Digital Experience</h1>
        <p>
          Create stunning, high-performance applications with our modern framework.
          Fast, responsive, and built with the latest technologies.
        </p>
        <div class="cta-buttons">
          <a href="#contact" class="btn-primary">Get Started</a>
          <a href="#learn-more" class="btn-secondary">Learn More</a>
        </div>
      </div>
      <div class="hero-image">
        <img src="/api/placeholder/450/300" alt="Dashboard Preview" />
      </div>
    </div>
  </section>

  <section id="features" class="features">
    <div class="container">
      <div class="section-header">
        <h2>Features</h2>
        <p>Discover what makes our platform stand out from the crowd</p>
      </div>
      <div class="feature-grid">
        {#each features as feature (feature.id)}
          <div class="feature-card">
            <div class="feature-icon">{feature.icon}</div>
            <h3>{feature.title}</h3>
            <p>{feature.description}</p>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <section id="testimonials" class="testimonials">
    <div class="container">
      <div class="section-header">
        <h2>What Our Clients Say</h2>
        <p>Testimonials from professionals who use our platform</p>
      </div>
      <div class="testimonial-grid">
        {#each testimonials as testimonial (testimonial.id)}
          <div class="testimonial-card">
            <div class="testimonial-content">
              <p>"{testimonial.content}"</p>
            </div>
            <div class="testimonial-author">
              <img src={testimonial.avatar} alt={testimonial.name} />
              <div>
                <h4>{testimonial.name}</h4>
                <span>{testimonial.role}</span>
              </div>
            </div>
          </div>
        {/each}
      </div>
    </div>
  </section>

  <section id="pricing" class="pricing">
    <div class="container">
      <div class="section-header">
        <h2>Simple, Transparent Pricing</h2>
        <p>Choose the plan that works best for your needs</p>
      </div>
      <div class="pricing-grid">
        <div class="pricing-card">
          <div class="pricing-header">
            <h3>Basic</h3>
            <div class="price">$29<span>/month</span></div>
          </div>
          <ul class="pricing-features">
            <li>Up to 5 projects</li>
            <li>Basic analytics</li>
            <li>24/7 support</li>
          </ul>
          <a href="#contact" class="btn-primary">Choose Plan</a>
        </div>
        <div class="pricing-card featured">
          <div class="pricing-tag">Most Popular</div>
          <div class="pricing-header">
            <h3>Pro</h3>
            <div class="price">$79<span>/month</span></div>
          </div>
          <ul class="pricing-features">
            <li>Up to 20 projects</li>
            <li>Advanced analytics</li>
            <li>Priority support</li>
            <li>Custom integrations</li>
          </ul>
          <a href="#contact" class="btn-primary">Choose Plan</a>
        </div>
        <div class="pricing-card">
          <div class="pricing-header">
            <h3>Enterprise</h3>
            <div class="price">Custom</div>
          </div>
          <ul class="pricing-features">
            <li>Unlimited projects</li>
            <li>Full analytics suite</li>
            <li>Dedicated support</li>
            <li>White labeling</li>
            <li>Custom development</li>
          </ul>
          <a href="#contact" class="btn-secondary">Contact Us</a>
        </div>
      </div>
    </div>
  </section>

  <section id="contact" class="contact">
    <div class="container">
      <div class="section-header">
        <h2>Ready to Get Started?</h2>
        <p>Join thousands of satisfied customers using our platform</p>
      </div>
      <div class="contact-form">
        <form on:submit|preventDefault={handleSubmit}>
          <input type="email" bind:value={email} placeholder="Enter your email" required />
          <button type="submit" class="btn-primary">Subscribe Now</button>
        </form>
        <p class="form-note">We respect your privacy. Unsubscribe at any time.</p>
      </div>
    </div>
  </section>

  <footer>
    <div class="container">
      <div class="footer-grid">
        <div class="footer-col">
          <div class="footer-logo">Nova</div>
          <p>Building the future of digital experiences with modern technologies and intuitive design.</p>
          <div class="social-links">
            <a href="#" aria-label="Twitter">T</a>
            <a href="#" aria-label="Facebook">F</a>
            <a href="#" aria-label="Instagram">I</a>
            <a href="#" aria-label="LinkedIn">L</a>
          </div>
        </div>
        <div class="footer-col">
          <h4>Company</h4>
          <ul>
            <li><a href="#">About Us</a></li>
            <li><a href="#">Careers</a></li>
            <li><a href="#">Blog</a></li>
            <li><a href="#">Press</a></li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Resources</h4>
          <ul>
            <li><a href="#">Documentation</a></li>
            <li><a href="#">Support</a></li>
            <li><a href="#">Tutorials</a></li>
            <li><a href="#">API</a></li>
          </ul>
        </div>
        <div class="footer-col">
          <h4>Legal</h4>
          <ul>
            <li><a href="#">Privacy Policy</a></li>
            <li><a href="#">Terms of Service</a></li>
            <li><a href="#">Cookie Policy</a></li>
            <li><a href="#">GDPR</a></li>
          </ul>
        </div>
      </div>
      <div class="footer-bottom">
        <p>&copy; 2025 Nova. All rights reserved.</p>
      </div>
    </div>
  </footer>
</main>

<style>
  /* Global Styles */
  :root {
    --primary-color: #6366f1;
    --primary-dark: #4f46e5;
    --secondary-color: #f43f5e;
    --neutral-100: #f9fafb;
    --neutral-200: #f3f4f6;
    --neutral-300: #e5e7eb;
    --neutral-700: #374151;
    --neutral-800: #1f2937;
    --neutral-900: #111827;
    --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
    --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
    --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
    --radius: 0.5rem;
  }
  
  /* Reset and Base Styles */
  * {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
  
  html {
    scroll-behavior: smooth;
  }
  
  body {
    font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    line-height: 1.6;
    color: var(--neutral-800);
    background-color: var(--neutral-100);
  }
  
  img {
    max-width: 100%;
    height: auto;
    border-radius: var(--radius);
  }
  
  h1, h2, h3, h4, h5, h6 {
    font-weight: 700;
    line-height: 1.2;
    margin-bottom: 1rem;
  }
  
  h1 {
    font-size: 3rem;
  }
  
  h2 {
    font-size: 2.25rem;
  }
  
  h3 {
    font-size: 1.5rem;
  }
  
  p {
    margin-bottom: 1rem;
  }
  
  a {
    color: var(--primary-color);
    text-decoration: none;
    transition: color 0.3s ease;
  }
  
  a:hover {
    color: var(--primary-dark);
  }
  
  ul {
    list-style: none;
  }
  
  .container {
    width: 100%;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 1.5rem;
  }
  
  section {
    padding: 5rem 0;
  }
  
  .section-header {
    text-align: center;
    margin-bottom: 3rem;
  }
  
  .section-header p {
    max-width: 600px;
    margin: 0 auto;
    color: var(--neutral-700);
  }
  
  /* Button Styles */
  .btn-primary, .btn-secondary {
    display: inline-block;
    padding: 0.75rem 1.5rem;
    border-radius: var(--radius);
    font-weight: 600;
    transition: all 0.3s ease;
    cursor: pointer;
  }
  
  .btn-primary {
    background-color: var(--primary-color);
    color: white;
  }
  
  .btn-primary:hover {
    background-color: var(--primary-dark);
    color: white;
  }
  
  .btn-secondary {
    background-color: var(--neutral-200);
    color: var(--neutral-800);
  }
  
  .btn-secondary:hover {
    background-color: var(--neutral-300);
  }
  
  /* Header and Navigation */
  header {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    background-color: rgba(255, 255, 255, 0.95);
    backdrop-filter: blur(10px);
    z-index: 1000;
    box-shadow: var(--shadow-sm);
  }
  
  nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    height: 80px;
  }
  
  .logo {
    font-size: 1.75rem;
    font-weight: 700;
    color: var(--primary-color);
  }
  
  .nav-links {
    display: flex;
    align-items: center;
    gap: 2rem;
  }
  
  .nav-toggle {
    display: none;
    flex-direction: column;
    justify-content: space-between;
    width: 30px;
    height: 21px;
    cursor: pointer;
  }
  
  .nav-toggle span {
    display: block;
    width: 100%;
    height: 3px;
    background-color: var(--neutral-800);
    border-radius: 3px;
    transition: all 0.3s ease;
  }
  
  /* Hero Section */
  .hero {
    padding: 9rem 0 5rem;
    background: linear-gradient(135deg, #e9eeff 0%, #f3e7ff 100%);
  }
  
  .hero .container {
    display: flex;
    align-items: center;
    gap: 3rem;
  }
  
  .hero-content {
    flex: 1;
  }
  
  .hero-image {
    flex: 1;
    display: flex;
    justify-content: center;
  }
  
  .cta-buttons {
    display: flex;
    gap: 1rem;
    margin-top: 2rem;
  }
  
  /* Features Section */
  .features {
    background-color: white;
  }
  
  .feature-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }
  
  .feature-card {
    padding: 2rem;
    background-color: var(--neutral-100);
    border-radius: var(--radius);
    box-shadow: var(--shadow-md);
    transition: transform 0.3s ease, box-shadow 0.3s ease;
  }
  
  .feature-card:hover {
    transform: translateY(-5px);
    box-shadow: var(--shadow-lg);
  }
  
  .feature-icon {
    font-size: 2.5rem;
    margin-bottom: 1rem;
  }
  
  /* Testimonials Section */
  .testimonials {
    background-color: var(--neutral-200);
  }
  
  .testimonial-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
    gap: 2rem;
  }
  
  .testimonial-card {
    background-color: white;
    border-radius: var(--radius);
    padding: 2rem;
    box-shadow: var(--shadow-md);
  }
  
  .testimonial-content {
    margin-bottom: 1.5rem;
    font-style: italic;
  }
  
  .testimonial-author {
    display: flex;
    align-items: center;
    gap: 1rem;
  }
  
  .testimonial-author img {
    width: 50px;
    height: 50px;
    border-radius: 50%;
    object-fit: cover;
  }
  
  .testimonial-author h4 {
    margin-bottom: 0.25rem;
  }
  
  .testimonial-author span {
    color: var(--neutral-700);
    font-size: 0.875rem;
  }
  
  /* Pricing Section */
  .pricing {
    background-color: white;
  }
  
  .pricing-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 2rem;
  }
  
  .pricing-card {
    background-color: var(--neutral-100);
    border-radius: var(--radius);
    padding: 2rem;
    box-shadow: var(--shadow-md);
    position: relative;
    transition: transform 0.3s ease;
  }
  
  .pricing-card:hover {
    transform: translateY(-5px);
  }
  
  .pricing-card.featured {
    background-color: white;
    border: 2px solid var(--primary-color);
    transform: translateY(-10px) scale(1.02);
    z-index: 1;
  }
  
  .pricing-card.featured:hover {
    transform: translateY(-15px) scale(1.02);
  }
  
  .pricing-tag {
    position: absolute;
    top: -10px;
    right: 20px;
    background-color: var(--primary-color);
    color: white;
    padding: 0.25rem 1rem;
    border-radius: 20px;
    font-size: 0.875rem;
  }
  
  .pricing-header {
    text-align: center;
    margin-bottom: 2rem;
  }
  
  .price {
    font-size: 2.5rem;
    font-weight: 700;
    color: var(--primary-color);
  }
  
  .price span {
    font-size: 1rem;
    font-weight: 400;
    color: var(--neutral-700);
  }
  
  .pricing-features {
    margin-bottom: 2rem;
  }
  
  .pricing-features li {
    padding: 0.5rem 0;
    position: relative;
    padding-left: 1.5rem;
  }
  
  .pricing-features li::before {
    content: "✓";
    position: absolute;
    left: 0;
    color: var(--primary-color);
  }
  
  .pricing-card .btn-primary, .pricing-card .btn-secondary {
    display: block;
    text-align: center;
    width: 100%;
  }
  
  /* Contact Section */
  .contact {
    background: linear-gradient(135deg, #e9eeff 0%, #f3e7ff 100%);
  }
  
  .contact-form {
    max-width: 600px;
    margin: 0 auto;
  }
  
  .contact-form form {
    display: flex;
    gap: 1rem;
    margin-bottom: 1rem;
  }
  
  .contact-form input {
    flex: 1;
    padding: 0.75rem 1rem;
    border: 1px solid var(--neutral-300);
    border-radius: var(--radius);
    outline: none;
    font-size: 1rem;
    transition: border-color 0.3s ease;
  }
  
  .contact-form input:focus {
    border-color: var(--primary-color);
  }
  
  .form-note {
    text-align: center;
    font-size: 0.875rem;
    color: var(--neutral-700);
  }
  
  /* Footer */
  footer {
    background-color: var(--neutral-900);
    color: var(--neutral-200);
    padding: 5rem 0 2rem;
  }
  
  .footer-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 3rem;
    margin-bottom: 3rem;
  }
  
  .footer-logo {
    font-size: 1.5rem;
    font-weight: 700;
    color: white;
    margin-bottom: 1rem;
  }
  
  .footer-col p {
    color: var(--neutral-300);
    margin-bottom: 1.5rem;
  }
  
  .footer-col h4 {
    color: white;
    margin-bottom: 1.5rem;
  }
  
  .footer-col ul li {
    margin-bottom: 0.75rem;
  }
  
  .footer-col a {
    color: var(--neutral-300);
  }
  
  .footer-col a:hover {
    color: white;
  }
  
  .social-links {
    display: flex;
    gap: 1rem;
  }
  
  .social-links a {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 36px;
    height: 36px;
    background-color: rgba(255, 255, 255, 0.1);
    border-radius: 50%;
    color: white;
    transition: background-color 0.3s ease;
  }
  
  .social-links a:hover {
    background-color: var(--primary-color);
  }
  
  .footer-bottom {
    text-align: center;
    padding-top: 2rem;
    border-top: 1px solid rgba(255, 255, 255, 0.1);
    font-size: 0.875rem;
    color: var(--neutral-300);
  }
  
  /* Responsive Design */
  @media (max-width: 992px) {
    h1 {
      font-size: 2.5rem;
    }
    
    h2 {
      font-size: 2rem;
    }
    
    .hero .container {
      flex-direction: column;
      text-align: center;
    }
    
    .cta-buttons {
      justify-content: center;
    }
  }
  
  @media (max-width: 768px) {
    .nav-toggle {
      display: flex;
    }
    
    .nav-links {
      position: absolute;
      top: 80px;
      left: 0;
      width: 100%;
      flex-direction: column;
      background-color: white;
      padding: 1.5rem;
      box-shadow: var(--shadow-md);
      transform: translateY(-150%);
      opacity: 0;
      pointer-events: none;
      transition: all 0.3s ease;
    }
    
    .nav-links.active {
      transform: translateY(0);
      opacity: 1;
      pointer-events: all;
    }
    
    .contact-form form {
      flex-direction: column;
    }
    
    .pricing-card.featured {
      transform: translateY(0) scale(1);
    }
    
    .pricing-card.featured:hover {
      transform: translateY(-5px) scale(1);
    }
  }
</style> -->