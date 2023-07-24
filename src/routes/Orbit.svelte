<script>
  const canvas = document.getElementById("canvas");
  const ctx = canvas?.getContext("2d");

  // Define the solar system data (semi-major axis in AU and eccentricity)
  const planets = [
    { name: "Mercury", semiMajorAxis: 0.39, eccentricity: 0.206 },
    { name: "Venus", semiMajorAxis: 0.72, eccentricity: 0.007 },
    { name: "Earth", semiMajorAxis: 1.0, eccentricity: 0.017 },
    // Add other planets here...
  ];

  // Define the scaling factor for the orbits (to fit on the canvas)
  const orbitScale = 100;

  // Function to calculate the position of a planet along its elliptical orbit
  function calculateOrbitPosition(semiMajorAxis, eccentricity, angle) {
    const distanceFromFocus =
      (semiMajorAxis * (1 - eccentricity * eccentricity)) /
      (1 + eccentricity * Math.cos(angle));
    return distanceFromFocus * orbitScale;
  }

  // Function to draw the orbits and planets
  function drawSolarSystem() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    // Draw the orbits
    ctx.strokeStyle = "rgba(255, 255, 255, 0.3)";
    ctx.beginPath();
    for (let planet of planets) {
      const orbitRadius = planet.semiMajorAxis * orbitScale;
      ctx.ellipse(
        canvas.width / 2,
        canvas.height / 2,
        orbitRadius,
        orbitRadius * (1 - planet.eccentricity),
        0,
        0,
        2 * Math.PI
      );
    }
    ctx.stroke();

    // Draw the planets
    const time = Date.now() * 0.0001; // Adjust the speed of the orbits
    for (let i = 0; i < planets.length; i++) {
      const planet = planets[i];
      const orbitRadius = planet.semiMajorAxis * orbitScale;
      const angle =
        time *
        Math.sqrt(
          1 /
            (planet.semiMajorAxis * planet.semiMajorAxis * planet.semiMajorAxis)
        );
      const xPos =
        canvas.width / 2 +
        calculateOrbitPosition(
          planet.semiMajorAxis,
          planet.eccentricity,
          angle
        ) *
          Math.cos(angle);
      const yPos =
        canvas.height / 2 +
        calculateOrbitPosition(
          planet.semiMajorAxis,
          planet.eccentricity,
          angle
        ) *
          Math.sin(angle);

      // Draw the planet
      ctx.beginPath();
      ctx.fillStyle = "white";
      ctx.arc(xPos, yPos, 5, 0, 2 * Math.PI);
      ctx.fill();

      // Optional: Draw the planet name
      ctx.fillStyle = "white";
      ctx.font = "12px Arial";
      ctx.fillText(planet.name, xPos + 10, yPos + 4);
    }

    requestAnimationFrame(drawSolarSystem);
  }

  // Call the function to start drawing the solar system
  drawSolarSystem();
</script>

<body>
  <canvas id="canvas" />
  <!-- Rest of your HTML content -->
</body>
