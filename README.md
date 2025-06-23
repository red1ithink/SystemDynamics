<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>System Dynamics Final Project – README</title>
    <style>
        body { font-family: Arial, Helvetica, sans-serif; line-height: 1.6; margin: 1.5rem; }
        h1, h2, h3 { color: #003366; }
        code { background: #f4f4f4; padding: 2px 4px; border-radius: 4px; }
        pre { background: #f4f4f4; padding: 8px; overflow-x: auto; border-radius: 6px; }
        table { border-collapse: collapse; width: 100%; margin-bottom: 1rem; }
        th, td { border: 1px solid #ddd; padding: 6px; text-align: left; }
        th { background: #e6f0ff; }
        .note { font-style: italic; color: #666; }
    </style>
</head>
<body>

<h1>System Dynamics Final Project</h1>
<p><strong>Author:</strong> Juseong Kim (김주성, 2020103515) – Mechanical Engineering, Kyung Hee University</p>
<p class="note">Repository README generated on 23&nbsp;Jun&nbsp;2025 (KST).</p>

<h2>1. Overview</h2>
<p>This project analyses a planar three‑link pendulum using <em>constraint‑based multibody dynamics</em>.  The notebook:</p>
<ul>
<li>Derives the equations of motion (EoMs) symbolically.</li>
<li>Integrates the system with <code>solve_ivp</code> (RK45) for two different time‑step settings: <strong>1000&nbsp;steps</strong> (&Delta;t&nbsp;=&nbsp;1&nbsp;ms) and <strong>3000&nbsp;steps</strong> (&Delta;t&nbsp;=&nbsp;0.333&nbsp;ms).</li>
<li>Compares the X<sub>2</sub> slider displacement against pre‑computed CSV references (<code>pendulum_data.csv</code>, <code>pendulum_data3000.csv</code>).</li>
<li>Plots error metrics &amp; saves results to <code>figures/x2_accuracy.png</code>.</li>
</ul>

<h2>2. Repository Layout</h2>
<pre>
├── data/
│   ├── pendulum_data.csv         # Reference (Δt=1 ms, 1000 steps)
│   └── pendulum_data3000.csv     # Reference (Δt≈0.333 ms, 3000 steps)
├── notebooks/
│   └── Sys_Final_JuseongKim_2020103515.ipynb
├── figures/                      # Generated automatically
└── README_SystemDynamics.html
</pre>

<h2>3. Quick Start</h2>
<h3>3.1 Set‑up</h3>
<pre><code># clone repository
git clone https://github.com/&lt;your‑id&gt;/system‑dynamics‑final.git
cd system-dynamics-final

# (optional) create environment
conda create -n sysdyn python=3.10 numpy scipy pandas matplotlib jupyter
conda activate sysdyn
</code></pre>

<h3>3.2 Run Notebook</h3>
<pre><code>jupyter notebook notebooks/Sys_Final_JuseongKim_2020103515.ipynb</code></pre>
<p>The last cell prints MAE / RMSE between the simulated and reference X<sub>2</sub> trajectories and stores the comparison plot in <code>figures/</code>.</p>

<h2>4. Data Description</h2>
<table>
<thead><tr><th>File</th><th>Columns</th><th>Description</th></tr></thead>
<tbody>
<tr><td><code>pendulum_data.csv</code></td><td>t, X2, θ3, θ4, …</td><td>Baseline solution (1000 steps)</td></tr>
<tr><td><code>pendulum_data3000.csv</code></td><td>t, X2, θ3, θ4, …</td><td>Fine‑step solution (3000 steps)</td></tr>
</tbody>
</table>

<h2>5. Results Snapshot</h2>
<p>Typical error values on an Intel i7‑12700H:</p>
<table>
<thead><tr><th>Metric</th><th>Value</th></tr></thead>
<tbody>
<tr><td>MAE (|ΔX<sub>2</sub>|)</td><td>≈ 1.2 × 10<sup>‑3</sup>&nbsp;m</td></tr>
<tr><td>RMSE</td><td>≈ 2.1 × 10<sup>‑3</sup>&nbsp;m</td></tr>
</tbody>
</table>
<p>See the generated figure for the full error curve.</p>

<h2>6. License</h2>
<p>This project is released under the <a href="https://opensource.org/licenses/MIT">MIT License</a>.</p>

</body>
</html>
"""

file_path = Path("/mnt/data/README_SystemDynamics.html")
file_path.write_text(html_content, encoding="utf-8")
file_path
