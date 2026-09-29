<h1 align="center">Hi, I'm Navya Bhat 👋</h1>

<p align="center">
  <b>Building AI products with a business lens</b><br/>
  ex-BCG, Starbucks, Dow &nbsp;·&nbsp; MS CS @ USC &nbsp;·&nbsp; Kellogg MBA
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/navya-bhat/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:navya2392@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

---

### 👋 About

I spent eight years in consulting and strategy (BCG, L.E.K., Starbucks, Dow), building business cases, analyzing markets, and advising clients on growth and pricing decisions. I loved the problem-solving but wanted to build the solutions myself, so I went back for an **M.S. in Computer Science at USC**. Today, I pair that business background with hands-on machine learning and software engineering to build products that solve real problems, from computer vision models and full-stack apps to agentic AI workflows.

🎓 M.S. Computer Science, USC &nbsp;·&nbsp; MBA, Kellogg (Northwestern) &nbsp;·&nbsp; B.E. Chemical Engineering, ICT Mumbai

---

### 🔬 Lawrence Livermore National Laboratory &nbsp;·&nbsp; ML Intern, NIF

Two systems (code and data internal to LLNL):

#### Laser-optics defect detection

Finding small, low-contrast defects in NIF near-field laser images (previously manual review), where defects sit near beam edges and labels were incomplete.

- **Detector.** Benchmarked five architectures (FCOS, YOLO11, Faster R-CNN, RetinaNet, RT-DETR) and shipped an FCOS + YOLO11 ensemble with cluster voting across six runs for stability, plus a second-stage ResNet verifier (chosen from 12 CNNs) that checks each candidate in companion views.
- **Honest evaluation.** Center-distance matching instead of IoU, and location-aware 5-fold cross-validation so no physical site appears in both train and test.
- **Error analysis to fix.** One location drove nearly half of all misses, so Difference-of-Gaussians preprocessing plus a union vote recovered faint edge defects neither ensemble found alone.
- **Result.** ~0.90 recall, cutting 3-4 hours of manual review per week.

*Tech: Python, PyTorch, Ultralytics YOLO11, FCOS (ResNet50-FPN), ResNet18/34, OpenCV*

#### Agentic defect detection for 3D-printed lattices

A 6-agent Python workflow that turns a raw CT scan into a ranked, strut-level defect report.

- **Pipeline.** An orchestrator reruns only the missing or stale stages, then segmentation (Otsu), 3D registration of the design geometry to the scan, and strut-level scoring that assigns a severity tier, labeling a strut Uncertain rather than guessing when a verdict is unreliable.
- **Interaction.** A chat agent grounded in saved artifacts answers questions and acts on plain-language requests (e.g. adjusting a severity cutoff), rerunning only the affected stages.
- **Trust.** Explicit artifact handoffs keep every verdict traceable; the review dashboard links four views (triage report, chat, an interactive 3D lattice inspector, and a strut-level evidence view).

*Tech: Python, Streamlit, Three.js, Plotly, Matplotlib, NumPy* &nbsp;·&nbsp; 📎 [Slides](#) *(coming soon)*

---

### 🚀 Projects

- 🌊 **[FathomNet 2026](https://github.com/navya2392/FathomNet2026_ObjectDetection)** &nbsp;14th on the CLEF 2026 leaderboard; underwater object detection across a train/test institutional gap. &nbsp;📊 **[RESULTS](https://github.com/navya2392/FathomNet2026_ObjectDetection/blob/main/notebooks/final_pipeline.ipynb)**
- ⚙️ **[Early Fault Detection (TEP)](https://github.com/navya2392/EarlyFaultDetection)** &nbsp;Two-stage 1D-CNN, 99% F1 with 0% false alarms on the industrial TEP benchmark. &nbsp;📄 **[PAPER](https://github.com/navya2392/EarlyFaultDetection/blob/main/CSCI567_FaultDetection_ProjectReport.pdf)**
- 📚 **[ML Coursework](https://github.com/navya2392/ML-coursework)** &nbsp;The fundamentals across 8 algorithms.
- 🌐 **[Full-Stack Apps](https://github.com/navya2392/Full-Stack-Apps)** &nbsp;End-to-end React/Node and Python/Flask web apps.

---

### 🛠️ Skills

**Languages** &nbsp; Python · SQL · Java · C++ · JavaScript · C <br/>
**Machine Learning** &nbsp; PyTorch · TensorFlow/Keras · scikit-learn · XGBoost · pandas · NumPy · OpenCV · Ultralytics/YOLO · LLM agents <br/>
**Tools & Platforms** &nbsp; Git · Docker · Google Cloud Platform · REST APIs · Streamlit · React · Node.js · Flask · Tableau · Alteryx

---

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=navya2392&show_icons=true&hide_border=true" alt="GitHub stats" height="150"/>
</p>
