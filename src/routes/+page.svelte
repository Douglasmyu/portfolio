<script> //about me or main page
    // You can add JavaScript functionality here if needed
    let activeSection = 'about';
    
    function navigateTo(section) {
      activeSection = section;
    }

    function sendEmail() {
      window.location.href = "mailto:douglasmyu@csu.fullerton.edu?subject=Hello&body=This%20is%20the%20body";
    }
    function openLinkedIn(){
      window.open('https://www.linkedin.com/in/douglas-yu-51614b165/');
    }
    function openGithub() {
      window.open('https://github.com/Douglasmyu');
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
        font-size: large;
        color:rgba(217, 129, 129, 0.8);
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


  .description{
    background-color: rgba(206, 184, 184, 0.8); /* Light background color */
    border-radius: 10px; /* Rounded corners */
    box-shadow: 0 4px 8px rgb(75, 69, 69); /* Subtle shadow effect */
    padding: 15px; /* Spacing inside the box */
    margin: 15px 0; /* Spacing outside the box */
    color: #333; /* Text color */
    font-size: 1rem; /* Font size for the text */
    max-width: 600px;
    position: relative;
    overflow: hidden;
  }
  .description::after{
    content: '';
    position: absolute;
    top: 0;
    left: -100%;
    width: 100%;
    height: 100%;
    background: linear-gradient(
      120deg,
      rgba(255, 255, 255, 0) 0%,
      rgba(255, 255, 255, 0.4) 50%,
      rgba(255, 255, 255, 0) 100%
    );
    animation: shiny 3s infinite;
  }

  @keyframes shiny {
  0% {
    left: -100%;
  }
  50% {
    left: 100%;
  }
  100% {
    left: 100%;
  }
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
        <a href="#links" class:active={activeSection === 'links'} on:click={() => navigateTo('links')}>Links</a>
    </div>
  </div>
  
  <section id="about"> <!--about me section-->
    <h2>About Me</h2>
    <p>
        hi. I am currently a Computer Science student at Cal State Fullerton.  
        I enjoy coding, learning new things, and having fun!
    </p>
    <p>
        When I am not coding, I am probably cooking, trying out new cafes, designing and sewing my own clothes, or gyming.  
    </p>
    <a href="src/routes/hobbies/+page.svelte">Click here to see my hobbies at work(maybe an icon of food)</a>
  
   
  </section>
  <section id="projects"> <!-- projects section-->
    <article>
      <h2>My Projects</h2>
        <a href = https://sympto-quest-phi.vercel.app/login><h2>SymptoQuest</h2></a>
            <p class="description">
                SymptoQuest is a web application that provides accurate medical diagnosis based on user input symptoms
            </p>
        <a href= https://github.com/Douglasmyu/svelteGPT><h2>SvelteGPT</h2></a>
            <p class="description">
              A website to run a chatbox using svelte.  
            </p>
    </article>
  </section>
  

  <section id="links" > <!--Links section-->
    <h2>add links with logos to github, linkedin, spotify, and email</h2>
    <p class="title">
      Connect with me!
  </p>
    <!-- <button class="Coolbutton" on:click={openGithub}>github</button> -->
    <img src="src/img/gitIcon.png" on:click={openGithub}>
    <img src="src/img/linkedInIcon.png" on:click={openGithub}>
  </section>