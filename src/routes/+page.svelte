<script> //about me or main page
    // You can add JavaScript functionality here if needed
    let activeSection = 'about';
    
    function navigateTo(section) {
      activeSection = section;
    }
  </script>
  
  <style>
    /* Basic styling for the menu and sections */
    .navbar {
      display: flex;
      justify-content: space-around;
      align-items: center;
      background-color: #333;
      padding: 1rem;
    }
  
    .navbar a {
      color: white;
      text-decoration: none;
      font-size: 1.2rem;
      padding: 0.5rem 1rem;
    }
  
    .navbar a.active {
      background-color: #555;
      border-radius: 5px;
    }
  
    section {
      padding: 2rem;
    }
  
    .about,
    .projects,
    .contact {
      display: none;
    }
  
    .active-section {
      display: block;
    }
  </style>
  
  <div class="navbar">
    <p><b>douglas yu</b></p>
    <a href="#about" class:active={activeSection === 'about'} on:click={() => navigateTo('about')}>About Me</a>
    <a href="#projects" class:active={activeSection === 'projects'} on:click={() => navigateTo('projects')}>Projects</a>
    <a href="#contact" class:active={activeSection === 'contact'} on:click={() => navigateTo('contact')}>Contact Me</a>
  </div>
  
  <section class="about" class:active-section={activeSection === 'about'}>
    <h2>About Me</h2>
    <p>
        hi. I am currently a Computer Science student at Cal State Fullerton.  
        I enjoy coding, learning new things, and having fun!
    </p>
    <p>
        When I am not coding, I am probably cooking, trying out new cafes, designing and sewing my own clothes, or going to the gym to practice football.  
    </p>
  </section>
  

  