<script> //about me or main page
    // You can add JavaScript functionality here if needed
    let activeSection = 'about';
    
    function navigateTo(section) {
      activeSection = section;
    }
    function handsubmit(event){
        event.preventDefault();
        alert('Your message has been sent');
    }
  </script>
  
  <style>
    /* Basic styling for the menu and sections */
    .navbar {
      display: flex;
      justify-content: space-around;
      align-items: center;
      background-color: #444;
      padding: 1rem;
    }
    .navbar-left {
        align-items: center;
        display: flex;
        gap: 1rem;
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
    .navbar img{
        width: 70px;
        height: 70px;
        border-radius: 50%; /* Makes the image circular */
        object-fit: cover; /* Ensures the image covers the container properly */
        margin-right: 1rem;
        
    }
  
    .active-section {
      display: block;
    }
  </style>
  
  <div class="navbar">
    <div class = "navbar-left">
        <img src= "src/img/pfp.jpg" alt="pfp">
        <center><p><b>douglas yu</b></p></center>
        <a href="#about" class:active={activeSection === 'about'} on:click={() => navigateTo('about')}>About Me</a>
        <a href="#projects" class:active={activeSection === 'projects'} on:click={() => navigateTo('projects')}>Projects</a>
        <a href="#contact" class:active={activeSection === 'contact'} on:click={() => navigateTo('contact')}>Contact Me</a>
    
    </div>
  </div>
  
  <section id="about">
    <h2>About Me</h2>
    <p>
        hi. I am currently a Computer Science student at Cal State Fullerton.  
        I enjoy coding, learning new things, and having fun!
    </p>
    <p>
        When I am not coding, I am probably cooking, trying out new cafes, designing and sewing my own clothes, or going to the gym to practice football.  
    </p>
  </section>
  <section id="projects">
    <h2>Projects</h2>
    <h4>Project 1</h4>
    <p>
        i did this and that
    </p>
  </section>

  <section id = "contact">
    <h2>Contact me</h2>
    <form class="contact-form" on:submit={handleSubmit}></form>
    <p>Name</p>
    <input id=name placeholder="Enter Name"/>
    <p>Email</p>
    <input id=email placeholder="Enter email"/>
    <p>Message</p>
    <textarea id=message placeholder="Enter message"/>
    <button type="submit">Send</button>
  </section>

  