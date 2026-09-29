<h1 align="center">Hi, I'm Navya Bhat 👋</h1>

<p align="center">
  <b>Machine Learning Engineer &amp; product builder.</b><br/>
  Eight years in strategy and consulting, now building the models and products behind the decisions.
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/navya-bhat/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:navya2392@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" alt="Email"/></a>
</p>

---

### 👋 About

I spent eight years in consulting and strategy (BCG, L.E.K., Starbucks, Dow), building business cases and analyzing markets. I loved the problem-solving but wanted to build the solutions myself, so I went back for an **M.S. in Computer Science at USC**. Today I pair that business background with hands-on machine learning and software engineering to build products that solve real problems, from computer vision models and full-stack apps to agentic AI workflows.

🎓 M.S. Computer Science, USC &nbsp;·&nbsp; MBA, Kellogg (Northwestern) &nbsp;·&nbsp; B.E. Chemical Engineering, ICT Mumbai

---

### 🔬 Lawrence Livermore National Laboratory &nbsp;·&nbsp; ML Intern, NIF

Two systems (code and data internal to LLNL):

**Laser-optics defect detection.** End-to-end detector for small, low-contrast defects in NIF near-field laser images, previously found by manual review, where defects sit near beam edges and the labels were incomplete. I benchmarked five detectors (FCOS, YOLO11, Faster R-CNN, RetinaNet, RT-DETR) and settled on an FCOS + YOLO11 ensemble, three seeds each, with cluster voting across all six runs for stability; a second-stage ResNet verifier, chosen from 12 CNNs, checks each candidate in companion views to filter false positives. Because labels were incomplete, I used center-distance matching instead of IoU and location-aware 5-fold cross-validation so no physical site appeared in both train and test, giving an honest estimate of performance at new locations. Error analysis showed one location drove nearly half of all misses, so I added Difference-of-Gaussians preprocessing plus a union vote to recover faint edge defects neither ensemble found alone. The final system reached ~0.90 recall and cut 3-4 hours of manual review per week.
<br/>*Tech: Python, PyTorch, Ultralytics YOLO11, FCOS (ResNet50-FPN), ResNet18/34, OpenCV*

**Agentic defect detection for 3D-printed lattices.** A 6-agent Python workflow that turns a raw CT scan into a ranked, strut-level defect report. An orchestrator runs only the stages whose inputs are missing or stale, then segmentation (Otsu), 3D registration of the design geometry to the scan, and strut-level scoring that samples each strut, computes support metrics, and assigns a severity tier, labeling a strut Uncertain rather than guessing when a verdict is unreliable. A report agent assembles a dashboard from saved artifacts, and a chat agent grounded in those artifacts answers questions and acts on plain-language requests (for example, adjusting a severity cutoff), rerunning only the affected stages to close the feedback loop. Explicit artifact handoffs keep every verdict traceable to the inputs that produced it, and the review dashboard links four views: a triage report, the chat agent, an interactive 3D lattice inspector, and a strut-level evidence view.
<br/>*Tech: Python, Streamlit, Three.js, Plotly, Matplotlib, NumPy* &nbsp;·&nbsp; 📎 [Slides](#) *(coming soon)*

---

### 🚀 Projects

- 🌊 **[FathomNet 2026](https://github.com/navya2392/FathomNet2026_ObjectDetection)** &nbsp;14th on the CLEF 2026 leaderboard; underwater object detection across a train/test institutional gap. &nbsp;[[results]](https://github.com/navya2392/FathomNet2026_ObjectDetection/blob/main/notebooks/final_pipeline.ipynb)
- ⚙️ **[Early Fault Detection (TEP)](https://github.com/navya2392/EarlyFaultDetection)** &nbsp;Two-stage 1D-CNN, 99% F1 with 0% false alarms on the industrial TEP benchmark. &nbsp;[[paper]](https://github.com/navya2392/EarlyFaultDetection/blob/main/CSCI567_FaultDetection_ProjectReport.pdf)
- 📚 **[ML Coursework](https://github.com/navya2392/ML-coursework)** &nbsp;The fundamentals across 8 algorithms.
- 🌐 **[Full-Stack Apps](https://github.com/navya2392/Full-Stack-Apps)** &nbsp;End-to-end React/Node and Python/Flask web apps.

---

### 🛠️ Skills

`Python` · `PyTorch` · `TensorFlow` · `scikit-learn` · `OpenCV` · `Ultralytics/YOLO` · `LLM agents` · `SQL` · `Docker` · `GCP` · `React` · `Node.js` · `Flask`

---

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=navya2392&show_icons=true&hide_border=true" alt="GitHub stats" height="150"/>
</p>
