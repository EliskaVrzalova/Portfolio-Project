<script>
  // Current year for copyright
  const currentYear = new Date().getFullYear();
</script>

<footer>
  <div class="footer-container">
    <!-- Quick links section -->
    <div class="footer-section">
      <h3>Portfolio</h3>
      <ul class="quick-links">
        <li><a href="/digital-art">Digital Art</a></li>
        <li><a href="/paintings">Paintings</a></li>
        <li><a href="/web-design">Web Design</a></li>
        <li><a href="/game-design">Game Design</a></li>
        <li><a href="/tattoo-design">Tattoo Design</a></li>
        <li><a href="/game dev">Game Development</a></li>
      </ul>
    </div>

    <!-- Social media section with image links -->
    <div class="footer-section social-section">
      <h3>Connect With Me</h3>
      <div class="social-links">
        <a href="https://www.instagram.com/_evrzlv_/" target="_blank" rel="noopener noreferrer" aria-label="Instagram Profile">
          <img src="/instagram.png" alt="Instagram" class="social-icon" />
        </a>
        <a href="https://github.com/EliskaVrzalova" target="_blank" rel="noopener noreferrer" aria-label="GitHub Profile">
          <img src="/github.png" alt="GitHub" class="social-icon" />
        </a>
        <a href="https://discord.com/users/1332386471621165226" target="_blank" rel="noopener noreferrer" aria-label="Discord Profile">
          <img src="/discord.png" alt="Discord" class="social-icon" />
        </a>
        <a href="https://x.com/vrzalova_eliska" target="_blank" rel="noopener noreferrer" aria-label="Twitter Profile">
          <img src="/twitter.png" alt="Twitter" class="social-icon" />
        </a>
        <a href="mailto:eliska.vrzalovaa@gmail.com" aria-label="Email Me">
          <img src="/gmail-logo.png" alt="Email" class="social-icon" />
        </a>
      </div>
    </div>

    <!-- Copyright section -->
    <div class="footer-section">
      <h3>Contact</h3>
      <p>Feel free to reach out for collaborations, inquiries, or just to say hello!</p>
      <a href="mailto:your.email@example.com" class="email-link">eliska.vrzalovaa@gmail.com</a>
      <div class="copyright">
        <p>&copy; {currentYear} Eliska Vrzalova. All rights reserved.</p>
      </div>
    </div>
  </div>
</footer>

<style>
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

  .social-links a:hover {
    transform: translateY(-5px);
  }

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

  .email-link:hover {
    color: var(--primary-color);
  }

  .copyright {
    margin-top: 2rem;
    font-size: 0.9rem;
    color: #777;
  }

  /* Responsive Design */
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

  @media (min-width: 1024px) {
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
