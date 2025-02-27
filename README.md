<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive Particles</title>
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <style>
         {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
 
        body {
            background-color: black;
            color: white;
            font-family: Arial, sans-serif;
        }

        .hero {
            position: relative;
            width: 100vw;
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            overflow: hidden;
        }

        #particles-js {
            position: absolute;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
        }

        .content {
            position: relative;
            z-index: 10;
        }

        .content h1 {
            font-size: 2.5rem;
            cursor: pointer; /* Makes it look interactive */
            transition: color 0.3s ease-in-out;
        }

        .content p {
            font-size: 1.2rem;
            opacity: 0.8;
        }

        .btn {
            display: inline-block;
            margin-top: 20px;
            padding: 10px 20px;
            background-color: white;
            color: black;
            border-radius: 20px;
            text-decoration: none;
            font-size: 1rem;
        }

        .btn:hover {
            color: rgb(255, 255, 255);
            background-color: rgb(0, 0, 0);
            transition: color 3s ease, background-color 3s ease;
        }
    </style>
</head>
<body>

    <div class="hero">
        <div id="particles-js"></div>
        <div class="content">
            <h1 id="hoverText">bofa</h1>
            <p>deeee.</p>
            <a href="#" class="btn">Learn more</a>
        </div>
    </div>

    <script>
        // Hover effect to change text
        const textElement = document.getElementById("hoverText");

        textElement.addEventListener("mouseover", function() {
            textElement.textContent = "deezzz nut";
        });

        textElement.addEventListener("mouseout", function() {
            textElement.textContent = "bofa";
        });

        // Particles.js configuration
        particlesJS("particles-js", {
            particles: {
                number: {
                    value: 100, 
                    density: { enable: true, value_area: 800 }
                },
                color: { value: "#ffffff" }, 
                shape: { type: "circle" },
                opacity: { value: 0.7, random: true },
                size: { value: 3, random: true },
                move: {
                    enable: true,
                    speed: 2, 
                    direction: "none",
                    random: false,
                    straight: false,
                    out_mode: "out",
                    attract: { enable: false }
                },
                line_linked: {
                    enable: true,
                    distance: 150,
                    color: "#ffffff",
                    opacity: 0.5,
                    width: 1
                }
            },
            interactivity: {
                detect_on: "canvas",
                events: {
                    onhover: { enable: true, mode: "repulse" }, 
                    onclick: { enable: true, mode: "push" }
                },
                modes: {
                    repulse: { distance: 100, duration: 0.4 }
                }
            },
            retina_detect: true
        });
    </script>

</body>
</html>


