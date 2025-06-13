<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1" />
<title>I Love You My Buggu Sneha</title>
<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@700&display=swap');

  /* Reset and base */
  * {
    box-sizing: border-box;
  }

  body, html {
    margin: 0;
    padding: 0;
    height: 100%;
    background: linear-gradient(135deg, #ff758c 0%, #7436d1 100%);
    font-family: 'Poppins', sans-serif;
    color: #fff;
    overflow-x: hidden;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  main {
    text-align: center;
    max-width: 600px;
    padding: 0 24px;
  }

  h1 {
    font-size: 3.5rem;
    font-weight: 700;
    line-height: 1.2;
    position: relative;
    margin-bottom: 24px;
    background: linear-gradient(90deg, #ffb6bc, #fff0f5, #ffb6bc);
    background-clip: text;
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    filter: drop-shadow(0 0 5px #ff6f91);
    animation: shimmeringText 4s ease-in-out infinite;
  }

  @keyframes shimmeringText {
    0%, 100% {
      background-position: 0% 50%;
    }
    50% {
      background-position: 100% 50%;
    }
  }

  p {
    font-size: 1.3rem;
    margin-top: 0;
    color: rgba(255 255 255 / 0.85);
    font-weight: 500;
  }

  /* Floating hearts */
  .heart {
    position: fixed;
    bottom: -50px;
    width: 24px;
    height: 24px;
    background-color: #ff4466;
    clip-path: polygon(
      50% 0%, 61% 8%, 68% 20%, 68% 32%, 50% 70%, 32% 32%, 32% 20%, 39% 8%
    );
    opacity: 0.85;
    animation-timing-function: linear;
    animation-iteration-count: infinite;
    will-change: transform, opacity;
  }

  /* Heart animation style */
  @keyframes floatUp {
    0% {
      transform: translateY(0) scale(1);
      opacity: 0.85;
    }
    80% {
      opacity: 0.5;
    }
    100% {
      transform: translateY(-120vh) scale(1.3);
      opacity: 0;
    }
  }

  /* Responsive text scaling */
  @media (max-width: 640px) {
    h1 {
      font-size: 2.6rem;
    }
    p {
      font-size: 1.1rem;
    }
  }

  @media (min-width: 641px) and (max-width: 1024px) {
    h1 {
      font-size: 3rem;
    }
    p {
      font-size: 1.2rem;
    }
  }
</style>
</head>
<body>
  <main role="main" aria-label="Love message to Buggu Sneha">
    <h1>I love you my Buggu Sneha</h1>
    <p>Every beat of my heart belongs to you, forever and always.</p>
  </main>

  <script>
    // Create multiple floating hearts with random horizontal positions and delays
    const heartCount = 20;

    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      // random horizontal position between 10% and 90% viewport width
      heart.style.left = `${Math.random() * 80 + 10}vw`;
      // random animation duration between 6 and 12 seconds
      const duration = Math.random() * 6 + 6;
      heart.style.animationDuration = `${duration}s`;
      // random animation delay negative so that hearts start at different times
      heart.style.animationDelay = `-${Math.random() * duration}s`;
      document.body.appendChild(heart);

      
      // Remove heart after animation ends to limit DOM elements
      heart.addEventListener('animationend', () => {
        heart.remove();
        createHeart(); // create a new heart to keep the count stable
      });
    }

    for(let i=0; i<heartCount; i++) {
      createHeart();
    }
  </script>
</body>
</html>

