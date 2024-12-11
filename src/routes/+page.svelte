<script> //about me or main page
    // You can add JavaScript functionality here if needed
    let activeSection = 'about';

    import Toggle from './Toggle.svelte'; //need to switch to toggle
    function navigateTo(section) {
      activeSection = section;
    }

    let email = '';
    let subject = '';
    let message = '';

    const sendEmail = () => {
    const mailtoLink = `mailto:douglasmyu@csu.fullerton.edu?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(message)}`;
    window.location.href = mailtoLink;
    };
    function openLinkedIn(){
      window.open('https://www.linkedin.com/in/douglas-yu-51614b165/');
    }
    function openGithub() {
      window.open('https://github.com/Douglasmyu');
    }
    function openSpotify(){
      window.open('https://open.spotify.com/user/douglife-us?si=e9b2a5f65a064dcc');
    }
    
    const resumePath = "/Douglas-2.pdf";
    function openResume(){
      const link = document.createElement('a');
      link.href = resumePath; // Path to your PDF file
      link.download = "Douglas_Resume.pdf"; // Suggested filename for the download
      link.click(); // Programmatically trigger the download
    }
  </script>
  
  <style>
      .contact-form {
      display: flex;
      flex-direction: column;
      width: 300px;
      margin: 0 auto;
    }
    .contact-form input,
    .contact-form textarea {
      margin-bottom: 10px;
      padding: 8px;
      font-size: 1rem;
    }
    .contact-form button {
      padding: 10px;
      background-color: rgba(255, 109, 109, 0.8);
      color: white;
      border: none;
      cursor: pointer;
    }
    .contact-form button:hover {
      background-color: rgba(255, 109, 109, 0.8);
    }

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
      text-align: center;
    }
  
    .navbar img{
        width: 70px;
        height: 70px;
        border-radius: 50%; /* Makes the image circular */
        object-fit: cover; 
        margin-right: 1rem;
        
    }

    h2{
        font-size: 40px;
        color:rgba(255, 109, 109, 0.8);
    }

    p{
      font-size: 18px;
    }

    .title{
      color:#963b44;
      font-size: medium;
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
    text-align: center;
    margin-left: auto;
    margin-right: auto;
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

  :global(body){
    background-color: #f2eee2;
    color: #0084f6;
    transition: background-color 0.3s;
  }

  :global(body.dark-mode){
    background-color: #1d3040;
    color: #bfc2c7;
  }

  .name{ 
    font-size: 2rem; 
  }

  .icon{
    cursor: pointer;
  }

  .icon:hover{
    opacity: 0.8;
  }

  </style>
  
  <div class="navbar">
    <div class = "navbar-left">
        <img src= "/img/pfp.jpg" alt="pfp">
        <center><p class="name"><b>douglas yu</b></p></center>
        <a href="#about" class:active={activeSection === 'about'} on:click={() => navigateTo('about')}>About Me</a>
        <a href="#projects" class:active={activeSection === 'projects'} on:click={() => navigateTo('projects')}>Projects</a>
        <a href="#links" class:active={activeSection === 'links'} on:click={() => navigateTo('links')}>Links</a>
        <Toggle/>
    </div>
  </div>
  
  <section id="about"> <!--about me section-->
    <h2>About Me</h2>
    <p>
        hi. I am currently a Computer Science student at Cal State Fullerton.  
        I enjoy coding, learning new things, and having fun!
    </p>
    <p>
        When I am not coding, I am probably cooking, trying out new cafes, designing and sewing my own clothes, gyming, golfing, or playing badminton.  
    </p>
    <img src="/img/resumeIcon.png" class="icon" on:click={openResume}>
  
   
  </section>
  <section id="projects"> <!-- projects section-->
    <article>
      <h2>My Projects</h2>
        <a href = https://sympto-quest-phi.vercel.app/login><h2>SymptoQuest</h2></a>
            <p class="description">
              SymptoQuest is a web application that provides accurate medical diagnosis based on user input symptoms
            </p>
        <a href = https://github.com/Tepah/Project-Nyaan><h2>Nyaan Cat</h2></a>
            <p class="description">
              Walk through space as Nyaan the space cat and eat as many smelly fish while dodging the falling bombs
            </p>
        <a href= https://github.com/Douglasmyu/svelteGPT><h2>SvelteGPT</h2></a>
            <p class="description">
              A website to run a chatbox using svelte.  
            </p>
    </article>
  </section>
  
  <section>
    <div class="contact-form">
      <h2>Contact Me</h2>
      <input type="email" bind:value={email} placeholder="Your Email" required />
      <input type="text" bind:value={subject} placeholder="Subject" required />
      <textarea bind:value={message} placeholder="Your Message" rows="4" required></textarea>
      <button on:click={sendEmail}>Send Email</button>
    </div>
  </section>
  <section id="links" > <!--Links section-->
    <p class="title">
      Connect with me!
  </p>
    <!-- <button class="Coolbutton" on:click={openGithub}>github</button> -->
    <img src="/img/gitIcon.png" class="icon" on:click={openGithub}>
    <img src="/img/linkedInIcon.png" class="icon "on:click={openGithub}>
    <img src="/img/spotifyIcon.png" class="icon" on:click={openSpotify}>
  </section>