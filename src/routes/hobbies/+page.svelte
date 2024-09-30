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
  
    .navbar img{
        width: 70px;
        height: 70px;
        border-radius: 50%; /* Makes the image circular */
        object-fit: cover; 
        margin-right: 1rem;
        
    }
  
    .active-section {
      display: block;
    }
    h2{
        font-size: medium;
        color:#9D5C63;
    }
    .title{
      color:#9D5C63;
      font-size: medium;
    }
    .button-link {
    display: inline-block;
    padding: 10px 20px;
    background-color: #007bff;
    color: white;
    text-align: center;
    text-decoration: none;
    border-radius: 5px;
    cursor: pointer;
    border: none;
    font-size: 16px;
  }

  .button-link:hover {
    background-color: #0056b3;
  }

  .description{
    background-color: rgba(218, 139, 139, 0.8); /* Light background color */
    border-radius: 10px; /* Rounded corners */
    box-shadow: 0 4px 8px rgb(75, 69, 69); /* Subtle shadow effect */
    padding: 15px; /* Spacing inside the box */
    margin: 15px 0; /* Spacing outside the box */
    color: #333; /* Text color */
    font-size: 1rem; /* Font size for the text */
    max-width: 600px;
  }
  .Coolbutton{
    background-color: rgba(218, 139, 139, 0.8);
    border-radius: 5px;
    padding: 5px;
    margin: 5px 0;
    color: #333;
  }
  .name{ 
    font-size: 2rem; 
  }
  </style>
  
  <div class="navbar">
    <div class = "navbar-left">
        <img src= "src/img/pfp.jpg" alt="pfp">
        <center><p class="name"><b>douglas yu</b></p></center>
        <a href="#about" class:active={activeSection === 'about'} on:click={() => navigateTo('about')}>About Me</a>
        <a href="#projects" class:active={activeSection === 'projects'} on:click={() => navigateTo('projects')}>Projects</a>
        <a href="#contact" class:active={activeSection === 'contact'} on:click={() => navigateTo('contact')}>Contact Me</a>
    
    </div>
  </div>
  
  <section id="about"> <!--about me section-->
    <h2>About Me</h2>
    <p class = "description">
        hi. I am currently a Computer Science student at Cal State Fullerton.  
        I enjoy coding, learning new things, and having fun!
    </p>
    <p>
        When I am not coding, I am probably cooking, trying out new cafes, designing and sewing my own clothes, or going to the gym to practice football.  
    </p>
    <a href="src/routes/hobbies/+page.svelte">Click here to see my hobbies at work</a>
    <p class="title">
        Connect with me!
    </p>
   
  </section>
  <section id="projects"> <!-- projects section-->

  </section>



  