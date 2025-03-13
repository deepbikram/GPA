<script>
  import svelteLogo from './assets/svelte.svg'
  import Calculate from './lib/Calculate.svelte'
  // import { Router, Link, Route } from "svelte-routing";
  // import { navigate } from 'svelte-routing';
  import Stream from './lib/Stream.svelte'
  import { course } from './stores.js';
  let choosen_course
  course.subscribe(val => choosen_course=val)
</script>

<header>
 
  <div class="header-content">
    <div class="logo">
      <img src="header.gif" alt="Enotes Nepal Logo" class="brand-logo" /><h1 class="main_text" on:click={()=>course.update(val => val=undefined)}>NEB GPA Calculator</h1>
    </div>



    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="https://www.enotesnepal.com/notes" target="_blank" rel="noopener noreferrer">Notes</a></li>
        <li><a href="https://www.enotesnepal.com/books" target="_blank" rel="noopener noreferrer">Books</a></li>
      </ul>
    </nav>
  </div>
</header>

<main>
<div class="container">
  {#if choosen_course}
    <Calculate></Calculate>
  {:else}
   <Stream></Stream>
   {/if}
</div>
</main>

<footer>
  <div class="footer-content">
    <div class="footer-section">
      <h4>NEB GPA Calculator</h4>
      <p>A simple tool to calculate your GPA for Nepal Education Board examinations.</p>
        <div class="footer-logo-container">
          <a href="https://www.enotesnepal.com" target="_blank" rel="noopener noreferrer">
            <img src="footer.png" alt="Enotes Nepal Logo" class="footer-logo" />
          </a>
      </div>
    </div>
    
    <div class="footer-section">
      <h4>Links</h4>
      <ul>
        <li><a href="https://github.com/anujpaude1/neb_gpa_calculator" target="_blank" rel="noopener noreferrer">GitHub Repository</a></li>
        <li><a href="https://neb.gov.np/" target="_blank" rel="noopener noreferrer">Nepal Education Board</a></li>
        <li><a href="https://www.enotesnepal.com" target="_blank" rel="noopener noreferrer">Enotes Nepal</a></li>
      </ul>
    </div>
    
    <div class="footer-section">
      <h4>Contact</h4>
      <p>Have suggestions or found a bug?</p>
      <a href="https://github.com/anujpaude1/neb_gpa_calculator/issues" target="_blank" rel="noopener noreferrer">Report an Issue</a>
    </div>
  </div>
  
  <div class="footer-bottom">
    <p>&copy; 2023-{new Date().getFullYear()} - NEB GPA Calculator | Created by <a href="https://github.com/anujpaude1" target="_blank" rel="noopener noreferrer">Anuj Paude</a> | Powered by <a href="https://www.enotesnepal.com" target="_blank" rel="noopener noreferrer">Enotes Nepal</a></p>
  </div>
</footer>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Bangers&display=swap');
  
  /* Header Styles */
  header {
    background-color: #f8f9fa;
    padding: 15px 0;
    border-bottom: 1px solid #e9ecef;
    font-family: Arial, sans-serif;
  }
  
  .header-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
    color: #1e61b9;
  }
  
  .logo {
    display: flex;
    align-items: center;
  }
  
  .brand-logo {
    height: 40px;
    margin-right: 15px;
  }
  
  header nav ul {
    display: flex;
    list-style: none;
    margin: 0;
    padding: 0;
  }
  
  header nav ul li {
    margin-left: 20px;
  }
  
  header nav ul li a {
    color: #007bff;
    text-decoration: none;
    font-size: 1rem;
    transition: color 0.2s;
  }
  
  header nav ul li a:hover {
    color: #0056b3;
    text-decoration: underline;
  }
  
  .main_text{
    cursor: pointer;
    font-family: 'Bangers', cursive;
    font-size: 2.5em;
    margin: 0;
  }
  
  @media screen and (max-width: 768px) {
    .header-content {
      flex-direction: column;
      text-align: center;
    }
    
    header nav ul {
      margin-top: 15px;
      justify-content: center;
    }
    
    header nav ul li {
      margin: 0 10px;
    }
  }
  
  @media screen and (max-width: 430px) {
    /* CSS rules for devices below width 420 */
    .main_text{
      font-size: 2em;
    }
    
    header nav ul li {
      margin: 0 5px;
    }
    
    header nav ul li a {
      font-size: 0.9rem;
    }
    
    .brand-logo {
      height: 30px;
    }
  }

  /* Main Content */
  main {
    max-width: 1200px;
    margin: 20px auto;
    padding: 0 20px;
  }

  /* Footer Styles */
  footer {
    background-color: #f8f9fa;
    padding: 20px 0 10px;
    margin-top: 40px;
    border-top: 1px solid #e9ecef;
    font-family: Arial, sans-serif;
  }

  .footer-content {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 20px;
  }

  .footer-section {
    flex: 1;
    min-width: 200px;
    max-width: 300px;
    margin: 10px;
      }

  .footer-section h4 {
    color: #333;
    font-size: 1.1rem;
    margin-bottom: 15px;
    position: relative;
  }

  .footer-section h4:after {
    content: '';
    position: absolute;
    width: 50px;
    height: 2px;
    background-color: #007bff;
    bottom: -5px;
    left: 0;
  }

  .footer-section p {
    color: #6c757d;
    font-size: 0.9rem;
    line-height: 1.5;
  }

  .footer-section ul {
    list-style: none;
    padding: 0;
  }

  .footer-section ul li {
    margin-bottom: 8px;
  }

  .footer-section a, .footer-bottom a {
    color: #007bff;
    text-decoration: none;
    transition: all 0.3s ease;
  }

  .footer-section a:hover, .footer-bottom a:hover {
    color: #0056b3;
    text-decoration: underline;
  }
  
  .footer-logo-container {
    margin-top: 15px;
  }
  
  .footer-logo {
    max-height: 60px;
    margin-top: 10px;
  }

  .footer-bottom {
    text-align: center;
    padding-top: 20px;
    margin-top: 20px;
    border-top: 1px solid #e9ecef;
    color: #6c757d;
    font-size: 0.85rem;
  }

  /* Media Queries for Responsive Footer */
  @media screen and (max-width: 768px) {
    .footer-content {
      flex-direction: column;
      align-items: center;
    }
    
    .footer-section {
      margin-bottom: 20px;
      text-align: center;
    }
    
    .footer-section h4:after {
      left: 50%;
      transform: translateX(-50%);
    }
    
    .footer-logo {
      max-height: 50px;
    }
  }
</style>