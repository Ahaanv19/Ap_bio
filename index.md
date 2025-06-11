---
layout: base
title: Homepage
search_exclude: true
nav: true
hide: true
menu: nav/home.html
---

<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Rock Pocket Mouse: Natural Selection and Adaptation</title>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body { font-family: 'Segoe UI', sans-serif; background: #f4f7f6; color: #333; margin: 0; line-height: 1.6; }
    header, footer { background: linear-gradient(90deg, #556b2f, #89a77e); color: #fff; text-align: center; padding: 20px; }
    header h1 { margin: 0; font-size: 2.8rem; }
    .container { max-width: 1200px; margin: auto; padding: 20px; }
    section { margin-bottom: 60px; }
    h2 { color: #556b2f; border-bottom: 2px solid #89a77e; padding-bottom: 10px; margin-bottom: 20px; font-size: 2rem; }
    .activity { background: #fff; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); padding: 20px; margin-bottom: 30px; }
    button { background: #556b2f; color: #fff; border: none; padding: 12px 24px; border-radius: 6px; cursor: pointer; font-size: 1rem; transition: background 0.3s; }
    button:hover { background: #6b8e23; }
    canvas { background: #fff; border-radius: 10px; }
    input[type="range"], input[type="number"] { width: 200px; }
    .slider-label { margin: 10px 0 5px; display: block; }
    #predatorSim div.mouse { width: 30px; height: 30px; border-radius: 50%; cursor: pointer; margin: 5px; display: inline-block; }
    .instruction { font-style: italic; color: #555; margin-bottom: 15px; }
  </style>
</head>
<body>
  <header>
    <h1>Rock Pocket Mouse: Evolution in Action</h1>
    <p>A College Board-aligned lesson on natural selection and adaptation</p>
    <a href="https://www.biointeractive.org/classroom-resources/making-fittest-natural-selection-and-adaptation" class="button-link">Video to Watch First</a>
  </header>

  <!-- KEEP THIS SECTION UNCHANGED -->
  <section style="max-width: 700px; margin: 30px auto; padding: 20px; background-color: #e2f0fb; border-radius: 8px; text-align: center;">
    <h2 style="color: #1a73e8;">For Teachers</h2>
    <p>Click the link below to access the <strong>Teacher’s Guide</strong> for this lesson.</p>
    <a href="https://www.biointeractive.org/sites/default/files/IDG_NaturalSelection.pdf" target="_blank" rel="noopener" style="display: inline-block; margin-top: 15px; padding: 12px 25px; background-color: #1a73e8; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">
      Download Teacher’s Guide. Teachers can teach lesson and students can work through actvity as lesson is taught.
    </a>
  </section>

  <!-- KEEP THIS SECTION UNCHANGED -->
  <section style="max-width: 700px; margin: 30px auto; padding: 20px; background-color: #fef8e7; border-radius: 8px; text-align: center;">
    <h2 style="color: #d2691e;">AP Biology Curriculum Connections</h2>
    <ul style="list-style: none; font-size: 16px;">
      <li><strong>Learning Objectives:</strong> IST-1.N, IST-1.O, IST-3.C, IST-3.D, IST-3.E, IST-3.G, IST-4.B, EVO-1.D</li>
      <li><strong>Science Practices:</strong> SP1, SP2, SP6</li>
    </ul>
  </section>

  <section>
  <h2>What Is Natural Selection?</h2>
  <p><strong>Natural selection</strong> is the process through which individuals with traits better suited to their environment are able to survive and reproduce more than others. Over time, this leads to the accumulation of advantageous traits in a population.</p>
  
  <ul>
    <li>Variation exists in populations due to mutations and genetic recombination.</li>
    <li>Not all individuals survive and reproduce equally—this is differential survival and reproduction.</li>
    <li>Traits that improve survival and reproduction increase in frequency over generations.</li>
    <li>The environment determines which traits are favorable. This makes natural selection a non-random process.</li>
  </ul>

  <p>This concept was first described by Charles Darwin and remains one of the fundamental principles of evolutionary biology. In the rock pocket mouse case, fur color variations affect visibility to predators, influencing survival based on the type of ground (lava rock vs. sand).</p>
</section>


  <div class="container">
    <section>
      <h2>Introduction</h2>
      <div class="activity">
        <p>
          The rock pocket mouse (*Chaetodipus intermedius*) is a small desert rodent that has become a model organism for studying natural selection in real time. These mice live on both light-colored sand and dark volcanic rock in the Sonoran Desert.
        </p>
        <p>
          Their fur color tends to match the substrate where they live: light-colored mice on sand and dark-colored mice on lava. This variation plays a key role in predator avoidance and fitness. This interactive activity will correspond with Rock Pocket Mice HMI Video. Follow along through the lesson, first watch the video, then the teacher will teach from the teacher guide as you follow along and particpate in these fun lessons.
        </p>
      </div>
    </section>

    <section>
      <h2>Objectives & Materials</h2>
      <div class="activity">
        <ul>
          <li>Analyze fur color distribution across time and habitat.</li>
          <li>Construct data tables and graphs based on simulated population data.</li>
          <li>Interpret the role of mutation and natural selection in phenotypic change.</li>
        </ul>
        <p><strong>Materials:</strong> You will not need any physical materials for this lesson, everything is included in the simulations and guides.</p>
      </div>
    </section>

  <div class="container">

    <section>
      <h2>1. Mutation & Fur Color Generator</h2>
      <div class="activity">
        <p class="instruction">Adjust the mutation rate and number of offspring, then generate offspring to see how many have light or dark fur.</p>
        <label class="slider-label">Mutation Rate (%): <span id="mutationRateVal">5</span></label>
        <input type="range" id="mutationRate" min="0" max="100" value="5" />
        <br />
        <label class="slider-label">Number of Offspring: </label>
        <input type="number" id="offspringCount" value="20" min="1" max="200" />
        <br/><br/>
        <button onclick="runMutationSim()">Generate Offspring</button>
        <canvas id="mutationChart" width="400" height="200"></canvas>
      </div>
    </section>

    <section>
      <h2>2. Habitat Survival Simulation</h2>
      <div class="activity">
        <p class="instruction">Select a habitat background and observe which fur color mice survive better.</p>
        <p>Select Habitat:</p>
        <button onclick="runHabitatSim('sand')">Light Sand</button>
        <button onclick="runHabitatSim('lava')">Dark Lava</button>
        <canvas id="habitatChart" width="400" height="200"></canvas>
      </div>
    </section>

    <section>
      <h2>3. Selection Over Generations</h2>
      <div class="activity">
        <p class="instruction">Set the initial percentage of dark fur mice and simulate changes over 10 generations due to natural selection.</p>
        <p>Initial Population (Dark %): <input id="darkStart" type="number" min="0" max="100" value="50" />%</p>
        <button onclick="runGenerations()">Run Generational Simulation</button>
        <canvas id="generationChart" width="400" height="200"></canvas>
      </div>
    </section>

    <section>
      <h2>4. Be the Predator!</h2>
      <div class="activity">
        <p class="instruction">Click on mice to “catch” them. Mice with fur color contrasting the background are easier prey.</p>
        <p>Try to catch as many contrasting mice as you can!</p>
        <div id="predatorSim" style="display:flex; flex-wrap:wrap; gap:10px;"></div>
        <p id="predatorScore"></p>
        <button onclick="setupPredatorSim()">Reset</button>
      </div>
    </section>

    <section>
      <h2>5. Mutation Rate Impact Over Time</h2>
      <div class="activity">
        <p class="instruction">Adjust mutation rate and simulate its effect on dark fur percentage across 15 generations.</p>
        <label class="slider-label">Mutation Rate (%): <span id="mutRateValGen">5</span></label>
        <input type="range" id="mutRateGen" min="0" max="20" value="5" />
        <br/>
        <button onclick="runMutationImpactGen()">Run Simulation</button>
        <canvas id="mutationGenChart" width="400" height="200"></canvas>
      </div>
    </section>

    <section>
      <h2>6. Environmental Change and Adaptation</h2>
      <div class="activity">
        <p class="instruction">Select an environment and simulate population adaptation over 12 generations.</p>
        <p>Select Environment:</p>
        <select id="environmentSelect">
          <option value="desert">Desert (light sand)</option>
          <option value="volcanic">Volcanic (dark lava)</option>
          <option value="mixed">Mixed Habitat</option>
        </select>
        <br/><br/>
        <button onclick="runEnvAdaptation()">Run Adaptation Simulation</button>
        <canvas id="envAdaptChart" width="400" height="200"></canvas>
      </div>
    </section>

    <section>
      <h2>7. Predation Pressure Toggle</h2>
      <div class="activity">
        <p class="instruction">Use the slider to adjust predator pressure and see how it affects survival rates of light and dark fur mice.</p>
        <label class="slider-label">Predation Pressure (%): <span id="predPressureVal">50</span></label>
        <input type="range" id="predPressure" min="0" max="100" value="50" />
        <br/>
        <button onclick="runPredPressureSim()">Simulate Survival</button>
        <canvas id="predPressureChart" width="400" height="200"></canvas>
      </div>
    </section>

    <section>
      <h2>8. Fur Color Frequency Toggle</h2>
      <div class="activity">
        <p class="instruction">Adjust initial fur color frequency and simulate how it changes under selection after 10 generations.</p>
        <label class="slider-label">Initial Dark Fur Frequency (%): <span id="initDarkFreqVal">50</span></label>
        <input type="range" id="initDarkFreq" min="0" max="100" value="50" />
        <br/>
        <button onclick="runFurFreqToggle()">Run Frequency Simulation</button>
        <canvas id="furFreqChart" width="400" height="200"></canvas>
      </div>
    </section>

  <section>
      <h2>9. Interpretation & Critical Thinking</h2>
      <div class="activity">
        <h3>Short Response Prompts</h3>
        <ol>
          <li>Why does fur color influence rock pocket mouse fitness?</li>
          <li>Why did the dark-colored mice not increase in frequency at Location A?</li>
          <li>Describe changes at Location B and predict what the population will look like in 100 years.</li>
          <li>How is mutation a random process, but natural selection non-random?</li>
        </ol>
        <textarea placeholder="Write your response here..."></textarea>
      </div>
    </section>


  <section>
  <h2>Multiple Choice Questions</h2>
  <ol>
    <li>
      Which of the following best describes the process of natural selection?<br/>
      <strong>A.</strong> Traits acquired during an organism’s lifetime are inherited<br/>
      <strong>B.</strong> All individuals in a population have equal chances of survival<br/>
      <strong>C.</strong> Individuals with favorable traits reproduce more successfully<br/>
      <strong>D.</strong> Evolution occurs randomly and independently of the environment<br/>
      <br/><em><strong>Correct Answer: C</strong></em>
    </li>
    <li>
      In the rock pocket mouse population, which of the following would most likely cause an increase in dark-colored fur?<br/>
      <strong>A.</strong> Decrease in predators<br/>
      <strong>B.</strong> Increased competition for food<br/>
      <strong>C.</strong> Mutation causing albinism<br/>
      <strong>D.</strong> Expansion of lava rock habitat<br/>
      <br/><em><strong>Correct Answer: D</strong></em>
    </li>
  </ol>
</section>

  </div>

  <footer>© 2025 AP Bio Prep | Based on HHMI BioInteractive Curriculum</footer>

  <script>
    // 1. Mutation & Fur Color Generator
    const ctx1 = document.getElementById('mutationChart').getContext('2d');
    let mutationChart;

    document.getElementById("mutationRate").addEventListener("input", (e) => {
      document.getElementById("mutationRateVal").innerText = e.target.value;
    });

    function runMutationSim() {
      const rate = parseInt(document.getElementById("mutationRate").value);
      const count = parseInt(document.getElementById("offspringCount").value);
      let light = 0, dark = 0;
      for (let i = 0; i < count; i++) {
        const mutated = Math.random() < rate / 100;
        const fur = mutated ? (Math.random() < 0.5 ? 'dark' : 'light') : 'light';
        if (fur === 'dark') dark++;
        else light++;
      }

      if(mutationChart) mutationChart.destroy();
      mutationChart = new Chart(ctx1, {
        type: 'bar',
        data: {
          labels: ['Light Fur', 'Dark Fur'],
          datasets: [{
            label: 'Offspring Count',
            data: [light, dark],
            backgroundColor: ['#f0e68c', '#333']
          }]
        },
        options: {
          responsive: true,
          scales: { y: { beginAtZero: true } }
        }
      });
    }

    // 2. Habitat Survival Simulation
    const ctx2 = document.getElementById('habitatChart').getContext('2d');
    let habitatChart;

    function runHabitatSim(habitat) {
      const total = 40;
      let survivors = { light: 0, dark: 0 };
      for (let i = 0; i < total; i++) {
        const fur = Math.random() < 0.5 ? 'light' : 'dark';
        const visible = (fur === 'light' && habitat === 'lava') || (fur === 'dark' && habitat === 'sand');
        const survives = Math.random() > (visible ? 0.6 : 0.1);
        if (survives) survivors[fur]++;
      }

      if(habitatChart) habitatChart.destroy();
      habitatChart = new Chart(ctx2, {
        type: 'bar',
        data: {
          labels: ['Light Fur', 'Dark Fur'],
          datasets: [{
            label: `Survivors in ${habitat}`,
            data: [survivors.light, survivors.dark],
            backgroundColor: ['#f0e68c', '#333']
          }]
        },
        options: {
          responsive: true,
          scales: { y: { beginAtZero: true } }
        }
      });
    }

    // 3. Selection Over Generations
    const ctx3 = document.getElementById('generationChart').getContext('2d');
    let generationChart;

    function runGenerations() {
      const startDark = parseInt(document.getElementById('darkStart').value);
      let darkPct = startDark;
      const genData = [];
      for (let gen = 0; gen <= 10; gen++) {
        genData.push(darkPct);
        // Apply natural selection model - increase dark fur by 10% of remaining light
        darkPct += (100 - darkPct) * 0.1;
        if (darkPct > 100) darkPct = 100;
      }

      if(generationChart) generationChart.destroy();
      generationChart = new Chart(ctx3, {
        type: 'line',
        data: {
          labels: Array.from({ length: 11 }, (_, i) => `Gen ${i}`),
          datasets: [{
            label: 'Dark Fur % Over Generations',
            data: genData,
            fill: false,
            borderColor: '#333',
            tension: 0.3
          }]
        },
        options: {
          responsive: true,
          scales: {
            y: { beginAtZero: true, max: 100 }
          }
        }
      });
    }

    // 4. Be the Predator!
    function setupPredatorSim() {
      const container = document.getElementById('predatorSim');
      const scoreText = document.getElementById('predatorScore');
      container.innerHTML = '';
      let score = 0;

      for (let i = 0; i < 20; i++) {
        const mouse = document.createElement('div');
        const fur = Math.random() < 0.5 ? 'light' : 'dark';
        mouse.className = 'mouse';
        mouse.style.background = fur === 'light' ? '#f0e68c' : '#333';
        mouse.title = `Fur: ${fur}`;
        mouse.addEventListener('click', () => {
          if (mouse.style.opacity === '0.2') return; // already caught
          mouse.style.opacity = 0.2;
          score++;
          scoreText.innerText = `You caught ${score} mice!`;
        });
        container.appendChild(mouse);
      }
      scoreText.innerText = 'Catch mice by clicking on them!';
    }
    setupPredatorSim();

    // 5. Mutation Rate Impact Over Time
    const ctx5 = document.getElementById('mutationGenChart').getContext('2d');
    let mutationGenChart;

    document.getElementById('mutRateGen').addEventListener('input', (e) => {
      document.getElementById('mutRateValGen').innerText = e.target.value;
    });

    function runMutationImpactGen() {
      const mutationRate = parseInt(document.getElementById('mutRateGen').value);
      let darkPct = 10;
      const generations = 15;
      const data = [];

      for (let i = 0; i <= generations; i++) {
        data.push(darkPct);
        // Mutation increases dark fur proportion by mutationRate%, but selection reduces it by 5%
        darkPct = darkPct + (100 - darkPct) * (mutationRate / 100) - darkPct * 0.05;
        if (darkPct < 0) darkPct = 0;
        if (darkPct > 100) darkPct = 100;
      }

      if(mutationGenChart) mutationGenChart.destroy();
      mutationGenChart = new Chart(ctx5, {
        type: 'line',
        data: {
          labels: Array.from({ length: generations + 1 }, (_, i) => `Gen ${i}`),
          datasets: [{
            label: 'Dark Fur % with Mutation Impact',
            data: data,
            borderColor: '#333',
            fill: false,
            tension: 0.3
          }]
        },
        options: {
          responsive: true,
          scales: { y: { beginAtZero: true, max: 100 } }
        }
      });
    }

    // 6. Environmental Change and Adaptation
    const ctx6 = document.getElementById('envAdaptChart').getContext('2d');
    let envAdaptChart;

    function runEnvAdaptation() {
      const env = document.getElementById('environmentSelect').value;
      const generations = 12;
      const lightAdvantage = env === 'desert' ? 0.3 : env === 'volcanic' ? -0.3 : 0;
      let darkPct = 50;
      const data = [];

      for (let i = 0; i <= generations; i++) {
        data.push(darkPct);
        // Adaptation shifts darkPct by advantage factor each gen
        darkPct = darkPct + (darkPct * lightAdvantage);
        // Clamp values between 0 and 100
        if (darkPct < 0) darkPct = 0;
        if (darkPct > 100) darkPct = 100;
      }

      if(envAdaptChart) envAdaptChart.destroy();
      envAdaptChart = new Chart(ctx6, {
        type: 'line',
        data: {
          labels: Array.from({ length: generations + 1 }, (_, i) => `Gen ${i}`),
          datasets: [{
            label: `Dark Fur % in ${env.charAt(0).toUpperCase() + env.slice(1)} Environment`,
            data: data,
            borderColor: '#556b2f',
            fill: false,
            tension: 0.3
          }]
        },
        options: {
          responsive: true,
          scales: { y: { beginAtZero: true, max: 100 } }
        }
      });
    }

    // 7. Predation Pressure Toggle
    const ctx7 = document.getElementById('predPressureChart').getContext('2d');
    let predPressureChart;

    document.getElementById('predPressure').addEventListener('input', (e) => {
      document.getElementById('predPressureVal').innerText = e.target.value;
    });

    function runPredPressureSim() {
      const pressure = parseInt(document.getElementById('predPressure').value);
      const baseSurvival = 80;
      // Light fur survival decreases by predation pressure * 0.5, dark increases by 0.3
      const lightSurvival = Math.max(0, baseSurvival - pressure * 0.5);
      const darkSurvival = Math.min(100, baseSurvival + pressure * 0.3);

      if(predPressureChart) predPressureChart.destroy();
      predPressureChart = new Chart(ctx7, {
        type: 'bar',
        data: {
          labels: ['Light Fur', 'Dark Fur'],
          datasets: [{
            label: 'Survival Rate (%)',
            data: [lightSurvival, darkSurvival],
            backgroundColor: ['#f0e68c', '#333']
          }]
        },
        options: {
          responsive: true,
          scales: { y: { beginAtZero: true, max: 100 } }
        }
      });
    }

    // 8. Fur Color Frequency Toggle
    const ctx8 = document.getElementById('furFreqChart').getContext('2d');
    let furFreqChart;

    document.getElementById('initDarkFreq').addEventListener('input', (e) => {
      document.getElementById('initDarkFreqVal').innerText = e.target.value;
    });

    function runFurFreqToggle() {
      const initDark = parseInt(document.getElementById('initDarkFreq').value);
      let darkPct = initDark;
      const generations = 10;
      const data = [];

      for (let i = 0; i <= generations; i++) {
        data.push(darkPct);
        // Natural selection favors dark fur by increasing 7% per gen up to 100%
        darkPct += (100 - darkPct) * 0.07;
        if (darkPct > 100) darkPct = 100;
      }

      if(furFreqChart) furFreqChart.destroy();
      furFreqChart = new Chart(ctx8, {
        type: 'line',
        data: {
          labels: Array.from({ length: generations + 1 }, (_, i) => `Gen ${i}`),
          datasets: [{
            label: 'Dark Fur Frequency (%)',
            data: data,
            borderColor: '#333',
            fill: false,
            tension: 0.3
          }]
        },
        options: {
          responsive: true,
          scales: { y: { beginAtZero: true, max: 100 } }
        }
      });
    }

  </script>


