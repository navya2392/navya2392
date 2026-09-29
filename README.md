<h1 align="center">Hi, I'm Navya Bhat 👋</h1>

<p align="center">
  Machine Learning Engineer and product builder with eight years in strategy and consulting behind me.<br/>
  I turn models into products that hold up outside the lab and tie back to real business impact.
</p>

<p align="center">
  <a href="https://www.linkedin.com/in/navya-bhat/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>
  <a href="mailto:navya2392@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=flat&logo=gmail&logoColor=white" alt="Email"/></a>
  <!-- Optional: portfolio site / Kaggle
  <a href="https://YOUR-PORTFOLIO"><img src="https://img.shields.io/badge/Portfolio-000000?style=flat&logo=aboutdotme&logoColor=white" alt="Portfolio"/></a>
  -->
</p>

---

### 👋 Background

Before moving into computer science, I spent eight years in sales, consulting, and strategy. I built business cases, analyzed markets, and recommended which products to launch, but my work ended at the recommendation. I wanted to be the one building, so I went back to school for a master's in computer science at USC (4.0 GPA).

**Education**
- **M.S. Computer Science**, University of Southern California (expected May 2027)
- **MBA**, Kellogg School of Management, Northwestern University: focus on finance and data analytics; Kellogg Growth Scholarship ($100K)
- **B.E. Chemical Engineering**, Institute of Chemical Technology, Mumbai: Sir Ratan Tata Scholarship (top 5% of class)

**Experience**
- **Starbucks, Manager, Existing Store Strategy:** Shaped the company's store renovation strategy with a data-driven prioritization model, and built a self-service SQL and Tableau dashboard that cut 5+ hours of weekly reporting.
- **Boston Consulting Group, Consultant:** Designed a large-scale consumer survey that informed a new store concept projected at $15-20B in annual revenue, built pricing models pointing to an 11-point gross margin gain, and automated 8+ legacy pricing tools into 2 workflows.
- **L.E.K. Consulting, Consultant:** Led 6 due diligence projects for private equity clients across consumer and industrial sectors.
- **Dow Chemical, Senior Account Executive:** Grew B2B revenue from $23M to $45M in two years, won Dow's Pinnacle Award for global selling excellence, and led India's first recyclable edible-oil packaging launch ($4M in annual revenue).

Today I combine that business background with hands-on ML and software engineering to build products that solve real problems.

---

### 🔬 Machine Learning Experience

**Lawrence Livermore National Laboratory** &nbsp;·&nbsp; Machine Learning Intern, National Ignition Facility &nbsp;·&nbsp; *Summer 2026*

The only ML practitioner on a team adopting machine learning for the first time. Delivered two systems: an object detector for laser-optics defects, and an agentic AI workflow for defect detection in 3D-printed lattices. *Code and data are internal to LLNL and not shared here.*

**1. End-to-end ML object detector for defects in NIF laser images**

Two-stage system for finding small, low-contrast defects in near-field laser images (previously manual review), where defects sat near beam edges and labels were incomplete.
- **Detector ensemble** of FCOS (ResNet50-FPN) + YOLO11, three seeds each, chosen after benchmarking FCOS, YOLO11, Faster R-CNN, RetinaNet, and RT-DETR; cluster voting across all six runs for stability, with the operating point picked on recall vs. false-positives-per-image (the reviewer's real workload).
- **Second-stage verifier** (ResNet18 + ResNet34 vote, selected from 12 CNNs) checks each candidate in companion views to filter false positives.
- **Leakage-safe evaluation:** location-aware 5-fold CV so no physical location appears in both train and test; switched to **center-distance matching** over IoU because incomplete labels penalized correct detections (~12 pts recall).
- **Error analysis to preprocessing:** one location drove nearly half of all misses; **Difference-of-Gaussians** preprocessing plus a union vote recovered faint edge defects neither ensemble found alone.

| Metric | Result |
|---|---|
| Box recall (baseline to baseline + DoG union vote) | 0.881 → 0.929 |
| Precision after second-stage verification | 0.577 → 0.663 |
| Final system recall | ~0.90 |
| Manual review time saved | 3-4 hours per week |

*Tech: Python, PyTorch, Ultralytics YOLO11, FCOS (ResNet50-FPN), ResNet18/34, OpenCV*

**2. Agentic AI workflow for defect detection in 3D-printed lattices**

A multi-agent Python workflow that turns a raw CT volume into a ranked, strut-level defect report for octet lattices (thousands of repeating cells, where a weak strut looks like any other void in noisy CT). Six agents:
- **Orchestrator** runs only the stages that are missing or stale by checking saved artifacts.
- **Segmentation** separates material from background (Otsu, chosen over Li and midpoint by material fraction).
- **Registration** aligns the ideal design geometry to the scan by scoring candidate transforms (scale, translation, small rotations).
- **Defect analysis** samples every strut along its centerline, computes four support metrics, and assigns a severity tier (Critical / Major / Minor / Nominal), labeling a strut **Uncertain** rather than guessing when a verdict is unreliable.
- **Report** builds the dashboard-ready report from saved artifacts without rerunning analysis.
- **Chat** answers artifact-grounded questions and applies plain-language changes (e.g. "lower the Tier 2 cutoff"), triggering reruns of only the affected stages.

Explicit artifact handoffs make every verdict traceable; a human can steer any stage; flagging uncertainty over guessing builds user trust. Review dashboard: four linked views (triage report, chat, interactive 3D lattice inspector, and a strut-level evidence view).

*Slides: in progress (link coming soon).*

*Tech: Python, Streamlit, Three.js, Plotly, Matplotlib, NumPy*

**Key takeaway:** across both projects, the hardest problems weren't modeling; they were choosing the right metrics, evaluating honestly, and building systems users trust enough to rely on.

---

### 🚀 Featured Projects

**🌊 [FathomNet 2026: Marine Species Detection](https://github.com/navya2392/FathomNet2026_ObjectDetection)** &nbsp;·&nbsp; *PyTorch · YOLO · RT-DETR · DINOv2*
> **14th on the public leaderboard** (CLEF 2026 underwater object detection). The twist: train and test come from *different research institutions*, so every "make the model fit better" trick hurt. Wins came from domain-agnostic methods: high-res multi-scale inference, cross-architecture ensembling, and a foundation-model consensus relabel that added **+0.023 mAP with no retraining**.
>
> 📊 **[See the full results notebook (28-experiment scoreboard, per-class AP, pipeline diagram)](https://github.com/navya2392/FathomNet2026_ObjectDetection/blob/main/notebooks/final_pipeline.ipynb)**

**⚙️ [Early Fault Detection on the Tennessee Eastman Process](https://github.com/navya2392/EarlyFaultDetection)** &nbsp;·&nbsp; *1D-CNN · Time-Series · Industrial ML*
> Two-stage 1D-CNN on the industry-standard TEP benchmark (52 sensors, 20 fault types). **Detector: 0% false alarms across 500 fault-free runs**, 60-min median detection. **Classifier: 99.08% accuracy / 0.9908 macro-F1.** Built around real deployment trade-offs: detection latency vs. false-alarm budget, chosen from operating-point curves.
>
> 📄 **[Read the full project report (paper)](https://github.com/navya2392/EarlyFaultDetection/blob/main/CSCI567_FaultDetection_ProjectReport.pdf)**

**📚 [ML Coursework Portfolio](https://github.com/navya2392/ML-coursework)** &nbsp;·&nbsp; *scikit-learn · XGBoost · TensorFlow*
> Breadth across the fundamentals: deep-learning image classification, SVMs, tree ensembles + SMOTE, ridge/LASSO/boosting, KNN, decision trees, and time-series classification. Graduate ML coursework at USC.

**🌐 [Full-Stack Web Apps](https://github.com/navya2392/Full-Stack-Apps)** &nbsp;·&nbsp; *React · Node.js · Python · Flask*
> A collection of end-to-end web applications: a Node.js + React events app and a Python/Flask Ticketmaster integration. Shows I can take an idea past the model and ship a working product, front to back.

---

### 🛠️ Technical Skills

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![TensorFlow](https://img.shields.io/badge/TensorFlow-FF6F00?style=flat&logo=tensorflow&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?style=flat&logo=scikit-learn&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=flat&logo=opencv&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?style=flat&logo=pandas&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![GCP](https://img.shields.io/badge/Google_Cloud-4285F4?style=flat&logo=googlecloud&logoColor=white)

**Languages:** Python · SQL · Java · C++ · JavaScript · C
**Machine Learning:** PyTorch · TensorFlow/Keras · scikit-learn · XGBoost · pandas · NumPy · OpenCV · Ultralytics/YOLO · LLM agents
**Tools & Platforms:** Git · Docker · Google Cloud Platform · REST APIs · Streamlit · React · Node.js · Flask · Tableau · Alteryx
**Focus areas:** Computer Vision · Object Detection · Time-Series · Domain Shift & Robustness · Model Ensembling · Agentic AI · Deployment-minded evaluation

---

### 📊 GitHub

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=navya2392&show_icons=true&hide_border=true" alt="GitHub stats" height="150"/>
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=navya2392&layout=compact&hide_border=true" alt="Top languages" height="150"/>
</p>
