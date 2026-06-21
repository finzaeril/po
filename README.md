<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>POPOL MARKET 🇮🇩 - Generator Nomor Unik</title>
  <style>
    :root {
      --bg: #fcfbff;
      --bg-2: #f7f4ff;
      --panel: rgba(255, 255, 255, 0.80);
      --panel-2: rgba(255, 255, 255, 0.92);
      --text: #2a2340;
      --muted: #7c7397;
      --line: rgba(137, 92, 255, 0.12);
      --line-strong: rgba(137, 92, 255, 0.24);
      --primary: #7c4dff;
      --primary-strong: #6a38f0;
      --primary-soft: rgba(124, 77, 255, 0.10);
      --accent: #9d7bff;
      --accent-soft: rgba(157, 123, 255, 0.14);
      --success: #8b5cff;
      --success-soft: rgba(139, 92, 255, 0.14);
      --danger: #e04f6d;
      --danger-soft: rgba(224, 79, 109, 0.12);
      --shadow-sm: 0 10px 24px rgba(92, 65, 170, 0.08);
      --shadow-md: 0 22px 60px rgba(92, 65, 170, 0.12);
      --glow-primary: 0 0 0 1px rgba(124, 77, 255, 0.12), 0 0 26px rgba(124, 77, 255, 0.18);
      --glow-accent: 0 0 0 1px rgba(157, 123, 255, 0.12), 0 0 28px rgba(157, 123, 255, 0.18);
      --radius-lg: 24px;
      --radius-md: 18px;
      --radius-sm: 14px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      min-height: 100vh;
      font-family: Arial, Helvetica, sans-serif;
      color: var(--text);
      background:
        radial-gradient(circle at 10% 12%, rgba(157, 123, 255, 0.16), transparent 22%),
        radial-gradient(circle at 88% 18%, rgba(124, 77, 255, 0.14), transparent 24%),
        radial-gradient(circle at 50% 100%, rgba(186, 164, 255, 0.18), transparent 28%),
        linear-gradient(180deg, var(--bg), var(--bg-2));
      padding: 24px;
      overflow-x: hidden;
      position: relative;
    }

    body::before,
    body::after {
      content: "";
      position: fixed;
      inset: 0;
      pointer-events: none;
      z-index: 0;
    }

    body::before {
      background-image:
        linear-gradient(rgba(124, 77, 255, 0.05) 1px, transparent 1px),
        linear-gradient(90deg, rgba(124, 77, 255, 0.05) 1px, transparent 1px);
      background-size: 44px 44px;
      mask-image: radial-gradient(circle at center, black 45%, transparent 88%);
    }

    body::after {
      background: linear-gradient(90deg, transparent, rgba(124, 77, 255, 0.07), transparent);
      transform: translateX(-100%);
      animation: scanner 9s linear infinite;
      opacity: 0.7;
    }

    @keyframes scanner {
      0% { transform: translateX(-100%); }
      100% { transform: translateX(100%); }
    }

    .app {
      position: relative;
      z-index: 1;
      width: 100%;
      max-width: 1220px;
      margin: 0 auto;
      display: grid;
      grid-template-columns: 1.08fr 0.92fr;
      gap: 22px;
      align-items: start;
    }

    .panel {
      position: relative;
      background: linear-gradient(180deg, rgba(255,255,255,0.82), rgba(250,247,255,0.92));
      border: 1px solid var(--line);
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-md), inset 0 1px 0 rgba(255,255,255,0.9);
      overflow: hidden;
      backdrop-filter: blur(14px);
    }

    .panel::before {
      content: "";
      position: absolute;
      inset: 0;
      background: linear-gradient(135deg, rgba(124,77,255,0.05), transparent 30%, transparent 70%, rgba(157,123,255,0.06));
      pointer-events: none;
    }

    .panel-head,
    .panel-body { position: relative; z-index: 1; }
    .panel-head { padding: 28px 28px 0; }
    .panel-body { padding: 28px; }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-size: 12px;
      font-weight: 800;
      letter-spacing: 1.6px;
      text-transform: uppercase;
      color: #6a38f0;
      margin-bottom: 12px;
      padding: 9px 14px;
      border-radius: 999px;
      background: rgba(124, 77, 255, 0.08);
      border: 1px solid rgba(124, 77, 255, 0.16);
      box-shadow: var(--glow-primary);
    }

    h1 {
      margin: 0 0 12px;
      font-size: 34px;
      line-height: 1.15;
      color: #241c3a;
      letter-spacing: -0.03em;
    }

    .desc,
    .history-sub,
    .note {
      margin: 0;
      color: var(--muted);
      line-height: 1.75;
      font-size: 15px;
    }

    .hero-box {
      position: relative;
      border: 1px solid rgba(124,77,255,0.16);
      background:
        radial-gradient(circle at top right, rgba(157,123,255,0.14), transparent 28%),
        linear-gradient(180deg, rgba(255,255,255,0.90), rgba(248,244,255,0.96));
      border-radius: 22px;
      padding: 24px;
      margin-bottom: 18px;
      overflow: hidden;
      box-shadow: var(--glow-primary), inset 0 1px 0 rgba(255,255,255,0.95);
    }

    .hero-box::before {
      content: "";
      position: absolute;
      inset: -1px;
      border-radius: inherit;
      padding: 1px;
      background: linear-gradient(135deg, rgba(124,77,255,0.30), transparent 40%, rgba(157,123,255,0.28));
      -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0);
      -webkit-mask-composite: xor;
      mask-composite: exclude;
      pointer-events: none;
    }

    .hero-box::after {
      content: "";
      position: absolute;
      top: 0;
      left: -40%;
      width: 36%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.55), transparent);
      transform: skewX(-20deg);
      animation: shine 4.8s infinite;
      pointer-events: none;
    }

    @keyframes shine {
      0% { left: -45%; }
      100% { left: 120%; }
    }

    .hero-label {
      font-size: 13px;
      color: #7f71a8;
      margin-bottom: 12px;
      text-transform: uppercase;
      letter-spacing: 0.08em;
    }

    .hero-number {
      min-height: 44px;
      font-size: 36px;
      font-weight: 700;
      letter-spacing: 2px;
      word-break: break-all;
      color: #5b33cf;
      text-shadow: 0 0 16px rgba(124,77,255,0.14);
    }

    .controls {
      display: grid;
      grid-template-columns: 1fr auto auto;
      gap: 12px;
      margin-bottom: 16px;
    }

    .field {
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .field label {
      font-size: 13px;
      color: #7f71a8;
      font-weight: 700;
    }

    .field input {
      height: 52px;
      border-radius: 15px;
      border: 1px solid var(--line);
      background: rgba(255, 255, 255, 0.92);
      color: var(--text);
      padding: 0 14px;
      outline: none;
      font-size: 15px;
      transition: 0.2s ease;
      box-shadow: inset 0 1px 0 rgba(255,255,255,0.95);
    }

    .field input:focus {
      border-color: rgba(124, 77, 255, 0.35);
      box-shadow: 0 0 0 4px rgba(124, 77, 255, 0.10), 0 0 24px rgba(124, 77, 255, 0.12);
    }

    button {
      height: 52px;
      border-radius: 15px;
      padding: 0 18px;
      font-size: 14px;
      font-weight: 700;
      cursor: pointer;
      transition: 0.2s ease;
      white-space: nowrap;
      border: 1px solid transparent;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 8px;
      position: relative;
      overflow: hidden;
    }

    button::after {
      content: "";
      position: absolute;
      inset: auto auto 0 -40%;
      width: 35%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.28), transparent);
      transform: skewX(-20deg);
      transition: 0.35s ease;
      pointer-events: none;
    }

    button:hover { transform: translateY(-1px); }
    button:hover::after { left: 120%; }

    .btn-primary {
      align-self: end;
      color: #ffffff;
      background: linear-gradient(180deg, #8b5cff, #6f3df2);
      border-color: rgba(124, 77, 255, 0.28);
      box-shadow:
        0 12px 26px rgba(124, 77, 255, 0.24),
        0 0 0 1px rgba(124, 77, 255, 0.10),
        0 0 26px rgba(124, 77, 255, 0.26);
      animation: generateGlow 2.2s ease-in-out infinite alternate;
    }

    .btn-primary:hover {
      filter: brightness(1.05);
      box-shadow:
        0 14px 28px rgba(124, 77, 255, 0.28),
        0 0 0 1px rgba(124, 77, 255, 0.14),
        0 0 34px rgba(124, 77, 255, 0.34);
    }

    @keyframes generateGlow {
      from {
        box-shadow:
          0 10px 22px rgba(124, 77, 255, 0.18),
          0 0 0 1px rgba(124, 77, 255, 0.08),
          0 0 16px rgba(124, 77, 255, 0.14);
      }
      to {
        box-shadow:
          0 14px 28px rgba(124, 77, 255, 0.26),
          0 0 0 1px rgba(124, 77, 255, 0.14),
          0 0 36px rgba(124, 77, 255, 0.30);
      }
    }

    .btn-secondary,
    .btn-soft,
    .copy-btn {
      color: #5a4c84;
      background: rgba(255, 255, 255, 0.78);
      border-color: rgba(137, 92, 255, 0.14);
      box-shadow: inset 0 1px 0 rgba(255,255,255,0.9);
    }

    .btn-secondary:hover,
    .btn-soft:hover,
    .copy-btn:hover {
      background: rgba(248, 244, 255, 0.95);
      border-color: rgba(137, 92, 255, 0.22);
      box-shadow: var(--glow-primary);
    }

    .danger-btn {
      color: #ffffff;
      background: linear-gradient(180deg, #ee6a87, #db4b6c);
      border-color: rgba(224, 79, 109, 0.18);
      box-shadow: 0 10px 24px rgba(224, 79, 109, 0.14);
    }

    .danger-btn:hover {
      box-shadow: 0 0 0 1px rgba(224,79,109,0.12), 0 0 22px rgba(224,79,109,0.12);
    }

    .success-state {
      background: linear-gradient(180deg, #8b5cff, #6f3df2) !important;
      border-color: rgba(124, 77, 255, 0.28) !important;
      color: #ffffff !important;
      box-shadow: 0 0 0 1px rgba(124,77,255,0.12), 0 0 24px rgba(124,77,255,0.24) !important;
    }

    .info-box {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 12px;
      margin-top: 8px;
    }

    .mini-card {
      position: relative;
      border: 1px solid var(--line);
      border-radius: 18px;
      padding: 16px;
      background: linear-gradient(180deg, rgba(255,255,255,0.88), rgba(250,247,255,0.95));
      box-shadow: var(--shadow-sm);
      overflow: hidden;
    }

    .mini-card::before {
      content: "";
      position: absolute;
      inset: 0 auto auto 0;
      width: 100%;
      height: 2px;
      background: linear-gradient(90deg, #8b5cff, #b28cff, transparent);
      opacity: 0.9;
    }

    .mini-card .label {
      color: #7f71a8;
      font-size: 12px;
      margin-bottom: 8px;
      text-transform: uppercase;
      letter-spacing: 0.05em;
    }

    .mini-card .value {
      font-size: 22px;
      font-weight: 700;
      color: #2f2550;
      word-break: break-word;
    }

    .footer-actions {
      display: flex;
      gap: 12px;
      margin-top: 16px;
      flex-wrap: wrap;
    }

    .note {
      margin-top: 14px;
      font-size: 13px;
    }

    .note strong { color: #5936c4; }

    .history-title {
      margin: 0 0 8px;
      font-size: 22px;
      color: #241c3a;
    }

    .history-sub {
      margin: 0 0 18px;
      font-size: 14px;
    }

    .history-wrap {
      max-height: 680px;
      overflow: auto;
      padding-right: 4px;
      scroll-behavior: smooth;
    }

    .history-wrap::-webkit-scrollbar { width: 10px; }
    .history-wrap::-webkit-scrollbar-track { background: transparent; }
    .history-wrap::-webkit-scrollbar-thumb {
      background: linear-gradient(180deg, rgba(124, 77, 255, 0.45), rgba(157, 123, 255, 0.40));
      border-radius: 999px;
    }

    .history-empty {
      border: 1px dashed var(--line-strong);
      border-radius: 18px;
      padding: 26px;
      text-align: center;
      color: var(--muted);
      background: rgba(255, 255, 255, 0.66);
    }

    .history-item {
      position: relative;
      display: grid;
      grid-template-columns: 1fr auto;
      gap: 14px;
      align-items: center;
      padding: 14px;
      border: 1px solid rgba(137, 92, 255, 0.12);
      border-radius: 18px;
      margin-bottom: 12px;
      background: linear-gradient(180deg, rgba(255,255,255,0.88), rgba(249,246,255,0.96));
      box-shadow: var(--shadow-sm);
      transition: 0.25s ease;
      overflow: hidden;
    }

    .history-item::before {
      content: "";
      position: absolute;
      inset: 0 auto 0 0;
      width: 2px;
      background: linear-gradient(180deg, #8b5cff, #b28cff);
      opacity: 0.85;
    }

    .history-item:hover {
      border-color: rgba(124, 77, 255, 0.22);
      transform: translateY(-1px);
      box-shadow: var(--shadow-sm), var(--glow-primary);
    }

    .history-item.new-item {
      animation: pulseNew 1.1s ease;
      box-shadow: var(--shadow-sm), var(--glow-accent);
    }

    @keyframes pulseNew {
      0% { transform: translateY(8px); opacity: 0.3; }
      45% { opacity: 1; }
      100% { transform: translateY(0); }
    }

    .history-left { min-width: 0; }

    .history-top {
      display: flex;
      align-items: center;
      gap: 10px;
      margin-bottom: 8px;
      flex-wrap: wrap;
    }

    .history-index {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 40px;
      height: 40px;
      border-radius: 999px;
      font-size: 14px;
      font-weight: 700;
      color: #ffffff;
      background: linear-gradient(180deg, #8b5cff, #6f3df2);
      flex: 0 0 40px;
      box-shadow: 0 0 18px rgba(124,77,255,0.22);
    }

    .history-badge {
      display: inline-block;
      font-size: 12px;
      color: #7b6e9d;
      border: 1px solid var(--line);
      border-radius: 999px;
      padding: 7px 10px;
      background: rgba(255,255,255,0.75);
    }

    .history-number {
      font-size: 18px;
      font-weight: 700;
      color: #4f2fc0;
      letter-spacing: 1px;
      word-break: break-all;
      line-height: 1.55;
      text-shadow: 0 0 12px rgba(124,77,255,0.08);
    }

    .history-meta {
      margin-top: 8px;
      font-size: 12px;
      color: var(--muted);
    }

    /* tombol copy kecil */
    .copy-btn {
      min-width: 64px;
      height: 34px;
      padding: 0 10px;
      font-size: 11px;
      border-radius: 10px;
      font-weight: 700;
    }

    .copy-btn .btn-icon {
      width: 13px;
      height: 13px;
      flex: 0 0 13px;
    }

    #copyLatestBtn {
      height: 44px;
      padding: 0 14px;
      font-size: 13px;
      border-radius: 12px;
    }

    .btn-icon {
      width: 16px;
      height: 16px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      flex: 0 0 16px;
    }

    .toast-wrap {
      position: fixed;
      right: 22px;
      bottom: 22px;
      z-index: 9999;
      display: flex;
      flex-direction: column;
      gap: 10px;
      pointer-events: none;
    }

    .toast {
      min-width: 260px;
      max-width: 360px;
      background: rgba(255, 255, 255, 0.92);
      color: var(--text);
      border: 1px solid rgba(124, 77, 255, 0.16);
      border-radius: 16px;
      box-shadow: var(--shadow-md), var(--glow-accent);
      padding: 14px 16px;
      display: flex;
      align-items: center;
      gap: 12px;
      opacity: 0;
      transform: translateY(12px) scale(0.98);
      animation: toastIn 0.28s ease forwards;
      backdrop-filter: blur(12px);
    }

    .toast-icon {
      width: 34px;
      height: 34px;
      border-radius: 999px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      background: var(--success-soft);
      color: var(--success);
      flex: 0 0 34px;
      box-shadow: 0 0 18px rgba(139,92,255,0.14);
    }

    .toast-title {
      font-size: 14px;
      font-weight: 700;
      color: #241c3a;
      margin-bottom: 2px;
    }

    .toast-text {
      font-size: 13px;
      color: #6e648d;
      line-height: 1.45;
      word-break: break-word;
    }

    @keyframes toastIn {
      to { opacity: 1; transform: translateY(0) scale(1); }
    }

    .toast.hide { animation: toastOut 0.22s ease forwards; }

    @keyframes toastOut {
      to { opacity: 0; transform: translateY(10px) scale(0.98); }
    }

    @media (max-width: 920px) {
      body { padding: 14px; }

      /* dua panel tetap menumpuk, tapi jarak lebih rapat */
      .app {
        grid-template-columns: 1fr;
        gap: 16px;
      }

      .panel-head { padding: 20px 18px 0; }
      .panel-body { padding: 18px; }

      h1 { font-size: 26px; }

      /* nomor besar dikecilkan agar tidak patah ke banyak baris */
      .hero-box { padding: 18px; }
      .hero-number { font-size: 24px; letter-spacing: 1px; }

      /* input penuh di atas, dua tombol berbagi ruang sejajar ke samping */
      .controls {
        grid-template-columns: 1fr 1fr;
        gap: 10px;
      }
      .controls .field { grid-column: 1 / -1; }
      .btn-primary,
      .btn-secondary { width: 100%; }

      /* kartu info TETAP 3 kolom sejajar agar melebar rata ke samping */
      .info-box {
        grid-template-columns: repeat(3, 1fr);
        gap: 8px;
      }
      .mini-card { padding: 12px; }
      .mini-card .value { font-size: 16px; }

      /* tombol bawah sejajar berdampingan, bukan menumpuk */
      .footer-actions { flex-wrap: nowrap; }
      .btn-soft,
      .danger-btn {
        flex: 1;
        width: auto;
      }

      /* item riwayat: nomor di kiri, tombol Copy tetap di kanan */
      .history-item { grid-template-columns: 1fr auto; }

      .toast-wrap { left: 16px; right: 16px; bottom: 16px; }
      .toast { min-width: 0; max-width: none; width: 100%; }
    }
  </style>
</head>
<body>
  <div class="app">
    <section class="panel">
      <div class="panel-head">
        <span class="eyebrow">POPOL MARKET 🇮🇩</span>
        <h1>Generator Nomor Unik</h1>
        <p class="desc">
          Sistem ini membuat nomor unik 16 digit secara lokal langsung dari browser tanpa database eksternal.
          Setiap nomor benar-benar acak dan hanya muncul satu kali selamanya.
        </p>
      </div>

      <div class="panel-body">
        <div class="hero-box">
          <div class="hero-label">Nomor terakhir yang dibuat</div>
          <div class="hero-number" id="latestNumber">Belum ada nomor</div>
        </div>

        <div class="controls">
          <div class="field">
            <label for="jumlahGenerate">Jumlah nomor per generate</label>
            <input id="jumlahGenerate" type="number" min="1" max="50" value="5" />
          </div>

          <button class="btn-primary" id="generateBtn">
            <span class="btn-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" width="16" height="16" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M12 5v14M5 12h14"></path>
              </svg>
            </span>
            Generate
          </button>

          <button class="btn-secondary" id="copyLatestBtn">
            <span class="btn-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" width="16" height="16" fill="none" stroke="currentColor" stroke-width="2">
                <rect x="9" y="9" width="10" height="10" rx="2"></rect>
                <path d="M5 15V7a2 2 0 0 1 2-2h8"></path>
              </svg>
            </span>
            Copy Terakhir
          </button>
        </div>

        <div class="info-box">
          <div class="mini-card">
            <div class="label">Total nomor tersimpan</div>
            <div class="value" id="totalData">0</div>
          </div>

          <div class="mini-card">
            <div class="label">Urutan pertama</div>
            <div class="value" id="firstNumberLabel">-</div>
          </div>

          <div class="mini-card">
            <div class="label">Urutan terakhir</div>
            <div class="value" id="lastNumberLabel">-</div>
          </div>
        </div>

        <div class="footer-actions">
          <button class="btn-soft" id="copyAllBtn">
            <span class="btn-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" width="16" height="16" fill="none" stroke="currentColor" stroke-width="2">
                <rect x="9" y="9" width="10" height="10" rx="2"></rect>
                <path d="M5 15V7a2 2 0 0 1 2-2h8"></path>
              </svg>
            </span>
            Copy Semua
          </button>

          <button class="danger-btn" id="clearBtn">
            <span class="btn-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" width="16" height="16" fill="none" stroke="currentColor" stroke-width="2">
                <path d="M3 6h18"></path>
                <path d="M8 6V4h8v2"></path>
                <path d="M19 6l-1 14H6L5 6"></path>
              </svg>
            </span>
            Hapus Semua
          </button>
        </div>

        <p class="note">
          <strong>Catatan:</strong> setiap nomor dibuat 100% acak merata (crypto) dan dicatat permanen,
          sehingga sebuah nomor hanya muncul satu kali selamanya dan tidak akan pernah keluar lagi —
          bahkan setelah daftar dihapus.
        </p>
      </div>
    </section>

    <section class="panel">
      <div class="panel-head">
        <h2 class="history-title">Riwayat Nomor</h2>
        <p class="history-sub">
          Semua nomor yang dihasilkan akan muncul di sini. Kamu bisa menyalin satuan atau menyalin nomor terakhir.
        </p>
      </div>

      <div class="panel-body">
        <div class="history-wrap" id="historyWrap">
          <div class="history-empty" id="emptyState">
            Belum ada data nomor. Klik tombol <strong>Generate</strong> untuk mulai membuat nomor unik.
          </div>
          <div id="historyList"></div>
        </div>
      </div>
    </section>
  </div>

  <div class="toast-wrap" id="toastWrap"></div>

  <script>
    const STORAGE_KEY = "popol_market_unique_numbers_v2";
    // ledger permanen: menyimpan SEMUA nomor yang pernah dibuat (tidak ikut terhapus)
    const USED_KEY = "popol_market_used_numbers_permanent_v1";
    const NUMBER_LENGTH = 16; // panjang digit tiap nomor

    const latestNumberEl = document.getElementById("latestNumber");
    const totalDataEl = document.getElementById("totalData");
    const firstNumberLabelEl = document.getElementById("firstNumberLabel");
    const lastNumberLabelEl = document.getElementById("lastNumberLabel");
    const jumlahGenerateEl = document.getElementById("jumlahGenerate");
    const generateBtn = document.getElementById("generateBtn");
    const copyLatestBtn = document.getElementById("copyLatestBtn");
    const copyAllBtn = document.getElementById("copyAllBtn");
    const clearBtn = document.getElementById("clearBtn");
    const historyListEl = document.getElementById("historyList");
    const emptyStateEl = document.getElementById("emptyState");
    const toastWrapEl = document.getElementById("toastWrap");

    let numbers = loadNumbers();
    let usedNumbers = loadUsedNumbers(); // Set berisi semua nomor yang pernah ada

    function loadNumbers() {
      try {
        const raw = localStorage.getItem(STORAGE_KEY);
        const parsed = raw ? JSON.parse(raw) : [];
        return Array.isArray(parsed) ? parsed : [];
      } catch {
        return [];
      }
    }

    function saveNumbers() {
      localStorage.setItem(STORAGE_KEY, JSON.stringify(numbers));
    }

    function loadUsedNumbers() {
      try {
        const raw = localStorage.getItem(USED_KEY);
        const parsed = raw ? JSON.parse(raw) : [];
        const set = new Set(Array.isArray(parsed) ? parsed : []);
        // pastikan nomor yang sedang tampil juga tercatat
        loadNumbers().forEach(item => set.add(item.value));
        return set;
      } catch {
        return new Set();
      }
    }

    function saveUsedNumbers() {
      localStorage.setItem(USED_KEY, JSON.stringify([...usedNumbers]));
    }

    function formatDateTime(dateString) {
      const date = new Date(dateString);
      return date.toLocaleString("id-ID", {
        day: "2-digit",
        month: "2-digit",
        year: "numeric",
        hour: "2-digit",
        minute: "2-digit",
        second: "2-digit"
      });
    }

    // hasilkan deret digit ACAK merata (crypto), tanpa bias, tanpa berbasis waktu
    function randomDigits(length) {
      let result = "";
      const cryptoObj = window.crypto || window.msCrypto;

      if (cryptoObj && cryptoObj.getRandomValues) {
        while (result.length < length) {
          const arr = new Uint8Array(length);
          cryptoObj.getRandomValues(arr);
          for (let i = 0; i < arr.length && result.length < length; i++) {
            // buang 250-255 untuk menghilangkan bias modulo → 0-9 merata
            if (arr[i] < 250) {
              result += (arr[i] % 10).toString();
            }
          }
        }
      } else {
        for (let i = 0; i < length; i++) {
          result += Math.floor(Math.random() * 10).toString();
        }
      }

      // pastikan digit pertama bukan 0
      if (result[0] === "0") {
        result = (1 + Math.floor(Math.random() * 9)).toString() + result.slice(1);
      }

      return result;
    }

    // buat nomor yang belum pernah ada (cek terhadap ledger permanen)
    function createUniqueNumber(sessionSet) {
      let candidate = "";
      do {
        candidate = randomDigits(NUMBER_LENGTH);
      } while (sessionSet.has(candidate) || usedNumbers.has(candidate));
      return candidate;
    }

    function renderStats() {
      totalDataEl.textContent = numbers.length;
      firstNumberLabelEl.textContent = numbers.length ? "1" : "-";
      lastNumberLabelEl.textContent = numbers.length ? String(numbers.length) : "-";
      latestNumberEl.textContent = numbers.length ? numbers[numbers.length - 1].value : "Belum ada nomor";
      emptyStateEl.style.display = numbers.length ? "none" : "block";
    }

    function renderHistory(highlightCount = 0) {
      historyListEl.innerHTML = "";

      numbers.forEach((item, index) => {
        const originalIndex = index + 1;
        const isNew = index >= numbers.length - highlightCount;

        const row = document.createElement("div");
        row.className = "history-item" + (isNew ? " new-item" : "");

        row.innerHTML = `
          <div class="history-left">
            <div class="history-top">
              <div class="history-index">${originalIndex}</div>
              <div class="history-badge">Nomor unik</div>
            </div>
            <div class="history-number">${item.value}</div>
            <div class="history-meta">Dibuat: ${formatDateTime(item.createdAt)}</div>
          </div>

          <button class="copy-btn" data-copy="${item.value}">
            <span class="btn-icon" aria-hidden="true">
              <svg viewBox="0 0 24 24" width="13" height="13" fill="none" stroke="currentColor" stroke-width="2">
                <rect x="9" y="9" width="10" height="10" rx="2"></rect>
                <path d="M5 15V7a2 2 0 0 1 2-2h8"></path>
              </svg>
            </span>
            Copy
          </button>
        `;

        historyListEl.appendChild(row);
      });
    }

    function renderAll(highlightCount = 0) {
      renderStats();
      renderHistory(highlightCount);
    }

    async function copyText(text, button, successLabel = "Copied") {
      try {
        await navigator.clipboard.writeText(text);

        if (button) {
          const original = button.dataset.originalLabel || button.innerHTML;
          button.dataset.originalLabel = original;
          button.classList.add("success-state");
          button.textContent = successLabel;

          clearTimeout(button._copyTimer);
          button._copyTimer = setTimeout(() => {
            button.classList.remove("success-state");
            button.innerHTML = original;
          }, 1400);
        }

        showToast("Berhasil disalin", text);
      } catch {
        showToast("Gagal menyalin", "Clipboard tidak tersedia di browser ini.");
      }
    }

    function showToast(title, text) {
      const toast = document.createElement("div");
      toast.className = "toast";
      toast.innerHTML = `
        <div class="toast-icon">
          <svg viewBox="0 0 24 24" width="18" height="18" fill="none" stroke="currentColor" stroke-width="2">
            <path d="M20 6L9 17l-5-5"></path>
          </svg>
        </div>
        <div>
          <div class="toast-title">${title}</div>
          <div class="toast-text">${text}</div>
        </div>
      `;

      toastWrapEl.appendChild(toast);

      setTimeout(() => {
        toast.classList.add("hide");
        setTimeout(() => toast.remove(), 220);
      }, 2200);
    }

    function generateNumbers() {
      const count = Number(jumlahGenerateEl.value);

      if (!Number.isInteger(count) || count < 1 || count > 50) {
        showToast("Input tidak valid", "Masukkan jumlah generate antara 1 sampai 50.");
        jumlahGenerateEl.focus();
        return;
      }

      const sessionSet = new Set(); // mencegah duplikat dalam batch yang sama
      const newItems = [];

      for (let i = 0; i < count; i++) {
        const value = createUniqueNumber(sessionSet);
        sessionSet.add(value);
        usedNumbers.add(value); // catat permanen → tak akan muncul lagi selamanya
        newItems.push({
          value,
          createdAt: new Date().toISOString()
        });
      }

      numbers = [...numbers, ...newItems];
      saveNumbers();
      saveUsedNumbers();
      renderAll(newItems.length);
      showToast("Nomor berhasil dibuat", `${newItems.length} nomor unik acak berhasil digenerate.`);
    }

    function copyLatest() {
      if (!numbers.length) {
        showToast("Belum ada nomor", "Generate nomor terlebih dahulu.");
        return;
      }
      const latest = numbers[numbers.length - 1].value;
      copyText(latest, copyLatestBtn, "Copied");
    }

    function copyAll() {
      if (!numbers.length) {
        showToast("Belum ada data", "Tidak ada nomor untuk disalin.");
        return;
      }
      const allText = numbers.map(item => item.value).join("\n");
      copyText(allText, copyAllBtn, "Copied");
    }

    function clearAll() {
      if (!numbers.length) {
        showToast("Kosong", "Tidak ada data untuk dihapus.");
        return;
      }

      const confirmed = confirm("Hapus daftar tampilan? Nomor yang sudah pernah dibuat tetap tidak akan muncul lagi.");
      if (!confirmed) return;

      // hanya kosongkan daftar tampilan; ledger permanen TETAP tersimpan
      numbers = [];
      saveNumbers();
      renderAll();
      showToast("Data dihapus", "Daftar dikosongkan. Nomor lama tetap tidak akan terulang.");
    }

    generateBtn.addEventListener("click", generateNumbers);
    copyLatestBtn.addEventListener("click", copyLatest);
    copyAllBtn.addEventListener("click", copyAll);
    clearBtn.addEventListener("click", clearAll);

    historyListEl.addEventListener("click", (event) => {
      const button = event.target.closest(".copy-btn");
      if (!button) return;
      const value = button.getAttribute("data-copy");
      if (!value) return;
      copyText(value, button, "Copied");
    });

    jumlahGenerateEl.addEventListener("keydown", (event) => {
      if (event.key === "Enter") {
        generateNumbers();
      }
    });

    renderAll();
  </script>
</body>
</html>
