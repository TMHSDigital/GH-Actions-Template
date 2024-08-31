Animation Libraries Guide
Introduction
This guide provides an overview of the animation libraries included in your Jekyll project. These libraries allow you to easily add animations to your site, ranging from simple CSS animations to advanced JavaScript-driven effects.

1. Animate.css
Animate.css is a library of ready-to-use, cross-browser animations.

Usage Example:

html
Copy code
<h1 class="animate__animated animate__bounce">Hello World</h1>
Refer to the Animate.css Documentation for a full list of available animations and customization options.

2. AOS (Animate On Scroll)
AOS helps you to animate elements as you scroll down the page.

Usage Example:

html
Copy code
<div data-aos="fade-up">I will fade up as you scroll!</div>
Refer to the AOS Documentation for detailed usage instructions.

3. Hover.css
Hover.css provides CSS3 hover effects.

Usage Example:

html
Copy code
<a class="hvr-grow" href="#">Hover me!</a>
Refer to the Hover.css Documentation for a full list of hover effects.

4. Velocity.js
Velocity.js is a fast JavaScript animation engine.

Usage Example:

javascript
Copy code
Velocity(document.getElementById("element"), { opacity: 0.5 }, 1000);
Refer to the Velocity.js Documentation for more details on how to use this library.

5. Lottie.js
Lottie.js renders Adobe After Effects animations.

Usage Example:

javascript
Copy code
var animation = lottie.loadAnimation({
  container: document.getElementById('animationContainer'),
  renderer: 'svg',
  loop: true,
  autoplay: true,
  path: 'data.json' // Your animation file
});
Refer to the Lottie.js Documentation for instructions on how to use Lottie animations.

6. GSAP (GreenSock Animation Platform)
GSAP is a powerful JavaScript library for animations.

Usage Example:

javascript
Copy code
gsap.to(".class", { duration: 2, x: 100 });
ScrollTrigger Example:

javascript
Copy code
gsap.registerPlugin(ScrollTrigger);
gsap.to(".box", {
  scrollTrigger: ".box", // Animate this element on scroll
  x: 400,
  rotation: 360,
  duration: 3
});
Refer to the GSAP Documentation for more details and advanced usage.

Extending the Animation Libraries
You can add more libraries by following the same steps, or you can create custom animations using CSS and JavaScript. All libraries are already integrated into your project and are ready to be used in your HTML pages and components.