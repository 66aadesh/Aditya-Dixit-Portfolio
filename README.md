<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Welcome to My Projects Portfolio</title>
  <style>
    /* Add some basic styling */
    body {
      margin: 0;
      font-family: Arial, sans-serif;
    }
    .header {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      background-color: #f0f0f0;
      padding: 10px 20px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      z-index: 1000;
    }
    .profile-img {
      width: 100px;
      height: 100px;
      border-radius: 50%;
      margin-bottom: 20px;
    }
    .basic-info {
      margin-bottom: 20px;
      padding: 20px;
      background-color: #fff;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    .resume-button,
    .repo-button {
      margin-bottom: 20px;
      padding: 10px 20px;
      background-color: #4CAF50;
      color: white;
      border: none;
      border-radius: 4px;
      cursor: pointer;
    }
    .projects {
      padding-top: 150px; /* Adjust according to header height */
    }
    .project-card {
      width: 300px;
      border: 1px solid #ccc;
      padding: 20px;
      text-align: center;
      border-radius: 8px;
      margin-bottom: 20px;
    }
  </style>
</head>
<body>

  <div class="header">
    <!-- Profile Image -->
    <img class="profile-img" src="(https://drive.google.com/file/d/1SUuxaG9nmThVpG3aAadmmsBPnXx_PQhj/view?usp=drive_link)" alt="Profile Picture">

    <!-- Basic Information Section -->
    <div class="basic-info">
      <!-- Input your basic information here -->
      <!-- For example:
      <p><strong>Name:</strong> Aditya Dixit</p>
      <p><strong>Address:</strong> 123 Main St, City, Country</p>
      <p><strong>Email:</strong> johndoe@example.com</p>
      <p><strong>Phone:</strong> +1 234 56789</p>
      <p><strong>Social Media:</strong> 
        <a href="https://www.linkedin.com/in/yourprofile">LinkedIn</a>, 
        <a href="https://twitter.com/yourprofile">Twitter</a>, 
        <a href="https://github.com/yourprofile">GitHub</a>
      </p>
      -->
    </div>

    <!-- Buttons -->
    <button class="repo-button" onclick="window.open('https://github.com/YOUR_USERNAME/YOUR_PORTFOLIO_REPO')">Portfolio GitHub Repo</button>
    <button class="resume-button" onclick="window.open('https://drive.google.com/uc?export=view&id=YOUR_PDF_FILE_ID_HERE')">View Resume</button>
  </div>

  <div class="projects">
    <!-- Project cards will be dynamically added here -->
  </div>

  <script>
    // Simulated data for projects
    const projects = [
      // Example project data - replace with your own
      { name: "Project 1", description: "Description for Project 1", image: "project1_image.jpg", link: "link_to_project_1_repository" },
      { name: "Project 2", description: "Description for Project 2", image: "project2_image.jpg", link: "link_to_project_2_repository" },
      // Add more project data as needed
    ];

    // Function to create project cards
    function createProjectCard(project) {
      const card = document.createElement('div');
      card.classList.add('project-card');
      card.innerHTML = `
        <h2>${project.name}</h2>
        <img class="project-img" src="https://raw.githubusercontent.com/YOUR_USERNAME/${project.image}" alt="${project.name} Image">
        <p>${project.description}</p>
        <a href="${project.link}">GitHub Repository</a>
      `;
      return card;
    }

    // Function to add project cards to the projects container
    function addProjects() {
      const projectsContainer = document.querySelector('.projects');
      projects.forEach((project) => {
        const card = createProjectCard(project);
        projectsContainer.appendChild(card);
      });
    }

    // Add projects when the page loads
    window.onload = addProjects;
  </script>

  <script>
    // Infinite scroll functionality
    window.addEventListener('scroll', () => {
      const { scrollTop, scrollHeight, clientHeight } = document.documentElement;
      if (scrollTop + clientHeight >= scrollHeight - 20) {
        addProjects(); // Load more projects when near the bottom
      }
    });
  </script>

</body>
</html>
