<h1>System Dynamics Final Project</h1>
<p><strong>Author:</strong> Juseong Kim (김주성, 2020103515) – Mechanical Engineering, Kyung Hee University</p>
<p class="note">Repository README generated on 23&nbsp;Jun&nbsp;2025 (KST).</p>

<!-- Pendulum simulation (animated GIF) -->
<figure style="text-align:center; margin: 1.5rem 0;">
  <img src="Result/pendulum.gif"
       alt="Animated simulation of the three-link pendulum"
       style="max-width:100%; height:auto; border:1px solid #ddd; border-radius:6px;">
  <figcaption style="font-size:0.9rem; color:#555;">
    Figure&nbsp;1. Time-lapse simulation of the three-link pendulum (X₂ slider highlighted).
  </figcaption>
</figure>


<h2>1. Overview</h2>
<p>This project analyses a planar three‑link pendulum using <em>constraint‑based multibody dynamics</em>.  The notebook:</p>
<ul>
<li>Derives the equations of motion (EoMs) symbolically.</li>
<li>Integrates the system with <code>solve_ivp</code> (RK45) for two different time‑step settings: <strong>1000&nbsp;steps</strong> (&Delta;t&nbsp;=&nbsp;1&nbsp;ms) and <strong>3000&nbsp;steps</strong> (&Delta;t&nbsp;=&nbsp;0.333&nbsp;ms).</li>
<li>Compares the X<sub>2</sub> slider displacement against pre‑computed CSV references (<code>pendulum_data.csv</code>, <code>pendulum_data3000.csv</code>).</li>
<li>Plots error metrics &amp; saves results to <code>figures/x2_accuracy.png</code>.</li>
</ul>

<h2>2. Data Description</h2>
<table>
<thead><tr><th>File</th><th>Columns</th><th>Description</th></tr></thead>
<tbody>
<tr><td><code>pendulum_data.csv</code></td><td>t, X2, θ3, θ4, …</td><td>Baseline solution (1000 steps)</td></tr>
<tr><td><code>pendulum_data_embedded.csv</code></td><td>t, X2, θ3, θ4, …</td><td>Embedded method solution (1000 steps)</td></tr>
<tr><td><code>pendulum_data3000.csv</code></td><td>t, X2, θ3, θ4, …</td><td>Fine‑step solution (3000 steps)</td></tr>
</tbody>
</table>

<h2>3. Results Snapshot</h2>
<p>Typical error values on an Intel i7‑12700H:</p>
<table>
<thead><tr><th>Metric</th><th>Value</th></tr></thead>
<tbody>
<tr><td>MAE (|ΔX<sub>2</sub>|)</td><td>≈ 1.2 × 10<sup>‑3</sup>&nbsp;m</td></tr>
<tr><td>RMSE</td><td>≈ 2.1 × 10<sup>‑3</sup>&nbsp;m</td></tr>
</tbody>
</table>
<p>See the generated figure for the full error curve.</p>
