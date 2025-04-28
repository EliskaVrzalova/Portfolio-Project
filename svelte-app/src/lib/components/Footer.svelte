<script>
  // Current year for copyright
  const currentYear = new Date().getFullYear();
</script>
<!-- 3 sections/column footer-->
<footer role="contentinfo">
  <div class="footer-container">
    <!-- Quick links section -->
    <div class="footer-section" role="navigation" aria-labelledby="portfolio-nav">
      <h3 id="portfolio-nav">Portfolio</h3>
      <ul class="quick-links">
        <li><a href="/digital-art">Digital Art</a></li>
        <li><a href="/paintings">Paintings</a></li>
        <li><a href="/web-design">Web Design</a></li>
        <li><a href="/game-design">Game Design</a></li>
        <li><a href="/tattoo-design">Tattoo Design</a></li>
        <li><a href="/game dev">Game Development</a></li>
      </ul>
    </div>

    <!-- Social media icons section -->
    <div class="footer-section social-section">
      <h3 id="social-links">Connect With Me</h3>
      <div class="social-links" aria-labelledby="social-links">
        <a href="https://www.instagram.com/_evrzlv_/" target="_blank" rel="noopener noreferrer" aria-label="Follow me on Instagram">
          <img src="/instagram.png" alt="" class="social-icon" aria-hidden="true" />
          <span class="visually-hidden">Instagram</span> <!--descriptions hidden but available for screen readers-->
        </a>
        <a href="https://github.com/EliskaVrzalova" target="_blank" rel="noopener noreferrer" aria-label="View my projects on GitHub">
          <img src="/github.png" alt="" class="social-icon" aria-hidden="true" />
          <span class="visually-hidden">GitHub</span>
        </a>
        <a href="https://discord.com/users/1332386471621165226" target="_blank" rel="noopener noreferrer" aria-label="Contact me on Discord">
          <img src="/discord.png" alt="" class="social-icon" aria-hidden="true" />
          <span class="visually-hidden">Discord</span>
        </a>
        <a href="https://x.com/vrzalova_eliska" target="_blank" rel="noopener noreferrer" aria-label="Follow me on X (formerly Twitter)">
          <img src="/twitter.png" alt="" class="social-icon" aria-hidden="true" />
          <span class="visually-hidden">X (Twitter)</span>
        </a>
        <a href="mailto:eliska.vrzalovaa@gmail.com" aria-label="Send me an email">
          <img src="/gmail-logo.png" alt="" class="social-icon" aria-hidden="true" />
          <span class="visually-hidden">Email</span>
        </a>
      </div>
    </div>

    <!-- Copyright section -->
    <div class="footer-section">
      <h3 id="contact-info">Contact</h3>
      <p>Feel free to reach out for collaborations, inquiries, or just to say hello!</p>
      <!--link to email-->
      <a href="mailto:eliska.vrzalovaa@gmail.com" class="email-link" aria-labelledby="contact-info">eliska.vrzalovaa@gmail.com</a>
      <div class="copyright" role="contentinfo">
        <p>&copy; {currentYear} Eliska Vrzalova. All rights reserved.</p>
      </div>
    </div>
  </div>
</footer>

<style>
      /* Accessibility text for icons*/
      .visually-hidden {
    position: absolute;
    width: 1px;
    height: 1px;
    margin: -1px;
    padding: 0;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
    white-space: nowrap;
    border: 0;
  }
  
  footer {
    background-color: rgb(255, 255, 255,0.5);
    color: #000000;
    padding: 3rem 1rem;
    margin-top: 4rem;
    border-top: 1px solid #eaeaea;
  }

  .footer-container {
    max-width: 1200px;
    margin: 0 auto;
    display: grid;
    grid-template-columns: 1fr;
    gap: 2.5rem;
  }
  /*portfolio menu*/
  .footer-section {
    display: flex;
    flex-direction: column;
  }

  h3 {
    font-size: 1.2rem;
    margin-bottom: 1.2rem;
    font-weight: 600;
    position: relative;
    padding-bottom: 0.5rem;
  }

  h3::after {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 40px;
    height: 2px;
    background-color: #000000;
  }

  /* Quick Links Styling */
  .quick-links {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .quick-links li {
    margin-bottom: 0.8rem;
  }

  .quick-links a {
    color: #000000;
    text-decoration: none;
    transition: color 0.3s ease, transform 0.3s ease;
    display: inline-block;
  }
  /*links change color and move to the right a bit*/
  .quick-links a:hover {
    color: var(--primary-color);
    transform: translateX(5px);
  }

  /* Social Links Styling */
  .social-links {
    display: flex;
    flex-wrap: wrap;
    gap: 1.5rem;
    justify-content: center;
  }

  .social-icon {
    width: 40px;
    height: 40px;
    object-fit: contain;
    transition: transform 0.3s ease, filter 0.3s ease, box-shadow 0.3s ease;
    border-radius: 8px;
    padding: 5px;
    background-color: white;
  }

  .social-links a {
    display: flex;
    align-items: center;
    justify-content: center;
    text-decoration: none;
    border-radius: 8px;
    transition: transform 0.3s ease;
  }
  /*social icons lift up slightly when hovered*/
  .social-links a:hover {
    transform: translateY(-5px);
  }
  /*social icons get slightly bigger when hovered*/
  .social-links a:hover .social-icon {
    transform: scale(1.1);
    box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  }

  /* Contact Section */
  .footer-section p {
    margin-bottom: 1rem;
    line-height: 1.6;
  }

  .email-link {
    color: #000000;
    text-decoration: none;
    transition: color 0.3s ease;
    margin-bottom: 1.5rem;
    display: inline-block;
  }
  /*email link changes colour when hovered*/
  .email-link:hover {
    color: var(--primary-color);
  }

  .copyright {
    margin-top: 2rem;
    font-size: 0.9rem;
    color: #777;
  }

  /* Responsive Design */
  /*mobile devices*/
  @media (min-width: 768px) {
    .footer-container {
      grid-template-columns: repeat(2, 1fr);
    }
    
    .social-section {
      grid-column: 1 / -1;
    }
    
    .social-links {
      justify-content: center;
    }
    
    .social-section h3 {
      text-align: center;
    }
    
    .social-section h3::after {
      left: 50%;
      transform: translateX(-50%);
    }
  }

  @media screen and (min-width: 769px) and (max-width: 1024px) {
    .footer-container {
      grid-template-columns: repeat(3, 1fr);
    }
    
    .social-section {
      grid-column: auto;
    }
    
    .social-section h3 {
      text-align: left;
    }
    
    .social-section h3::after {
      left: 0;
      transform: none;
    }
    
    .social-links {
      justify-content: flex-start;
    }
  }
</style>
