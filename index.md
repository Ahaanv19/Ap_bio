---
layout: base
title: Rock Pocket Mice Lesson
search_exclude: true
nav: true
hide: true
menu: nav/home.html
---


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rock Pocket Mouse Evolution Interactive</title>
  <script src="https://unpkg.com/Sortablejs@latest/Sortable.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
  <style>
    body { font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; background: #f4f7f6; color: #333; margin: 0; }
    header { background: linear-gradient(90deg, #556b2f, #89a77e); color: #fff; padding: 30px 20px; text-align: center; }
    header h1 { font-size: 2.5rem; margin: 0; }
    .container { max-width: 1100px; margin: auto; padding: 20px; }
    section { margin-bottom: 50px; }
    h2 { color: #556b2f; border-bottom: 2px solid #89a77e; padding-bottom: 10px; }
    .snapshots { display: flex; flex-wrap: wrap; gap: 15px; justify-content: center; margin-top: 15px; }
    .snap { position: relative; width: 140px; border: 2px solid #ccc; border-radius: 10px; overflow: hidden; cursor: grab; }
    .snap img { display: block; width: 100%; }
    .count-badge { position: absolute; bottom: 5px; right: 5px; background: rgba(0,0,0,0.6); color: #fff; padding: 4px 8px; border-radius: 12px; font-size: 0.9rem; }
    button { background: #556b2f; color: #fff; border: none; padding: 12px 24px; border-radius: 6px; cursor: pointer; font-size: 1rem; transition: background 0.3s; }
    button:hover { background: #6b8e23; }
    table { width: 100%; border-collapse: collapse; margin-top: 15px; }
    th, td { border: 1px solid #bbb; padding: 10px; text-align: center; }
    td[contenteditable] { background: #eef3f2; }
    .chart-container { width: 100%; max-width: 700px; margin: 25px auto; }
    .slider-container { display: flex; align-items: center; gap: 15px; margin: 20px 0; justify-content: center; }
    input[type=range] { width: 60%; }
    textarea { width: 100%; min-height: 100px; padding: 10px; border-radius: 6px; border: 1px solid #ccc; resize: vertical; }
    .quiz-feedback { font-weight: bold; margin-top: 10px; }
    footer { text-align: center; padding: 15px; font-size: 0.9rem; color: #666; }
  </style>
</head>
<body>
  <header>
    <h1>Rock-Pocket Mouse: Evolution in Action</h1>
    <p>Interactive lesson on natural selection, adaptation, and data analysis</p>
  </header>

  <div class="container">
    <section>
      <h2>Introduction & Materials</h2>
      <p>Explore how coat color in <em>Perognathus intermedius</em> is shaped by predation and environment. Light mice blend in sand, dark mice on lava.</p>
      <ul>
        <li>4 unlabeled population snapshots</li>
        <li>Colored pencils or digital graphing</li>
        <li>"The Making of the Fittest" video from HHMI</li>
      </ul>
    </section>

    <section>
      <h2>1. Snapshots: Count & Order</h2>
      <p>Click mice in each snapshot to tally light vs. dark. Drag to arrange chronologically.</p>
      <div id="snapshots" class="snapshots"></div>
      <button id="checkOrder">Check Chronology</button>
      <p id="orderResult" class="quiz-feedback"></p>
    </section>

    <section>
      <h2>2. Data Table & Interactive Graph</h2>
      <p>Finalize your counts and visualize population shifts over time.</p>
      <table id="dataTable">
        <thead><tr><th>Seq</th><th>A Light</th><th>A Dark</th><th>B Light</th><th>B Dark</th></tr></thead>
        <tbody></tbody>
      </table>
      <button id="renderGraph">Show Bar Chart</button>
      <div class="chart-container"><canvas id="barChart"></canvas></div>
    </section>

    <section>
      <h2>3. Evolution Simulation</h2>
      <p>Adjust time and selection strength to predict future frequencies.</p>
      <div class="slider-container">
        <label for="timeSlider">Years: <span id="timeValue">0</span></label>
        <input type="range" id="timeSlider" min="0" max="100" value="0">
        <label for="rSlider">Selection Rate: <span id="rValue">0.05</span></label>
        <input type="range" id="rSlider" min="0" max="1" step="0.01" value="0.05">
      </div>
      <div class="chart-container"><canvas id="simChart"></canvas></div>
    </section>

    <section>
      <h2>4. Concept-Check Quizzes</h2>
      <div>
        <p><strong>Q1:</strong> Why does fur color affect fitness?</p>
        <textarea id="ans1"></textarea>
        <p><strong>Q2:</strong> Why didn’t dark mice persist at Location A?</p>
        <textarea id="ans2"></textarea>
        <p><strong>Q3:</strong> Summarize changes at Location B and predict 100 years ahead.</p>
        <textarea id="ans3"></textarea>
        <p><strong>Q4:</strong> Explain how mutation is random but selection isn’t.</p>
        <textarea id="ans4"></textarea>
        <button id="submitQuiz">Submit Answers</button>
        <p id="quizFeedback" class="quiz-feedback"></p>
      </div>
    </section>
  </div>

  <footer>© 2025 Interactive Evolution Lessons</footer>

  <script>
    // Initialize snapshots with clickable counts and draggable ordering
    const imagePaths = ['snapshot1.png','snapshot2.png','snapshot3.png','snapshot4.png'];
    const container = document.getElementById('snapshots');
    imagePaths.forEach((src,id) => {
      const div = document.createElement('div'); div.className='snap'; div.dataset.id=id;
      const img = document.createElement('img'); img.src=src; div.appendChild(img);
      const badge = document.createElement('div'); badge.className='count-badge'; badge.textContent='0/0'; div.appendChild(badge);
      div.light=0; div.dark=0;
      img.onclick = e => {
        const rect=e.target.getBoundingClientRect();
        const x=e.clientX-rect.left;
        if(x<rect.width/2) div.light++; else div.dark++;
        badge.textContent = div.light + '/' + div.dark;
      };
      container.appendChild(div);
    });
    Sortable.create(container,{ animation:150 });
    document.getElementById('checkOrder').onclick = () => {
      const ids = Array.from(container.children).map(d=>d.dataset.id);
      const correct='0,1,2,3';
      document.getElementById('orderResult').textContent = ids.join(',')===correct ? 'Perfect chronology!' : 'Keep trying!';
      buildTable(ids);
    };

    // Build data table based on ordered snapshots
    function buildTable(order) {
      const tbody=document.querySelector('#dataTable tbody'); tbody.innerHTML='';
      order.forEach((id,i)=>{
        const div=container.children[i];
        const row=document.createElement('tr');
        row.innerHTML = `<td>${i+1}</td><td contenteditable>${div.light}</td><td contenteditable>${div.dark}</td><td contenteditable>0</td><td contenteditable>0</td>`;
        tbody.appendChild(row);
      });
    }

    // Bar chart
    document.getElementById('renderGraph').onclick = () => {
      const rows=document.querySelectorAll('#dataTable tbody tr');
      const labels=[],dataSets={'A Light':[],'A Dark':[],'B Light':[],'B Dark':[]};
      rows.forEach(r=>{const c=r.querySelectorAll('td'); labels.push(c[0].textContent);
        ['A Light','A Dark','B Light','B Dark'].forEach((k,i)=>dataSets[k].push(+c[i+1].textContent||0));});
      new Chart(document.getElementById('barChart').getContext('2d'),{type:'bar',data:{labels,datasets:Object.entries(dataSets).map(([l,d])=>({label:l,data:d}))},options:{responsive:true,scales:{y:{beginAtZero:true}}}});
    };

    // Simulation
    const simCtx=document.getElementById('simChart').getContext('2d');
    const simChart=new Chart(simCtx,{type:'bar',data:{labels:['Light','Dark'],datasets:[{data:[1,0]}]},options:{scales:{y:{beginAtZero:true,max:1}}}});
    function updateSim() {
      const t=+document.getElementById('timeSlider').value;
      const r=+document.getElementById('rSlider').value;
      document.getElementById('timeValue').textContent=t;
      document.getElementById('rValue').textContent=r;
      const P0=0.2, P=1/(1+((1-P0)/P0)*Math.exp(-r*t));
      simChart.data.datasets[0].data=[1-P,P]; simChart.update();
    }
    document.getElementById('timeSlider').oninput=updateSim;
    document.getElementById('rSlider').oninput=updateSim;
    updateSim();

    // Quiz feedback
    document.getElementById('submitQuiz').onclick = () => {
      const f=document.getElementById('quizFeedback');
      f.textContent = 'Great effort! Compare your answers to key concepts: camouflage, selective pressure, allele frequency changes, and non-random survival.';
    };
  </script>
</body>
</html>


