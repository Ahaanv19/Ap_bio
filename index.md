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
  <script src="https://unpkg.com/Sortablejs@latest/Sortable.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body { font-family: 'Segoe UI', sans-serif; background: #f4f7f6; color: #333; margin: 0; line-height: 1.6; }
    header, footer { background: linear-gradient(90deg, #556b2f, #89a77e); color: #fff; text-align: center; padding: 20px; }
    header h1 { margin: 0; font-size: 2.8rem; }
    .container { max-width: 1200px; margin: auto; padding: 20px; }
    section { margin-bottom: 60px; }
    h2 { color: #556b2f; border-bottom: 2px solid #89a77e; padding-bottom: 10px; margin-bottom: 20px; font-size: 2rem; }
    .activity { background: #fff; border-radius: 8px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); padding: 20px; margin-bottom: 30px; }
    .activity h3 { margin-top: 0; color: #6b8e23; font-size: 1.3rem; }
    .snapshots { display: flex; flex-wrap: wrap; gap: 15px; justify-content: center; margin-top: 15px; }
    .snap { position: relative; width: 120px; height: 120px; border: 2px solid #ccc; border-radius: 10px; display: flex; flex-wrap: wrap; align-content: flex-start; padding: 5px; cursor: grab; background: #fff; }
    .mouse { width: 20px; height: 20px; border-radius: 50%; margin: 3px; }
    .mouse.light { background: #f0e68c; }
    .mouse.dark { background: #333; }
    .count-badge { position: absolute; bottom: 5px; right: 5px; background: rgba(0,0,0,0.6); color: #fff; padding: 3px 6px; border-radius: 10px; font-size: 0.8rem; }
    button { background: #556b2f; color: #fff; border: none; padding: 12px 24px; border-radius: 6px; cursor: pointer; font-size: 1rem; transition: background 0.3s; }
    button:hover { background: #6b8e23; }
    table { width: 100%; border-collapse: collapse; margin-top: 15px; }
    th, td { border: 1px solid #bbb; padding: 10px; text-align: center; }
    td[contenteditable] { background: #eef3f2; }
    .chart-container { width: 100%; max-width: 800px; margin: 25px auto; }
    textarea { width: 100%; min-height: 120px; padding: 10px; border-radius: 6px; border: 1px solid #ccc; resize: vertical; }
    .quiz-feedback { font-weight: bold; margin-top: 10px; color: #b22222; }
  </style>
</head>
<body>
  <header>
    <h1>Rock Pocket Mouse: Evolution in Action</h1>
    <p>A College Board-aligned interactive lesson on natural selection and adaptation</p>
    <a href="https://www.biointeractive.org/classroom-resources/making-fittest-natural-selection-and-adaptation" class="button-link">Video to Watch First</a>
  </header>
<section style="max-width: 700px; margin: 30px auto; padding: 20px; background-color: #e2f0fb; border-radius: 8px; text-align: center; font-family: Arial, sans-serif;">
  <h2 style="color: #1a73e8; margin-bottom: 15px;">For Teachers</h2>
  <p style="font-size: 16px; color: #333;">
    Click the link below to access the <strong>Teacher’s Guide</strong> for this lesson.  
    This guide provides helpful strategies and resources to support your instruction.  
    Meanwhile, students will work on interactive activities designed to deepen their understanding as you teach.
  </p>
  <a href="https://www.biointeractive.org/sites/default/files/IDG_NaturalSelection.pdf" target="_blank" rel="noopener" style="display: inline-block; margin-top: 15px; padding: 12px 25px; background-color: #1a73e8; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">
    Download Teacher’s Guide
  </a>
</section>
<section style="max-width: 700px; margin: 30px auto; padding: 20px; background-color: #fef8e7; border-radius: 8px; text-align: center; font-family: Arial, sans-serif;">
  <h2 style="color: #d2691e; margin-bottom: 15px;">AP Biology Curriculum Connections</h2>
  <p style="font-size: 16px; color: #333;">
    This interactive lesson supports the following AP Biology Learning Objectives and Science Practices:
  </p>
  <ul style="list-style: none; padding-left: 0; font-size: 16px; color: #333;">
    <li><strong>Learning Objectives:</strong> IST-1.N, IST-1.O, IST-3.C, IST-3.D, IST-3.E, IST-3.G, IST-4.B, EVO-1.D</li>
    <li><strong>Science Practices:</strong> SP1, SP2, SP6</li>
  </ul>
</section>

<section>
  <h2>What Is Natural Selection?</h2>
  <p><strong>Natural selection</strong> is the process through which individuals with traits better suited to their environment tend to survive and reproduce more than others. Over time, this leads to the accumulation of advantageous traits in a population.</p>
  
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
      <h2>1. Introduction</h2>
      <div class="activity">
        <p>
          The rock pocket mouse (*Chaetodipus intermedius*) is a small desert rodent that has become a model organism for studying natural selection in real time. These mice live on both light-colored sand and dark volcanic rock in the Sonoran Desert.
        </p>
        <p>
          Their fur color tends to match the substrate where they live: light-colored mice on sand and dark-colored mice on lava. This variation plays a key role in predator avoidance and fitness. This interactive activity will correspond with Rock Pocket Mice HMI Video. Follow along.
        </p>
      </div>
    </section>

    <section>
      <h2>2. Objectives & Materials</h2>
      <div class="activity">
        <ul>
          <li>Analyze fur color distribution across time and habitat.</li>
          <li>Construct data tables and graphs based on simulated population data.</li>
          <li>Interpret the role of mutation and natural selection in phenotypic change.</li>
        </ul>
        <p><strong>Materials:</strong> This interactive lesson replaces paper-based colored pencils and illustrations. All simulation and data tools are included below.</p>
      </div>
    </section>

    <section>
      <h2>3. Data Analysis: Population Snapshots</h2>
      <div class="activity">
        <h3>3.1 Counting Exercise</h3>
        <p>Click through mouse icons to tally counts for each population snapshot.</p>
        <div id="snapshots" class="snapshots"></div>
      </div>
      <div class="activity">
        <h3>3.2 Chronological Ordering</h3>
        <p>Drag-and-drop the snapshots below into what you believe is the correct order from oldest to most recent.</p>
        <button id="checkOrder">Check Chronology</button>
        <p id="orderResult" class="quiz-feedback"></p>
      </div>
    </section>

    <section>
      <h2>4. Table & Graph Construction</h2>
      <div class="activity">
        <h3>4.1 Table Compilation</h3>
        <p>Use the snapshot data to complete the population counts over time:</p>
        <table id="dataTable">
          <thead>
            <tr><th>Seq</th><th>A Light</th><th>A Dark</th><th>B Light</th><th>B Dark</th></tr>
          </thead>
          <tbody></tbody>
        </table>
      </div>
      <div class="activity">
        <h3>4.2 Bar Graph</h3>
        <p>Click the button below to visualize fur color distribution over time at each site.</p>
        <button id="renderGraph">Show Bar Chart</button>
        <div class="chart-container">
          <canvas id="barChart"></canvas>
        </div>
      </div>
    </section>

    <section>
      <h2>5. Interpretation & Critical Thinking</h2>
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
  </div>

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

  <footer>© 2025 Interactive Evolution | Based on HHMI BioInteractive Curriculum</footer>

  <script>
    const snapshotsData = [
      { A_light: 15, A_dark: 2, B_light: 3, B_dark: 12 },
      { A_light: 14, A_dark: 3, B_light: 1, B_dark: 14 },
      { A_light: 17, A_dark: 0, B_light: 5, B_dark: 10 },
      { A_light: 10, A_dark: 7, B_light: 0, B_dark: 15 }
    ];

    const snapshotsContainer = document.getElementById('snapshots');
    snapshotsData.forEach((data, index) => {
      const snap = document.createElement('div');
      snap.className = 'snap';
      snap.dataset.index = index;
      for (let i = 0; i < data.A_light; i++) snap.innerHTML += '<div class="mouse light"></div>';
      for (let i = 0; i < data.A_dark; i++) snap.innerHTML += '<div class="mouse dark"></div>';
      snap.innerHTML += `<div class="count-badge">${index + 1}</div>`;
      snapshotsContainer.appendChild(snap);
    });

    Sortable.create(snapshotsContainer, {
      animation: 150,
      ghostClass: 'sortable-ghost'
    });

    document.getElementById('checkOrder').addEventListener('click', () => {
      const orderResult = document.getElementById('orderResult');
      const currentOrder = Array.from(snapshotsContainer.children).map(el => Number(el.dataset.index));
      const isCorrect = currentOrder.every((val, i) => val === i);
      orderResult.textContent = isCorrect ? 'Correct order!' : 'Incorrect - try again!';
    });

    const tableBody = document.querySelector('#dataTable tbody');
    snapshotsData.forEach((d, idx) => {
      const row = document.createElement('tr');
      row.innerHTML = `
        <td>${idx + 1}</td>
        <td contenteditable="true">${d.A_light}</td>
        <td contenteditable="true">${d.A_dark}</td>
        <td contenteditable="true">${d.B_light}</td>
        <td contenteditable="true">${d.B_dark}</td>
      `;
      tableBody.appendChild(row);
    });

    document.getElementById('renderGraph').addEventListener('click', () => {
      const ctx = document.getElementById('barChart').getContext('2d');
      const labels = snapshotsData.map((_, i) => `Time ${i + 1}`);
      const dataA_light = snapshotsData.map(d => d.A_light);
      const dataA_dark = snapshotsData.map(d => d.A_dark);
      const dataB_light = snapshotsData.map(d => d.B_light);
      const dataB_dark = snapshotsData.map(d => d.B_dark);

      new Chart(ctx, {
        type: 'bar',
        data: {
          labels: labels,
          datasets: [
            { label: 'A Light', data: dataA_light, backgroundColor: '#f0e68c' },
            { label: 'A Dark', data: dataA_dark, backgroundColor: '#333' },
            { label: 'B Light', data: dataB_light, backgroundColor: '#add8e6' },
            { label: 'B Dark', data: dataB_dark, backgroundColor: '#00008b' }
          ]
        },
        options: {
          responsive: true,
          scales: {
            y: {
              beginAtZero: true,
              title: { display: true, text: 'Mouse Count' }
            }
          }
        }
      });
    });
  </script>
</body>
</html>
