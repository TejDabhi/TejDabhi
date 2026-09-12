<!DOCTYPE html>
<html lang="en" class="scroll-smooth">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tej Dabhi | AI/ML Engineer & Systems Developer</title>

  <!-- SEO -->
  <meta name="description" content="Tej Dabhi - AI/ML Engineer & Computer Engineering Undergrad. Ex-AI/ML Intern at Shine Infosoft. Specializing in computer vision, deterministic ML pipelines, and production Streamlit apps." />
  <meta property="og:title" content="Tej Dabhi | Applied AI/ML Portfolio" />
  <meta property="og:description" content="High-performance machine learning pipelines, deep computer vision, and interactive web tools." />
  <meta property="og:type" content="website" />

  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Fonts & Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@400;500;600&family=Inter:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet" />
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" />

  <script>
    tailwind.config = {
      darkMode: "class",
      theme: {
        extend: {
          fontFamily: {
            inter: ["Inter", "sans-serif"],
            mono: ["Fira Code", "monospace"],
          },
          colors: {
            brand: {
              cyan: "#38bdf8",
              indigo: "#6366f1",
              violet: "#8b5cf6",
            },
            dark: {
              950: "#05070d",
              900: "#0a0d17",
              850: "#0f1422",
              800: "#161b2c",
              700: "#1f263d",
            },
          },
        },
      },
    };
  </script>

  <style>
    * {
      box-sizing: border-box;
      max-width: 100%;
    }
    body {
      background-color: #05070d;
      color: #94a3b8;
      font-family: "Inter", sans-serif;
      overflow-x: hidden;
    }
    .font-mono {
      font-family: "Fira Code", monospace;
    }
    .gradient-text {
      background: linear-gradient(135deg, #38bdf8 0%, #6366f1 50%, #c084fc 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .glass-card {
      background: rgba(15, 20, 34, 0.7);
      backdrop-filter: blur(14px);
      -webkit-backdrop-filter: blur(14px);
      border: 1px solid rgba(255, 255, 255, 0.07);
    }
    .glass-card:hover {
      border-color: rgba(99, 102, 241, 0.35);
    }
    .glass-nav {
      background: rgba(5, 7, 13, 0.85);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border-bottom: 1px solid rgba(255, 255, 255, 0.06);
    }
    .pulse-glow {
      box-shadow: 0 0 25px rgba(56, 189, 248, 0.25);
    }
    .grid-bg {
      background-image: linear-gradient(to right, rgba(255, 255, 255, 0.03) 1px, transparent 1px),
                        linear-gradient(to bottom, rgba(255, 255, 255, 0.03) 1px, transparent 1px);
      background-size: 48px 48px;
    }
    ::-webkit-scrollbar {
      width: 6px;
    }
    ::-webkit-scrollbar-thumb {
      background: #312e81;
      border-radius: 9999px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: #4338ca;
    }
  </style>
</head>
<body class="selection:bg-indigo-500 selection:text-white">

  <!-- Interactive Background Canvas -->
  <canvas id="neuralCanvas" class="fixed inset-0 pointer-events-none z-0"></canvas>

  <!-- NAVIGATION -->
  <nav class="fixed top-0 w-full z-50 glass-nav transition-all duration-300">
    <div class="max-w-7xl mx-auto px-6 h-20 flex items-center justify-between">
      <a href="#" class="flex items-center gap-2 group">
        <span class="w-2.5 h-2.5 rounded-full bg-brand-cyan group-hover:scale-125 transition-transform duration-300"></span>
        <span class="font-mono font-bold text-xl text-white tracking-wider">TEJ.DABHI<span class="text-brand-cyan">()</span></span>
      </a>

      <div class="hidden md:flex items-center gap-8 text-sm font-medium text-slate-300">
        <a href="#about" class="hover:text-brand-cyan transition-colors">/about</a>
        <a href="#experience" class="hover:text-brand-cyan transition-colors">/experience</a>
        <a href="#skills" class="hover:text-brand-cyan transition-colors">/stack</a>
        <a href="#projects" class="hover:text-brand-cyan transition-colors">/projects</a>
        <a href="#contact" class="hover:text-brand-cyan transition-colors">/contact</a>
      </div>

      <div class="hidden md:flex items-center gap-3">
        <button id="terminalBtn" class="px-3.5 py-1.5 rounded-lg border border-slate-700 font-mono text-xs text-slate-300 hover:text-white hover:border-brand-cyan transition-all flex items-center gap-2">
          <i class="fas fa-terminal text-brand-cyan"></i>
          <span>cli_view</span>
        </button>
        <a href="./Resume.pdf" download class="px-4 py-2 rounded-lg bg-indigo-600/20 text-indigo-300 border border-indigo-500/40 hover:bg-indigo-600 hover:text-white transition-all text-xs font-semibold">
          Resume.pdf
        </a>
      </div>

      <button id="mobileMenuToggle" class="md:hidden text-white text-xl p-2" aria-label="Toggle Navigation">
        <i class="fas fa-bars"></i>
      </button>
    </div>

    <!-- Mobile Menu -->
    <div id="mobileDropdown" class="hidden md:hidden glass-card border-b border-white/10 px-6 py-6 space-y-4 font-mono text-sm">
      <a href="#about" class="block text-slate-300 hover:text-brand-cyan">/about</a>
      <a href="#experience" class="block text-slate-300 hover:text-brand-cyan">/experience</a>
      <a href="#skills" class="block text-slate-300 hover:text-brand-cyan">/stack</a>
      <a href="#projects" class="block text-slate-300 hover:text-brand-cyan">/projects</a>
      <a href="#contact" class="block text-slate-300 hover:text-brand-cyan">/contact</a>
    </div>
  </nav>

  <!-- HERO SECTION -->
  <section class="relative min-h-screen pt-32 pb-20 flex items-center grid-bg z-10">
    <div class="max-w-7xl mx-auto px-6 w-full">
      <div class="max-w-4xl">
        <!-- Status Pill -->
        <div class="inline-flex items-center gap-3 px-3 py-1.5 rounded-full glass-card text-xs font-mono mb-8 border border-white/10">
          <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
          <span class="text-slate-300">Ex-AI/ML Intern @ Shine Infosoft</span>
          <span class="text-slate-500">•</span>
          <span class="text-brand-cyan">Open for Roles</span>
        </div>

        <h1 class="text-4xl sm:text-6xl lg:text-7xl font-extrabold text-white leading-tight tracking-tight mb-6">
          Architecting models into <br />
          <span class="gradient-text">production interfaces.</span>
        </h1>

        <p class="text-lg sm:text-xl text-slate-400 font-normal leading-relaxed mb-10 max-w-2xl">
          Computer Engineering undergraduate specializing in statistical Machine Learning,
          deep Computer Vision inference loops, and end-to-end deployed Streamlit applications.
        </p>

        <!-- Command Deck CTA -->
        <div class="flex flex-wrap items-center gap-4 mb-12">
          <a href="#projects" class="px-6 py-3.5 rounded-xl bg-gradient-to-r from-brand-indigo to-brand-cyan text-white font-semibold text-sm tracking-wide hover:shadow-lg hover:shadow-brand-indigo/30 transition-all flex items-center gap-2">
            <span>Inspect Repositories</span>
            <i class="fas fa-arrow-right text-xs"></i>
          </a>
          <a href="#contact" class="px-6 py-3.5 rounded-xl glass-card text-slate-200 font-semibold text-sm tracking-wide hover:border-slate-500 transition-all">
            Get In Touch
          </a>
        </div>

        <!-- Metric Cards -->
        <div class="grid grid-cols-2 sm:grid-cols-4 gap-4 max-w-3xl font-mono">
          <div class="glass-card p-4 rounded-xl">
            <div class="text-2xl font-bold text-white">02 Mo.</div>
            <div class="text-xs text-slate-400 uppercase tracking-widest mt-1">Industry Tenure</div>
          </div>
          <div class="glass-card p-4 rounded-xl">
            <div class="text-2xl font-bold text-white">03+</div>
            <div class="text-xs text-slate-400 uppercase tracking-widest mt-1">Deployed Apps</div>
          </div>
          <div class="glass-card p-4 rounded-xl">
            <div class="text-2xl font-bold text-white">100%</div>
            <div class="text-xs text-slate-400 uppercase tracking-widest mt-1">Python Centric</div>
          </div>
          <div class="glass-card p-4 rounded-xl">
            <div class="text-2xl font-bold text-white">120+ Yr</div>
            <div class="text-xs text-slate-400 uppercase tracking-widest mt-1">Data Analyzed</div>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- ARCHITECTURAL PIPELINE / ABOUT -->
  <section id="about" class="py-24 border-t border-slate-800/80 relative z-10 bg-dark-900/60">
    <div class="max-w-7xl mx-auto px-6">
      <div class="flex flex-col md:flex-row gap-12 items-start">
        <div class="md:w-5/12">
          <span class="text-xs font-mono uppercase tracking-widest text-brand-cyan">01 // Engineering Profile</span>
          <h2 class="text-3xl sm:text-4xl font-black text-white mt-2 mb-6">Bridging notebooks and web services.</h2>
          <p class="text-slate-400 leading-relaxed mb-6">
            A machine learning model locked in an isolated <code>.ipynb</code> notebook serves zero operational value.
            My engineering philosophy centers on clean exploratory validation, robust feature pipelines,
            and reliable inference engines built for end-users.
          </p>
          <p class="text-slate-400 leading-relaxed mb-6">
            Equipped with foundational industry exposure from Shine Infosoft, I optimize tabular regressions,
            construct OpenCV inference loops, and serve models via modern frameworks.
          </p>
        </div>

        <div class="md:w-7/12 w-full">
          <div class="glass-card rounded-2xl p-6 font-mono text-sm">
            <div class="flex items-center justify-between border-b border-white/10 pb-4 mb-4 text-xs text-slate-400">
              <span class="flex items-center gap-2">
                <span class="w-3 h-3 rounded-full bg-rose-500 inline-block"></span>
                <span class="w-3 h-3 rounded-full bg-amber-500 inline-block"></span>
                <span class="w-3 h-3 rounded-full bg-emerald-500 inline-block"></span>
              </span>
              <span>pipeline_architecture.json</span>
            </div>
            <pre class="text-slate-300 text-xs sm:text-sm overflow-x-auto leading-relaxed"><code>{
  <span class="text-brand-cyan">"engineer"</span>: <span class="text-emerald-400">"Tej Dabhi"</span>,
  <span class="text-brand-cyan">"credentials"</span>: <span class="text-emerald-400">"Computer Engineering Undergrad"</span>,
  <span class="text-brand-cyan">"tenure_history"</span>: [
    {
      <span class="text-brand-indigo">"firm"</span>: <span class="text-emerald-400">"Shine Infosoft (Pirotan Technolabs)"</span>,
      <span class="text-brand-indigo">"role"</span>: <span class="text-emerald-400">"AI/ML Intern"</span>,
      <span class="text-brand-indigo">"duration"</span>: <span class="text-emerald-400">"2 Months"</span>
    }
  ],
  <span class="text-brand-cyan">"core_pipeline"</span>: [
    <span class="text-amber-300">"Exploratory Data Analysis & Imputation"</span>,
    <span class="text-amber-300">"Outlier Remediation & Log Transformations"</span>,
    <span class="text-amber-300">"Scikit-Learn Regression & Classification"</span>,
    <span class="text-amber-300">"Artifact Serialization (.pkl / .h5)"</span>,
    <span class="text-amber-300">"Streamlit Production Deployment"</span>
  ]
}</code></pre>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PRODUCTION EXPERIENCE -->
  <section id="experience" class="py-24 border-t border-slate-800/80 relative z-10">
    <div class="max-w-7xl mx-auto px-6">
      <div class="mb-16">
        <span class="text-xs font-mono uppercase tracking-widest text-brand-cyan">02 // Experience Log</span>
        <h2 class="text-3xl sm:text-4xl font-black text-white mt-2">Work History & Roles</h2>
      </div>

      <div class="space-y-8">
        <!-- Shine Infosoft Item -->
        <div class="glass-card rounded-2xl p-8 transition-all hover:translate-x-1">
          <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 border-b border-white/10 pb-6 mb-6">
            <div>
              <div class="flex items-center gap-3">
                <h3 class="text-xl font-bold text-white">AI / Machine Learning Intern</h3>
                <span class="px-2.5 py-0.5 rounded-full text-xs font-mono bg-emerald-500/10 text-emerald-400 border border-emerald-500/20">Completed</span>
              </div>
              <div class="text-sm font-mono text-indigo-400 mt-1">Shine Infosoft (Pirotan Technolabs Pvt. Ltd.)</div>
            </div>
            <div class="text-xs font-mono text-slate-400 flex md:flex-col items-end gap-1">
              <span>Duration: 2 Months</span>
              <span>Ahmedabad, Gujarat</span>
            </div>
          </div>

          <ul class="space-y-3 text-slate-400 text-sm leading-relaxed">
            <li class="flex items-start gap-3">
              <i class="fas fa-check text-brand-cyan text-xs mt-1"></i>
              <span>Engineered predictive models using Python, NumPy, Pandas, and Scikit-learn, optimizing hyperparameter bounds to maximize validation accuracy.</span>
            </li>
            <li class="flex items-start gap-3">
              <i class="fas fa-check text-brand-cyan text-xs mt-1"></i>
              <span>Structured preprocessing and data-cleansing pipelines for tabular sets, mitigating missing value skew and handling categorical encodings.</span>
            </li>
            <li class="flex items-start gap-3">
              <i class="fas fa-check text-brand-cyan text-xs mt-1"></i>
              <span>Coordinated with core technical teams on production standards, version control hygiene (Git/GitHub), and practical real-world software workflows.</span>
            </li>
          </ul>
        </div>

        <!-- QA Tester Item -->
        <div class="glass-card rounded-2xl p-8 transition-all hover:translate-x-1">
          <div class="flex flex-col md:flex-row md:items-center justify-between gap-4 border-b border-white/10 pb-6 mb-6">
            <div>
              <h3 class="text-xl font-bold text-white">QA Automation Tester</h3>
              <div class="text-sm font-mono text-slate-400 mt-1">Selenium Web Testing</div>
            </div>
            <div class="text-xs font-mono text-slate-400">
              Regression & Functional Suite
            </div>
          </div>

          <p class="text-slate-400 text-sm leading-relaxed">
            Scripted automated test workflows in Selenium to execute regression passes, locate UI defects, and audit application performance stability across dynamic releases.
          </p>
        </div>
      </div>
    </div>
  </section>

  <!-- SKILLS & ECOSYSTEM -->
  <section id="skills" class="py-24 border-t border-slate-800/80 bg-dark-900/60 relative z-10">
    <div class="max-w-7xl mx-auto px-6">
      <div class="mb-16">
        <span class="text-xs font-mono uppercase tracking-widest text-brand-cyan">03 // Capabilities</span>
        <h2 class="text-3xl sm:text-4xl font-black text-white mt-2">Technical Matrix</h2>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
        <!-- Col 1 -->
        <div class="glass-card p-6 rounded-2xl">
          <div class="w-10 h-10 rounded-xl bg-indigo-500/20 text-indigo-400 flex items-center justify-center mb-6">
            <i class="fas fa-brain text-lg"></i>
          </div>
          <h3 class="text-lg font-bold text-white mb-2">Model & Inference</h3>
          <p class="text-xs text-slate-400 mb-6">Deterministic statistical estimation, neural network foundations, and spatial vision.</p>
          <div class="flex flex-wrap gap-2 font-mono text-xs">
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Scikit-Learn</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">TensorFlow</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Keras</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">OpenCV</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Supervised Learning</span>
          </div>
        </div>

        <!-- Col 2 -->
        <div class="glass-card p-6 rounded-2xl">
          <div class="w-10 h-10 rounded-xl bg-cyan-500/20 text-brand-cyan flex items-center justify-center mb-6">
            <i class="fas fa-database text-lg"></i>
          </div>
          <h3 class="text-lg font-bold text-white mb-2">Data Processing & EDA</h3>
          <p class="text-xs text-slate-400 mb-6">Large-scale data transformation, distribution analysis, and tabular feature preparation.</p>
          <div class="flex flex-wrap gap-2 font-mono text-xs">
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">NumPy</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Pandas</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Matplotlib</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Seaborn</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">SQL / MySQL</span>
          </div>
        </div>

        <!-- Col 3 -->
        <div class="glass-card p-6 rounded-2xl">
          <div class="w-10 h-10 rounded-xl bg-violet-500/20 text-brand-violet flex items-center justify-center mb-6">
            <i class="fas fa-cloud-arrow-up text-lg"></i>
          </div>
          <h3 class="text-lg font-bold text-white mb-2">Deployment & Tooling</h3>
          <p class="text-xs text-slate-400 mb-6">Serving model artifacts and ensuring reproducible development environments.</p>
          <div class="flex flex-wrap gap-2 font-mono text-xs">
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Streamlit</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Git / GitHub</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">VS Code</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">FastAPI (Learning)</span>
            <span class="px-2.5 py-1 rounded bg-slate-800 text-slate-300">Linux CLI</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- PROJECTS (FILTERABLE) -->
  <section id="projects" class="py-24 border-t border-slate-800/80 relative z-10">
    <div class="max-w-7xl mx-auto px-6">
      <div class="flex flex-col md:flex-row md:items-end justify-between gap-6 mb-12">
        <div>
          <span class="text-xs font-mono uppercase tracking-widest text-brand-cyan">04 // Featured Deployments</span>
          <h2 class="text-3xl sm:text-4xl font-black text-white mt-2">Functional Production Systems</h2>
        </div>

        <!-- Filter Buttons -->
        <div class="flex gap-2 font-mono text-xs">
          <button onclick="filterProjects('all')" class="project-filter-btn px-3 py-1.5 rounded-lg bg-slate-800 text-white border border-slate-700 active-filter" data-category="all">All</button>
          <button onclick="filterProjects('ml')" class="project-filter-btn px-3 py-1.5 rounded-lg bg-dark-900 text-slate-400 border border-slate-800 hover:text-white" data-category="ml">Machine Learning</button>
          <button onclick="filterProjects('cv')" class="project-filter-btn px-3 py-1.5 rounded-lg bg-dark-900 text-slate-400 border border-slate-800 hover:text-white" data-category="cv">Computer Vision</button>
          <button onclick="filterProjects('analytics')" class="project-filter-btn px-3 py-1.5 rounded-lg bg-dark-900 text-slate-400 border border-slate-800 hover:text-white" data-category="analytics">Analytics</button>
        </div>
      </div>

      <div class="grid grid-cols-1 md:grid-cols-3 gap-8" id="projectsContainer">
        <!-- PROJECT 1: Laptop Price Predictor -->
        <div class="project-card glass-card rounded-2xl overflow-hidden flex flex-col justify-between" data-category="ml">
          <div class="p-6">
            <div class="flex justify-between items-start mb-4">
              <div class="w-12 h-12 rounded-xl bg-cyan-500/10 text-brand-cyan flex items-center justify-center text-xl">
                <i class="fas fa-microchip"></i>
              </div>
              <span class="text-xs font-mono text-slate-500 uppercase">Regression Model</span>
            </div>
            <h3 class="text-xl font-bold text-white mb-3">Laptop Price Predictor</h3>
            <p class="text-slate-400 text-sm leading-relaxed mb-6">
              Machine learning-driven valuation system that predicts laptop prices from hardware configurations (RAM, CPU, GPU, display PPI, and storage architectures).
            </p>
            <div class="flex flex-wrap gap-2 text-xs font-mono text-brand-cyan mb-6">
              <span>Scikit-learn</span> • <span>Pandas</span> • <span>Pipeline</span> • <span>Streamlit</span>
            </div>
          </div>
          <div class="p-6 border-t border-white/5 flex items-center justify-between font-mono text-xs">
            <a href="https://tej-laptop-price-predictor.streamlit.app/" target="_blank" class="text-white hover:text-brand-cyan flex items-center gap-1.5">
              <span>Live Instance</span> <i class="fas fa-arrow-up-right-from-square text-[10px]"></i>
            </a>
            <a href="https://github.com/TejDabhi" target="_blank" class="text-slate-400 hover:text-white">
              GitHub Repo
            </a>
          </div>
        </div>

        <!-- PROJECT 2: Face Mask Detection -->
        <div class="project-card glass-card rounded-2xl overflow-hidden flex flex-col justify-between" data-category="cv">
          <div class="p-6">
            <div class="flex justify-between items-start mb-4">
              <div class="w-12 h-12 rounded-xl bg-emerald-500/10 text-emerald-400 flex items-center justify-center text-xl">
                <i class="fas fa-head-side-mask"></i>
              </div>
              <span class="text-xs font-mono text-slate-500 uppercase">Vision Inferencing</span>
            </div>
            <h3 class="text-xl font-bold text-white mb-3">Face Mask Detection System</h3>
            <p class="text-slate-400 text-sm leading-relaxed mb-6">
              Dual-stage computer vision application combining spatial face boundary identification with a deep learning classification model to flag mask compliance in real time.
            </p>
            <div class="flex flex-wrap gap-2 text-xs font-mono text-emerald-400 mb-6">
              <span>OpenCV</span> • <span>TensorFlow</span> • <span>Keras</span> • <span>Streamlit</span>
            </div>
          </div>
          <div class="p-6 border-t border-white/5 flex items-center justify-between font-mono text-xs">
            <a href="https://face-mask-detection-tej.streamlit.app/" target="_blank" class="text-white hover:text-emerald-400 flex items-center gap-1.5">
              <span>Live Instance</span> <i class="fas fa-arrow-up-right-from-square text-[10px]"></i>
            </a>
            <a href="https://github.com/TejDabhi" target="_blank" class="text-slate-400 hover:text-white">
              GitHub Repo
            </a>
          </div>
        </div>

        <!-- PROJECT 3: Olympic Analytics -->
        <div class="project-card glass-card rounded-2xl overflow-hidden flex flex-col justify-between" data-category="analytics">
          <div class="p-6">
            <div class="flex justify-between items-start mb-4">
              <div class="w-12 h-12 rounded-xl bg-violet-500/10 text-brand-violet flex items-center justify-center text-xl">
                <i class="fas fa-chart-pie"></i>
              </div>
              <span class="text-xs font-mono text-slate-500 uppercase">Data Analytics</span>
            </div>
            <h3 class="text-xl font-bold text-white mb-3">Olympic Data Analysis Dashboard</h3>
            <p class="text-slate-400 text-sm leading-relaxed mb-6">
              Longitudinal analysis platform parsing over 120 years of historical Olympic records with dynamic country-level filtering, athlete tallies, and medal density insights.
            </p>
            <div class="flex flex-wrap gap-2 text-xs font-mono text-brand-violet mb-6">
              <span>Pandas</span> • <span>Seaborn</span> • <span>Matplotlib</span> • <span>Streamlit</span>
            </div>
          </div>
          <div class="p-6 border-t border-white/5 flex items-center justify-between font-mono text-xs">
            <a href="https://olympic-app-tej.streamlit.app/" target="_blank" class="text-white hover:text-brand-violet flex items-center gap-1.5">
              <span>Live Instance</span> <i class="fas fa-arrow-up-right-from-square text-[10px]"></i>
            </a>
            <a href="https://github.com/TejDabhi" target="_blank" class="text-slate-400 hover:text-white">
              GitHub Repo
            </a>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- CONTACT & CONNECT -->
  <section id="contact" class="py-24 border-t border-slate-800/80 bg-dark-900/60 relative z-10">
    <div class="max-w-7xl mx-auto px-6">
      <div class="max-w-3xl mx-auto text-center mb-16">
        <span class="text-xs font-mono uppercase tracking-widest text-brand-cyan">05 // Transmission</span>
        <h2 class="text-3xl sm:text-4xl font-black text-white mt-2">Initialize Contact</h2>
        <p class="text-slate-400 mt-4 text-sm">
          Interested in discussing machine learning internships, junior developer roles, or open-source software projects.
        </p>
      </div>

      <div class="max-w-4xl mx-auto grid grid-cols-1 md:grid-cols-2 gap-12">
        <form action="https://formspree.io/f/xkoeqagq" method="POST" class="space-y-4">
          <div>
            <label class="block text-xs font-mono text-slate-400 mb-2">NAME</label>
            <input type="text" name="name" required class="w-full px-4 py-3 rounded-xl bg-dark-850 border border-slate-800 text-white font-mono text-sm focus:border-brand-cyan focus:outline-none" placeholder="Recruiter / Collaborator" />
          </div>
          <div>
            <label class="block text-xs font-mono text-slate-400 mb-2">EMAIL</label>
            <input type="email" name="email" required class="w-full px-4 py-3 rounded-xl bg-dark-850 border border-slate-800 text-white font-mono text-sm focus:border-brand-cyan focus:outline-none" placeholder="work@domain.com" />
          </div>
          <div>
            <label class="block text-xs font-mono text-slate-400 mb-2">MESSAGE</label>
            <textarea name="message" rows="4" required class="w-full px-4 py-3 rounded-xl bg-dark-850 border border-slate-800 text-white font-mono text-sm focus:border-brand-cyan focus:outline-none" placeholder="Write message details..."></textarea>
          </div>
          <button type="submit" class="w-full py-3.5 rounded-xl bg-indigo-600 hover:bg-indigo-500 text-white font-semibold text-sm transition-colors flex items-center justify-center gap-2">
            <span>Send Message</span>
            <i class="fas fa-paper-plane text-xs"></i>
          </button>
        </form>

        <div class="flex flex-col justify-between space-y-6">
          <div class="glass-card p-6 rounded-2xl space-y-4">
            <div>
              <div class="text-xs font-mono text-slate-500">DIRECT INBOX</div>
              <a href="mailto:tejdabhi84@gmail.com" class="text-white hover:text-brand-cyan font-mono text-sm">tejdabhi84@gmail.com</a>
            </div>
            <div>
              <div class="text-xs font-mono text-slate-500">LOCATION</div>
              <div class="text-white font-mono text-sm">Ahmedabad, Gujarat, India</div>
            </div>
            <div>
              <div class="text-xs font-mono text-slate-500">CODE & REPOSITORIES</div>
              <a href="https://github.com/TejDabhi" target="_blank" class="text-brand-cyan font-mono text-sm">github.com/TejDabhi</a>
            </div>
            <div>
              <div class="text-xs font-mono text-slate-500">PROFESSIONAL NETWORK</div>
              <a href="https://www.linkedin.com/in/tej-dabhi" target="_blank" class="text-brand-indigo font-mono text-sm">linkedin.com/in/tej-dabhi</a>
            </div>
          </div>

          <div class="p-4 rounded-xl border border-white/5 font-mono text-xs text-slate-500 flex items-center justify-between">
            <span>PGP: VALIDATED</span>
            <span>STATUS: ACTIVE_LISTENING</span>
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- FOOTER -->
  <footer class="py-8 border-t border-slate-800/80 font-mono text-xs text-slate-500 relative z-10">
    <div class="max-w-7xl mx-auto px-6 flex flex-col sm:flex-row justify-between items-center gap-4">
      <div>© 2026 Tej Dabhi • System Architecture & Machine Learning</div>
      <div class="flex gap-6">
        <a href="https://github.com/TejDabhi" target="_blank" class="hover:text-white">GitHub</a>
        <a href="https://www.linkedin.com/in/tej-dabhi" target="_blank" class="hover:text-white">LinkedIn</a>
        <a href="mailto:tejdabhi84@gmail.com" class="hover:text-white">Email</a>
      </div>
    </div>
  </footer>

  <!-- TERMINAL MODAL -->
  <div id="terminalModal" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 hidden flex items-center justify-center p-4">
    <div class="glass-card w-full max-w-2xl rounded-2xl border border-slate-700 overflow-hidden font-mono text-sm shadow-2xl">
      <div class="bg-slate-900 px-4 py-3 border-b border-slate-800 flex items-center justify-between">
        <div class="flex items-center gap-2">
          <span class="w-3 h-3 rounded-full bg-rose-500 cursor-pointer" id="closeTerminal"></span>
          <span class="w-3 h-3 rounded-full bg-amber-500"></span>
          <span class="w-3 h-3 rounded-full bg-emerald-500"></span>
          <span class="text-xs text-slate-400 ml-2">bash - tej@portfolio:~$</span>
        </div>
        <button id="closeTerminalBtn" class="text-slate-400 hover:text-white"><i class="fas fa-times"></i></button>
      </div>
      <div class="p-6 space-y-4 max-h-[70vh] overflow-y-auto" id="terminalOutput">
        <p class="text-slate-400">Type <span class="text-brand-cyan font-bold">help</span> to view available system commands.</p>
        <div class="flex items-center gap-2">
          <span class="text-brand-cyan">tej@portfolio:~$</span>
          <input type="text" id="terminalInput" class="bg-transparent text-white focus:outline-none w-full" autofocus />
        </div>
      </div>
    </div>
  </div>

  <!-- SCRIPT ENGINE -->
  <script>
    // 1. Interactive Particle Network on Canvas
    const canvas = document.getElementById("neuralCanvas");
    const ctx = canvas.getContext("2d");
    let particles = [];

    function resizeCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    window.addEventListener("resize", resizeCanvas);
    resizeCanvas();

    class Particle {
      constructor() {
        this.x = Math.random() * canvas.width;
        this.y = Math.random() * canvas.height;
        this.vx = (Math.random() - 0.5) * 0.4;
        this.vy = (Math.random() - 0.5) * 0.4;
        this.radius = 1.2;
      }
      update() {
        this.x += this.vx;
        this.y += this.vy;
        if (this.x < 0 || this.x > canvas.width) this.vx *= -1;
        if (this.y < 0 || this.y > canvas.height) this.vy *= -1;
      }
      draw() {
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius, 0, Math.PI * 2);
        ctx.fillStyle = "rgba(99, 102, 241, 0.4)";
        ctx.fill();
      }
    }

    function initParticles(count) {
      particles = [];
      for (let i = 0; i < count; i++) {
        particles.push(new Particle());
      }
    }
    initParticles(50);

    function animateParticles() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      for (let i = 0; i < particles.length; i++) {
        particles[i].update();
        particles[i].draw();
        for (let j = i + 1; j < particles.length; j++) {
          const dx = particles[i].x - particles[j].x;
          const dy = particles[i].y - particles[j].y;
          const dist = Math.sqrt(dx * dx + dy * dy);
          if (dist < 130) {
            ctx.beginPath();
            ctx.strokeStyle = `rgba(56, 189, 248, ${0.15 * (1 - dist / 130)})`;
            ctx.lineWidth = 0.6;
            ctx.moveTo(particles[i].x, particles[i].y);
            ctx.lineTo(particles[j].x, particles[j].y);
            ctx.stroke();
          }
        }
      }
      requestAnimationFrame(animateParticles);
    }
    animateParticles();

    // 2. Project Dynamic Filter
    function filterProjects(category) {
      const cards = document.querySelectorAll(".project-card");
      const buttons = document.querySelectorAll(".project-filter-btn");

      buttons.forEach((btn) => {
        if (btn.getAttribute("data-category") === category) {
          btn.classList.add("bg-slate-800", "text-white");
          btn.classList.remove("bg-dark-900", "text-slate-400");
        } else {
          btn.classList.remove("bg-slate-800", "text-white");
          btn.classList.add("bg-dark-900", "text-slate-400");
        }
      });

      cards.forEach((card) => {
        if (category === "all" || card.getAttribute("data-category") === category) {
          card.style.display = "flex";
        } else {
          card.style.display = "none";
        }
      });
    }

    // 3. Mobile Navigation Toggle
    const mobileBtn = document.getElementById("mobileMenuToggle");
    const mobileDropdown = document.getElementById("mobileDropdown");
    mobileBtn.addEventListener("click", () => {
      mobileDropdown.classList.toggle("hidden");
    });

    // 4. Interactive CLI Terminal Logic
    const terminalBtn = document.getElementById("terminalBtn");
    const terminalModal = document.getElementById("terminalModal");
    const closeTerminal = document.getElementById("closeTerminal");
    const closeTerminalBtn = document.getElementById("closeTerminalBtn");
    const terminalInput = document.getElementById("terminalInput");
    const terminalOutput = document.getElementById("terminalOutput");

    function openTerminal() {
      terminalModal.classList.remove("hidden");
      terminalInput.focus();
    }
    function hideTerminal() {
      terminalModal.classList.add("hidden");
    }

    terminalBtn.addEventListener("click", openTerminal);
    closeTerminal.addEventListener("click", hideTerminal);
    closeTerminalBtn.addEventListener("click", hideTerminal);

    terminalInput.addEventListener("keydown", (e) => {
      if (e.key === "Enter") {
        const cmd = terminalInput.value.trim().toLowerCase();
        const historyNode = document.createElement("div");
        historyNode.innerHTML = `<span class="text-brand-cyan">tej@portfolio:~$</span> <span class="text-white">${terminalInput.value}</span>`;
        terminalOutput.insertBefore(historyNode, terminalInput.parentElement);

        const responseNode = document.createElement("div");
        responseNode.className = "text-slate-300 mb-2";

        switch (cmd) {
          case "help":
            responseNode.innerHTML = `Available commands:<br/>
            - <span class="text-brand-cyan">experience</span>: Print recent industry track<br/>
            - <span class="text-brand-cyan">skills</span>: List technical ecosystem<br/>
            - <span class="text-brand-cyan">projects</span>: View verified project links<br/>
            - <span class="text-brand-cyan">clear</span>: Clear terminal console<br/>
            - <span class="text-brand-cyan">exit</span>: Close CLI view`;
            break;
          case "experience":
            responseNode.innerHTML = `AI/ML Intern @ Shine Infosoft (2 Months Tenure) • Completed real-world data pipelines, tabular ML, model training & Streamlit integration.`;
            break;
          case "skills":
            responseNode.innerHTML = `Python, Scikit-learn, TensorFlow, Keras, OpenCV, Pandas, NumPy, Streamlit, SQL, Git.`;
            break;
          case "projects":
            responseNode.innerHTML = `1. Laptop Price Predictor (Regression)<br/>2. Face Mask Detection (OpenCV + CNN)<br/>3. Olympic Dashboard (Pandas Analytics)`;
            break;
          case "clear":
            terminalOutput.innerHTML = "";
            terminalOutput.appendChild(terminalInput.parentElement);
            terminalInput.value = "";
            return;
          case "exit":
            hideTerminal();
            terminalInput.value = "";
            return;
          default:
            responseNode.innerHTML = `Command not recognized: "${cmd}". Type <span class="text-brand-cyan">help</span> for command list.`;
        }

        terminalOutput.insertBefore(responseNode, terminalInput.parentElement);
        terminalInput.value = "";
        terminalOutput.scrollTop = terminalOutput.scrollHeight;
      }
    });
  </script>
</body>
</html>
