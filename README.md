<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Petualangan Akidah Akhlak - Kelas VII MTs</title>
  <!-- Tailwind CSS via CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Tone.js via CDN for Synthesized BGM & SFX -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/tone/14.8.49/Tone.js"></script>
  <!-- Google Fonts: Plus Jakarta Sans & Fredoka -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@500;600;700&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">

  <style>
    /* Base Typography & Theme */
    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
      color: #ffffff;
      overflow-x: hidden;
      user-select: none;
    }

    h1, h2, h3, .font-display {
      font-family: 'Fredoka', sans-serif;
    }

    /* Animated 4-Color Vibrant Gradient Background (Indigo, Pink, Amber, Emerald) */
    .bg-animated-aurora {
      background: linear-gradient(-45deg, #1e1b4b, #4c1d95, #831843, #78350f, #064e3b, #312e81);
      background-size: 400% 400%;
      animation: gradientFlow 16s ease infinite;
    }

    @keyframes gradientFlow {
      0% { background-position: 0% 50%; }
      50% { background-position: 100% 50%; }
      100% { background-position: 0% 50%; }
    }

    /* Decorative Floating Orbs */
    .orb {
      position: fixed;
      border-radius: 50%;
      filter: blur(80px);
      z-index: 0;
      opacity: 0.45;
      pointer-events: none;
      animation: floatOrb 10s ease-in-out infinite alternate;
    }

    @keyframes floatOrb {
      0% { transform: translate(0, 0) scale(1); }
      100% { transform: translate(30px, -40px) scale(1.12); }
    }

    /* Neon Glassmorphism Panels */
    .glass-panel {
      background: rgba(15, 23, 42, 0.58);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      border: 1.5px solid rgba(255, 255, 255, 0.16);
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.45), inset 0 1px 0 rgba(255, 255, 255, 0.2);
    }

    .neon-border-cyan {
      border: 2px solid rgba(52, 211, 153, 0.65);
      box-shadow: 0 0 22px rgba(52, 211, 153, 0.35), inset 0 0 15px rgba(52, 211, 153, 0.15);
    }

    .neon-border-pink {
      border: 2px solid rgba(244, 114, 182, 0.65);
      box-shadow: 0 0 22px rgba(244, 114, 182, 0.35), inset 0 0 15px rgba(244, 114, 182, 0.15);
    }

    /* Text Glow */
    .text-glow {
      text-shadow: 0 0 18px rgba(255, 255, 255, 0.55);
    }
    .text-glow-amber {
      text-shadow: 0 0 18px rgba(251, 191, 36, 0.75);
    }
    .text-glow-emerald {
      text-shadow: 0 0 18px rgba(52, 211, 153, 0.75);
    }

    /* Kahoot/Quizizz Inspired 3D Gradient Buttons */
    .btn-choice {
      transition: all 0.2s cubic-bezier(0.34, 1.56, 0.64, 1);
      position: relative;
      overflow: hidden;
    }
    .btn-choice:hover:not(:disabled) {
      transform: translateY(-4px) scale(1.015);
      filter: brightness(1.1);
    }
    .btn-choice:active:not(:disabled) {
      transform: translateY(2px) scale(0.98);
    }

    .choice-a {
      background: linear-gradient(135deg, #4f46e5 0%, #db2777 100%);
      box-shadow: 0 6px 0 #831843, 0 12px 24px rgba(219, 39, 119, 0.4);
    }
    .choice-b {
      background: linear-gradient(135deg, #d97706 0%, #10b981 100%);
      box-shadow: 0 6px 0 #065f46, 0 12px 24px rgba(16, 185, 129, 0.4);
    }
    .choice-c {
      background: linear-gradient(135deg, #0284c7 0%, #7c3aed 100%);
      box-shadow: 0 6px 0 #4c1d95, 0 12px 24px rgba(124, 58, 237, 0.4);
    }
    .choice-d {
      background: linear-gradient(135deg, #e11d48 0%, #f59e0b 100%);
      box-shadow: 0 6px 0 #9a3412, 0 12px 24px rgba(245, 158, 11, 0.4);
    }

    /* Animations */
    @keyframes shake {
      0%, 100% { transform: translateX(0); }
      20%, 60% { transform: translateX(-10px); }
      40%, 80% { transform: translateX(10px); }
    }
    .animate-shake {
      animation: shake 0.45s cubic-bezier(.36,.07,.19,.97) both;
      border-color: #f43f5e !important;
      box-shadow: 0 0 20px rgba(244, 63, 94, 0.7) !important;
    }

    @keyframes popIn {
      0% { opacity: 0; transform: scale(0.82) translateY(18px); }
      100% { opacity: 1; transform: scale(1) translateY(0); }
    }
    .animate-pop-in {
      animation: popIn 0.35s cubic-bezier(0.34, 1.56, 0.64, 1) forwards;
    }

    @keyframes floatSlow {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-8px); }
    }
    .animate-float {
      animation: floatSlow 3.5s ease-in-out infinite;
    }

    /* Custom Scrollbar for small screens */
    ::-webkit-scrollbar {
      width: 6px;
    }
    ::-webkit-scrollbar-track {
      background: rgba(15, 23, 42, 0.4);
    }
    ::-webkit-scrollbar-thumb {
      background: rgba(255, 255, 255, 0.25);
      border-radius: 9999px;
    }
  </style>
</head>
<body class="bg-animated-aurora min-h-screen flex flex-col justify-between relative">

  <!-- Ambient Neon Orbs -->
  <div class="orb w-72 h-72 bg-indigo-500 top-6 left-6"></div>
  <div class="orb w-80 h-80 bg-pink-500 bottom-10 right-6" style="animation-delay: 2s;"></div>
  <div class="orb w-64 h-64 bg-emerald-500 top-1/2 left-1/3" style="animation-delay: 4s;"></div>
  <div class="orb w-64 h-64 bg-amber-500 bottom-1/3 right-1/4" style="animation-delay: 6s;"></div>

  <!-- Main App Container -->
  <main class="relative z-10 w-full max-w-5xl mx-auto px-4 py-4 sm:py-6 flex-1 flex flex-col justify-center">

    <!-- ==================== 1. START SCREEN ==================== -->
    <section id="start-screen" class="w-full max-w-xl mx-auto animate-pop-in">
      <div class="glass-panel rounded-3xl p-6 sm:p-10 text-center relative overflow-hidden">
        <!-- Top Badge -->
        <div class="inline-flex items-center gap-2 px-4 py-1.5 rounded-full bg-white/10 border border-white/20 text-xs sm:text-sm font-semibold text-amber-300 mb-4 tracking-wide">
          <span>✨ MTs KELAS VII • SEMESTER 1 ✨</span>
        </div>

        <!-- Title & Icon -->
        <div class="w-20 h-20 sm:w-24 sm:h-24 mx-auto mb-4 rounded-2xl bg-gradient-to-tr from-indigo-500 via-pink-500 to-amber-400 p-1 shadow-lg animate-float">
          <div class="w-full h-full bg-slate-900/90 rounded-xl flex items-center justify-center text-4xl sm:text-5xl">
            🌙
          </div>
        </div>

        <h1 class="text-3xl sm:text-5xl font-extrabold tracking-tight text-white text-glow mb-2">
          Petualangan Akidah Akhlak
        </h1>
        <p class="text-slate-200/90 text-sm sm:text-base mb-6 max-w-md mx-auto">
          Uji pemahaman dan kecepatanmu menaklukkan 3 Level tantangan: <strong>Asmaul Husna</strong>, <strong>Utusan Cahaya</strong>, dan <strong>Detektif Akhlak</strong>!
        </p>

        <!-- Level Preview Badges -->
        <div class="grid grid-cols-3 gap-2 sm:gap-3 mb-7 text-left">
          <div class="bg-indigo-950/60 border border-indigo-400/30 rounded-2xl p-2.5 sm:p-3">
            <div class="text-lg sm:text-xl mb-1">🔮</div>
            <div class="text-xs font-bold text-indigo-300">LEVEL 1</div>
            <div class="text-[11px] sm:text-xs text-slate-300 leading-tight">Misteri Asmaul Husna</div>
          </div>
          <div class="bg-emerald-950/60 border border-emerald-400/30 rounded-2xl p-2.5 sm:p-3">
            <div class="text-lg sm:text-xl mb-1">🪽</div>
            <div class="text-xs font-bold text-emerald-300">LEVEL 2</div>
            <div class="text-[11px] sm:text-xs text-slate-300 leading-tight">Para Utusan Cahaya</div>
          </div>
          <div class="bg-pink-950/60 border border-pink-400/30 rounded-2xl p-2.5 sm:p-3">
            <div class="text-lg sm:text-xl mb-1">🕵️</div>
            <div class="text-xs font-bold text-pink-300">LEVEL 3</div>
            <div class="text-[11px] sm:text-xs text-slate-300 leading-tight">Detektif Akhlak</div>
          </div>
        </div>

        <!-- Input Form -->
        <div id="login-form-box" class="space-y-4 text-left">
          <div>
            <label for="player-name" class="block text-xs sm:text-sm font-bold text-slate-200 mb-1.5 ml-1">
              Nama Lengkap Siswa
            </label>
            <input
              type="text"
              id="player-name"
              placeholder="Contoh: Ahmad Fauzi"
              autocomplete="off"
              class="w-full px-4 py-3.5 rounded-2xl bg-slate-900/75 border-2 border-white/20 text-white placeholder-slate-400 focus:outline-none focus:border-emerald-400 focus:ring-2 focus:ring-emerald-400/30 transition text-base font-semibold"
            />
          </div>

          <div>
            <label for="player-class" class="block text-xs sm:text-sm font-bold text-slate-200 mb-1.5 ml-1">
              Kelas
            </label>
            <input
              type="text"
              id="player-class"
              placeholder="Contoh: VII A"
              autocomplete="off"
              class="w-full px-4 py-3.5 rounded-2xl bg-slate-900/75 border-2 border-white/20 text-white placeholder-slate-400 focus:outline-none focus:border-pink-400 focus:ring-2 focus:ring-pink-400/30 transition text-base font-semibold"
            />
          </div>

          <!-- Validation Warning Message -->
          <p id="validation-msg" class="hidden text-rose-400 text-xs sm:text-sm font-bold text-center bg-rose-950/60 border border-rose-500/40 py-2 px-3 rounded-xl">
            ⚠️ Mohon isi Nama Lengkap dan Kelas terlebih dahulu ya!
          </p>

          <button
            id="btn-start"
            type="button"
            class="w-full mt-2 py-4 rounded-2xl font-display font-bold text-lg sm:text-xl tracking-wide text-white bg-gradient-to-r from-indigo-500 via-pink-500 to-amber-500 hover:from-indigo-400 hover:via-pink-400 hover:to-amber-400 shadow-[0_8px_25px_rgba(236,72,153,0.5)] active:scale-95 transition-all cursor-pointer flex items-center justify-center gap-2"
          >
            <span>MULAI PETUALANGAN</span>
            <span class="text-2xl">🚀</span>
          </button>
        </div>
      </div>
    </section>

    <!-- ==================== 2. GAMEPLAY SCREEN ==================== -->
    <section id="game-screen" class="hidden w-full flex-col gap-4 sm:gap-5 animate-pop-in">
      <!-- Top HUD Bar -->
      <header class="glass-panel rounded-2xl sm:rounded-3xl p-3 sm:p-4 flex flex-wrap items-center justify-between gap-3">
        <!-- Player Info -->
        <div class="flex items-center gap-2.5 sm:gap-3">
          <div class="w-10 h-10 sm:w-12 sm:h-12 rounded-xl bg-gradient-to-br from-indigo-500 to-pink-500 flex items-center justify-center font-display font-bold text-lg sm:text-xl shadow-md">
            🎓
          </div>
          <div>
            <div id="hud-player" class="font-bold text-sm sm:text-base text-white leading-tight">Siswa - VII A</div>
            <div class="flex items-center gap-1.5 mt-0.5">
              <span id="hud-combo" class="hidden text-[11px] font-extrabold px-2 py-0.5 rounded-full bg-amber-400/20 text-amber-300 border border-amber-400/40">
                🔥 Streak x2
              </span>
              <span id="hud-progress-text" class="text-xs text-slate-300 font-medium">Soal 1 / 30</span>
            </div>
          </div>
        </div>

        <!-- Score Display -->
        <div class="flex items-center gap-3 sm:gap-5">
          <div class="text-center px-3 sm:px-5 py-1.5 rounded-2xl bg-slate-900/70 border border-amber-400/30">
            <div class="text-[10px] sm:text-xs uppercase tracking-wider text-amber-300 font-bold">Total Skor</div>
            <div id="hud-score" class="font-display font-extrabold text-xl sm:text-2xl text-white text-glow-amber">0</div>
          </div>

          <!-- Audio Mute/Unmute Toggle -->
          <button
            id="btn-mute"
            type="button"
            aria-label="Toggle Suara"
            class="w-11 h-11 sm:w-12 sm:h-12 rounded-2xl bg-white/10 hover:bg-white/20 border border-white/20 flex items-center justify-center text-xl transition active:scale-90 cursor-pointer"
            title="Suara Aktif/Mati"
          >
            🔊
          </button>
        </div>
      </header>

      <!-- Level Banner & Timer Progress -->
      <div class="flex flex-col items-center gap-2.5">
        <div id="level-badge" class="glass-panel neon-border-cyan px-5 py-2 rounded-2xl text-center">
          <div id="level-title" class="font-display font-bold text-sm sm:text-lg text-emerald-300 tracking-wide">
            LEVEL 1: Misteri Asmaul Husna
          </div>
          <div id="level-subtitle" class="text-[11px] sm:text-xs text-slate-300">
            Sifat Wajib, Mustahil, Jaiz Allah & Asmaul Husna
          </div>
        </div>

        <!-- Speed Bonus Timer Bar -->
        <div class="w-full max-w-2xl bg-slate-900/70 h-3 rounded-full p-0.5 border border-white/15 overflow-hidden">
          <div id="timer-bar" class="h-full rounded-full bg-gradient-to-r from-emerald-400 via-amber-400 to-pink-500 transition-all duration-200" style="width: 100%;"></div>
        </div>
      </div>

      <!-- Question Card -->
      <div class="glass-panel neon-border-pink rounded-3xl p-6 sm:p-9 text-center min-h-[150px] sm:min-h-[190px] flex flex-col items-center justify-center relative">
        <span id="question-number-pill" class="absolute top-3.5 left-4 text-xs font-bold px-3 py-1 rounded-full bg-white/10 text-pink-200 border border-white/15">
          Pertanyaan #1
        </span>
        <span id="speed-bonus-indicator" class="absolute top-3.5 right-4 text-xs font-bold px-3 py-1 rounded-full bg-amber-500/20 text-amber-300 border border-amber-400/30">
          ⚡ Bonus Cepat Aktif
        </span>

        <h2 id="question-text" class="text-lg sm:text-2xl md:text-3xl font-bold text-white leading-snug mt-5 sm:mt-3">
          Memuat pertanyaan...
        </h2>
      </div>

      <!-- 4 Answer Choice Buttons (Grid 1 col on mobile, 2 cols on tablet/projector) -->
      <div id="choices-grid" class="grid grid-cols-1 md:grid-cols-2 gap-3.5 sm:gap-4 mt-1">
        <button type="button" data-index="0" class="btn-choice choice-a rounded-2xl p-4 sm:p-5 text-left flex items-center gap-3.5 sm:gap-4 text-white cursor-pointer">
          <span class="w-10 h-10 sm:w-12 sm:h-12 rounded-xl bg-black/25 flex items-center justify-center font-display font-extrabold text-xl sm:text-2xl shrink-0">A</span>
          <span class="choice-label font-bold text-base sm:text-lg leading-snug">Pilihan A</span>
        </button>

        <button type="button" data-index="1" class="btn-choice choice-b rounded-2xl p-4 sm:p-5 text-left flex items-center gap-3.5 sm:gap-4 text-white cursor-pointer">
          <span class="w-10 h-10 sm:w-12 sm:h-12 rounded-xl bg-black/25 flex items-center justify-center font-display font-extrabold text-xl sm:text-2xl shrink-0">B</span>
          <span class="choice-label font-bold text-base sm:text-lg leading-snug">Pilihan B</span>
        </button>

        <button type="button" data-index="2" class="btn-choice choice-c rounded-2xl p-4 sm:p-5 text-left flex items-center gap-3.5 sm:gap-4 text-white cursor-pointer">
          <span class="w-10 h-10 sm:w-12 sm:h-12 rounded-xl bg-black/25 flex items-center justify-center font-display font-extrabold text-xl sm:text-2xl shrink-0">C</span>
          <span class="choice-label font-bold text-base sm:text-lg leading-snug">Pilihan C</span>
        </button>

        <button type="button" data-index="3" class="btn-choice choice-d rounded-2xl p-4 sm:p-5 text-left flex items-center gap-3.5 sm:gap-4 text-white cursor-pointer">
          <span class="w-10 h-10 sm:w-12 sm:h-12 rounded-xl bg-black/25 flex items-center justify-center font-display font-extrabold text-xl sm:text-2xl shrink-0">D</span>
          <span class="choice-label font-bold text-base sm:text-lg leading-snug">Pilihan D</span>
        </button>
      </div>
    </section>

    <!-- ==================== 3. END / RESULT SCREEN ==================== -->
    <section id="end-screen" class="hidden w-full max-w-2xl mx-auto animate-pop-in">
      <div class="glass-panel rounded-3xl p-6 sm:p-10 text-center relative overflow-hidden">
        <div class="text-5xl sm:text-6xl mb-3 animate-float" id="end-trophy">🏆</div>
        <h2 class="font-display text-3xl sm:text-4xl font-extrabold text-white text-glow mb-1">
          Petualangan Selesai!
        </h2>
        <p id="end-student-info" class="text-amber-300 font-bold text-base sm:text-lg mb-6">
          Ahmad Fauzi • Kelas VII A
        </p>

        <!-- Predicate Badge -->
        <div id="predicate-box" class="mb-6 p-4 sm:p-5 rounded-2xl bg-gradient-to-r from-emerald-500/25 via-indigo-500/25 to-pink-500/25 border-2 border-emerald-400/50">
          <div class="text-xs uppercase tracking-widest text-slate-300 font-bold mb-1">Predikat Kelulusan</div>
          <div id="end-predicate" class="font-display text-2xl sm:text-4xl font-extrabold text-emerald-300 text-glow-emerald">
            MUMTAZ (Istimewa)
          </div>
          <p id="end-message" class="text-xs sm:text-sm text-slate-200 mt-1.5">
            MasyaAllah! Pemahaman Akidah Akhlak kamu sangat luar biasa!
          </p>
        </div>

        <!-- Stats Grid -->
        <div class="grid grid-cols-3 gap-3 sm:gap-4 mb-7">
          <div class="bg-slate-900/75 border border-white/15 rounded-2xl p-3 sm:p-4">
            <div class="text-xs text-slate-400 font-semibold">Total Skor</div>
            <div id="end-score" class="font-display text-xl sm:text-3xl font-extrabold text-amber-400 mt-1">3000</div>
          </div>
          <div class="bg-slate-900/75 border border-white/15 rounded-2xl p-3 sm:p-4">
            <div class="text-xs text-slate-400 font-semibold">Jawaban Benar</div>
            <div id="end-correct" class="font-display text-xl sm:text-3xl font-extrabold text-emerald-400 mt-1">30 / 30</div>
          </div>
          <div class="bg-slate-900/75 border border-white/15 rounded-2xl p-3 sm:p-4">
            <div class="text-xs text-slate-400 font-semibold">Akurasi</div>
            <div id="end-accuracy" class="font-display text-xl sm:text-3xl font-extrabold text-pink-400 mt-1">100%</div>
          </div>
        </div>

        <button
          id="btn-restart"
          type="button"
          class="w-full py-4 rounded-2xl font-display font-bold text-lg sm:text-xl text-white bg-gradient-to-r from-emerald-500 via-teal-500 to-indigo-500 hover:brightness-110 shadow-[0_8px_25px_rgba(16,185,129,0.45)] active:scale-95 transition cursor-pointer"
        >
          🔄 MAIN LAGI
        </button>
      </div>
    </section>

  </main>

  <!-- ==================== PERSONAL FEEDBACK MODAL (POP-UP) ==================== -->
  <div id="feedback-modal" class="hidden fixed inset-0 z-50 bg-slate-950/80 backdrop-blur-md flex items-center justify-center p-4">
    <div id="feedback-card" class="glass-panel max-w-lg w-full rounded-3xl p-6 sm:p-7 text-center animate-pop-in border-2">
      <!-- Mascot / Mentor Avatar -->
      <div class="flex items-center justify-center gap-3 mb-3">
        <div id="feedback-icon" class="w-16 h-16 rounded-2xl flex items-center justify-center text-4xl shadow-lg">
          🤖
        </div>
      </div>

      <h3 id="feedback-title" class="font-display text-2xl sm:text-3xl font-extrabold mb-1">
        Luar Biasa!
      </h3>

      <div id="feedback-points" class="inline-block px-3.5 py-1 rounded-full text-xs sm:text-sm font-extrabold mb-4 bg-white/10">
        +100 Poin
      </div>

      <!-- Correct Answer Info (shown especially if wrong) -->
      <div id="correct-answer-box" class="hidden mb-3 p-2.5 rounded-xl bg-emerald-950/70 border border-emerald-400/40 text-emerald-300 text-xs sm:text-sm font-bold">
        Jawaban Benar: <span id="correct-answer-text"></span>
      </div>

      <!-- Explanation Box -->
      <div class="bg-slate-900/80 border border-white/15 rounded-2xl p-4 text-left mb-6">
        <div class="text-xs font-bold uppercase tracking-wider text-amber-300 mb-1 flex items-center gap-1.5">
          <span>💡 Pembahasan Materi:</span>
        </div>
        <p id="feedback-explanation" class="text-sm sm:text-base text-slate-200 leading-relaxed">
          Penjelasan singkat akan muncul di sini.
        </p>
      </div>

      <button
        id="btn-next"
        type="button"
        class="w-full py-3.5 sm:py-4 rounded-2xl font-display font-bold text-lg text-white bg-gradient-to-r from-indigo-500 to-cyan-500 hover:brightness-110 shadow-lg active:scale-95 transition cursor-pointer flex items-center justify-center gap-2"
      >
        <span id="btn-next-text">LANJUT</span>
        <span>❯</span>
      </button>
    </div>
  </div>

  <!-- ==================== LEVEL UP CELEBRATION TOAST ==================== -->
  <div id="levelup-modal" class="hidden fixed inset-0 z-50 bg-slate-950/85 backdrop-blur-md flex items-center justify-center p-4">
    <div class="glass-panel neon-border-cyan max-w-md w-full rounded-3xl p-7 text-center animate-pop-in">
      <div class="text-6xl mb-3 animate-bounce">🌟</div>
      <div class="text-xs font-extrabold uppercase tracking-widest text-amber-300 mb-1">NAIK TINGKAT!</div>
      <h3 id="levelup-heading" class="font-display text-2xl sm:text-3xl font-extrabold text-white text-glow mb-2">
        Memasuki Level 2
      </h3>
      <p id="levelup-desc" class="text-sm sm:text-base text-slate-200 mb-6">
        Bersiaplah mengenal tugas-tugas mulia para Malaikat Allah SWT!
      </p>
      <button
        id="btn-continue-level"
        type="button"
        class="w-full py-3.5 rounded-2xl font-display font-bold text-lg text-slate-950 bg-gradient-to-r from-emerald-400 to-amber-300 hover:brightness-110 shadow-lg active:scale-95 transition cursor-pointer"
      >
        SIAP LANJUT! ⚡
      </button>
    </div>
  </div>

  <!-- Footer Credit -->
  <footer class="relative z-10 text-center py-3 text-[11px] sm:text-xs text-slate-300/75 px-4">
    Media Pembelajaran Interaktif Akidah Akhlak Kelas VII MTs • Semester 1
  </footer>

  <!-- ==================== GAME LOGIC & STRUCTURED DATA ==================== -->
  <script>
    /**
     * 1. STRUCTURED QUESTION BANK (30 Soal Lengkap: 3 Level x 10 Soal)
     * Kurikulum Akidah Akhlak MTs Kelas VII Semester 1
     */
    const quizData = [
      // ================= LEVEL 1: MISTERI ASMAUL HUSNA (10 Soal) =================
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Sifat yang pasti dimiliki oleh Allah SWT sebagai Zat Yang Maha Sempurna disebut...",
        options: ["Sifat Wajib Allah", "Sifat Mustahil Allah", "Sifat Jaiz Allah", "Sifat Mubah Allah"],
        correct: 0,
        explanation: "Sifat Wajib bagi Allah adalah sifat-sifat kesempurnaan yang pasti dimiliki oleh Allah SWT, yang berjumlah 20 sifat."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Adanya alam semesta beserta seluruh isinya yang teratur menjadi bukti nyata bahwa Allah SWT memiliki sifat wajib...",
        options: ["Fana", "Wujud", "'Adam", "Huduts"],
        correct: 1,
        explanation: "Wujud artinya 'Ada'. Adanya langit, bumi, dan seluruh ciptaan membuktikan keberadaan Allah SWT sebagai Sang Pencipta."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Allah SWT bersifat 'Qidam' yang artinya Terdahulu. Lawan kata (sifat mustahil) dari Qidam adalah...",
        options: ["Baqa'", "Huduts", "Mumatsalatu lil hawaditsi", "Qiyamuhu binafsihi"],
        correct: 1,
        explanation: "Lawan dari Qidam (Terdahulu tanpa permulaan) adalah Huduts, yang artinya baru atau ada permulaannya."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Segala sesuatu di dunia ini pasti akan rusak dan binasa, kecuali Allah SWT karena Dia memiliki sifat...",
        options: ["Baqa'", "Fana", "Iradat", "Hayat"],
        correct: 0,
        explanation: "Baqa' artinya Kekal. Allah SWT Maha Kekal selama-lamanya dan tidak akan pernah mengalami kebinasaan."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Sifat Jaiz bagi Allah SWT hanya ada satu, yaitu 'Fi'lu kulli mumkinin au tarkuhu' yang artinya...",
        options: [
          "Allah wajib menciptakan semua manusia masuk surga",
          "Allah berwenang menciptakan sesuatu atau tidak menciptakannya",
          "Allah tidak mungkin memiliki sekutu dalam kerajaan-Nya",
          "Allah berbeda dengan seluruh makhluk ciptaan-Nya"
        ],
        correct: 1,
        explanation: "Sifat Jaiz Allah berarti Allah bebas berkehendak untuk memperbuat sesuatu yang mungkin terjadi atau meninggalkannya tanpa paksaan siapa pun."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Nama-nama Allah SWT yang baik, indah, dan agung yang berjumlah 99 disebut...",
        options: ["Asmaul Husna", "Kalimat Thayyibah", "Sifat Salbiyah", "Sifat Ma'nawiyah"],
        correct: 0,
        explanation: "Asmaul Husna secara bahasa berarti nama-nama yang baik dan indah, yang mencerminkan keagungan sifat Allah SWT."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Rafi selalu berkata jujur dan menjaga ucapannya meski sendirian karena yakin Allah melihat dan mendengar. Perilaku Rafi meneladani Asmaul Husna...",
        options: ["Al-'Aziz", "Al-Bashir", "Al-Qayyum", "Al-Fattah"],
        correct: 1,
        explanation: "Al-Bashir artinya Allah Maha Melihat segala sesuatu, baik yang tampak maupun yang tersembunyi di hati manusia."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Asmaul Husna 'Al-Qayyum' memiliki arti bahwa Allah SWT Maha...",
        options: ["Maha Perkasa", "Maha Berdiri Sendiri / Mengurus Makhluk-Nya", "Maha Adil", "Maha Pengampun"],
        correct: 1,
        explanation: "Al-Qayyum artinya Yang Maha Berdiri Sendiri (tidak membutuhkan bantuan makhluk) serta terus-menerus mengurus makhluk-Nya."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Allah SWT memberikan rezeki dan kasih sayang kepada seluruh makhluk di bumi tanpa membeda-bedakan, ini mencerminkan sifat...",
        options: ["Ar-Rahman", "Al-'Adl", "Al-Muntaqim", "Al-Qabidh"],
        correct: 0,
        explanation: "Ar-Rahman artinya Maha Pengasih. Kasih sayang Allah di dunia diberikan kepada seluruh makhluk-Nya tanpa terkecuali."
      },
      {
        level: 1,
        levelTitle: "LEVEL 1: Misteri Asmaul Husna",
        levelSubtitle: "Sifat Wajib, Mustahil, Jaiz Allah SWT & Asmaul Husna",
        question: "Sebagai ketua kelas, Zahra membagi tugas piket secara merata tanpa pilih kasih. Sikap Zahra meneladani Asmaul Husna...",
        options: ["Al-'Adl", "Al-Ghaffar", "An-Nafi'", "Al-Barr"],
        correct: 0,
        explanation: "Al-'Adl artinya Yang Maha Adil. Meneladani sifat Al-'Adl diwujudkan dengan bersikap objektif dan tidak memihak."
      },

      // ================= LEVEL 2: TUGAS PARA UTUSAN CAHAYA (10 Soal) =================
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Malaikat adalah makhluk gaib ciptaan Allah SWT yang diciptakan dari...",
        options: ["Tanah liat", "Nyala api", "Nur (Cahaya)", "Angin topan"],
        correct: 2,
        explanation: "Berdasarkan hadis sahih riwayat Muslim, malaikat diciptakan dari Nur (cahaya), jin dari nyala api, dan Nabi Adam AS dari tanah."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Di bawah ini yang merupakan sifat-sifat mulia Malaikat Allah SWT adalah...",
        options: [
          "Memiliki hawa nafsu dan butuh makan",
          "Selalu taat dan tidak pernah durhaka kepada Allah",
          "Memiliki jenis kelamin laki-laki dan perempuan",
          "Kadang lalai saat menjalankan perintah Allah"
        ],
        correct: 1,
        explanation: "Malaikat tidak memiliki hawa nafsu, tidak makan/minum, tidak berjenis kelamin, dan senantiasa bertasbih serta patuh mutlak kepada Allah."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Malaikat yang bertugas menyampaikan wahyu Allah SWT kepada para Nabi dan Rasul adalah...",
        options: ["Malaikat Mikail", "Malaikat Jibril", "Malaikat Israfil", "Malaikat Ridwan"],
        correct: 1,
        explanation: "Malaikat Jibril (Ruhul Qudus) bertugas menyampaikan wahyu dari Allah SWT kepada para nabi dan rasul."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Turunnya hujan yang menyuburkan tanaman dan rezeki yang diterima makhluk hidup diatur oleh Allah melalui tugas...",
        options: ["Malaikat Mikail", "Malaikat Izrail", "Malaikat Malik", "Malaikat Munkar"],
        correct: 0,
        explanation: "Malaikat Mikail bertugas mengatur pembagian rezeki, menurunkan hujan, dan menumbuhkan tumbuh-tumbuhan atas izin Allah SWT."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Malaikat yang bertugas meniup sangkakala pada hari kiamat dan hari kebangkitan adalah...",
        options: ["Malaikat Izrail", "Malaikat Israfil", "Malaikat Raqib", "Malaikat Atid"],
        correct: 1,
        explanation: "Malaikat Israfil bertugas meniup sangkakala sebagai tanda dimulainya hari kiamat dan dibangkitkannya manusia dari alam kubur."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Setiap makhluk yang bernyawa pasti akan merasakan mati. Malaikat yang bertugas mencabut nyawa adalah...",
        options: ["Malaikat Izrail", "Malaikat Nakir", "Malaikat Ridwan", "Malaikat Jibril"],
        correct: 0,
        explanation: "Malaikat Izrail (Malakul Maut) bertugas mencabut nyawa seluruh makhluk hidup apabila ajalnya telah tiba."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Dua malaikat yang bertugas menanyai manusia di alam kubur (barzakh) adalah...",
        options: ["Raqib dan Atid", "Munkar dan Nakir", "Malik dan Ridwan", "Jibril dan Mikail"],
        correct: 1,
        explanation: "Malaikat Munkar dan Nakir bertugas memeriksa dan menanyai amal perbuatan manusia di alam kubur."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Ketika seorang siswa membantu temannya yang terjatuh dengan ikhlas, amal kebaikannya langsung dicatat oleh...",
        options: ["Malaikat Atid", "Malaikat Raqib", "Malaikat Malik", "Malaikat Israfil"],
        correct: 1,
        explanation: "Malaikat Raqib berada di sebelah kanan manusia dan bertugas mencatat segala amal kebaikan sekecil apa pun."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Sebaliknya, segala perkataan dusta dan perbuatan buruk manusia akan dicatat dengan teliti oleh...",
        options: ["Malaikat Raqib", "Malaikat Atid", "Malaikat Ridwan", "Malaikat Mikail"],
        correct: 1,
        explanation: "Malaikat Atid berada di sebelah kiri manusia dan bertugas mencatat setiap amal keburukan."
      },
      {
        level: 2,
        levelTitle: "LEVEL 2: Tugas Para Utusan Cahaya",
        levelSubtitle: "Mengenal Malaikat Allah SWT, Sifat & Tugas Mulianya",
        question: "Malaikat penjaga pintu Neraka dan Malaikat penjaga pintu Surga secara berurutan adalah...",
        options: ["Ridwan dan Malik", "Malik dan Ridwan", "Munkar dan Nakir", "Israfil dan Izrail"],
        correct: 1,
        explanation: "Malaikat Malik bertugas menjaga pintu Neraka dengan tegas, sedangkan Malaikat Ridwan menjaga pintu Surga dengan ramah."
      },

      // ================= LEVEL 3: DETEKTIF AKHLAK (10 Soal) =================
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Mengerjakan suatu ibadah atau amal kebaikan semata-mata hanya mengharap rida Allah SWT disebut...",
        options: ["Taubat", "Ikhlas", "Khauf", "Riya"],
        correct: 1,
        explanation: "Ikhlas adalah memurnikan niat beribadah dan beramal saleh hanya karena Allah SWT, tanpa mengharap pujian manusia."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Berikut ini yang merupakan ciri-ciri orang yang memiliki sifat Ikhlas adalah...",
        options: [
          "Rajin beribadah hanya saat dilihat guru dan orang tua",
          "Mengungkit-ungkit sedekah yang telah diberikan",
          "Tetap semangat berbuat baik meski tidak ada yang memuji",
          "Kecewa berat jika bantuannya tidak diumumkan"
        ],
        correct: 2,
        explanation: "Orang yang ikhlas tidak terpengaruh oleh pujian maupun celaan manusia; hatinya tenang karena tujuannya hanya rida Allah."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Tunduk dan patuh menjalankan segala perintah Allah SWT, Rasul-Nya, serta aturan orang tua dan guru disebut...",
        options: ["Taat", "Khauf", "Nifaq", "Riya"],
        correct: 0,
        explanation: "Taat berarti patuh dan tunduk secara sadar terhadap perintah Allah SWT, Rasulullah SAW, dan ulil amri selama tidak dalam kemaksiatan."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Perasaan takut kepada murka dan azab Allah SWT sehingga mendorong seseorang menjauhi larangan-Nya disebut...",
        options: ["Raja'", "Khauf", "Taubat", "Tawadhu"],
        correct: 1,
        explanation: "Khauf adalah rasa takut kepada Allah SWT yang melahirkan ketaatan dan mencegah seorang mukmin berbuat dosa."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Menyesali perbuatan dosa yang telah dilakukan, berhenti melakukannya, dan bertekad tidak mengulanginya disebut...",
        options: ["Taubat", "Ikhlas", "Qana'ah", "Tawakal"],
        correct: 0,
        explanation: "Taubat nasuha berarti kembali ke jalan Allah dengan menyesali dosa, meninggalkannya, dan berjanji tidak akan mengulanginya."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Jika dosa yang dilakukan berkaitan dengan hak sesama manusia (seperti mengambil barang teman), syarat taubatnya harus ditambah dengan...",
        options: [
          "Berdiam diri di kamar selama seminggu",
          "Meminta maaf dan mengembalikan hak teman tersebut",
          "Menceritakan kesalahan itu di media sosial",
          "Menunggu hingga teman itu lupa sendiri"
        ],
        correct: 1,
        explanation: "Taubat atas dosa sesama manusia mensyaratkan meminta maaf secara langsung dan mengembalikan hak yang pernah diambil."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Memperlihatkan amal ibadah atau kebaikan kepada orang lain agar mendapat pujian dan sanjungan disebut...",
        options: ["Ikhlas", "Riya", "Taubat", "Khauf"],
        correct: 1,
        explanation: "Riya adalah melakukan amal kebaikan bukan karena Allah, melainkan agar dilihat dan dipuji oleh manusia. Riya termasuk syirik kecil."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Salman memasukkan uang ke kotak infak sambil melirik teman-temannya dan mengeraskan suaranya agar dianggap dermawan. Perilaku Salman termasuk...",
        options: ["Riya dalam perbuatan", "Ikhlas beramal", "Taat beribadah", "Khauf kepada Allah"],
        correct: 0,
        explanation: "Memamerkan sedekah supaya dianggap dermawan oleh orang sekitar merupakan contoh nyata perilaku Riya yang menghapus pahala."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Sikap bermuka dua, yaitu menampakkan keimanan atau kebaikan di luar, namun menyembunyikan kekufuran atau niat buruk di dalam hati disebut...",
        options: ["Nifaq", "Taubat", "Taat", "Khauf"],
        correct: 0,
        explanation: "Nifaq adalah ketidaksesuaian antara ucapan/penampilan luar dengan apa yang tersembunyi di dalam hati. Pelakunya disebut Munafik."
      },
      {
        level: 3,
        levelTitle: "LEVEL 3: Detektif Akhlak",
        levelSubtitle: "Akhlak Terpuji (Ikhlas, Taat, Khauf, Taubat) & Tercela (Riya, Nifaq)",
        question: "Menurut sabda Nabi Muhammad SAW, salah satu tanda orang yang memiliki sifat Nifaq (munafik) adalah...",
        options: [
          "Apabila berbicara ia selalu jujur",
          "Apabila berjanji ia selalu menepati",
          "Apabila dipercaya (diberi amanah) ia berkhianat",
          "Apabila bersalah ia segera bertaubat"
        ],
        correct: 2,
        explanation: "Tiga tanda orang munafik menurut hadis Nabi SAW: apabila berkata ia dusta, apabila berjanji ia mengingkari, dan apabila dipercaya ia berkhianat."
      }
    ];

    /**
     * 2. AUDIO ENGINE WITH TONE.JS (Synthesized SFX & Light BGM)
     */
    const AudioEngine = {
      isMuted: false,
      isInitialized: false,
      bgmLoop: null,
      bgmSynth: null,
      sfxSynth: null,

      async init() {
        if (this.isInitialized) return;
        try {
          await Tone.start();
          // PolySynth for pleasant chords & SFX
          this.sfxSynth = new Tone.PolySynth(Tone.Synth, {
            oscillator: { type: "triangle" },
            envelope: { attack: 0.01, decay: 0.15, sustain: 0.1, release: 0.4 }
          }).toDestination();
          this.sfxSynth.volume.value = -6;

          // Soft Pluck/Bell Synth for Light Educational BGM
          this.bgmSynth = new Tone.Synth({
            oscillator: { type: "sine" },
            envelope: { attack: 0.05, decay: 0.3, sustain: 0.1, release: 0.8 }
          }).toDestination();
          this.bgmSynth.volume.value = -18;

          const melody = ["C4", "E4", "G4", "B4", "A4", "G4", "E4", "D4"];
          let step = 0;
          this.bgmLoop = new Tone.Loop((time) => {
            if (!this.isMuted) {
              this.bgmSynth.triggerAttackRelease(melody[step % melody.length], "8n", time);
            }
            step++;
          }, "4n");

          Tone.Transport.bpm.value = 96;
          Tone.Transport.start();
          this.bgmLoop.start(0);
          this.isInitialized = true;
        } catch (e) {
          console.warn("Audio init deferred:", e);
        }
      },

      toggleMute() {
        this.isMuted = !this.isMuted;
        Tone.Destination.mute = this.isMuted;
        return this.isMuted;
      },

      playClick() {
        if (this.isMuted || !this.sfxSynth) return;
        this.sfxSynth.triggerAttackRelease("G5", "32n");
      },

      playCorrect() {
        if (this.isMuted || !this.sfxSynth) return;
        const now = Tone.now();
        this.sfxSynth.triggerAttackRelease("C5", "16n", now);
        this.sfxSynth.triggerAttackRelease("E5", "16n", now + 0.08);
        this.sfxSynth.triggerAttackRelease("G5", "16n", now + 0.16);
        this.sfxSynth.triggerAttackRelease("C6", "8n", now + 0.24);
      },

      playWrong() {
        if (this.isMuted || !this.sfxSynth) return;
        const now = Tone.now();
        this.sfxSynth.triggerAttackRelease("Eb4", "8n", now);
        this.sfxSynth.triggerAttackRelease("C4", "4n", now + 0.14);
      },

      playLevelUp() {
        if (this.isMuted || !this.sfxSynth) return;
        const now = Tone.now();
        ["C4", "E4", "G4", "C5", "E5", "G5"].forEach((note, idx) => {
          this.sfxSynth.triggerAttackRelease(note, "16n", now + idx * 0.08);
        });
      },

      playVictory() {
        if (this.isMuted || !this.sfxSynth) return;
        const now = Tone.now();
        this.sfxSynth.triggerAttackRelease(["C4", "E4", "G4"], "8n", now);
        this.sfxSynth.triggerAttackRelease(["F4", "A4", "C5"], "8n", now + 0.2);
        this.sfxSynth.triggerAttackRelease(["G4", "B4", "D5"], "8n", now + 0.4);
        this.sfxSynth.triggerAttackRelease(["C5", "E5", "G5", "C6"], "2n", now + 0.6);
      }
    };

    /**
     * 3. GAME STATE & CONTROLLER
     */
    const state = {
      playerName: "",
      playerClass: "",
      currentIndex: 0,
      score: 0,
      correctCount: 0,
      streak: 0,
      questionStartTime: 0,
      timerInterval: null,
      maxTimeSec: 20,
      isAnswered: false
    };

    // DOM References
    const startScreen = document.getElementById("start-screen");
    const gameScreen = document.getElementById("game-screen");
    const endScreen = document.getElementById("end-screen");

    const inputName = document.getElementById("player-name");
    const inputClass = document.getElementById("player-class");
    const loginFormBox = document.getElementById("login-form-box");
    const validationMsg = document.getElementById("validation-msg");
    const btnStart = document.getElementById("btn-start");

    const hudPlayer = document.getElementById("hud-player");
    const hudScore = document.getElementById("hud-score");
    const hudCombo = document.getElementById("hud-combo");
    const hudProgressText = document.getElementById("hud-progress-text");
    const btnMute = document.getElementById("btn-mute");

    const levelBadge = document.getElementById("level-badge");
    const levelTitle = document.getElementById("level-title");
    const levelSubtitle = document.getElementById("level-subtitle");
    const timerBar = document.getElementById("timer-bar");
    const speedBonusIndicator = document.getElementById("speed-bonus-indicator");

    const questionNumberPill = document.getElementById("question-number-pill");
    const questionText = document.getElementById("question-text");
    const choiceButtons = document.querySelectorAll(".btn-choice");

    const feedbackModal = document.getElementById("feedback-modal");
    const feedbackCard = document.getElementById("feedback-card");
    const feedbackIcon = document.getElementById("feedback-icon");
    const feedbackTitle = document.getElementById("feedback-title");
    const feedbackPoints = document.getElementById("feedback-points");
    const correctAnswerBox = document.getElementById("correct-answer-box");
    const correctAnswerText = document.getElementById("correct-answer-text");
    const feedbackExplanation = document.getElementById("feedback-explanation");
    const btnNext = document.getElementById("btn-next");
    const btnNextText = document.getElementById("btn-next-text");

    const levelupModal = document.getElementById("levelup-modal");
    const levelupHeading = document.getElementById("levelup-heading");
    const levelupDesc = document.getElementById("levelup-desc");
    const btnContinueLevel = document.getElementById("btn-continue-level");

    // Praise & Encouragement Pools
    const praises = [
      "MasyaAllah, Hebat Sekali!",
      "Luar Biasa, Jawabanmu Tepat!",
      "Mumtaz! Kamu Cerdas!",
      "Keren Banget, Tepat Sasaran!",
      "Alhamdulillah, Benar Sekali!"
    ];

    const motivations = [
      "Tetap Semangat, Yuk Belajar Lagi!",
      "Hampir Tepat! Perhatikan Pembahasannya Ya.",
      "Jangan Menyerah, Kesalahan Adalah Awal Kepintaran!",
      "Yuk Cermati Materi Ini Supaya Makin Paham!"
    ];

    // Start Game Validation & Handler
    btnStart.addEventListener("click", async () => {
      const nameVal = inputName.value.trim();
      const classVal = inputClass.value.trim();

      if (!nameVal || !classVal) {
        // Trigger Shake Animation
        loginFormBox.classList.remove("animate-shake");
        void loginFormBox.offsetWidth; // Force reflow
        loginFormBox.classList.add("animate-shake");
        validationMsg.classList.remove("hidden");

        if (!nameVal) inputName.focus();
        else inputClass.focus();
        return;
      }

      validationMsg.classList.add("hidden");
      state.playerName = nameVal;
      state.playerClass = classVal.toUpperCase();

      await AudioEngine.init();
      AudioEngine.playClick();

      startGame();
    });

    // Allow Enter key on inputs
    [inputName, inputClass].forEach(inp => {
      inp.addEventListener("keydown", (e) => {
        if (e.key === "Enter") btnStart.click();
      });
    });

    // Mute Toggle
    btnMute.addEventListener("click", async () => {
      await AudioEngine.init();
      const muted = AudioEngine.toggleMute();
      btnMute.textContent = muted ? "🔇" : "🔊";
    });

    function startGame() {
      state.currentIndex = 0;
      state.score = 0;
      state.correctCount = 0;
      state.streak = 0;

      hudPlayer.textContent = `${state.playerName} • ${state.playerClass}`;
      updateScoreHUD();

      startScreen.classList.add("hidden");
      endScreen.classList.add("hidden");
      gameScreen.classList.remove("hidden");
      gameScreen.classList.add("flex");

      loadQuestion();
    }

    function updateScoreHUD() {
      hudScore.textContent = state.score.toLocaleString("id-ID");
      if (state.streak >= 2) {
        hudCombo.classList.remove("hidden");
        hudCombo.textContent = `🔥 Streak x${state.streak}`;
      } else {
        hudCombo.classList.add("hidden");
      }
    }

    function loadQuestion() {
      state.isAnswered = false;
      const q = quizData[state.currentIndex];

      // Update Level Banner Styling
      levelTitle.textContent = q.levelTitle;
      levelSubtitle.textContent = q.levelSubtitle;

      if (q.level === 1) {
        levelTitle.className = "font-display font-bold text-sm sm:text-lg text-indigo-300 tracking-wide";
      } else if (q.level === 2) {
        levelTitle.className = "font-display font-bold text-sm sm:text-lg text-emerald-300 tracking-wide";
      } else {
        levelTitle.className = "font-display font-bold text-sm sm:text-lg text-amber-300 tracking-wide";
      }

      // Update Counters
      hudProgressText.textContent = `Soal ${state.currentIndex + 1} / ${quizData.length}`;
      questionNumberPill.textContent = `Pertanyaan #${state.currentIndex + 1}`;
      questionText.textContent = q.question;

      // Populate Choices
      choiceButtons.forEach((btn, idx) => {
        btn.disabled = false;
        btn.style.opacity = "1";
        btn.querySelector(".choice-label").textContent = q.options[idx];
      });

      // Start Speed Timer
      startQuestionTimer();
    }

    function startQuestionTimer() {
      clearInterval(state.timerInterval);
      state.questionStartTime = Date.now();
      timerBar.style.width = "100%";
      speedBonusIndicator.textContent = "⚡ Bonus Cepat Aktif";
      speedBonusIndicator.className = "absolute top-3.5 right-4 text-xs font-bold px-3 py-1 rounded-full bg-amber-500/20 text-amber-300 border border-amber-400/30";

      state.timerInterval = setInterval(() => {
        if (state.isAnswered) {
          clearInterval(state.timerInterval);
          return;
        }
        const elapsed = (Date.now() - state.questionStartTime) / 1000;
        const remainingPct = Math.max(0, 100 - (elapsed / state.maxTimeSec) * 100);
        timerBar.style.width = `${remainingPct}%`;

        if (remainingPct <= 0) {
          speedBonusIndicator.textContent = "⏱️ Waktu Bonus Habis (Poin Dasar +100)";
          speedBonusIndicator.className = "absolute top-3.5 right-4 text-xs font-bold px-3 py-1 rounded-full bg-slate-700/60 text-slate-300 border border-white/15";
          clearInterval(state.timerInterval);
        }
      }, 100);
    }

    // Handle Answer Click
    choiceButtons.forEach((btn) => {
      btn.addEventListener("click", () => {
        if (state.isAnswered) return;
        state.isAnswered = true;
        clearInterval(state.timerInterval);

        const selectedIdx = parseInt(btn.getAttribute("data-index"), 10);
        const q = quizData[state.currentIndex];
        const isCorrect = selectedIdx === q.correct;

        // Disable all buttons visually
        choiceButtons.forEach((b, idx) => {
          b.disabled = true;
          if (idx !== selectedIdx && idx !== q.correct) {
            b.style.opacity = "0.45";
          }
        });

        // Calculate Points (Base 100 + Speed Bonus up to 50)
        let earnedPoints = 0;
        let speedBonus = 0;

        if (isCorrect) {
          const elapsedSec = (Date.now() - state.questionStartTime) / 1000;
          if (elapsedSec < state.maxTimeSec) {
            speedBonus = Math.round(((state.maxTimeSec - elapsedSec) / state.maxTimeSec) * 50);
          }
          earnedPoints = 100 + speedBonus;
          state.score += earnedPoints;
          state.correctCount++;
          state.streak++;

          AudioEngine.playCorrect();
        } else {
          state.streak = 0;
          AudioEngine.playWrong();
        }

        updateScoreHUD();
        showFeedbackModal(isCorrect, earnedPoints, speedBonus, q);
      });
    });

    function showFeedbackModal(isCorrect, earnedPoints, speedBonus, q) {
      const letters = ["A", "B", "C", "D"];
      feedbackExplanation.textContent = q.explanation;

      if (isCorrect) {
        feedbackCard.className = "glass-panel max-w-lg w-full rounded-3xl p-6 sm:p-7 text-center animate-pop-in border-2 border-emerald-400 shadow-[0_0_40px_rgba(52,211,153,0.4)]";
        feedbackIcon.className = "w-16 h-16 rounded-2xl bg-gradient-to-br from-emerald-400 to-teal-600 flex items-center justify-center text-4xl shadow-lg";
        feedbackIcon.textContent = "🌟";
        feedbackTitle.className = "font-display text-2xl sm:text-3xl font-extrabold mb-1 text-emerald-300";
        feedbackTitle.textContent = praises[Math.floor(Math.random() * praises.length)];

        feedbackPoints.className = "inline-block px-4 py-1 rounded-full text-xs sm:text-sm font-extrabold mb-4 bg-emerald-500/25 text-emerald-200 border border-emerald-400/40";
        feedbackPoints.textContent = speedBonus > 0
          ? `+100 Poin Dasar + ${speedBonus} Bonus Cepat = +${earnedPoints} Poin!`
          : `+100 Poin!`;

        correctAnswerBox.classList.add("hidden");
      } else {
        feedbackCard.className = "glass-panel max-w-lg w-full rounded-3xl p-6 sm:p-7 text-center animate-pop-in border-2 border-rose-500 shadow-[0_0_40px_rgba(244,63,94,0.4)]";
        feedbackIcon.className = "w-16 h-16 rounded-2xl bg-gradient-to-br from-rose-500 to-pink-600 flex items-center justify-center text-4xl shadow-lg";
        feedbackIcon.textContent = "💡";
        feedbackTitle.className = "font-display text-2xl sm:text-3xl font-extrabold mb-1 text-rose-300";
        feedbackTitle.textContent = motivations[Math.floor(Math.random() * motivations.length)];

        feedbackPoints.className = "inline-block px-4 py-1 rounded-full text-xs sm:text-sm font-extrabold mb-3 bg-rose-500/25 text-rose-200 border border-rose-400/40";
        feedbackPoints.textContent = "+0 Poin • Ayo Pelajari Jawabannya!";

        correctAnswerBox.classList.remove("hidden");
        correctAnswerText.textContent = `${letters[q.correct]}. ${q.options[q.correct]}`;
      }

      btnNextText.textContent = state.currentIndex === quizData.length - 1 ? "LIHAT HASIL AKHIR" : "LANJUT";
      feedbackModal.classList.remove("hidden");
    }

    // Next Question / Level Transition
    btnNext.addEventListener("click", () => {
      AudioEngine.playClick();
      feedbackModal.classList.add("hidden");

      const nextIndex = state.currentIndex + 1;

      if (nextIndex >= quizData.length) {
        showEndScreen();
        return;
      }

      // Check if transitioning to a new level (index 10 -> Level 2, index 20 -> Level 3)
      const currentLevel = quizData[state.currentIndex].level;
      const nextLevel = quizData[nextIndex].level;

      state.currentIndex = nextIndex;

      if (nextLevel > currentLevel) {
        AudioEngine.playLevelUp();
        levelupHeading.textContent = quizData[nextIndex].levelTitle;
        levelupDesc.textContent = `Hebat, ${state.playerName}! Kamu berhasil menaklukkan Level ${currentLevel}. Sekarang bersiaplah untuk tantangan ${quizData[nextIndex].levelSubtitle}!`;
        levelupModal.classList.remove("hidden");
      } else {
        loadQuestion();
      }
    });

    btnContinueLevel.addEventListener("click", () => {
      AudioEngine.playClick();
      levelupModal.classList.add("hidden");
      loadQuestion();
    });

    // End Screen & Predicate Evaluation
    function showEndScreen() {
      AudioEngine.playVictory();
      gameScreen.classList.add("hidden");
      gameScreen.classList.remove("flex");
      endScreen.classList.remove("hidden");

      const accuracy = Math.round((state.correctCount / quizData.length) * 100);

      document.getElementById("end-student-info").textContent = `${state.playerName} • Kelas ${state.playerClass}`;
      document.getElementById("end-score").textContent = state.score.toLocaleString("id-ID");
      document.getElementById("end-correct").textContent = `${state.correctCount} / ${quizData.length}`;
      document.getElementById("end-accuracy").textContent = `${accuracy}%`;

      const predicateEl = document.getElementById("end-predicate");
      const messageEl = document.getElementById("end-message");
      const trophyEl = document.getElementById("end-trophy");
      const predicateBox = document.getElementById("predicate-box");

      if (accuracy >= 90) {
        trophyEl.textContent = "👑";
        predicateEl.textContent = "MUMTAZ (Istimewa)";
        predicateEl.className = "font-display text-2xl sm:text-4xl font-extrabold text-emerald-300 text-glow-emerald";
        predicateBox.className = "mb-6 p-4 sm:p-5 rounded-2xl bg-emerald-500/20 border-2 border-emerald-400/60";
        messageEl.textContent = `MasyaAllah! ${state.playerName} menguasai materi Akidah Akhlak Semester 1 dengan sangat gemilang!`;
      } else if (accuracy >= 75) {
        trophyEl.textContent = "🏆";
        predicateEl.textContent = "JAYYID JIDDAN (Sangat Baik)";
        predicateEl.className = "font-display text-2xl sm:text-4xl font-extrabold text-amber-300 text-glow-amber";
        predicateBox.className = "mb-6 p-4 sm:p-5 rounded-2xl bg-amber-500/20 border-2 border-amber-400/60";
        messageEl.textContent = `Alhamdulillah! Hasil yang sangat membanggakan, terus pertahankan semangat belajarmu!`;
      } else if (accuracy >= 60) {
        trophyEl.textContent = "🎖️";
        predicateEl.textContent = "JAYYID (Baik)";
        predicateEl.className = "font-display text-2xl sm:text-4xl font-extrabold text-cyan-300 text-glow";
        predicateBox.className = "mb-6 p-4 sm:p-5 rounded-2xl bg-cyan-500/20 border-2 border-cyan-400/60";
        messageEl.textContent = `Bagus! Kamu sudah memahami dasar-dasarnya, ayo ulangi sedikit lagi agar meraih Mumtaz!`;
      } else {
        trophyEl.textContent = "📚";
        predicateEl.textContent = "MAQBUL (Terus Berlatih)";
        predicateEl.className = "font-display text-2xl sm:text-4xl font-extrabold text-pink-300 text-glow";
        predicateBox.className = "mb-6 p-4 sm:p-5 rounded-2xl bg-pink-500/20 border-2 border-pink-400/60";
        messageEl.textContent = `Tetap semangat ${state.playerName}! Coba mainkan kembali dan baca pembahasannya dengan saksama.`;
      }
    }

    // Restart Button
    document.getElementById("btn-restart").addEventListener("click", () => {
      AudioEngine.playClick();
      endScreen.classList.add("hidden");
      startScreen.classList.remove("hidden");
    });
  </script>
</body>
</html>
