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
    function sendEmail() {
      window.location.href = "mailto:douglasmyu@csu.fullerton.edu?subject=Hello&body=This%20is%20the%20body";
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
  
    .about,
    .projects,
    .contact {
      display: none;
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
  
  <section id="about"> <!--about me section-->
    <h2>About Me</h2>
    <p>
        hi. I am currently a Computer Science student at Cal State Fullerton.  
        I enjoy coding, learning new things, and having fun!
    </p>
    <p>
        When I am not coding, I am probably cooking, trying out new cafes, designing and sewing my own clothes, or going to the gym to practice football.  
    </p>
    <a href="src/routes/hobbies/+page.svelte">Click here to see my hobbies</a>
    <p class="title">
        Connect with me!
    </p>
    <p>
      <button on:click={openGithub}>github</button>
    </p>
    
    <p> 
      <button on:click={sendEmail}>Send Email</button>
    </p>
   
  </section>
  <section id="projects"> <!-- projects section-->
    <article>
      <h2>My Projects</h2>
        <a href = https://sympto-quest-phi.vercel.app/login><h2>SymptoQuest</h2></a>
            <p>
                SymptoQuest is a web application that provides accurate medical diagnosis based on user input symptoms
            </p>
    </article>
  </section>

  <section id = "contact"> <!-- contact me section-->
    <h2>Contact me</h2>
    <form class="contact-form" on:submit={handsubmit}></form>

    <p>Name</p>
    <input id=name placeholder="Enter Name"/>

    <p>Email</p>
    <input id=email placeholder="Enter email"/>

    <p>Message</p>
    <textarea id=message placeholder="Enter message"/>
    <button type="submit">Send</button>
  </section>

  