<template>
    <div class="contact-bar">
      <div class="container">
        <div class="contact-item">
          <div class="icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M22 16.92v3a2 2 0 0 1-2.18 2 19.79 19.79 0 0 1-8.63-3.07 19.5 19.5 0 0 1-6-6 19.79 19.79 0 0 1-3.07-8.67A2 2 0 0 1 4.11 2h3a2 2 0 0 1 2 1.72 12.84 12.84 0 0 0 .7 2.81 2 2 0 0 1-.45 2.11L8.09 9.91a16 16 0 0 0 6 6l1.27-1.27a2 2 0 0 1 2.11-.45 12.84 12.84 0 0 0 2.81.7A2 2 0 0 1 22 16.92z"/>
              <text x="24" y="10" class="small-text">24</text>
            </svg>
          </div>
          <div class="content">
            <div class="title"><a href="#" class="hover:underline">+(123) 456 78910</a></div>
            <div class="subtitle">Have a question? Call us now</div>
          </div>
        </div>
  
        <div class="contact-item">
          <div class="icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <path d="M4 4h16c1.1 0 2 .9 2 2v12c0 1.1-.9 2-2 2H4c-1.1 0-2-.9-2-2V6c0-1.1.9-2 2-2z"/>
              <polyline points="22,6 12,13 2,6"/>
            </svg>
          </div>
          <div class="content">
            <div class="title"><a href="#" class="hover:underline">help@medicare.com</a></div>
            <div class="subtitle">Need support? Drop us an email</div>
          </div>
        </div>
  
        <div class="contact-item">
          <div class="icon">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
              <circle cx="12" cy="12" r="10"/>
              <polyline points="12 6 12 12 16 14"/>
            </svg>
          </div>
          <div class="content">
            <div class="title">Mon – Sat 07:00 – 21:00</div>
            <div class="subtitle">We are open on</div>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: 'ContactInfoBar'
  }
  </script>
  
  <style scoped>
  .contact-bar {
    background-color: #003B7E;
    color: white;
    padding: 15px 0;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  }
  
  .container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 15px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .contact-item {
    display: flex;
    align-items: center;
    gap: 15px;
  }
  
  .icon {
    display: flex;
    align-items: center;
    justify-content: center;
    position: relative;
  }
  
  .icon svg {
    color: white;
  }
  
  .small-text {
    font-size: 8px;
    fill: white;
  }
  
  .content {
    display: flex;
    flex-direction: column;
  }
  
  .title {
    font-size: 16px;
    font-weight: 500;
    color: white;
  }
  
  .subtitle {
    font-size: 14px;
    color: rgba(255, 255, 255, 0.8);
    margin-top: 2px;
  }
  
  /* @media (max-width: 768px) {
    .container {
      flex-direction: column;
      gap: 20px;
    }
    
    .contact-item {
      width: 100%;
    }
  } */
  </style>