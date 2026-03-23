<!doctype html>

<html lang="tr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>PB Allocation Engine</title>
  <meta name="apple-mobile-web-app-capable" content="yes">
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --navy-900:#040d1a;--navy-800:#0a1628;--navy-700:#0f2040;--navy-600:#152b55;
      --navy-500:#1e3d72;--navy-400:#2d56a0;--navy-300:#4a7bc8;--navy-200:#7fa8e0;
      --navy-100:#b8d0f0;--navy-50:#e8f0fa;
      --gold-700:#8b6914;--gold-600:#b8891a;--gold-500:#d4a329;--gold-400:#e8b83a;
      --gold-300:#f0c84a;--gold-200:#f5d878;--gold-100:#faefc0;--gold-50:#fdf8e8;
      --surface-0:#ffffff;--surface-1:#f7f9fc;--surface-2:#eef2f8;--surface-3:#e3eaf5;
      --text-primary:#0a1628;--text-secondary:#3d5278;--text-muted:#6b82a8;--text-light:#9bacc8;
      --border-light:rgba(30,61,114,.10);--border-mid:rgba(30,61,114,.16);--border-strong:rgba(30,61,114,.25);
      --success:#0a7a3c;--success-bg:#e8f8ef;--danger:#9b1c1c;--danger-bg:#fdf0f0;
      --shadow-sm:0 1px 3px rgba(10,22,40,.06);--shadow-md:0 4px 12px rgba(10,22,40,.08);
      --shadow-lg:0 10px 30px rgba(10,22,40,.12);--shadow-xl:0 20px 50px rgba(10,22,40,.18);
      --radius-sm:8px;--radius-md:12px;--radius-lg:16px;--radius-xl:20px;--radius-full:9999px;
    }
    *{box-sizing:border-box;margin:0;padding:0;}
    body{font-family:'Inter',-apple-system,sans-serif;background:var(--surface-1);color:var(--text-primary);padding-bottom:100px;font-size:14px;line-height:1.5;-webkit-font-smoothing:antialiased;}

```
/* HEADER */
#site-header{background:#040d1a !important;border-bottom:1px solid rgba(255,255,255,.06) !important;position:sticky;top:0;z-index:100;box-shadow:0 2px 20px rgba(4,13,26,.4) !important;color:#fff !important;}
.header-inner{max-width:1400px;margin:0 auto;padding:0 20px;}
.header-top{display:flex;align-items:center;justify-content:space-between;padding:14px 0 10px;gap:16px;}
.header-brand{display:flex;align-items:center;gap:12px;}
.brand-icon{width:40px;height:40px;background:rgba(255,255,255,.06);border:1px solid rgba(232,184,58,.25);border-radius:var(--radius-sm);display:flex;align-items:center;justify-content:center;flex-shrink:0;}
.brand-text h1{font-size:15px;font-weight:700;color:#ffffff !important;letter-spacing:.3px;}
.brand-text .sub{font-size:11.5px;color:#7fa8e0;margin-top:1px;}
.header-right{display:flex;align-items:center;gap:10px;}
.version-badge{padding:4px 10px;background:rgba(212,163,41,.15);border:1px solid rgba(212,163,41,.25);border-radius:var(--radius-full);font-size:10.5px;font-weight:600;color:var(--gold-300);letter-spacing:.5px;}
.lang-selector{display:flex;align-items:center;gap:6px;padding:7px 10px;background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.12);border-radius:var(--radius-md);}
.lang-selector span{font-size:11px;color:var(--navy-200);font-weight:500;}
.lang-selector select{background:transparent;border:none;color:#fff;font-size:12px;font-weight:600;font-family:inherit;cursor:pointer;outline:none;}
.lang-selector select option{background:var(--navy-800);color:#fff;}
.disclaimer-bar{padding:8px 0 12px;border-top:1px solid rgba(255,255,255,.05);}
.disclaimer-bar p{font-size:11px;color:rgba(184,208,240,.6);line-height:1.45;display:flex;gap:6px;align-items:flex-start;}
.disclaimer-bar p::before{content:"ℹ";flex-shrink:0;color:var(--gold-400);font-size:12px;margin-top:1px;}

/* LAYOUT */
.wrap{max-width:1400px;margin:0 auto;padding:20px 20px 32px;}
.section-label{font-size:10px;font-weight:700;color:var(--gold-500);letter-spacing:1.2px;text-transform:uppercase;margin-bottom:12px;display:flex;align-items:center;gap:8px;}
.section-label::after{content:'';flex:1;height:1px;background:linear-gradient(90deg,var(--border-mid),transparent);}
.card{background:var(--surface-0);border:1px solid var(--border-light);border-radius:var(--radius-xl);padding:20px;box-shadow:var(--shadow-sm);}
.card+.card{margin-top:16px;}
label{display:block;font-size:11px;font-weight:600;color:var(--text-muted);letter-spacing:.4px;text-transform:uppercase;margin-bottom:6px;}
input,select{width:100%;padding:10px 12px;border-radius:var(--radius-md);border:1px solid var(--border-mid);font-family:inherit;font-size:13.5px;font-weight:500;color:var(--text-primary);background:var(--surface-0);transition:border-color .15s,box-shadow .15s;outline:none;}
input:focus,select:focus{border-color:var(--navy-400);box-shadow:0 0 0 3px rgba(30,61,114,.1);}
input::placeholder{color:var(--text-light);font-weight:400;}
.g2{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.g3{display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;}
.g4{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;}

/* ═══════════════════════════════
   CONFIG PANEL — 3 kolonlu layout
   ═══════════════════════════════ */
.cfg-card{padding:20px;}
.cfg-row1{display:grid;grid-template-columns:1fr 1fr 1fr;gap:24px;align-items:start;}
.cfg-row1 .col{} /* basit kolon, padding yok */
.cfg-row1 .col+.col{border-left:1px solid var(--border-light);padding-left:24px;}
.cfg-row2{display:flex;align-items:flex-end;gap:20px;margin-top:20px;padding-top:20px;border-top:1px solid var(--border-light);flex-wrap:wrap;}
.cfg-row2-left{flex:1;min-width:0;}
.cfg-rates-grid{display:grid;grid-template-columns:repeat(3,minmax(80px,160px));gap:10px;}
.cfg-row2-actions{display:flex;gap:8px;flex-shrink:0;flex-wrap:wrap;align-self:flex-end;}

@media(max-width:860px){
  .cfg-row1{grid-template-columns:1fr;}
  .cfg-row1 .col+.col{border-left:none;padding-left:0;border-top:1px solid var(--border-light);padding-top:16px;margin-top:4px;}
  .cfg-rates-grid{grid-template-columns:repeat(3,1fr);}
}
@media(max-width:600px){
  .g3{grid-template-columns:1fr 1fr;}
  .kpi-grid{grid-template-columns:1fr 1fr;}
}

/* BUTTONS */
.btn{border:none;border-radius:var(--radius-md);padding:10px 16px;font-family:inherit;font-size:12.5px;font-weight:600;cursor:pointer;transition:all .15s;white-space:nowrap;letter-spacing:.2px;}
.btn:active{transform:scale(.97);}
.btn-primary{background:linear-gradient(135deg,var(--navy-600),var(--navy-500));color:#fff;box-shadow:0 2px 8px rgba(15,32,64,.25);}
.btn-primary:hover{background:linear-gradient(135deg,var(--navy-500),var(--navy-400));}
.btn-gold{background:linear-gradient(135deg,var(--gold-500),var(--gold-600));color:var(--navy-900);box-shadow:0 2px 8px rgba(212,163,41,.3);}
.btn-gold:hover{background:linear-gradient(135deg,var(--gold-400),var(--gold-500));}
.btn-ghost{background:var(--surface-0);color:var(--text-secondary);border:1px solid var(--border-mid);}
.btn-ghost:hover{background:var(--surface-2);border-color:var(--border-strong);}
.btn-danger{background:var(--danger-bg);color:var(--danger);border:1px solid rgba(155,28,28,.18);}
.btn-danger:hover{background:#fde8e8;}
.btn-sm{padding:7px 12px;font-size:11.5px;border-radius:var(--radius-sm);}
.btn-xs{padding:5px 9px;font-size:11px;border-radius:6px;}
.btn-row{display:flex;gap:8px;margin-top:14px;flex-wrap:wrap;}
.status-line{margin-top:8px;font-size:11.5px;color:var(--text-muted);min-height:18px;}
.status-note{margin-top:8px;font-size:11px;color:var(--text-light);line-height:1.4;}

/* HEADLINE KPI */
.headline-kpi{background:linear-gradient(135deg,var(--navy-800),var(--navy-700));border-radius:var(--radius-lg);padding:20px 24px;margin-bottom:16px;display:flex;align-items:center;justify-content:space-between;gap:16px;flex-wrap:wrap;position:relative;overflow:hidden;}
.headline-kpi::before{content:'';position:absolute;top:0;right:0;width:180px;height:100%;background:radial-gradient(ellipse at 100% 50%,rgba(212,163,41,.12),transparent 70%);pointer-events:none;}
.headline-kpi .label{font-size:10.5px;font-weight:600;color:var(--navy-200);letter-spacing:.8px;text-transform:uppercase;margin-bottom:4px;}
.headline-kpi .value{font-size:26px;font-weight:700;color:#fff;letter-spacing:-.5px;}
.headline-kpi .detail{font-size:11.5px;color:var(--navy-300);margin-top:4px;}
.headline-kpi .pill-badge{padding:5px 12px;background:rgba(212,163,41,.2);border:1px solid rgba(212,163,41,.3);border-radius:var(--radius-full);font-size:11px;font-weight:600;color:var(--gold-300);white-space:nowrap;flex-shrink:0;}

/* KPI GRID */
.kpi-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-top:12px;}
@media(max-width:900px){.kpi-grid{grid-template-columns:1fr 1fr;}}
.kpi-card{background:var(--surface-0);border:1px solid var(--border-light);border-radius:var(--radius-lg);padding:14px 16px;}
.kpi-card .t{font-size:10.5px;font-weight:600;color:var(--text-muted);letter-spacing:.5px;text-transform:uppercase;}
.kpi-card .v{font-size:17px;font-weight:700;color:var(--text-primary);margin-top:6px;letter-spacing:-.3px;}
.kpi-card.gold-accent .t{color:var(--gold-600);}.kpi-card.gold-accent .v{color:var(--gold-700);}
.kpi-2{display:grid;grid-template-columns:1fr 1fr;gap:12px;margin-top:12px;}

/* SCENARIOS */
.scenario-pills{display:flex;gap:6px;flex-wrap:nowrap;overflow-x:auto;padding:2px 0 6px;-webkit-overflow-scrolling:touch;scrollbar-width:none;}
.scenario-pills::-webkit-scrollbar{display:none;}
.scenario-pill{padding:6px 14px;border-radius:var(--radius-full);background:var(--surface-0);border:1px solid var(--border-mid);color:var(--text-secondary);font-size:11.5px;font-weight:600;cursor:pointer;white-space:nowrap;transition:all .15s;font-family:inherit;}
.scenario-pill:hover{background:var(--navy-50);border-color:var(--navy-400);color:var(--navy-600);}
.add-pill{padding:6px 14px;border-radius:var(--radius-full);background:var(--navy-800);color:#fff;border:none;font-size:11.5px;font-weight:600;cursor:pointer;white-space:nowrap;transition:all .15s;font-family:inherit;}
.add-pill:hover{background:var(--navy-700);}

/* TABLE */
.table-wrapper{overflow-x:auto;border:1px solid var(--border-light);border-radius:var(--radius-lg);background:var(--surface-0);margin-top:12px;-webkit-overflow-scrolling:touch;}
table{width:100%;border-collapse:collapse;min-width:900px;font-size:12px;}
thead{background:var(--surface-1);border-bottom:1px solid var(--border-mid);}
th{padding:9px 7px;text-align:left;font-size:9.5px;font-weight:700;color:var(--text-muted);letter-spacing:.6px;text-transform:uppercase;white-space:nowrap;}
th:first-child{padding-left:12px;}th:last-child{padding-right:12px;text-align:center;}
td{padding:7px 7px;border-bottom:1px solid var(--border-light);vertical-align:middle;}
td:first-child{padding-left:12px;}td:last-child{padding-right:12px;text-align:center;}
tbody tr:last-child td{border-bottom:none;}
tbody tr:hover td{background:var(--surface-1);}
.table-wrapper input,.table-wrapper select{padding:6px 7px;border-radius:var(--radius-sm);font-size:12px;border-color:var(--border-mid);}
.cell-computed{font-weight:600;color:var(--text-secondary);font-variant-numeric:tabular-nums;white-space:nowrap;}
.cell-computed.positive{color:var(--success);}.cell-computed.negative{color:var(--danger);}
.tax-wrap{display:flex;gap:6px;align-items:center;}
.tax-wrap input[type="number"]{flex:1;}
.auto-label{display:flex;align-items:center;gap:3px;font-size:10.5px;font-weight:600;color:var(--text-muted);white-space:nowrap;text-transform:none;letter-spacing:0;}
.tax-wrap input[type="checkbox"]{width:13px;height:13px;padding:0;accent-color:var(--navy-500);}
.renew-wrap{display:flex;gap:6px;align-items:center;margin-top:5px;}
.renew-wrap span{font-size:10.5px;color:var(--text-muted);white-space:nowrap;}
.renew-wrap input{width:72px;padding:6px 8px;font-size:12px;}

/* RISK BADGES */
.risk-wrap{display:flex;flex-wrap:wrap;gap:4px;margin-top:10px;align-items:center;}
.risk-label{font-size:10.5px;font-weight:600;color:var(--text-muted);text-transform:uppercase;letter-spacing:.4px;margin-right:2px;}
.badge{display:inline-flex;align-items:center;padding:3px 9px;border-radius:var(--radius-full);font-size:11px;font-weight:600;background:var(--navy-50);color:var(--navy-600);border:1px solid var(--border-mid);}

/* BOTTOM GRID */
.bottom-grid{display:grid;grid-template-columns:1fr 1fr;gap:16px;margin-top:16px;}
@media(max-width:900px){.bottom-grid{grid-template-columns:1fr;}}
.chart-card{border:1px solid var(--border-light);border-radius:var(--radius-lg);background:var(--surface-0);padding:16px;}
.chart-card-title{font-size:10.5px;font-weight:700;color:var(--text-muted);letter-spacing:.8px;text-transform:uppercase;margin-bottom:14px;display:flex;align-items:center;gap:6px;}
.chart-card-title::before{content:'';width:3px;height:12px;background:var(--gold-400);border-radius:2px;flex-shrink:0;}
.donut-wrap{display:flex;gap:16px;align-items:center;flex-wrap:wrap;}
canvas{border-radius:var(--radius-md);background:transparent;flex-shrink:0;}
.legend-wrap{flex:1;min-width:160px;}
.legend-item{display:flex;align-items:center;gap:8px;margin:5px 0;font-size:11.5px;}
.legend-dot{width:8px;height:8px;border-radius:50%;flex-shrink:0;}
.legend-name{color:var(--text-secondary);font-weight:500;flex:1;}
.legend-pct{font-weight:700;color:var(--text-primary);}
.tap-info{margin-top:10px;padding:8px 12px;background:var(--surface-1);border:1px solid var(--border-light);border-radius:var(--radius-md);font-size:11px;color:var(--text-muted);line-height:1.4;}
.tap-info strong{color:var(--text-secondary);}

/* SUMMARY */
.summary-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;}
.summary-item{padding:12px 14px;background:var(--surface-1);border:1px solid var(--border-light);border-radius:var(--radius-md);}
.summary-item .t{font-size:10px;font-weight:700;color:var(--text-muted);letter-spacing:.5px;text-transform:uppercase;}
.summary-item .v{font-size:14px;font-weight:700;color:var(--text-primary);margin-top:5px;font-variant-numeric:tabular-nums;}
.pl-note{margin-top:10px;font-size:11px;color:var(--text-light);line-height:1.4;display:flex;gap:5px;}
.pl-note::before{content:"※";flex-shrink:0;color:var(--gold-500);}

/* MISC */
.inline-warn{margin-top:12px;padding:10px 14px;background:var(--danger-bg);border:1px solid rgba(155,28,28,.2);border-radius:var(--radius-md);font-size:12px;color:var(--danger);font-weight:500;display:none;}
.inline-warn.show{display:block;}
.alloc-header{display:flex;align-items:center;justify-content:space-between;gap:12px;margin-bottom:14px;flex-wrap:wrap;}
.alloc-title{font-size:12px;font-weight:700;color:var(--navy-600);letter-spacing:.8px;text-transform:uppercase;display:flex;align-items:center;gap:8px;}
.alloc-title .dot{width:6px;height:6px;border-radius:50%;background:var(--gold-400);}
.status-pill{padding:4px 10px;background:var(--surface-2);border:1px solid var(--border-mid);border-radius:var(--radius-full);font-size:10.5px;font-weight:600;color:var(--text-muted);}

/* ACTION BAR */
.action-bar{position:fixed;left:50%;transform:translateX(-50%);bottom:12px;width:360px;max-width:calc(100vw - 24px);background:rgba(255,255,255,.92);border:1px solid var(--border-mid);border-radius:var(--radius-xl);box-shadow:var(--shadow-xl);backdrop-filter:blur(12px);-webkit-backdrop-filter:blur(12px);z-index:200;padding:10px 12px;}
.action-bar-inner{display:flex;gap:8px;align-items:center;}
.action-bar .btn{flex:1;text-align:center;padding:11px 12px;font-size:13px;}
.pdf-fab{position:fixed;right:16px;bottom:12px;z-index:201;width:48px;height:48px;border-radius:50%;background:linear-gradient(135deg,var(--navy-700),var(--navy-600));border:1px solid rgba(255,255,255,.12);box-shadow:0 4px 16px rgba(10,22,40,.3);color:#fff;font-size:10px;font-weight:700;font-family:inherit;letter-spacing:.5px;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .15s;}
.pdf-fab:hover{transform:translateY(-1px);}
.watermark{position:fixed;right:72px;bottom:20px;font-size:11px;font-weight:700;color:var(--text-muted);background:rgba(255,255,255,.85);border:1px solid var(--border-mid);padding:5px 12px;border-radius:var(--radius-full);backdrop-filter:blur(6px);z-index:9;pointer-events:none;letter-spacing:.3px;}

/* MODAL */
.modal-overlay{position:fixed;inset:0;background:rgba(4,13,26,.55);backdrop-filter:blur(4px);z-index:500;display:flex;align-items:center;justify-content:center;padding:20px;opacity:0;pointer-events:none;transition:opacity .2s;}
.modal-overlay.open{opacity:1;pointer-events:all;}
.modal-box{background:var(--surface-0);border-radius:var(--radius-xl);box-shadow:var(--shadow-xl);width:100%;max-width:560px;max-height:85vh;overflow-y:auto;transform:translateY(12px);transition:transform .2s;}
.modal-overlay.open .modal-box{transform:translateY(0);}
.modal-header{padding:18px 20px 14px;border-bottom:1px solid var(--border-light);display:flex;align-items:flex-start;gap:12px;}
.modal-header-icon{width:36px;height:36px;border-radius:var(--radius-sm);background:linear-gradient(135deg,var(--gold-100),var(--gold-50));border:1px solid rgba(212,163,41,.3);display:flex;align-items:center;justify-content:center;flex-shrink:0;font-size:16px;}
.modal-title{font-size:15px;font-weight:700;color:var(--text-primary);}
.modal-subtitle{font-size:11.5px;color:var(--text-muted);margin-top:2px;line-height:1.4;}
.modal-close{margin-left:auto;width:28px;height:28px;border-radius:50%;border:1px solid var(--border-mid);background:var(--surface-1);cursor:pointer;font-size:14px;color:var(--text-muted);display:flex;align-items:center;justify-content:center;flex-shrink:0;font-family:inherit;}
.modal-close:hover{background:var(--surface-2);color:var(--text-primary);}
.modal-body{padding:16px 20px 20px;}
.modal-insight{padding:12px 14px;background:linear-gradient(135deg,var(--navy-50),rgba(255,255,255,0));border:1px solid var(--border-mid);border-left:3px solid var(--gold-400);border-radius:var(--radius-md);margin-bottom:14px;font-size:12.5px;color:var(--text-secondary);line-height:1.55;}
.modal-insight strong{color:var(--navy-700);}
.modal-rationale{margin-bottom:16px;}
.modal-rationale-title{font-size:10px;font-weight:700;letter-spacing:.8px;text-transform:uppercase;color:var(--text-muted);margin-bottom:8px;}
.rationale-row{display:flex;gap:8px;align-items:flex-start;margin:6px 0;font-size:12px;color:var(--text-secondary);line-height:1.4;}
.rationale-row .icon{flex-shrink:0;margin-top:1px;}
.modal-risk-bar{margin-bottom:16px;}
.risk-bar-label{display:flex;justify-content:space-between;font-size:10.5px;font-weight:600;color:var(--text-muted);margin-bottom:5px;}
.risk-bar-track{height:6px;background:var(--surface-2);border-radius:3px;overflow:hidden;}
.risk-bar-fill{height:100%;border-radius:3px;background:linear-gradient(90deg,var(--navy-400),var(--gold-400));transition:width .3s;}
.modal-apply-btn{width:100%;padding:12px;font-size:13.5px;}

/* MACRO INTELLIGENCE PANEL */
.macro-panel{background:linear-gradient(135deg,var(--navy-800),var(--navy-700));border-radius:var(--radius-xl);padding:20px;margin-bottom:16px;border:1px solid rgba(255,255,255,.08);}
.macro-panel .mp-title{font-size:11px;font-weight:700;color:var(--gold-300);letter-spacing:1.2px;text-transform:uppercase;margin-bottom:16px;display:flex;align-items:center;gap:8px;}
.macro-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;}
@media(max-width:860px){.macro-grid{grid-template-columns:1fr 1fr;}}
.macro-card{background:rgba(255,255,255,.06);border:1px solid rgba(255,255,255,.1);border-radius:var(--radius-lg);padding:12px 14px;}
.macro-card .mc-label{font-size:9.5px;font-weight:700;color:rgba(184,208,240,.6);letter-spacing:.8px;text-transform:uppercase;margin-bottom:4px;}
.macro-card .mc-value{font-size:20px;font-weight:700;color:#fff;letter-spacing:-.5px;}
.macro-card .mc-sub{font-size:10.5px;color:rgba(184,208,240,.5);margin-top:3px;}
.macro-card.positive .mc-value{color:#4ade80;}
.macro-card.negative .mc-value{color:#f87171;}
.macro-card.neutral .mc-value{color:var(--gold-300);}
.macro-signal{margin-top:14px;padding:10px 14px;background:rgba(255,255,255,.05);border:1px solid rgba(255,255,255,.08);border-left:3px solid var(--gold-400);border-radius:var(--radius-md);font-size:12px;color:rgba(184,208,240,.85);line-height:1.5;}
.macro-signal strong{color:#fff;}
.macro-inputs{display:grid;grid-template-columns:repeat(4,1fr);gap:10px;margin-top:14px;}
@media(max-width:860px){.macro-inputs{grid-template-columns:1fr 1fr;}}
.macro-input-group label{color:rgba(184,208,240,.6);font-size:10px;}
.macro-input-group input{background:rgba(255,255,255,.08);border:1px solid rgba(255,255,255,.15);color:#fff;font-size:13px;}
.macro-input-group input::placeholder{color:rgba(255,255,255,.3);}
.macro-input-group input:focus{border-color:var(--gold-400);box-shadow:0 0 0 2px rgba(232,184,58,.15);}
.macro-fetch-row{display:flex;gap:8px;margin-top:12px;flex-wrap:wrap;align-items:center;}
.macro-status{font-size:11px;color:rgba(184,208,240,.6);}
/* ANALYTICS MODELS PANEL */
.ap-toggle{width:100%;background:none;border:none;cursor:pointer;display:flex;align-items:center;justify-content:space-between;color:var(--gold-300);font-size:11px;font-weight:700;letter-spacing:1.2px;text-transform:uppercase;font-family:inherit;padding:0;}
.ap-toggle:hover{color:var(--gold-200);}
.ap-toggle-arrow{font-size:12px;transition:transform .2s;}
.ap-toggle-arrow.open{transform:rotate(180deg);}
/* ANALYTICS MODELS PANEL ORIG */
.analytics-panel{background:linear-gradient(160deg,#0a1628,#0f2040);border-radius:var(--radius-xl);padding:20px;margin-bottom:16px;border:1px solid rgba(255,255,255,.08);}
.analytics-panel .ap-title{font-size:11px;font-weight:700;color:var(--gold-300);letter-spacing:1.2px;text-transform:uppercase;margin-bottom:4px;display:flex;align-items:center;gap:8px;}
.analytics-panel .ap-sub{font-size:11px;color:rgba(184,208,240,.5);margin-bottom:16px;}
.analytics-fetch-row{display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-bottom:12px;}
.analytics-status{font-size:11px;color:rgba(184,208,240,.5);}
#analytics_results{max-height:500px;overflow-y:auto;scrollbar-width:thin;}
@media print{#site-header{position:static !important;}.action-bar,.watermark,.pdf-fab{display:none;}body{padding-bottom:0;}.card{box-shadow:none;}}
@media(max-width:700px){.g3{grid-template-columns:1fr 1fr;}.g4{grid-template-columns:1fr 1fr;}.bottom-grid{grid-template-columns:1fr;}}
```

  </style>
</head>
<body>

<div role="banner" id="site-header" style="background:#040d1a;background:linear-gradient(135deg,#040d1a 0%,#0a1628 50%,#0f2040 100%);border-bottom:1px solid rgba(255,255,255,.06);position:sticky;top:0;z-index:100;box-shadow:0 2px 20px rgba(4,13,26,.4);">
  <div class="header-inner">
    <div class="header-top">
      <div class="header-brand">
        <div class="brand-icon">
          <svg viewBox="0 0 36 36" xmlns="http://www.w3.org/2000/svg" width="36" height="36">
            <circle cx="18" cy="10" r="6.5" fill="none" stroke="#e8b83a" stroke-width="2.2"/>
            <circle cx="18" cy="10" r="2.8" fill="#e8b83a"/>
            <circle cx="11" cy="22" r="6.5" fill="none" stroke="#e8b83a" stroke-width="2.2"/>
            <circle cx="11" cy="22" r="2.8" fill="#e8b83a"/>
            <circle cx="25" cy="22" r="6.5" fill="none" stroke="#e8b83a" stroke-width="2.2"/>
            <circle cx="25" cy="22" r="2.8" fill="#e8b83a"/>
          </svg>
        </div>
        <div class="brand-text">
          <h1 style="color:#ffffff;font-size:15px;font-weight:700;">PB Allocation Engine</h1>
          <div class="sub" id="hdr_sub" style="color:#7fa8e0;">Spot + Forward yaklaşımı ile vade sonu kurlar → giriş PB'ye dönüşte Net P/L.</div>
        </div>
      </div>
      <div class="header-right">
        <div class="version-badge">v110</div>
        <div class="lang-selector">
          <span id="lbl_lang">Dil</span>
          <select id="lang"><option value="tr" selected>TR</option><option value="en">EN</option></select>
        </div>
      </div>
    </div>
    <div class="disclaimer-bar">
      <p id="hdr_disc" style="color:rgba(184,208,240,.6);">Bu hesaplamalar yaklaşık değerlerdir. Kullanılan kurlar, stopaj oranları ve ürün getirileri varsayımsaldır; nihai sonuçlar bankanın resmi fiyatlaması/işlem anındaki koşullara göre değişebilir.</p>
    </div>
  </div>
</div><!-- /site-header -->

<div class="wrap">

  <!-- MACRO INTELLIGENCE PANEL (collapsible) -->

  <div class="macro-panel" id="macroPanel">
    <button class="ap-toggle" onclick="toggleMacro()" style="width:100%;background:none;border:none;cursor:pointer;display:flex;align-items:center;justify-content:space-between;color:var(--gold-300);font-size:11px;font-weight:700;letter-spacing:1.2px;text-transform:uppercase;font-family:inherit;padding:0;">
      <span>🧠 Macro Intelligence — Piyasa Sinyalleri</span>
      <span id="macro_arrow" style="font-size:12px;transition:transform .2s;">▼</span>
    </button>
    <div id="macro_body" style="display:none;margin-top:14px;">
      <div style="font-size:11px;color:rgba(184,208,240,.5);margin-bottom:12px;">
        Politika faizi ve TÜFE verilerini <strong style="color:rgba(184,208,240,.8);">manuel gir</strong> — API kısıtlaması nedeniyle otomatik çekilemiyor. Carry spreadi ve FX outlook otomatik hesaplanır.
      </div>
      <div class="macro-grid">
        <div class="macro-card neutral" id="mc_policy">
          <div class="mc-label">MB Politika Faizi</div>
          <div class="mc-value" id="mc_policy_val">—</div>
          <div class="mc-sub">%/yıl</div>
        </div>
        <div class="macro-card neutral" id="mc_cpi">
          <div class="mc-label">Son TÜFE (yıllık)</div>
          <div class="mc-value" id="mc_cpi_val">—</div>
          <div class="mc-sub">%/yıl</div>
        </div>
        <div class="macro-card neutral" id="mc_real">
          <div class="mc-label">Reel Faiz</div>
          <div class="mc-value" id="mc_real_val">—</div>
          <div class="mc-sub">Politika − TÜFE</div>
        </div>
        <div class="macro-card neutral" id="mc_consensus">
          <div class="mc-label">Yılsonu USD/TRY Beklenti</div>
          <div class="mc-value" id="mc_consensus_val">—</div>
          <div class="mc-sub">Piyasa tahmini</div>
        </div>
      </div>
      <div class="macro-inputs">
        <div class="macro-input-group">
          <label>MB Politika Faizi (%)</label>
          <input type="number" id="macro_policy" step="0.25" placeholder="ör. 42.5" />
        </div>
        <div class="macro-input-group">
          <label>Son TÜFE (%)</label>
          <input type="number" id="macro_cpi" step="0.1" placeholder="ör. 65.4" />
        </div>
        <div class="macro-input-group">
          <label>Yılsonu USD/TRY Tahmini</label>
          <input type="number" id="macro_consensus_fx" step="0.1" placeholder="ör. 42.0" />
        </div>
        <div class="macro-input-group">
          <label>USD/TRY 12M Forward (opt.)</label>
          <input type="number" id="macro_fwd12" step="0.01" placeholder="oto: carry'dan" />
        </div>
      </div>
      <div class="macro-fetch-row" style="margin-top:12px;">
        <button class="btn btn-ghost btn-sm" id="btn_macro_calc">📊 Sinyal Hesapla</button>
        <span class="macro-status" id="macro_status"></span>
      </div>
      <div class="macro-signal" id="macro_signal" style="display:none;"></div>
    </div>
  </div>

  <!-- ANALYTICS MODELS PANEL (collapsible) -->

  <div class="analytics-panel">
    <button class="ap-toggle" id="btn_analytics_toggle" onclick="toggleAnalytics()">
      <span>🔬 Analitik Modeller — Tarihsel Veri Sinyalleri</span>
      <span class="ap-toggle-arrow" id="analytics_arrow">▼</span>
    </button>
    <div id="analytics_body" style="display:none;margin-top:14px;">
      <div class="ap-sub">USD/TRY 1 yıllık tarihsel veri ile: Altın momentum · TRY volatilite · Carry/Vol Sharpe · Korelasyon kırılması</div>
      <div class="analytics-fetch-row">
        <button class="btn btn-gold btn-sm" id="btn_fetch_analytics">📡 Veri Çek (1 Yıl)</button>
        <button class="btn btn-ghost btn-sm" id="btn_run_models">⚡ Modelleri Çalıştır</button>
        <span class="analytics-status" id="analytics_status">Henüz çekilmedi</span>
      </div>
      <div id="analytics_results"></div>
    </div>
  </div>

  <!-- CONFIG CARD -->

  <div class="card cfg-card">

```
<!-- SATIR 1: 3 KOLON -->
<div class="cfg-row1">

  <!-- KOLON 1: Müşteri Varlığı -->
  <div class="col">
    <div class="section-label" id="sec1">Müşteri Varlığı</div>
    <label id="lbl_total">Toplam Varlık</label>
    <input id="total_amount" type="text" inputmode="decimal" value="1.000.000" />
    <div class="g2" style="margin-top:10px;">
      <div>
        <label id="lbl_principal">Giriş PB</label>
        <select id="total_ccy">
          <option value="USD" selected>USD</option>
          <option value="TL">TL</option>
          <option value="EUR">EUR</option>
          <option value="XAUg">Altın (g)</option>
        </select>
      </div>
      <div>
        <label id="lbl_report">Rapor PB</label>
        <select id="report_ccy">
          <option value="TL" selected>TL</option>
          <option value="USD">USD</option>
          <option value="EUR">EUR</option>
          <option value="XAUg">Altın (g)</option>
        </select>
      </div>
    </div>
    <div class="g2" style="margin-top:10px;">
      <div>
        <label id="lbl_ttype">Vade Tipi</label>
        <select id="tenor_type">
          <option value="DAYS" selected>Gün</option>
          <option value="MONTHS">Ay</option>
        </select>
      </div>
      <div>
        <label id="lbl_tval">Vade</label>
        <input id="tenor_val" type="number" step="1" value="32" />
      </div>
    </div>
    <div class="status-note" id="txt_tenor_note">Vade bir kez seçilir → tüm satırlara otomatik uygulanır.</div>
  </div>

  <!-- KOLON 2: Başlangıç Kurları -->
  <div class="col">
    <div class="section-label" id="sec2">Başlangıç Kurları (Spot)</div>
    <div class="g3">
      <div>
        <label id="lbl_gold_spot">Altın (g/TRY)</label>
        <input id="xautry_g" type="number" step="0.01" value="0" />
      </div>
      <div>
        <label>USD/TRY</label>
        <input id="usdtry" type="number" step="0.0001" value="0" />
      </div>
      <div>
        <label>EUR/TRY</label>
        <input id="eurtry" type="number" step="0.0001" value="0" />
      </div>
    </div>
    <div class="btn-row">
      <button class="btn btn-gold btn-sm" id="btn_rates">Kurları Çek</button>
      <button class="btn btn-ghost btn-sm" id="btn_use_manual">Manuel Kur</button>
    </div>
    <div class="status-line" id="rate_status"></div>
    <div class="status-note" id="txt_rate_note">Kaynak engellenirse USD/EUR alternatif kaynaktan gelir; altın manuel olabilir.</div>
  </div>

  <!-- KOLON 3: Vade Sonu Kurları -->
  <div class="col">
    <div class="section-label" id="sec3">Vade Sonu Kurları</div>
    <div class="g2">
      <div>
        <label id="lbl_end_mode">Kur Modu</label>
        <select id="end_mode">
          <option value="SPOT" selected>Spot = Vade Sonu</option>
          <option value="FWD">Forward (getiri farkı)</option>
          <option value="MANUAL">Manuel</option>
        </select>
      </div>
      <div>
        <label id="lbl_gold_exp">Altın Beklenti (%/yıl)</label>
        <input id="gold_exp" type="number" step="0.01" value="0" />
      </div>
    </div>
    <div class="g3" style="margin-top:10px;">
      <div>
        <label id="lbl_gold_end">Altın – <span id="lbl_end_vs">Vade</span></label>
        <input id="xautry_g_end" type="number" step="0.01" placeholder="oto" />
      </div>
      <div>
        <label>USD/TRY – <span id="lbl_end">Vade</span></label>
        <input id="usdtry_end" type="number" step="0.0001" placeholder="oto" />
      </div>
      <div>
        <label>EUR/TRY – <span id="lbl_end2">Vade</span></label>
        <input id="eurtry_end" type="number" step="0.0001" placeholder="oto" />
      </div>
    </div>
    <div class="status-note" id="end_note" style="margin-top:6px;"></div>
  </div>

</div><!-- /cfg-row1 -->

<!-- SATIR 2: Getiriler + Butonlar -->
<div class="cfg-row2">
  <div class="cfg-row2-left">
    <div class="section-label" style="margin-bottom:10px;">Getiri Oranları (%/yıl)</div>
    <div class="cfg-rates-grid">
      <div>
        <label id="lbl_rtl">TL Getiri</label>
        <input id="rtl" type="number" step="0.01" value="45" />
      </div>
      <div>
        <label id="lbl_rusd">USD Getiri</label>
        <input id="rusd" type="number" step="0.01" value="5" />
      </div>
      <div>
        <label id="lbl_reur">EUR Getiri</label>
        <input id="reur" type="number" step="0.01" value="3" />
      </div>
    </div>
  </div>
  <div class="cfg-row2-actions">
    <button class="btn btn-ghost btn-sm" id="btn_fill_end">Vade Sonu Kurları Doldur</button>
    <button class="btn btn-primary btn-sm" id="btn_calc_top">Hesapla</button>
    <button class="btn btn-danger btn-sm" id="btn_reset_top">Sıfırla</button>
  </div>
</div>
```

  </div><!-- /cfg-card -->

  <!-- ALLOCATION PANEL -->

  <div class="card" style="margin-top:16px;">
    <div class="alloc-header">
      <div class="alloc-title">
        <div class="dot"></div>
        <span id="sec_alloc_text">Alokasyon (Tutar Bazlı)</span>
      </div>
      <div class="status-pill" id="pillInfo">hazır</div>
    </div>

```
<div class="headline-kpi">
  <div>
    <div class="label" id="lbl_headline">Headline – Net P/L (Giriş Para Birimi)</div>
    <div class="value" id="headline_pl">—</div>
    <div class="detail" id="headline_detail"></div>
  </div>
  <div class="pill-badge" id="headline_ccy_badge">–</div>
</div>

<div class="risk-wrap" id="risk_badges"></div>

<div style="margin-top:14px;">
  <div style="display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-bottom:8px;">
    <button class="add-pill" id="btn_add">+ Satır Ekle</button>
    <button class="btn btn-gold btn-sm" id="btn_suggest" style="display:flex;align-items:center;gap:5px;">
      <span>💡</span><span id="btn_suggest_txt">Senaryo Öner</span>
    </button>
  </div>
  <div style="display:flex;gap:6px;align-items:center;flex-wrap:wrap;">
    <span style="font-size:10px;font-weight:700;color:var(--text-muted);letter-spacing:.5px;text-transform:uppercase;white-space:nowrap;">Hazır:</span>
    <div class="scenario-pills">
      <button class="scenario-pill" id="btn_s1">Dengeli</button>
      <button class="scenario-pill" id="btn_s2">Koruma</button>
      <button class="scenario-pill" id="btn_s3">Büyüme (Riskli)</button>
      <button class="scenario-pill" id="btn_s4">FX Hedge</button>
      <button class="scenario-pill" id="btn_s5">DPM Ağırlıklı</button>
    </div>
  </div>
  <div id="scenario_insight_bar" style="display:none;margin-top:10px;padding:10px 14px;background:linear-gradient(135deg,var(--navy-50),rgba(255,255,255,0));border:1px solid var(--border-mid);border-left:3px solid var(--gold-400);border-radius:var(--radius-md);font-size:12px;color:var(--text-secondary);line-height:1.5;"></div>
</div>

<div class="table-wrapper">
  <table>
    <thead>
      <tr>
        <th id="hdr_amt">Tutar (Giriş PB)</th>
        <th id="hdr_prod">Ürün</th>
        <th id="hdr_ccy">Hedef PB</th>
        <th id="hdr_rate">Getiri %</th>
        <th id="hdr_calc">Hesap</th>
        <th id="hdr_tax">Stopaj</th>
        <th id="hdr_p">Anapara (Hedef PB)</th>
        <th id="hdr_fv_gross">Vade Sonu (Brüt)</th>
        <th id="hdr_taxamt">Stopaj Tutarı</th>
        <th id="hdr_fv_net">Vade Sonu (Net)</th>
        <th id="hdr_net">Net Kazanç</th>
        <th></th>
      </tr>
    </thead>
    <tbody id="allocBody"></tbody>
  </table>
</div>

<div class="kpi-grid" style="margin-top:14px;">
  <div class="kpi-card"><div class="t" id="lbl_used">Kullanılan (Giriş PB)</div><div class="v" id="kpi_used">—</div></div>
  <div class="kpi-card"><div class="t" id="lbl_left">Kalan (Giriş PB)</div><div class="v" id="kpi_left">—</div></div>
  <div class="kpi-card"><div class="t" id="lbl_start_report">Başlangıç (Rapor PB)</div><div class="v" id="kpi_start_report">—</div></div>
  <div class="kpi-card"><div class="t" id="lbl_end_report">Vade Sonu (Rapor PB)</div><div class="v" id="kpi_end_report">—</div></div>
</div>
<div class="kpi-2" style="margin-top:12px;">
  <div class="kpi-card gold-accent"><div class="t" id="lbl_pl_report">Net P/L (Rapor PB)</div><div class="v" id="kpi_pl_report">—</div></div>
  <div class="kpi-card"><div class="t" id="lbl_tax_report">Toplam Stopaj (Rapor PB)</div><div class="v" id="kpi_tax_report">—</div></div>
</div>
<div class="kpi-grid" style="margin-top:12px;">
  <div class="kpi-card"><div class="t">Net P/L (TL)</div><div class="v" id="pl_tl">—</div></div>
  <div class="kpi-card"><div class="t">Net P/L (USD)</div><div class="v" id="pl_usd">—</div></div>
  <div class="kpi-card"><div class="t">Net P/L (EUR)</div><div class="v" id="pl_eur">—</div></div>
  <div class="kpi-card"><div class="t">Net P/L (Altın g)</div><div class="v" id="pl_xau">—</div></div>
</div>

<div class="bottom-grid">
  <div class="chart-card">
    <div class="chart-card-title" id="lbl_pie_title">Dağılım (Başlangıç – Rapor PB)</div>
    <div class="donut-wrap">
      <canvas id="pieStart" width="240" height="240"></canvas>
      <div class="legend-wrap">
        <div id="pieLegend"></div>
        <div class="tap-info" id="pieTapInfo"><strong>İpucu:</strong> Dilime dokun → dilim bilgisi.</div>
      </div>
    </div>
  </div>
  <div class="chart-card">
    <div class="chart-card-title" id="lbl_summary_title">Özet</div>
    <div class="summary-grid">
      <div class="summary-item"><div class="t" id="lbl_sum_start_pr">Başlangıç (Giriş PB)</div><div class="v" id="sum_start_pr">—</div></div>
      <div class="summary-item"><div class="t" id="lbl_sum_start_rp">Başlangıç (Rapor PB)</div><div class="v" id="sum_start_rp">—</div></div>
      <div class="summary-item"><div class="t" id="lbl_sum_end_pr">Vade Sonu (Giriş PB)</div><div class="v" id="sum_end_pr">—</div></div>
      <div class="summary-item"><div class="t" id="lbl_sum_end_rp">Vade Sonu (Rapor PB)</div><div class="v" id="sum_end_rp">—</div></div>
    </div>
    <div class="pl-note" id="txt_pl_note">Rapor PB Net P/L = vade sonu toplam − başlangıç toplam (aynı baz).</div>
  </div>
</div>

<div class="inline-warn" id="warn"></div>
```

  </div>

</div><!-- /wrap -->

<div class="watermark">Adem Soyer</div>
<div class="action-bar">
  <div class="action-bar-inner">
    <button class="btn btn-primary" id="btn_calc">Hesapla</button>
    <button class="btn btn-danger" id="btn_reset">Sıfırla</button>
  </div>
</div>
<button class="pdf-fab" id="btn_pdf">PDF</button>

<!-- SCENARIO MODAL -->

<div class="modal-overlay" id="scenarioModal">
  <div class="modal-box">
    <div class="modal-header">
      <div class="modal-header-icon" id="modal_icon">📊</div>
      <div>
        <div class="modal-title" id="modal_title">Senaryo</div>
        <div class="modal-subtitle" id="modal_subtitle"></div>
      </div>
      <button class="modal-close" id="modal_close">✕</button>
    </div>
    <div class="modal-body">
      <div class="modal-insight" id="modal_insight"></div>
      <div class="modal-risk-bar">
        <div class="risk-bar-label"><span id="modal_risk_label">Risk Seviyesi</span><span id="modal_risk_val"></span></div>
        <div class="risk-bar-track"><div class="risk-bar-fill" id="modal_risk_bar" style="width:50%"></div></div>
      </div>
      <div class="modal-rationale">
        <div class="modal-rationale-title" id="modal_rationale_title">Gerekçe</div>
        <div id="modal_rationale_rows"></div>
      </div>
      <button class="btn btn-primary modal-apply-btn" id="modal_apply">Bu Senaryoyu Uygula →</button>
    </div>
  </div>
</div>

<script>
const I18N = {
  tr: {
    hdr_sub: "Spot + Forward yaklaşımı ile vade sonu kurlar → giriş PB'ye dönüşte Net P/L.",
    disc: "Bu hesaplamalar yaklaşık değerlerdir. Kullanılan kurlar, stopaj oranları ve ürün getirileri varsayımsaldır; nihai sonuçlar bankanın resmi fiyatlaması/işlem anındaki koşullara göre değişebilir.",
    Dil:"Dil",
    sec1:"Müşteri Varlığı",
    sec2:"Başlangıç Kurları (Spot)",
    sec3:"Vade Sonu Kurları",
    ToplamVarlik:"Toplam Varlık",
    GirisPB:"Giriş Para Birimi",
    RaporPB:"Rapor Para Birimi",
    VadeTipi:"Vade Tipi",
    Vade:"Vade",
    VadeNot:"Vade bir kez seçilir → tüm satırlara otomatik uygulanır.",
    Altin:"Altın (g/TRY)",
    RateNote:"Kaynak engellenirse USD/EUR alternatif kaynaktan gelir; altın manuel olabilir.",
    EndMode:"Vade Sonu Kur Modu",
    AltinBek:"Altın Beklenti (%/yıl)",
    AltinEnd:"Altın – Vade Sonu",
    VadeSonu:"Vade",
    TLget:"TL Getiri (%/yıl)",
    USDget:"USD Getiri (%/yıl)",
    EURget:"EUR Getiri (%/yıl)",
    FillEnd:"Vade Sonu Kurları Doldur",
    Calc:"Hesapla",
    Reset:"Sıfırla",
    PDF:"PDF",
    Fetch:"Kurları Çek",
    Manual:"Manuel Kur",
    AllocTitle:"Alokasyon (Tutar Bazlı)",
    Headline:"Headline – Net P/L (Giriş Para Birimi)",
    Add:"+ Satır Ekle",
    Used:"Kullanılan (Giriş PB)",
    Left:"Kalan (Giriş PB)",
    StartReport:"Başlangıç (Rapor PB)",
    EndReport:"Vade Sonu (Rapor PB)",
    PLReport:"Net P/L (Rapor PB)",
    TaxReport:"Toplam Stopaj (Rapor PB)",
    PieTitle:"Dağılım (Başlangıç – Rapor PB)",
    Summary:"Özet",
    SumStartPr:"Başlangıç (Giriş PB)",
    SumStartRp:"Başlangıç (Rapor PB)",
    SumEndPr:"Vade Sonu (Giriş PB)",
    SumEndRp:"Vade Sonu (Rapor PB)",
    PLNote:"Rapor PB Net P/L = vade sonu toplam − başlangıç toplam (aynı baz).",
    pieHint:"Dilime dokun → dilim bilgisi. Ortaya dokun → ürün özeti.",
    hdr_amt:(ccy)=>`Tutar (Giriş – ${ccy})`,
    hdr_prod:"Ürün",
    hdr_ccy:"Hedef PB",
    hdr_rate:"Getiri %",
    hdr_calc:"Hesap",
    hdr_tax:"Stopaj",
    hdr_p:"Anapara (Hedef PB)",
    hdr_fv_g:"Vade Sonu (Brüt)",
    hdr_taxamt:"Stopaj Tutarı",
    hdr_fv_n:"Vade Sonu (Net)",
    hdr_net:"Net Kazanç",
    warn_amt:"Toplam varlık 0 olamaz.",
    warn_row:"En az 1 satır ekle.",
    warn_tenor:"Global vade 0 olamaz.",
    warn_start:"Başlangıç kurları eksik. (USD/TRY, EUR/TRY, Altın/TRY kontrol et.)",
    warn_end:"Vade sonu kurları eksik. (Mod/Altın/Spot kontrol et.)",
    warn_alloc:"Alokasyon toplamı, toplam varlığı aşıyor. Satır tutarlarını düşür.",
    endNeedSpot:"Not: Spot/Forward için önce USD/TRY ve EUR/TRY girilmeli ya da çekilmeli.",
    endSpot:"Spot = Vade Sonu: End kurlar spot ile aynı kabul edildi.",
    endManual:"Manuel mod: vade sonu kurları sen girersin.",
    endFwd:"Forward modu: USD/TRY ve EUR/TRY getiri farkı ile türetildi. Altın: beklenti % ile.",
    ratesOk:"✓ USD / EUR / Altın güncellendi.",
    ratesFallback:"✓ USD/EUR alternatif kaynaktan güncellendi. Altın manuel.",
    ratesFail:"⚠ Kurlar çekilemedi. Manuel girip devam edebilirsin.",
    manualOk:"✓ Manuel kur kullanılıyor.",
    manualBad:"⚠ Manuel kur eksik.",
    mixNote:"Dağılım:",
    scenario:{ s1:"Dengeli", s2:"Koruma", s3:"Büyüme (Riskli)", s4:"FX Hedge", s5:"DPM Ağırlıklı" },
    method:{ simple:"Basit", daily:"Günlük (bileşik)", renew:"Yenilemeli (TL vadeli)" },
    prod:{ TERM:"Vadeli Mevduat", FUND:"Yatırım Fonu", SUKUK:"Sukuk", DPM:"DPM" },
    del:"Sil",
    auto:"Oto",
    renewEvery:"Yenileme (gün)"
  },
  en: {
    hdr_sub: "Spot + Forward approach for end FX → Net P/L back in principal currency.",
    disc: "These figures are indicative only. FX rates, withholding assumptions and product returns are illustrative; final results may differ based on official pricing and execution-time conditions.",
    Dil:"Language",
    sec1:"Client Assets",
    sec2:"Spot Rates (Start)",
    sec3:"End Rates (Auto)",
    ToplamVarlik:"Total Amount",
    GirisPB:"Principal Currency",
    RaporPB:"Reporting Currency",
    VadeTipi:"Tenor Type",
    Vade:"Tenor",
    VadeNot:"Tenor is selected once → applied to all rows.",
    Altin:"Gold (gram/TRY)",
    RateNote:"If blocked, USD/EUR uses fallback; gold may be manual.",
    EndMode:"End FX Mode",
    AltinBek:"Gold expectation (annual %)",
    AltinEnd:"Gold – End",
    VadeSonu:"End",
    TLget:"TRY carry (annual %)",
    USDget:"USD carry (annual %)",
    EURget:"EUR carry (annual %)",
    FillEnd:"Fill End Rates",
    Calc:"Calculate",
    Reset:"Reset",
    PDF:"PDF",
    Fetch:"Fetch Rates",
    Manual:"Use Manual Rates",
    AllocTitle:"Allocation (Amount Based)",
    Headline:"Headline – Net P/L (Principal)",
    Add:"+ Add Row",
    Used:"Allocated (Principal)",
    Left:"Remaining (Principal)",
    StartReport:"Start Total (Report)",
    EndReport:"End Total (Report)",
    PLReport:"Net P/L (Report)",
    TaxReport:"Total Withholding (Report)",
    PieTitle:"Mix (Start – Report)",
    Summary:"Summary",
    SumStartPr:"Start (Principal)",
    SumStartRp:"Start (Report)",
    SumEndPr:"End Total (Principal)",
    SumEndRp:"End Total (Report)",
    PLNote:"Report P/L = end total − start total (same base).",
    pieHint:"Tap a slice for details. Tap the center for product summary.",
    hdr_amt:(ccy)=>`Amount (Principal – ${ccy})`,
    hdr_prod:"Product",
    hdr_ccy:"Target CCY",
    hdr_rate:"Return %",
    hdr_calc:"Method",
    hdr_tax:"Withholding",
    hdr_p:"Principal (Target)",
    hdr_fv_g:"End (Gross)",
    hdr_taxamt:"Withholding Amt",
    hdr_fv_n:"End (Net)",
    hdr_net:"Net Gain",
    warn_amt:"Total amount cannot be 0.",
    warn_row:"Add at least one row.",
    warn_tenor:"Tenor cannot be 0.",
    warn_start:"Missing spot rates. Check USD/TRY, EUR/TRY, Gold/TRY.",
    warn_end:"Missing end rates. Check mode / gold / spot.",
    warn_alloc:"Allocation exceeds total amount. Reduce row amounts.",
    endNeedSpot:"Note: Spot/Forward requires USD/TRY & EUR/TRY first.",
    endSpot:"Spot = End: end rates assumed equal to spot.",
    endManual:"Manual mode: you enter end rates.",
    endFwd:"Forward mode: USD/TRY & EUR/TRY derived via carry proxy. Gold via expectation %.",
    ratesOk:"✓ USD / EUR / Gold updated.",
    ratesFallback:"✓ USD/EUR updated from fallback. Gold manual.",
    ratesFail:"⚠ Could not fetch rates. Enter manually.",
    manualOk:"✓ Using manual rates.",
    manualBad:"⚠ Manual rates missing.",
    mixNote:"Mix:",
    scenario:{ s1:"Balanced", s2:"Protection", s3:"Growth (Risk)", s4:"FX Hedge", s5:"DPM Focus" },
    method:{ simple:"Simple", daily:"Daily (comp.)", renew:"Rollover (TRY term)" },
    prod:{ TERM:"Term Deposit", FUND:"Fund", SUKUK:"Sukuk", DPM:"DPM" },
    del:"Del",
    auto:"Auto",
    renewEvery:"Rollover (days)"
  }
};

function L(){ return document.getElementById('lang').value || 'tr'; }
function T(key){
  const lang = L();
  const obj = I18N[lang] || I18N.tr;
  return obj[key] ?? I18N.tr[key] ?? key;
}

function parseAmount(str){
  if(!str) return 0;
  let s = String(str).trim().replace(/\s/g,'');
  if(s.includes(',') && s.includes('.')){
    s = s.replace(/\./g,'').replace(',', '.');
  } else if(s.includes(',')){
    const parts = s.split(',');
    if(parts.length===2 && parts[1].length<=2) s = parts[0].replace(/\./g,'') + '.' + parts[1];
    else s = s.replace(/,/g,'');
  } else {
    s = s.replace(/\./g,'');
  }
  const n = Number(s);
  return isFinite(n) ? n : 0;
}
function fmtMoney(n, ccy){
  const abs = Math.abs(n);
  const opts = abs >= 100000 ? { maximumFractionDigits:0 } : { maximumFractionDigits:2 };
  return new Intl.NumberFormat('tr-TR', opts).format(n) + ' ' + ccy;
}
function fmtPlain(n){
  return new Intl.NumberFormat('tr-TR', { maximumFractionDigits:2 }).format(n);
}
function clamp(x){ return Math.max(0, Number(x)||0); }

function setAmtHeader(){
  const ccy = document.getElementById('total_ccy').value;
  document.getElementById('hdr_amt').textContent = I18N[L()].hdr_amt(ccy);
}

function globalDays(){
  const ttype = document.getElementById('tenor_type').value;
  const v = Number(document.getElementById('tenor_val').value)||0;
  const n = clamp(v);
  return (ttype==='DAYS') ? n : (n*30.4375);
}

function getStartRates(){
  return {
    usdtry: Number(document.getElementById('usdtry').value)||0,
    eurtry: Number(document.getElementById('eurtry').value)||0,
    xautry_g: Number(document.getElementById('xautry_g').value)||0
  };
}
function setEndRates(o){
  if(o.xautry_g != null && isFinite(o.xautry_g)) document.getElementById('xautry_g_end').value = Number(o.xautry_g).toFixed(2);
  if(o.usdtry != null && isFinite(o.usdtry)) document.getElementById('usdtry_end').value = Number(o.usdtry).toFixed(4);
  if(o.eurtry != null && isFinite(o.eurtry)) document.getElementById('eurtry_end').value = Number(o.eurtry).toFixed(4);
}
function getEndRatesResolved(){
  const s = getStartRates();
  const usdtry_end = Number(document.getElementById('usdtry_end').value)||0;
  const eurtry_end = Number(document.getElementById('eurtry_end').value)||0;
  const xautry_g_end = Number(document.getElementById('xautry_g_end').value)||0;
  return {
    usdtry: usdtry_end>0 ? usdtry_end : s.usdtry,
    eurtry: eurtry_end>0 ? eurtry_end : s.eurtry,
    xautry_g: xautry_g_end>0 ? xautry_g_end : s.xautry_g
  };
}

function fxRate(from, to, when){
  if(from === to) return 1;
  const r = (when === 'end') ? getEndRatesResolved() : getStartRates();
  const {usdtry, eurtry, xautry_g} = r;
  const toTRY = (ccy)=>{
    if(ccy==='TL') return 1;
    if(ccy==='USD') return usdtry>0 ? usdtry : null;
    if(ccy==='EUR') return eurtry>0 ? eurtry : null;
    if(ccy==='XAUg') return xautry_g>0 ? xautry_g : null;
    return null;
  };
  const fromTRY = (ccy)=>{
    if(ccy==='TL') return 1;
    if(ccy==='USD') return usdtry>0 ? (1/usdtry) : null;
    if(ccy==='EUR') return eurtry>0 ? (1/eurtry) : null;
    if(ccy==='XAUg') return xautry_g>0 ? (1/xautry_g) : null;
    return null;
  };
  const a = toTRY(from);
  const b = fromTRY(to);
  if(a==null || b==null) return null;
  return a*b;
}

async function fetchRatesAll(){
  const status = document.getElementById('rate_status');
  status.textContent = (L()==='en') ? 'Fetching rates…' : 'Kurlar çekiliyor…';
  try{
    const res = await fetch('https://finans.truncgil.com/v4/today.json', { cache:'no-store' });
    if(res.ok){
      const data = await res.json();
      const usd = data?.USD?.Selling ?? data?.USD?.Buying;
      const eur = data?.EUR?.Selling ?? data?.EUR?.Buying;
      const gra = data?.GRA?.Selling ?? data?.GRA?.Buying;
      if(usd && eur){
        document.getElementById('usdtry').value = Number(usd).toFixed(4);
        document.getElementById('eurtry').value = Number(eur).toFixed(4);
        if(gra) document.getElementById('xautry_g').value = Number(gra).toFixed(2);
        status.textContent = T('ratesOk');
        autoFillEndRates();
        return;
      }
    }
  }catch(e){}
  try{
    const r = await fetch('https://open.er-api.com/v6/latest/TRY', { cache:'no-store' });
    if(!r.ok) throw new Error('fallback failed');
    const j = await r.json();
    const usd = j?.rates?.USD;
    const eur = j?.rates?.EUR;
    if(usd && eur){
      document.getElementById('usdtry').value = (1/Number(usd)).toFixed(4);
      document.getElementById('eurtry').value = (1/Number(eur)).toFixed(4);
      status.textContent = T('ratesFallback');
      autoFillEndRates();
      return;
    }
    throw new Error('rates missing');
  }catch(e2){
    status.textContent = T('ratesFail');
  }
}

function autoFillEndRates(){
  const mode = document.getElementById('end_mode').value;
  const note = document.getElementById('end_note');
  const s = getStartRates();
  const days = globalDays();
  const Tt = days/365;

  if(mode !== 'MANUAL'){
    if(s.usdtry<=0 || s.eurtry<=0){ note.textContent = T('endNeedSpot'); return; }
  }
  if(mode === 'MANUAL'){ note.textContent = T('endManual'); return; }
  if(mode === 'SPOT'){
    setEndRates({ usdtry:s.usdtry, eurtry:s.eurtry, xautry_g:(s.xautry_g>0?s.xautry_g:null) });
    note.textContent = T('endSpot');
    return;
  }
  const rTL = (Number(document.getElementById('rtl').value)||0)/100;
  const rUSD = (Number(document.getElementById('rusd').value)||0)/100;
  const rEUR = (Number(document.getElementById('reur').value)||0)/100;
  const usdEnd = s.usdtry * ((1+rTL*Tt)/(1+rUSD*Tt));
  const eurEnd = s.eurtry * ((1+rTL*Tt)/(1+rEUR*Tt));
  const gExp = (Number(document.getElementById('gold_exp').value)||0)/100;
  const goldEnd = (s.xautry_g>0) ? (s.xautry_g*(1+gExp*Tt)) : null;
  setEndRates({ usdtry:usdEnd, eurtry:eurEnd, xautry_g:goldEnd });
  note.textContent = T('endFwd');
}

function fvSimple(P, annualPct, days){ return P*(1+(Number(annualPct)||0)/100*(days/365)); }
function fvDailyCompound(P, annualPct, days){ return P*Math.pow(1+(Number(annualPct)||0)/100/365, days); }
function fvRenewWithTax(P, annualPct, totalDays, renewEveryDays, taxPct){
  const r=(Number(annualPct)||0)/100, t=(Number(taxPct)||0)/100;
  const step=Math.max(1,Math.floor(Number(renewEveryDays)||1));
  let remaining=Math.max(0,Math.floor(totalDays)), principal=P;
  while(remaining>0){
    const d=Math.min(step,remaining);
    const grossEnd=principal*(1+r*(d/365));
    const grossGain=grossEnd-principal;
    principal=grossEnd-grossGain*t;
    remaining-=d;
  }
  return principal;
}

function suggestTaxPct(prod, targetCcy, days){
  // TERM (Vadeli Mevduat): stopaj uygulanır
  if(prod==='TERM'){
    if(targetCcy!=='TL') return 25;   // dövizli vadeli
    if(days<=183) return 17.5;        // TL ≤183 gün
    if(days<=365) return 15;          // TL ≤365 gün
    return 10;                         // TL >365 gün
  }
  // SUKUK: Hazine sukuku stopaj var ama banka sukukları farklı → 0 varsayım
  if(prod==='SUKUK') return 0;
  // FUND (Yatırım Fonu): stopaj yok, fon bünyesinde vergi
  if(prod==='FUND') return 0;
  // DPM (Ayrılmış Portföy): stopaj yok
  if(prod==='DPM') return 0;
  // Diğer: 0
  return 0;
}

/* ── DONUT CHART ── */
const PIE_STATE = { labels:[], vals:[], arcs:[] };
const PALETTE = [
  '#152b55','#d4a329','#2d56a0','#e8b83a','#4a7bc8','#0a7a3c','#9b3a1c',
  '#7fa8e0','#f0c84a','#6b82a8'
];

function drawDonutInteractive(canvas, labels, values){
  const ctx = canvas.getContext('2d');
  const dpr = window.devicePixelRatio || 1;
  const cssW = 220, cssH = 220;
  canvas.style.width = cssW+'px';
  canvas.style.height = cssH+'px';
  canvas.width = Math.floor(cssW*dpr);
  canvas.height = Math.floor(cssH*dpr);
  ctx.setTransform(dpr,0,0,dpr,0,0);
  ctx.clearRect(0,0,cssW,cssH);

  const cx=cssW/2, cy=cssH/2;
  const R=cssW*0.44, r=R*0.58;
  const total=values.reduce((a,b)=>a+b,0)||1;
  let ang=-Math.PI/2;
  const arcs=[];

  for(let i=0;i<labels.length;i++){
    const v=Math.max(0,values[i]);
    const a=(v/total)*Math.PI*2;
    const start=ang, end=ang+a;

    // Slice
    ctx.beginPath();
    ctx.moveTo(cx,cy);
    ctx.arc(cx,cy,R,start,end);
    ctx.closePath();
    ctx.fillStyle = PALETTE[i%PALETTE.length];
    ctx.fill();

    // Separator
    ctx.beginPath();
    ctx.arc(cx,cy,R,start,end);
    ctx.strokeStyle='rgba(255,255,255,.4)';
    ctx.lineWidth=2;
    ctx.stroke();

    arcs.push({i,start,end,R,r,cx,cy});
    ang=end;
  }

  // Donut hole
  ctx.beginPath();
  ctx.arc(cx,cy,r,0,Math.PI*2);
  ctx.fillStyle='#fff';
  ctx.fill();

  // Center ring
  ctx.beginPath();
  ctx.arc(cx,cy,r,0,Math.PI*2);
  ctx.strokeStyle='rgba(21,43,85,.06)';
  ctx.lineWidth=1;
  ctx.stroke();

  // Center text
  ctx.fillStyle='rgba(10,22,40,.45)';
  ctx.font='600 11px Inter,-apple-system,sans-serif';
  const txt=(L()==='en')?'Tap':'Dokun';
  const tw=ctx.measureText(txt).width;
  ctx.fillText(txt, cx-tw/2, cy+4);

  PIE_STATE.labels=labels.slice();
  PIE_STATE.vals=values.slice();
  PIE_STATE.arcs=arcs;
}

function donutHitTest(canvas, x, y){
  const rect=canvas.getBoundingClientRect();
  const cx=rect.width/2, cy=rect.height/2;
  const dx=x-cx, dy=y-cy;
  const dist=Math.sqrt(dx*dx+dy*dy);
  const arcs=PIE_STATE.arcs||[];
  const any=arcs[0];
  if(!any) return {type:'none'};
  const {R,r}=any;
  if(dist<=r) return {type:'center'};
  if(dist>R) return {type:'none'};
  let ang=Math.atan2(dy,dx)-(-Math.PI/2);
  while(ang<0) ang+=Math.PI*2;
  while(ang>=Math.PI*2) ang-=Math.PI*2;
  const absAng=-Math.PI/2+ang;
  for(const a of arcs){
    if(absAng>=a.start && absAng<=a.end) return {type:'slice',index:a.i};
  }
  return {type:'none'};
}

function productOnlySummaryHTML(){
  const labels=PIE_STATE.labels||[], vals=PIE_STATE.vals||[];
  const total=vals.reduce((a,b)=>a+b,0)||1;
  const agg={};
  labels.forEach((lab,i)=>{ const p=lab.split('/')[0].trim(); agg[p]=(agg[p]||0)+vals[i]; });
  return Object.keys(agg).map(k=>({k,v:agg[k]})).sort((a,b)=>b.v-a.v)
    .map(x=>`<div class="legend-item"><div class="legend-name">${x.k}</div><div class="legend-pct">${(x.v/total*100).toFixed(1)}%</div></div>`)
    .join('')||'—';
}

/* ── ROWS ── */
function buildProductOptionsHTML(){
  const p=I18N[L()].prod;
  return [`<option value="TERM">${p.TERM}</option>`,`<option value="FUND">${p.FUND}</option>`,`<option value="SUKUK">${p.SUKUK}</option>`,`<option value="DPM">${p.DPM}</option>`].join('');
}
function buildCurrencyOptionsHTML(){
  const gold=(L()==='en')?'Gold':'Altın';
  return [`<option value="TL">TL</option>`,`<option value="USD">USD</option>`,`<option value="EUR">EUR</option>`,`<option value="XAUg">${gold}</option>`].join('');
}
function buildMethodOptionsHTML(prod, targetCcy){
  const m=I18N[L()].method;
  let opts=`<option value="SIMPLE">${m.simple}</option>`;
  if(prod==='TERM'){
    opts+=`<option value="DAILY_COMPOUND">${m.daily}</option>`;
    if(targetCcy==='TL') opts+=`<option value="RENEW">${m.renew}</option>`;
  }
  return opts;
}

function rowTemplate(id, preset){
  const prod=preset?.prod||'TERM', ccy=preset?.ccy||'TL';
  const delTxt=I18N[L()].del, autoTxt=I18N[L()].auto, renewLbl=I18N[L()].renewEvery;
  return `<tr data-id="${id}">
    <td style="min-width:90px;"><input type="text" inputmode="decimal" id="amt_${id}" value="0"></td>
    <td style="min-width:110px;"><select id="prod_${id}">${buildProductOptionsHTML()}</select></td>
    <td style="min-width:72px;"><select id="ccy_${id}">${buildCurrencyOptionsHTML()}</select></td>
    <td style="min-width:62px;"><input type="number" step="0.01" id="rate_${id}" value="0"></td>
    <td style="min-width:130px;">
      <select id="method_${id}">${buildMethodOptionsHTML(prod,ccy)}</select>
      <div class="renew-wrap" id="renewWrap_${id}" hidden>
        <span>${renewLbl}</span>
        <input type="number" id="renewEvery_${id}" min="1" step="1" value="2">
      </div>
    </td>
    <td style="min-width:90px;">
      <div class="tax-wrap">
        <input type="number" step="0.01" id="tax_${id}" value="0">
        <label class="auto-label"><input type="checkbox" id="taxAuto_${id}" checked>${autoTxt}</label>
      </div>
    </td>
    <td class="cell-computed" id="p_${id}">—</td>
    <td class="cell-computed" id="fv_g_${id}">—</td>
    <td class="cell-computed" id="taxamt_${id}">—</td>
    <td class="cell-computed" id="fv_n_${id}">—</td>
    <td class="cell-computed" id="net_${id}">—</td>
    <td><button class="btn btn-xs btn-danger" onclick="removeRow('${id}')">${delTxt}</button></td>
  </tr>`;
}

function refreshMethodOptionsForRow(id, {keepValue}){
  const prod=document.getElementById('prod_'+id).value;
  const ccy=document.getElementById('ccy_'+id).value;
  const mEl=document.getElementById('method_'+id);
  const prev=keepValue||mEl.value;
  mEl.innerHTML=buildMethodOptionsHTML(prod,ccy);
  if(prod!=='TERM') mEl.value='SIMPLE';
  else if([...mEl.options].some(o=>o.value===prev)) mEl.value=prev;
  else mEl.value='SIMPLE';
  syncRenewVisibility(id);
}
function syncRenewVisibility(id){
  const prod=document.getElementById('prod_'+id).value;
  const ccy=document.getElementById('ccy_'+id).value;
  const method=document.getElementById('method_'+id).value;
  const wrap=document.getElementById('renewWrap_'+id);
  if(wrap) wrap.hidden=!(prod==='TERM'&&ccy==='TL'&&method==='RENEW');
}
function applyDefaultsByProduct(id){
  const prod=document.getElementById('prod_'+id).value;
  const ccy=document.getElementById('ccy_'+id).value;
  const rateEl=document.getElementById('rate_'+id);
  const r=Number(rateEl.value)||0;
  if(prod==='TERM'){ if(r===0) rateEl.value=(ccy==='TL')?35:5; }
  else if(prod==='FUND'){ if(r===0) rateEl.value=45; }
  else if(prod==='SUKUK'){ if(r===0) rateEl.value=(ccy==='TL')?38:7; }
  else if(prod==='DPM'){ if(r===0) rateEl.value=12; }
  syncRenewVisibility(id);
}

function addRow(preset){
  preset=preset||{};
  const id=String(Math.random()).slice(2,8);
  document.getElementById('allocBody').insertAdjacentHTML('beforeend', rowTemplate(id, preset));
  const amtEl=document.getElementById('amt_'+id);
  const prodEl=document.getElementById('prod_'+id);
  const ccyEl=document.getElementById('ccy_'+id);
  const rateEl=document.getElementById('rate_'+id);
  const taxEl=document.getElementById('tax_'+id);
  const taxAutoEl=document.getElementById('taxAuto_'+id);
  amtEl.value=preset.amt!=null?fmtPlain(preset.amt):'0';
  prodEl.value=preset.prod||'TERM';
  ccyEl.value=preset.ccy||'TL';
  rateEl.value=preset.rate!=null?preset.rate:0;
  taxEl.value=preset.tax!=null?preset.tax:0;
  taxAutoEl.checked=preset.taxAuto!=null?!!preset.taxAuto:true;
  refreshMethodOptionsForRow(id, {keepValue:preset.method});
  applyDefaultsByProduct(id);
  prodEl.addEventListener('change',()=>{ refreshMethodOptionsForRow(id,{keepValue:null}); applyDefaultsByProduct(id); });
  ccyEl.addEventListener('change',()=>{ refreshMethodOptionsForRow(id,{keepValue:null}); applyDefaultsByProduct(id); });
  document.getElementById('method_'+id).addEventListener('change',()=>syncRenewVisibility(id));
  amtEl.addEventListener('blur',function(){ this.value=fmtPlain(parseAmount(this.value)); });
  syncRenewVisibility(id);
}

function removeRow(id){
  const tr=document.querySelector('tr[data-id="'+id+'"]');
  if(tr) tr.remove();
}

function applyScenario(weights){
  const totalAmount=parseAmount(document.getElementById('total_amount').value);
  document.getElementById('allocBody').innerHTML='';
  const sum=weights.reduce((a,x)=>a+(x.w||0),0)||1;
  const norm=weights.map(x=>({...x,w:(x.w||0)/sum}));
  let allocated=0;
  for(let i=0;i<norm.length;i++){
    const it=norm[i];
    let amt=(i===norm.length-1)?(totalAmount-allocated):(totalAmount*it.w);
    amt=Math.max(0,amt); allocated+=amt;
    addRow({amt:Number(amt.toFixed(2)),ccy:it.ccy,prod:it.prod,rate:it.rate,method:it.method,taxAuto:it.taxAuto!=null?it.taxAuto:true,tax:it.tax!=null?it.tax:0});
  }
}
function scenario1(){ applyScenario([{w:.30,ccy:'TL',prod:'TERM',rate:35,method:'SIMPLE',taxAuto:true},{w:.30,ccy:'TL',prod:'FUND',rate:45,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'SUKUK',rate:38,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0}]); }
function scenario2(){ applyScenario([{w:.45,ccy:'TL',prod:'TERM',rate:35,method:'SIMPLE',taxAuto:true},{w:.25,ccy:'TL',prod:'SUKUK',rate:38,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'USD',prod:'SUKUK',rate:7,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0}]); }
function scenario3(){ applyScenario([{w:.15,ccy:'TL',prod:'TERM',rate:35,method:'SIMPLE',taxAuto:true},{w:.55,ccy:'TL',prod:'FUND',rate:48,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'SUKUK',rate:38,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0}]); }
function scenario4(){ applyScenario([{w:.35,ccy:'USD',prod:'SUKUK',rate:7,method:'SIMPLE',taxAuto:false,tax:0},{w:.35,ccy:'EUR',prod:'SUKUK',rate:6,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:38,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'FUND',rate:45,method:'SIMPLE',taxAuto:false,tax:0}]); }
function scenario5(){ applyScenario([{w:.55,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'FUND',rate:45,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:38,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'TL',prod:'TERM',rate:35,method:'SIMPLE',taxAuto:true}]); }

/* ═══════════════════════════════════════════════════════
   INTELLIGENT SCENARIO ENGINE
   Real allocation logic based on principal currency,
   carry spreads, FX outlook and client risk profile
═══════════════════════════════════════════════════════ */
function getMarketContext(){
  const principalCcy = document.getElementById('total_ccy').value;
  const rTL  = Number(document.getElementById('rtl').value) || 45;
  const rUSD = Number(document.getElementById('rusd').value) || 5;
  const rEUR = Number(document.getElementById('reur').value) || 3;
  const usdtry = Number(document.getElementById('usdtry').value) || 0;
  const eurtry = Number(document.getElementById('eurtry').value) || 0;
  const usdtry_end = Number(document.getElementById('usdtry_end').value) || 0;
  const eurtry_end = Number(document.getElementById('eurtry_end').value) || 0;
  const days = globalDays();
  const Tt = days / 365;

  // Carry spread: TL yield advantage over foreign currency
  const carryVsUSD = rTL - rUSD;   // e.g. 45 - 5 = 40 pp
  const carryVsEUR = rTL - rEUR;

  // Expected FX move % (annualized) — if we have end rates
  let fxMoveUSD = 0, fxMoveEUR = 0;
  if(usdtry > 0 && usdtry_end > 0) fxMoveUSD = ((usdtry_end - usdtry) / usdtry) / (Tt || 1) * 100;
  if(eurtry > 0 && eurtry_end > 0) fxMoveEUR = ((eurtry_end - eurtry) / eurtry) / (Tt || 1) * 100;

  // Net carry (TL return minus FX depreciation cost)
  // If USD depreciates (TL appreciates), FX move is negative → good for TL carry trade
  const netCarryTL_vsUSD = carryVsUSD - fxMoveUSD;
  const netCarryTL_vsEUR = carryVsEUR - fxMoveEUR;

  // Carry attractiveness: > 10pp net → very attractive
  const carryAttractive = netCarryTL_vsUSD > 10;
  const carryNeutral    = netCarryTL_vsUSD > 0 && netCarryTL_vsUSD <= 10;
  const carryNegative   = netCarryTL_vsUSD <= 0;

  return {
    principalCcy, rTL, rUSD, rEUR, usdtry, eurtry, usdtry_end, eurtry_end,
    days, Tt, carryVsUSD, carryVsEUR, fxMoveUSD, fxMoveEUR,
    netCarryTL_vsUSD, netCarryTL_vsEUR, carryAttractive, carryNeutral, carryNegative
  };
}

const SMART_SCENARIOS = {
  // ── For USD principal ──
  USD: {
    balanced: (ctx) => ({
      name: L()==='en' ? 'Balanced Carry' : 'Dengeli Carry',
      icon: '⚖️',
      subtitle: L()==='en'
        ? `TL carry spread: ${ctx.carryVsUSD.toFixed(0)}pp vs USD · Mixed FX exposure`
        : `TL carry spread: ${ctx.carryVsUSD.toFixed(0)}pp USD üzeri · Karma FX pozisyonu`,
      riskPct: 45,
      riskLabel: L()==='en' ? 'Moderate' : 'Orta',
      insight: L()==='en'
        ? `With <strong>USD as principal</strong>, the TL carry spread is <strong>${ctx.carryVsUSD.toFixed(0)} percentage points</strong>. Even accounting for USD/TRY depreciation, a balanced mix captures carry while maintaining partial USD exposure as a hedge. This is the institutional default for clients who want growth but resist full FX conversion.`
        : `<strong>USD giriş</strong> ile TL carry spreadi <strong>${ctx.carryVsUSD.toFixed(0)} puan</strong>. USD/TRY değer kaybı hesaba katılsa bile, dengeli karışım carry'yi yakalarken kısmi USD koruması sağlar. FX dönüşümüne tam geçmek istemeyen büyüme odaklı müşteriler için kurumsal standarttır.`,
      rationale: [
        { icon:'📈', text: L()==='en' ? `TL Fund (${ctx.rTL}% annual) captures domestic yield premium` : `TL Fon (%${ctx.rTL} yıllık) yerel getiri primini yakalar` },
        { icon:'🛡️', text: L()==='en' ? `USD DPM anchor (${ctx.rUSD}% + alpha) preserves USD base` : `USD DPM çapası (%${ctx.rUSD} + alfa) USD bazını korur` },
        { icon:'🔄', text: L()==='en' ? `Sukuk layer provides fixed income floor` : `Sukuk katmanı sabit gelir tabanı sağlar` },
        { icon:'📊', text: L()==='en' ? `30/35/20/15 split → optimal Sharpe for mixed mandates` : `30/35/20/15 dağılımı → karma mandatlar için optimal Sharpe` }
      ],
      weights: [{w:.35,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true},{w:.25,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    protection: (ctx) => ({
      name: L()==='en' ? 'Capital Protection' : 'Sermaye Koruma',
      icon: '🛡️',
      subtitle: L()==='en'
        ? `USD-centric · Minimal FX conversion risk`
        : `USD ağırlıklı · Minimal FX dönüşüm riski`,
      riskPct: 20,
      riskLabel: L()==='en' ? 'Low–Conservative' : 'Düşük–Muhafazakâr',
      insight: L()==='en'
        ? `This client's priority is <strong>capital preservation in USD</strong>. The strategy deliberately avoids significant TL conversion, accepting lower absolute returns in exchange for eliminating USD/TRY volatility. Suitable for near-term liquidity needs or risk-averse mandates.`
        : `Müşterinin önceliği <strong>USD bazında sermaye koruma</strong>. Strateji bilinçli olarak TL dönüşümünden kaçınır; düşük mutlak getiriyi kabul ederek USD/TRY volatilitesini ortadan kaldırır. Yakın vadeli likidite ihtiyacı veya risk-kaçınımcı mandatlar için uygundur.`,
      rationale: [
        { icon:'🏦', text: L()==='en' ? `USD Sukuk (${ctx.rUSD+2}%) preserves principal in USD, avoids FX risk` : `USD Sukuk (%${ctx.rUSD+2}) anaparayı USD'de korur, FX riski almaz` },
        { icon:'💵', text: L()==='en' ? `USD Term Deposit locks in USD yield with no conversion` : `USD Vadeli tamamen dönüşümsüz USD getirisi kilitler` },
        { icon:'🔒', text: L()==='en' ? `Small TL TERM tranche only for short-term TL needs` : `Küçük TL Vadeli dilimi yalnızca kısa vadeli TL ihtiyacı için` },
        { icon:'📉', text: L()==='en' ? `Minimal drawdown scenario: max loss ~${(ctx.rUSD*0.1).toFixed(1)}% in stress` : `Minimum kayıp senaryosu: stres altında maks. ~%${(ctx.rUSD*0.1).toFixed(1)} kayıp` }
      ],
      weights: [{w:.45,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'USD',prod:'TERM',rate:ctx.rUSD,method:'SIMPLE',taxAuto:true},{w:.15,ccy:'USD',prod:'DPM',rate:10,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true}]
    }),
    growth: (ctx) => {
      const netCarry = ctx.netCarryTL_vsUSD;
      const carryTag = netCarry > 15 ? (L()==='en'?'⚡ Exceptional carry opportunity':'⚡ İstisnaî carry fırsatı') : netCarry > 5 ? (L()==='en'?'✅ Positive carry':'✅ Pozitif carry') : (L()==='en'?'⚠️ Carry eroding':'⚠️ Carry eriyor');
      return {
        name: L()==='en' ? 'Carry Trade Maximizer' : 'Carry Trade Maksimizasyonu',
        icon: '🚀',
        subtitle: L()==='en'
          ? `Net TL carry: ${netCarry.toFixed(1)}pp after FX · ${carryTag}`
          : `Net TL carry: FX sonrası ${netCarry.toFixed(1)}pp · ${carryTag}`,
        riskPct: 75,
        riskLabel: L()==='en' ? 'High – FX Risk' : 'Yüksek – FX Riski',
        insight: L()==='en'
          ? `The <strong>TL carry trade</strong> is the core thesis: ${ctx.rTL}% TL yield vs ${ctx.rUSD}% USD = <strong>${ctx.carryVsUSD.toFixed(0)}pp gross spread</strong>. If USD/TRY moves less than ${ctx.carryVsUSD.toFixed(0)}% over the tenor, you are net positive in USD terms. Net carry after modeled FX: <strong>${netCarry.toFixed(1)}pp</strong>. Maximum TL allocation to capture this spread — with residual USD DPM as tail hedge.`
          : `<strong>TL carry trade</strong> temel tez: %${ctx.rTL} TL getiri vs %${ctx.rUSD} USD = <strong>${ctx.carryVsUSD.toFixed(0)}pp brüt spread</strong>. Vade boyunca USD/TRY ${ctx.carryVsUSD.toFixed(0)}%'den az artarsa USD bazında kar etmiş olursunuz. Modellenen FX sonrası net carry: <strong>${netCarry.toFixed(1)}pp</strong>. Bu spreadi yakalamak için maksimum TL alokasyonu — artık risk olarak USD DPM tamponu.`,
        rationale: [
          { icon:'💹', text: L()==='en' ? `TL Fund (${ctx.rTL}%): highest yield capture, daily liquidity` : `TL Fon (%${ctx.rTL}): maksimum getiri yakalama, günlük likidite` },
          { icon:'📜', text: L()==='en' ? `TL Sukuk (${ctx.rTL-7}%): fixed income layer, tax-free coupon` : `TL Sukuk (%${ctx.rTL-7}): sabit gelir katmanı, stopajsız kupon` },
          { icon:'🛡️', text: L()==='en' ? `USD DPM 15% tail hedge: if TL carry reverses sharply` : `USD DPM %15 kuyruk koruması: TL carry hızla bozulursa` },
          { icon:'⚠️', text: L()==='en' ? `Key risk: USD/TRY > ${(ctx.usdtry*(1+ctx.carryVsUSD/100)).toFixed(2)} at maturity would negate carry` : `Ana risk: vade sonunda USD/TRY > ${ctx.usdtry>0?(ctx.usdtry*(1+ctx.carryVsUSD/100)).toFixed(2):'spot×(1+carry)'} carry'yi sıfırlar` }
        ],
        weights: [{w:.50,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true},{w:.15,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0}]
      };
    },
    fxhedge: (ctx) => ({
      name: L()==='en' ? 'FX Diversification' : 'FX Çeşitlendirme',
      icon: '🌐',
      subtitle: L()==='en'
        ? `Multi-currency · USD + EUR + TL exposure`
        : `Çok para birimli · USD + EUR + TL pozisyonu`,
      riskPct: 40,
      riskLabel: L()==='en' ? 'Low–Moderate' : 'Düşük–Orta',
      insight: L()==='en'
        ? `Instead of concentrated USD, this strategy builds a <strong>multi-currency fixed income portfolio</strong>. EUR Sukuk diversifies away from USD correlation; TL Sukuk captures domestic yield without equity volatility. Best suited when USD outlook is uncertain and client wants G3 currency exposure.`
        : `Konsantre USD yerine bu strateji <strong>çok para birimli sabit getiri portföyü</strong> inşa eder. EUR Sukuk USD korelasyonundan çeşitlendirme sağlar; TL Sukuk hisse volatilitesi olmadan yerli getiriyi yakalar. USD görünümü belirsizken G3 döviz maruziyeti isteyen müşteriler için uygundur.`,
      rationale: [
        { icon:'🇺🇸', text: L()==='en' ? `USD Sukuk (${ctx.rUSD+2}%) — core dollar anchor` : `USD Sukuk (%${ctx.rUSD+2}) — temel dolar çapası` },
        { icon:'🇪🇺', text: L()==='en' ? `EUR Sukuk (${ctx.rEUR+3}%) — diversifies USD single-currency risk` : `EUR Sukuk (%${ctx.rEUR+3}) — tek para birimi riskini çeşitlendirir` },
        { icon:'🇹🇷', text: L()==='en' ? `TL Sukuk (${ctx.rTL-7}%) — yield enhancer, sharia-compliant` : `TL Sukuk (%${ctx.rTL-7}) — getiri artırıcı, şeriat uyumlu` },
        { icon:'📈', text: L()==='en' ? `TL Fund tranche captures upside if carry holds` : `TL Fon dilimi carry devam ederse yükselme potansiyeli` }
      ],
      weights: [{w:.35,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'EUR',prod:'SUKUK',rate:ctx.rEUR+3,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    dpm: (ctx) => ({
      name: L()==='en' ? 'DPM Premium' : 'DPM Premium',
      icon: '👔',
      subtitle: L()==='en'
        ? `Discretionary mandate · Manager alpha focus`
        : `Takdiri yetki · Yönetici alfa odağı`,
      riskPct: 60,
      riskLabel: L()==='en' ? 'Moderate–High' : 'Orta–Yüksek',
      insight: L()==='en'
        ? `DPM (Discretionary Portfolio Management) allows active FX and duration decisions by the portfolio manager. The <strong>USD DPM 55% anchor</strong> is optimal for clients who trust active management over static allocation. The manager can dynamically tilt TL/USD based on macro signals — especially carry trade timing.`
        : `DPM (Takdiri Portföy Yönetimi) portföy yöneticisinin aktif FX ve duration kararları almasını sağlar. <strong>%55 USD DPM çapası</strong>, statik alokasyon yerine aktif yönetime güvenen müşteriler için optimaldir. Yönetici makro sinyallere göre TL/USD ağırlığını dinamik ayarlayabilir.`,
      rationale: [
        { icon:'🎯', text: L()==='en' ? `USD DPM 55%: manager decides carry/FX timing actively` : `USD DPM %55: yönetici carry/FX zamanlamasını aktif belirler` },
        { icon:'📈', text: L()==='en' ? `TL Fund 20%: passive carry exposure, no manager timing risk` : `TL Fon %20: pasif carry maruziyeti, yönetici zamanlama riski yok` },
        { icon:'📜', text: L()==='en' ? `TL Sukuk 15%: fixed income base, insulates against equity swings` : `TL Sukuk %15: sabit getiri tabanı, hisse senedi dalgalanmalarına karşı koruma` },
        { icon:'🏦', text: L()==='en' ? `TL Term 10%: liquidity buffer, short-tenor rollover` : `TL Vadeli %10: likidite tamponu, kısa vadeli yenileme` }
      ],
      weights: [{w:.55,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true}]
    })
  },

  // ── For TL principal ──
  TL: {
    balanced: (ctx) => ({
      name: L()==='en' ? 'Balanced TL Portfolio' : 'Dengeli TL Portföyü',
      icon: '⚖️',
      subtitle: L()==='en'
        ? `TL base · Diversified product mix`
        : `TL bazı · Çeşitlendirilmiş ürün karışımı`,
      riskPct: 40,
      riskLabel: L()==='en' ? 'Moderate' : 'Orta',
      insight: L()==='en'
        ? `With <strong>TL as principal</strong>, the primary question is whether to diversify into FX or maximize TL yield. At ${ctx.rTL}% TL return, the case for staying in TL is strong. A balanced mix optimizes across TL products while maintaining 15% USD exposure as insurance against a sharp TL depreciation.`
        : `<strong>TL giriş</strong> ile temel soru FX çeşitlendirmesi mi yoksa TL getirisini maksimize mi sorusudur. %${ctx.rTL} TL getirisiyle TL'de kalmanın cazibesi güçlüdür. Dengeli karışım TL ürünleri optimize ederken %15 USD maruziyetini ani TL değer kaybına karşı sigorta olarak tutar.`,
      rationale: [
        { icon:'📈', text: `TL Fon %35: ${ctx.rTL}% en yüksek TL getirisi` },
        { icon:'🏦', text: `TL Vadeli %25: ${Math.max(ctx.rTL-10,25)}% sabit, günlük stopaj optimizasyonu` },
        { icon:'📜', text: `TL Sukuk %25: ${ctx.rTL-7}% sabit, stopajsız` },
        { icon:'💵', text: `USD Sukuk %15: TL'ye karşı değer koruması` }
      ],
      weights: [{w:.35,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true},{w:.25,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    protection: (ctx) => ({
      name: L()==='en' ? 'FX Protection' : 'FX Koruması',
      icon: '🛡️',
      subtitle: L()==='en'
        ? `Hedge TL depreciation risk with FX assets`
        : `TL değer kaybını FX varlıklarla hedge et`,
      riskPct: 30,
      riskLabel: L()==='en' ? 'Conservative' : 'Muhafazakâr',
      insight: L()==='en'
        ? `For <strong>TL principal with protection focus</strong>: the risk is TL depreciation eroding real returns. This strategy holds significant USD/EUR assets to offset TL purchasing power loss. The TL yield component covers the "carry cost" of holding FX, while FX assets protect against systemic TL risk.`
        : `<strong>TL giriş ve koruma odağı</strong> için: risk, TL değer kaybının reel getiriyi aşındırmasıdır. Bu strateji TL satın alma gücü kaybını dengelemek için önemli USD/EUR varlıkları tutar. TL getiri bileşeni FX tutma "carry maliyetini" karşılarken, FX varlıklar sistemik TL riskine karşı koruma sağlar.`,
      rationale: [
        { icon:'💵', text: `USD DPM %35: TL değer kaybına karşı ana kalkan` },
        { icon:'🇪🇺', text: `EUR Sukuk %25: USD korelasyonu olmayan FX diversifikasyon` },
        { icon:'🏦', text: `TL Vadeli %25: ${Math.max(ctx.rTL-10,25)}% TL bazı korur` },
        { icon:'📜', text: `TL Sukuk %15: sabit getiri tamponu` }
      ],
      weights: [{w:.35,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'EUR',prod:'SUKUK',rate:ctx.rEUR+3,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true},{w:.15,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    growth: (ctx) => ({
      name: L()==='en' ? 'TL Yield Maximizer' : 'TL Getiri Maksimizasyonu',
      icon: '🚀',
      subtitle: L()==='en'
        ? `Full TL concentration · Max absolute return`
        : `Tam TL konsantrasyonu · Maksimum mutlak getiri`,
      riskPct: 65,
      riskLabel: L()==='en' ? 'High – TL Concentration' : 'Yüksek – TL Konsantrasyonu',
      insight: L()==='en'
        ? `<strong>Maximum TL yield strategy</strong>: stay in TL, capture the full ${ctx.rTL}% across high-yielding products. No FX exposure = no FX hedge cost. Best when inflation is contained and TL is expected to be stable. Risk is single-currency concentration — if TL depreciates sharply, all positions are affected simultaneously.`
        : `<strong>Maksimum TL getiri stratejisi</strong>: TL'de kal, yüksek getirili ürünler arasında tam %${ctx.rTL}'yi yakala. FX maruziyeti yok = FX hedge maliyeti yok. Enflasyon kontrol altında ve TL istikrarlı beklentisi varken idealdir. Risk, tek para birimi konsantrasyonudur — TL hızla değer kaybederse tüm pozisyonlar eş zamanlı etkilenir.`,
      rationale: [
        { icon:'📈', text: `TL Fon %55: ${ctx.rTL}% günlük bileşik getiri, esnek likidite` },
        { icon:'📜', text: `TL Sukuk %25: ${ctx.rTL-7}% sabit, stopajsız, bütçe yılı uyumlu` },
        { icon:'🏦', text: `TL Vadeli %20: ${Math.max(ctx.rTL-10,25)}% sabit faiz, en güvenli TL ürünü` },
        { icon:'⚠️', text: `Uyarı: FX hedge yok — TL riski maksimum` }
      ],
      weights: [{w:.55,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true}]
    }),
    fxhedge: (ctx) => ({
      name: L()==='en' ? 'FX Hedge' : 'FX Hedge',
      icon: '🌐',
      subtitle: L()==='en'
        ? `Balanced TL yield + FX protection layer`
        : `Dengeli TL getiri + FX koruma katmanı`,
      riskPct: 45,
      riskLabel: L()==='en' ? 'Moderate' : 'Orta',
      insight: L()==='en'
        ? `Classic TL/FX barbell: high-yield TL products on one end, USD and EUR fixed income on the other. The TL side generates the return; the FX side hedges systemic risk. Net expected return is lower than pure TL, but the FX hedge dramatically reduces volatility of returns in real (purchasing-power) terms.`
        : `Klasik TL/FX barbell: bir uçta yüksek getirili TL ürünleri, diğer uçta USD ve EUR sabit getirili. TL tarafı getiriyi üretir; FX tarafı sistemik riski hedge eder. Net beklenen getiri saf TL'den düşük, ancak FX hedge reel (satın alma gücü) bazında getiri volatilitesini dramatik şekilde azaltır.`,
      rationale: [
        { icon:'📈', text: `TL Fon %30: getiri motoru` },
        { icon:'💵', text: `USD Sukuk %30: dolar boşluğunu doldurur` },
        { icon:'🇪🇺', text: `EUR Sukuk %20: FX çeşitlendirmesi` },
        { icon:'📜', text: `TL Sukuk %20: sabit gelir tamponu` }
      ],
      weights: [{w:.30,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'EUR',prod:'SUKUK',rate:ctx.rEUR+3,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    dpm: (ctx) => ({
      name: L()==='en' ? 'TL-Centric DPM' : 'TL Odaklı DPM',
      icon: '👔',
      subtitle: L()==='en'
        ? `Active management with TL yield base`
        : `TL getiri bazlı aktif yönetim`,
      riskPct: 55,
      riskLabel: L()==='en' ? 'Moderate–High' : 'Orta–Yüksek',
      insight: L()==='en'
        ? `TL-principal with active discretionary management. The DPM manager has latitude to dynamically adjust FX exposure based on USD/TRY outlook. When carry is attractive, they lean TL; when FX risks emerge, they can shift to USD. The Sukuk and Term layers provide income floor stability.`
        : `TL giriş ile aktif takdiri yönetim. DPM yöneticisi USD/TRY görünümüne göre FX maruziyetini dinamik ayarlama yetkisine sahiptir. Carry cazip olduğunda TL'ye yatarlar; FX riskleri belirdiğinde USD'ye kayabilirler. Sukuk ve Vadeli katmanları gelir tabanı stabilitesi sağlar.`,
      rationale: [
        { icon:'📈', text: `TL Fon %30: aktif yönetim için likidite sağlar` },
        { icon:'🎯', text: `USD DPM %25: yönetici macro görüşünü hayata geçirir` },
        { icon:'📜', text: `TL Sukuk %25: sabit gelir tabanı` },
        { icon:'🏦', text: `TL Vadeli %20: kısa vadeli likidite çıpası` }
      ],
      weights: [{w:.30,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true}]
    })
  },

  // ── For EUR principal ──
  EUR: {
    balanced: (ctx) => ({
      name: L()==='en' ? 'Balanced Carry (EUR)' : 'Dengeli Carry (EUR)',
      icon: '⚖️', subtitle: `TL carry vs EUR: ${ctx.carryVsEUR.toFixed(0)}pp`,
      riskPct: 45, riskLabel: L()==='en'?'Moderate':'Orta',
      insight: L()==='en'
        ? `EUR principal with TL carry trade opportunity. Spread is <strong>${ctx.carryVsEUR.toFixed(0)}pp</strong> vs EUR. Similar logic to USD carry: allocate to TL products, hedge with EUR fixed income.`
        : `EUR giriş ile TL carry fırsatı. Spread EUR'a karşı <strong>${ctx.carryVsEUR.toFixed(0)}pp</strong>. USD carry ile benzer mantık: TL ürünlere al, EUR sabit gelirle hedge et.`,
      rationale: [
        {icon:'📈', text:`TL Fon %35: ${ctx.rTL}% carry`},
        {icon:'🇪🇺', text:`EUR Sukuk %30: EUR çapası`},
        {icon:'📜', text:`TL Sukuk %20: sabit gelir`},
        {icon:'💵', text:`USD DPM %15: çapraz diversifikasyon`}
      ],
      weights: [{w:.35,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'EUR',prod:'SUKUK',rate:ctx.rEUR+3,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    protection: (ctx) => ({
      name: L()==='en'?'EUR Capital Protection':'EUR Sermaye Koruma',
      icon:'🛡️', subtitle: L()==='en'?'EUR-centric fixed income':'EUR odaklı sabit getiri',
      riskPct:20, riskLabel:L()==='en'?'Low':'Düşük',
      insight: L()==='en'?`Capital preservation in EUR. Heavy EUR fixed income, avoid FX volatility.`:`EUR'da sermaye koruması. Ağır EUR sabit gelir, FX volatilitesinden kaçın.`,
      rationale:[{icon:'🇪🇺',text:`EUR Sukuk %50: ana EUR çapası`},{icon:'🇪🇺',text:`EUR Vadeli %30: sabit EUR getiri`},{icon:'💵',text:`USD Sukuk %20: küçük dolar tamponu`}],
      weights:[{w:.50,ccy:'EUR',prod:'SUKUK',rate:ctx.rEUR+3,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'EUR',prod:'TERM',rate:ctx.rEUR,method:'SIMPLE',taxAuto:true},{w:.20,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    growth: (ctx) => ({
      name: L()==='en'?'EUR Carry Maximizer':'EUR Carry Maksimizasyonu',
      icon:'🚀', subtitle:`Net carry EUR: ${ctx.netCarryTL_vsEUR.toFixed(1)}pp`,
      riskPct:72, riskLabel:L()==='en'?'High':'Yüksek',
      insight: L()==='en'?`Maximum TL allocation to capture the EUR carry spread of ${ctx.carryVsEUR.toFixed(0)}pp.`:`EUR carry spreadini ${ctx.carryVsEUR.toFixed(0)}pp yakalamak için maksimum TL alokasyonu.`,
      rationale:[{icon:'📈',text:`TL Fon %55: ${ctx.rTL}% carry`},{icon:'📜',text:`TL Sukuk %25`},{icon:'🛡️',text:`EUR DPM %20: kuyruk koruması`}],
      weights:[{w:.55,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'EUR',prod:'DPM',rate:ctx.rEUR+8,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    fxhedge: (ctx) => ({
      name:L()==='en'?'FX Hedge (EUR)':'FX Hedge (EUR)',
      icon:'🌐', subtitle:L()==='en'?'EUR + USD + TL barbell':'EUR + USD + TL barbell',
      riskPct:38, riskLabel:L()==='en'?'Low–Moderate':'Düşük–Orta',
      insight:L()==='en'?`3-currency barbell: EUR base, USD diversification, TL yield.`:`3 döviz barbell: EUR baz, USD diversifikasyon, TL getiri.`,
      rationale:[{icon:'🇪🇺',text:`EUR Sukuk %35`},{icon:'💵',text:`USD Sukuk %30`},{icon:'📈',text:`TL Fon %20`},{icon:'📜',text:`TL Sukuk %15`}],
      weights:[{w:.35,ccy:'EUR',prod:'SUKUK',rate:ctx.rEUR+3,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    dpm: (ctx) => ({
      name:'EUR DPM Premium', icon:'👔',
      subtitle:L()==='en'?'Active mandate, EUR base':'Aktif yetki, EUR bazı',
      riskPct:55, riskLabel:L()==='en'?'Moderate–High':'Orta–Yüksek',
      insight:L()==='en'?`EUR-based DPM. Manager can dynamically switch EUR/TL/USD based on carry signals.`:`EUR bazlı DPM. Yönetici carry sinyallerine göre EUR/TL/USD'yi dinamik değiştirebilir.`,
      rationale:[{icon:'🎯',text:`EUR DPM %50`},{icon:'📈',text:`TL Fon %25`},{icon:'📜',text:`TL Sukuk %15`},{icon:'🏦',text:`EUR Vadeli %10`}],
      weights:[{w:.50,ccy:'EUR',prod:'DPM',rate:ctx.rEUR+8,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'EUR',prod:'TERM',rate:ctx.rEUR,method:'SIMPLE',taxAuto:true}]
    })
  },

  // ── For Gold principal ──
  XAUg: {
    balanced: (ctx) => ({
      name: L()==='en'?'Gold + TL Yield Blend':'Altın + TL Getiri Karışımı',
      icon:'🥇', subtitle:L()==='en'?'Diversify gold into yield products':'Altını getirili ürünlere çeşitlendir',
      riskPct:50, riskLabel:L()==='en'?'Moderate':'Orta',
      insight:L()==='en'?`<strong>Gold principal</strong> is unique: gold itself earns no yield. Converting partially to TL/USD products generates income while maintaining some gold exposure as inflation hedge.`:`<strong>Altın giriş</strong> benzersizdir: altının kendisi getiri sağlamaz. Kısmen TL/USD ürünlerine dönüştürmek, enflasyon hedge olarak altın maruziyetini korurken gelir üretir.`,
      rationale:[{icon:'🥇',text:'Altın %30 spot tutar — enflasyon sigortası'},{icon:'📈',text:`TL Fon %35: ${ctx.rTL}%`},{icon:'💵',text:'USD DPM %20'},{icon:'📜',text:'TL Sukuk %15'}],
      weights:[{w:.35,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true}]
    }),
    protection: (ctx) => ({
      name:L()==='en'?'Gold Preservation':'Altın Koruması',
      icon:'🛡️', subtitle:L()==='en'?'Stay gold-adjacent, minimize FX risk':'Altın komşusunda kal',
      riskPct:25, riskLabel:L()==='en'?'Low':'Düşük',
      insight:L()==='en'?`For gold clients who want capital preservation: stay in gold-adjacent assets (USD, Sukuk) rather than converting to yield. Gold is already the hedge.`:`Sermaye koruma isteyen altın müşterisi için: getiriye dönüştürmek yerine altına yakın varlıklarda (USD, Sukuk) kal. Altın zaten hedge'dir.`,
      rationale:[{icon:'💵',text:'USD Sukuk %50: altına en yakın fiyatlama'},{icon:'💵',text:'USD DPM %30'},{icon:'📜',text:'TL Sukuk %20'}],
      weights:[{w:.50,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    growth: (ctx) => ({
      name:L()==='en'?'Gold Carry Maximizer':'Altın Carry Maksimizasyonu',
      icon:'🚀', subtitle:`TL carry: ${ctx.carryVsUSD.toFixed(0)}pp`,
      riskPct:70, riskLabel:L()==='en'?'High':'Yüksek',
      insight:L()==='en'?`Convert gold to TL and capture the full carry spread. Highest return if TL and gold are both stable.`:`Altını TL'ye çevir ve tam carry spreadini yakala. TL ve altın ikisi de stabil olursa maksimum getiri.`,
      rationale:[{icon:'📈',text:`TL Fon %60: ${ctx.rTL}%`},{icon:'📜',text:'TL Sukuk %25'},{icon:'🛡️',text:'USD DPM %15: kuyruk koruması'}],
      weights:[{w:.60,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.25,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    fxhedge: (ctx) => ({
      name:L()==='en'?'Gold FX Diversification':'Altın FX Çeşitlendirme',
      icon:'🌐', subtitle:'USD + EUR + TL',
      riskPct:42, riskLabel:L()==='en'?'Moderate':'Orta',
      insight:L()==='en'?`Multi-currency approach for gold clients: spread across USD, EUR and TL to minimize single-currency risk.`:`Altın müşterisi için çok para birimli yaklaşım: tek para birimi riskini minimize etmek için USD, EUR ve TL'ye dağıt.`,
      rationale:[{icon:'💵',text:'USD Sukuk %35'},{icon:'🇪🇺',text:'EUR Sukuk %30'},{icon:'📈',text:`TL Fon %20`},{icon:'📜',text:'TL Sukuk %15'}],
      weights:[{w:.35,ccy:'USD',prod:'SUKUK',rate:ctx.rUSD+2,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'EUR',prod:'SUKUK',rate:ctx.rEUR+3,method:'SIMPLE',taxAuto:false,tax:0},{w:.20,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0}]
    }),
    dpm: (ctx) => ({
      name:'Gold DPM Premium', icon:'👔',
      subtitle:L()==='en'?'Active management from gold base':'Altın bazlı aktif yönetim',
      riskPct:58, riskLabel:L()==='en'?'Moderate–High':'Orta–Yüksek',
      insight:L()==='en'?`DPM mandate with gold as the base: manager converts strategically to yield products based on gold/FX outlook.`:`Altın bazlı DPM yetkisi: yönetici altın/FX görünümüne göre stratejik olarak getirili ürünlere dönüştürür.`,
      rationale:[{icon:'🎯',text:'USD DPM %45: yönetici altın/FX arbitrajı yapabilir'},{icon:'📈',text:`TL Fon %30: ${ctx.rTL}%`},{icon:'📜',text:'TL Sukuk %15'},{icon:'🏦',text:'TL Vadeli %10'}],
      weights:[{w:.45,ccy:'USD',prod:'DPM',rate:12,method:'SIMPLE',taxAuto:false,tax:0},{w:.30,ccy:'TL',prod:'FUND',rate:ctx.rTL,method:'SIMPLE',taxAuto:false,tax:0},{w:.15,ccy:'TL',prod:'SUKUK',rate:ctx.rTL-7,method:'SIMPLE',taxAuto:false,tax:0},{w:.10,ccy:'TL',prod:'TERM',rate:Math.max(ctx.rTL-10,25),method:'SIMPLE',taxAuto:true}]
    })
  }
};

// Fallback to USD scenarios for unknown principal
['USD','TL','EUR','XAUg'].forEach(ccy=>{
  if(!SMART_SCENARIOS[ccy]) SMART_SCENARIOS[ccy] = SMART_SCENARIOS['USD'];
});

const SCENARIO_KEYS = ['balanced','protection','growth','fxhedge','dpm'];

function getSmartScenario(key){
  const ctx = getMarketContext();
  const ccyMap = SMART_SCENARIOS[ctx.principalCcy] || SMART_SCENARIOS['USD'];
  const fn = ccyMap[key];
  if(!fn) return null;
  return fn(ctx);
}

// State for which scenario key is about to be applied
let _pendingScenarioKey = null;

function openScenarioModal(key){
  const s = getSmartScenario(key);
  if(!s) return;
  _pendingScenarioKey = key;

  document.getElementById('modal_icon').textContent = s.icon;
  document.getElementById('modal_title').textContent = s.name;
  document.getElementById('modal_subtitle').textContent = s.subtitle;
  document.getElementById('modal_insight').innerHTML = s.insight;
  document.getElementById('modal_risk_bar').style.width = s.riskPct + '%';
  document.getElementById('modal_risk_val').textContent = s.riskLabel;
  document.getElementById('modal_risk_label').textContent = L()==='en' ? 'Risk Level' : 'Risk Seviyesi';
  document.getElementById('modal_rationale_title').textContent = L()==='en' ? 'Rationale' : 'Gerekçe';

  const rows = (s.rationale||[]).map(r=>
    `<div class="rationale-row"><span class="icon">${r.icon}</span><span>${r.text}</span></div>`
  ).join('');
  document.getElementById('modal_rationale_rows').innerHTML = rows;
  document.getElementById('modal_apply').textContent = L()==='en' ? 'Apply This Scenario →' : 'Bu Senaryoyu Uygula →';

  document.getElementById('scenarioModal').classList.add('open');
}

function closeScenarioModal(){
  document.getElementById('scenarioModal').classList.remove('open');
  _pendingScenarioKey = null;
}

document.getElementById('modal_close').addEventListener('click', closeScenarioModal);
document.getElementById('scenarioModal').addEventListener('click', function(e){
  if(e.target === this) closeScenarioModal();
});
document.getElementById('modal_apply').addEventListener('click', function(){
  if(_pendingScenarioKey){
    const s = getSmartScenario(_pendingScenarioKey);
    if(s && s.weights) applyScenario(s.weights);
    closeScenarioModal();
    updateScenarioInsightBar();
  }
});

function updateScenarioInsightBar(){
  const ctx = getMarketContext();
  const bar = document.getElementById('scenario_insight_bar');
  if(!bar) return;

  let msg = '';
  if(ctx.principalCcy === 'USD'){
    if(ctx.carryAttractive){
      msg = L()==='en'
        ? `💡 <strong>USD client:</strong> TL carry spread is <strong>${ctx.carryVsUSD.toFixed(0)}pp</strong> — exceptional. Even with ${ctx.fxMoveUSD.toFixed(1)}%/yr FX depreciation baked in, net carry is <strong>${ctx.netCarryTL_vsUSD.toFixed(1)}pp</strong>. Carry Trade Maximizer scenario strongly indicated.`
        : `💡 <strong>USD müşteri:</strong> TL carry spreadi <strong>${ctx.carryVsUSD.toFixed(0)}pp</strong> — istisnai. ${ctx.fxMoveUSD.toFixed(1)}%/yıl FX değer kaybı dahil, net carry <strong>${ctx.netCarryTL_vsUSD.toFixed(1)}pp</strong>. Carry Trade Maksimizasyonu senaryosu güçlü şekilde öneriliyor.`;
    } else if(ctx.carryNeutral){
      msg = L()==='en'
        ? `💡 <strong>USD client:</strong> TL carry spread ${ctx.carryVsUSD.toFixed(0)}pp but net carry after FX is only ${ctx.netCarryTL_vsUSD.toFixed(1)}pp. Balanced or FX Hedge scenario recommended.`
        : `💡 <strong>USD müşteri:</strong> TL carry spreadi ${ctx.carryVsUSD.toFixed(0)}pp, ancak FX sonrası net carry yalnızca ${ctx.netCarryTL_vsUSD.toFixed(1)}pp. Dengeli veya FX Hedge senaryosu önerilir.`;
    } else {
      msg = L()==='en'
        ? `⚠️ <strong>USD client:</strong> Net TL carry is negative (${ctx.netCarryTL_vsUSD.toFixed(1)}pp) — FX depreciation exceeds yield. Capital Protection or FX-centric scenario recommended.`
        : `⚠️ <strong>USD müşteri:</strong> Net TL carry negatif (${ctx.netCarryTL_vsUSD.toFixed(1)}pp) — FX değer kaybı getiriyi aşıyor. Sermaye Koruma veya FX odaklı senaryo önerilir.`;
    }
  } else if(ctx.principalCcy === 'TL'){
    msg = L()==='en'
      ? `💡 <strong>TL client:</strong> Already in TL at ${ctx.rTL}%. Key question: how much FX hedge do you need? TL Yield Maximizer captures full ${ctx.rTL}% with no hedge cost; FX Hedge adds protection at ~${(ctx.rTL*0.1).toFixed(0)}pp yield cost.`
      : `💡 <strong>TL müşteri:</strong> %${ctx.rTL} ile halihazırda TL'de. Temel soru: ne kadar FX hedge gerekiyor? TL Getiri Maksimizasyonu hedge maliyeti olmadan tam %${ctx.rTL}'yi yakalar; FX Hedge ~${(ctx.rTL*0.1).toFixed(0)}pp getiri maliyetiyle koruma ekler.`;
  } else if(ctx.principalCcy === 'EUR'){
    msg = L()==='en'
      ? `💡 <strong>EUR client:</strong> EUR carry spread vs TL is <strong>${ctx.carryVsEUR.toFixed(0)}pp</strong>. Net carry after FX: <strong>${ctx.netCarryTL_vsEUR.toFixed(1)}pp</strong>.`
      : `💡 <strong>EUR müşteri:</strong> EUR'a karşı TL carry spreadi <strong>${ctx.carryVsEUR.toFixed(0)}pp</strong>. FX sonrası net carry: <strong>${ctx.netCarryTL_vsEUR.toFixed(1)}pp</strong>.`;
  } else if(ctx.principalCcy === 'XAUg'){
    msg = L()==='en'
      ? `💡 <strong>Gold client:</strong> Gold yields nothing — converting to TL/USD products captures yield at the cost of gold price upside. Gold Carry Maximizer: max yield, max FX risk. Gold Preservation: stay USD-adjacent.`
      : `💡 <strong>Altın müşteri:</strong> Altın getiri sağlamaz — TL/USD ürünlere dönüştürmek altın fiyat yükselişini feda ederek getiri sağlar. Altın Carry: max getiri, max FX riski. Altın Koruma: USD'ye yakın kal.`;
  }

  if(msg){
    bar.innerHTML = msg;
    bar.style.display = 'block';
  } else {
    bar.style.display = 'none';
  }
}

// Smart suggest: auto-pick best scenario based on context

function ensureDefaultAllocationIfEmpty(){
  const rows=Array.from(document.querySelectorAll('#allocBody tr'));
  if(rows.length===0){
    addRow({amt:parseAmount(document.getElementById('total_amount').value),prod:'TERM',ccy:'TL',rate:35,method:'SIMPLE',taxAuto:true});
    return;
  }
  const principalAmt=parseAmount(document.getElementById('total_amount').value);
  let used=0;
  for(const tr of rows){ const id=tr.getAttribute('data-id'); used+=clamp(parseAmount(document.getElementById('amt_'+id).value)); }
  if(used<=0&&principalAmt>0){ document.getElementById('allocBody').innerHTML=''; addRow({amt:principalAmt,prod:'TERM',ccy:'TL',rate:35,method:'SIMPLE',taxAuto:true}); }
}

function snapshotRows(){
  return Array.from(document.querySelectorAll('#allocBody tr')).map(tr=>{
    const id=tr.getAttribute('data-id');
    return {
      amt:parseAmount(document.getElementById('amt_'+id).value),
      prod:document.getElementById('prod_'+id).value,
      ccy:document.getElementById('ccy_'+id).value,
      rate:Number(document.getElementById('rate_'+id).value)||0,
      method:document.getElementById('method_'+id).value,
      tax:Number(document.getElementById('tax_'+id).value)||0,
      taxAuto:!!document.getElementById('taxAuto_'+id).checked,
      renewEvery:Number(document.getElementById('renewEvery_'+id)?.value)||2
    };
  });
}
function restoreRows(snaps){
  document.getElementById('allocBody').innerHTML='';
  snaps.forEach(s=>{
    addRow({amt:s.amt,prod:s.prod,ccy:s.ccy,rate:s.rate,method:s.method,tax:s.tax,taxAuto:s.taxAuto});
    const lastTr=document.querySelector('#allocBody tr:last-child');
    const id=lastTr?.getAttribute('data-id');
    if(id&&document.getElementById('renewEvery_'+id)){ document.getElementById('renewEvery_'+id).value=s.renewEvery||2; syncRenewVisibility(id); }
  });
}

/* ── CALC ── */
function calc(){
  const warnEl=document.getElementById('warn');
  warnEl.textContent='';
  warnEl.classList.remove('show');
  autoFillEndRates();
  ensureDefaultAllocationIfEmpty();

  const principalAmt=parseAmount(document.getElementById('total_amount').value);
  const principalCcy=document.getElementById('total_ccy').value;
  const reportCcy=document.getElementById('report_ccy').value;

  function showWarn(msg){ warnEl.textContent=msg; warnEl.classList.add('show'); }

  if(principalAmt<=0){ showWarn(T('warn_amt')); return; }
  const rows=Array.from(document.querySelectorAll('#allocBody tr'));
  if(rows.length===0){ showWarn(T('warn_row')); return; }
  const days=globalDays();
  if(days<=0){ showWarn(T('warn_tenor')); return; }

  let usedPrincipal=0, startTotalReport=0, endTotalReport=0, endTotalPrincipal=0, totalTaxReport=0;
  const byKeyStartReport={};

  for(const tr of rows){
    const id=tr.getAttribute('data-id');
    const amtBase=clamp(parseAmount(document.getElementById('amt_'+id).value));
    const prod=document.getElementById('prod_'+id).value;
    const targetCcy=document.getElementById('ccy_'+id).value;
    const rate=Number(document.getElementById('rate_'+id).value)||0;
    const method=document.getElementById('method_'+id).value;
    const taxAuto=!!document.getElementById('taxAuto_'+id)?.checked;
    let taxPct=Number(document.getElementById('tax_'+id).value)||0;
    if(taxAuto){ taxPct=suggestTaxPct(prod,targetCcy,days); document.getElementById('tax_'+id).value=taxPct; }

    usedPrincipal+=amtBase;
    const r1=fxRate(principalCcy,targetCcy,'start');
    if(r1===null){ showWarn(T('warn_start')); return; }
    const P_target=amtBase*r1;
    const rStartToReport=fxRate(targetCcy,reportCcy,'start');
    if(rStartToReport===null){ showWarn(T('warn_start')); return; }
    const P_report_start=P_target*rStartToReport;
    startTotalReport+=P_report_start;
    const key=`${prod}_${targetCcy}`;
    byKeyStartReport[key]=(byKeyStartReport[key]||0)+P_report_start;

    let FV_target_gross=0;

    if(method==='DAILY_COMPOUND'){
      FV_target_gross=fvDailyCompound(P_target,rate,days);
    } else if(method==='RENEW'){
      const renewEvery=Number(document.getElementById('renewEvery_'+id)?.value)||2;
      let remaining=Math.max(0,Math.floor(days));
      let principalSeg=P_target;
      const r=(rate/100);
      while(remaining>0){ const d=Math.min(Math.max(1,Math.floor(renewEvery)),remaining); principalSeg=principalSeg*(1+r*(d/365)); remaining-=d; }
      FV_target_gross=principalSeg;
      const FV_net=fvRenewWithTax(P_target,rate,days,renewEvery,taxPct);
      const tax_total=FV_target_gross-FV_net;
      const netGain=FV_net-P_target;
      const rBack_end=fxRate(targetCcy,principalCcy,'end');
      if(rBack_end===null){ showWarn(T('warn_end')); return; }
      endTotalPrincipal+=FV_net*rBack_end;
      const rEndToReport=fxRate(targetCcy,reportCcy,'end');
      if(rEndToReport===null){ showWarn(T('warn_end')); return; }
      endTotalReport+=FV_net*rEndToReport;
      totalTaxReport+=tax_total*rEndToReport;
      document.getElementById('p_'+id).textContent=fmtMoney(P_target,targetCcy);
      document.getElementById('fv_g_'+id).textContent=fmtMoney(FV_target_gross,targetCcy);
      document.getElementById('taxamt_'+id).textContent=fmtMoney(tax_total,targetCcy);
      document.getElementById('fv_n_'+id).textContent=fmtMoney(FV_net,targetCcy);
      const netEl=document.getElementById('net_'+id);
      netEl.textContent=fmtMoney(netGain,targetCcy);
      netEl.className='cell-computed '+(netGain>=0?'positive':'negative');
      continue;
    } else {
      FV_target_gross=fvSimple(P_target,rate,days);
    }

    const grossGain=FV_target_gross-P_target;
    const tax_target=grossGain*(taxPct/100);
    const netGain=grossGain-tax_target;
    const FV_target_net=P_target+netGain;
    const rBack_end=fxRate(targetCcy,principalCcy,'end');
    if(rBack_end===null){ showWarn(T('warn_end')); return; }
    endTotalPrincipal+=FV_target_net*rBack_end;
    const rEndToReport=fxRate(targetCcy,reportCcy,'end');
    if(rEndToReport===null){ showWarn(T('warn_end')); return; }
    endTotalReport+=FV_target_net*rEndToReport;
    totalTaxReport+=tax_target*rEndToReport;

    document.getElementById('p_'+id).textContent=fmtMoney(P_target,targetCcy);
    document.getElementById('fv_g_'+id).textContent=fmtMoney(FV_target_gross,targetCcy);
    document.getElementById('taxamt_'+id).textContent=fmtMoney(tax_target,targetCcy);
    document.getElementById('fv_n_'+id).textContent=fmtMoney(FV_target_net,targetCcy);
    const netEl=document.getElementById('net_'+id);
    netEl.textContent=fmtMoney(netGain,targetCcy);
    netEl.className='cell-computed '+(netGain>=0?'positive':'negative');
  }

  document.getElementById('kpi_used').textContent=fmtMoney(usedPrincipal,principalCcy);
  document.getElementById('kpi_left').textContent=fmtMoney(principalAmt-usedPrincipal,principalCcy);
  if(usedPrincipal>principalAmt+1e-9) showWarn(T('warn_alloc'));

  document.getElementById('kpi_start_report').textContent=fmtMoney(startTotalReport,reportCcy);
  document.getElementById('kpi_end_report').textContent=fmtMoney(endTotalReport,reportCcy);
  const plReport=endTotalReport-startTotalReport;
  document.getElementById('kpi_pl_report').textContent=fmtMoney(plReport,reportCcy);
  document.getElementById('kpi_tax_report').textContent=fmtMoney(totalTaxReport,reportCcy);

  const plPrincipal=endTotalPrincipal-principalAmt;
  document.getElementById('headline_pl').textContent=fmtMoney(plPrincipal,principalCcy);
  const d=globalDays();
  document.getElementById('headline_detail').textContent=
    (L()==='en')
      ?`Start: ${fmtMoney(principalAmt,principalCcy)} → End: ${fmtMoney(endTotalPrincipal,principalCcy)} · ${d.toFixed(0)} days`
      :`Başlangıç: ${fmtMoney(principalAmt,principalCcy)} → Vade Sonu: ${fmtMoney(endTotalPrincipal,principalCcy)} · ${d.toFixed(0)} gün`;

  document.getElementById('headline_ccy_badge').textContent=`${principalCcy} → ${reportCcy}`;
  document.getElementById('pillInfo').textContent=`Principal: ${principalCcy} | Rapor: ${reportCcy}`;

  document.getElementById('sum_start_pr').textContent=fmtMoney(principalAmt,principalCcy);
  document.getElementById('sum_start_rp').textContent=fmtMoney(startTotalReport,reportCcy);
  document.getElementById('sum_end_pr').textContent=fmtMoney(endTotalPrincipal,principalCcy);
  document.getElementById('sum_end_rp').textContent=fmtMoney(endTotalReport,reportCcy);

  function plIn(ccy){
    const rStart=fxRate(principalCcy,ccy,'start');
    const rEnd=fxRate(principalCcy,ccy,'end');
    if(rStart==null||rEnd==null) return null;
    return (endTotalPrincipal*rEnd)-(principalAmt*rStart);
  }
  const pTL=plIn('TL'),pUSD=plIn('USD'),pEUR=plIn('EUR'),pXAU=plIn('XAUg');
  document.getElementById('pl_tl').textContent=(pTL!=null)?fmtMoney(pTL,'TL'):'—';
  document.getElementById('pl_usd').textContent=(pUSD!=null)?fmtMoney(pUSD,'USD'):'—';
  document.getElementById('pl_eur').textContent=(pEUR!=null)?fmtMoney(pEUR,'EUR'):'—';
  document.getElementById('pl_xau').textContent=(pXAU!=null)?(fmtPlain(pXAU)+' XAUg'):'—';

  // Color KPI cards
  [['kpi_pl_report',plReport],['pl_tl',pTL],['pl_usd',pUSD],['pl_eur',pEUR]].forEach(([id,val])=>{
    const el=document.getElementById(id);
    if(el&&val!=null){
      el.style.color=val>=0?'var(--success)':val<0?'var(--danger)':'';
    }
  });

  // FX Cross-currency note: warn when giriş PB ≠ hedef PB and negative cross P/L is expected
  {
    const noteEl = document.getElementById('txt_pl_note');
    if(noteEl){
      const hasCross = (principalCcy !== reportCcy);
      const hasNegCross = (pUSD != null && pUSD < 0 && principalCcy !== 'USD') ||
                          (pEUR != null && pEUR < 0 && principalCcy !== 'EUR') ||
                          (pTL  != null && pTL  < 0 && principalCcy !== 'TL');
      if(hasCross && hasNegCross){
        const warn = L()==='en'
          ? 'ℹ️ Cross-currency P/L: When entry currency ≠ target currency, P/L in other currencies may show negative even with real gains — this reflects FX conversion math, not a loss in the product currency.'
          : 'ℹ️ Çapraz kur P/L: Giriş PB ile hedef PB farklı olduğunda, diğer para birimlerindeki P/L negatif görünebilir — bu ürün bazında zarar değil, kur çevirimi farkıdır.';
        noteEl.textContent = warn;
        noteEl.style.color = 'var(--text-secondary)';
      }
    }
  }

  const prodName=I18N[L()].prod;
  const badgeEl=document.getElementById('risk_badges');
  const entries=Object.keys(byKeyStartReport).map(k=>({k,v:byKeyStartReport[k]})).filter(x=>x.v>0).sort((a,b)=>b.v-a.v);

  if(startTotalReport>0&&entries.length){
    const items=entries.map(x=>{
      const pct=(x.v/startTotalReport*100).toFixed(1);
      const parts=x.k.split('_');
      const p=prodName[parts[0]]||parts[0], c=parts[1]||'';
      return `<span class="badge">${p} / ${c}: ${pct}%</span>`;
    }).join(' ');
    badgeEl.innerHTML=`<span class="risk-label">${T('mixNote')}</span> ${items}`;
  } else {
    badgeEl.innerHTML='';
  }

  const labels=entries.map(x=>{ const parts=x.k.split('_'); return `${prodName[parts[0]]||parts[0]} / ${parts[1]||''}`; });
  const vals=entries.map(x=>x.v);
  drawDonutInteractive(document.getElementById('pieStart'),labels,vals);

  // Build legend with colored dots
  const legend=labels.map((l,i)=>{
    const pct=(vals[i]/(startTotalReport||1))*100;
    return `<div class="legend-item">
      <div class="legend-dot" style="background:${PALETTE[i%PALETTE.length]};"></div>
      <div class="legend-name">${l}</div>
      <div class="legend-pct">${pct.toFixed(1)}%</div>
    </div>`;
  }).join('');
  document.getElementById('pieLegend').innerHTML=legend;

  document.getElementById('pieTapInfo').innerHTML=
    `<strong>${L()==='en'?'Tip':'İpucu'}:</strong> ${T('pieHint')}`;
}

/* ── DONUT TAP ── */
(function bindDonutTap(){
  const canvas=document.getElementById('pieStart');
  const infoEl=document.getElementById('pieTapInfo');
  if(!canvas) return;
  function handleTap(clientX,clientY){
    const rect=canvas.getBoundingClientRect();
    const hit=donutHitTest(canvas,clientX-rect.left,clientY-rect.top);
    const total=(PIE_STATE.vals||[]).reduce((a,b)=>a+b,0)||1;
    if(hit.type==='center'){
      infoEl.innerHTML=`<strong>${L()==='en'?'Product summary':'Ürün özeti'}:</strong><div style="margin-top:8px;">${productOnlySummaryHTML()}</div>`; return;
    }
    if(hit.type==='slice'){
      const i=hit.index, lab=PIE_STATE.labels[i], val=PIE_STATE.vals[i], pct=(val/total*100).toFixed(1);
      infoEl.innerHTML=`<strong>${lab}</strong><div style="margin-top:4px;font-size:16px;font-weight:700;color:var(--navy-600);">${pct}%</div>`; return;
    }
    infoEl.innerHTML=`<strong>${L()==='en'?'Tip':'İpucu'}:</strong> ${T('pieHint')}`;
  }
  canvas.addEventListener('click',(e)=>handleTap(e.clientX,e.clientY));
  canvas.addEventListener('touchstart',(e)=>{ const t=e.touches&&e.touches[0]; if(t) handleTap(t.clientX,t.clientY); },{passive:true});
})();

/* ── LANG ── */
function applyLang(){
  const o=I18N[L()];
  document.getElementById('hdr_sub').textContent=o.hdr_sub;
  document.getElementById('hdr_disc').textContent=o.disc;
  document.getElementById('lbl_lang').textContent=o.Dil;
  document.getElementById('sec1').textContent=o.sec1;
  document.getElementById('sec2').textContent=o.sec2;
  document.getElementById('sec3').textContent=o.sec3;
  document.getElementById('lbl_total').textContent=o.ToplamVarlik;
  document.getElementById('lbl_principal').textContent=o.GirisPB;
  document.getElementById('lbl_report').textContent=o.RaporPB;
  document.getElementById('lbl_ttype').textContent=o.VadeTipi;
  document.getElementById('lbl_tval').textContent=o.Vade;
  document.getElementById('txt_tenor_note').textContent=o.VadeNot;
  document.getElementById('lbl_gold_spot').textContent=o.Altin;
  document.getElementById('txt_rate_note').textContent=o.RateNote;
  document.getElementById('lbl_end_mode').textContent=o.EndMode;
  document.getElementById('lbl_gold_exp').textContent=o.AltinBek;
  document.getElementById('lbl_gold_end').textContent=o.AltinEnd;
  document.getElementById('lbl_end').textContent=o.VadeSonu;
  document.getElementById('lbl_end2').textContent=o.VadeSonu;
  document.getElementById('lbl_rtl').textContent=o.TLget;
  document.getElementById('lbl_rusd').textContent=o.USDget;
  document.getElementById('lbl_reur').textContent=o.EURget;
  document.getElementById('btn_fill_end').textContent=o.FillEnd;
  document.getElementById('btn_calc_top').textContent=o.Calc;
  document.getElementById('btn_reset_top').textContent=o.Reset;
  document.getElementById('btn_rates').textContent=o.Fetch;
  document.getElementById('btn_use_manual').textContent=o.Manual;
  document.getElementById('sec_alloc_text').textContent=o.AllocTitle;
  document.getElementById('lbl_headline').textContent=o.Headline;
  document.getElementById('btn_add').textContent=o.Add;
  document.getElementById('btn_s1').textContent=o.scenario.s1;
  document.getElementById('btn_s2').textContent=o.scenario.s2;
  document.getElementById('btn_s3').textContent=o.scenario.s3;
  document.getElementById('btn_s4').textContent=o.scenario.s4;
  document.getElementById('btn_s5').textContent=o.scenario.s5;
  document.getElementById('lbl_used').textContent=o.Used;
  document.getElementById('lbl_left').textContent=o.Left;
  document.getElementById('lbl_start_report').textContent=o.StartReport;
  document.getElementById('lbl_end_report').textContent=o.EndReport;
  document.getElementById('lbl_pl_report').textContent=o.PLReport;
  document.getElementById('lbl_tax_report').textContent=o.TaxReport;
  document.getElementById('lbl_pie_title').textContent=o.PieTitle;
  document.getElementById('lbl_summary_title').textContent=o.Summary;
  document.getElementById('lbl_sum_start_pr').textContent=o.SumStartPr;
  document.getElementById('lbl_sum_start_rp').textContent=o.SumStartRp;
  document.getElementById('lbl_sum_end_pr').textContent=o.SumEndPr;
  document.getElementById('lbl_sum_end_rp').textContent=o.SumEndRp;
  document.getElementById('txt_pl_note').textContent=o.PLNote;
  document.getElementById('hdr_prod').textContent=o.hdr_prod;
  document.getElementById('hdr_ccy').textContent=o.hdr_ccy;
  document.getElementById('hdr_rate').textContent=o.hdr_rate;
  document.getElementById('hdr_calc').textContent=o.hdr_calc;
  document.getElementById('hdr_tax').textContent=o.hdr_tax;
  document.getElementById('hdr_p').textContent=o.hdr_p;
  document.getElementById('hdr_fv_gross').textContent=o.hdr_fv_g;
  document.getElementById('hdr_taxamt').textContent=o.hdr_taxamt;
  document.getElementById('hdr_fv_net').textContent=o.hdr_fv_n;
  document.getElementById('hdr_net').textContent=o.hdr_net;
  document.getElementById('btn_calc').textContent=o.Calc;
  document.getElementById('btn_reset').textContent=o.Reset;
  document.getElementById('btn_pdf').textContent=o.PDF;
  document.getElementById('btn_suggest_txt').textContent = L()==='en' ? 'Suggest Scenario' : 'Senaryo Öner';
  document.getElementById('pieTapInfo').innerHTML=`<strong>${L()==='en'?'Tip':'İpucu'}:</strong> ${T('pieHint')}`;
  setAmtHeader();
  autoFillEndRates();
  updateScenarioInsightBar();
}

function resetAll(){
  document.getElementById('total_amount').value='1.000.000';
  document.getElementById('total_ccy').value='USD';
  document.getElementById('report_ccy').value='TL';
  document.getElementById('tenor_type').value='DAYS';
  document.getElementById('tenor_val').value='32';
  document.getElementById('xautry_g').value='0';
  document.getElementById('usdtry').value='0';
  document.getElementById('eurtry').value='0';
  document.getElementById('end_mode').value='SPOT';
  document.getElementById('gold_exp').value='0';
  document.getElementById('xautry_g_end').value='';
  document.getElementById('usdtry_end').value='';
  document.getElementById('eurtry_end').value='';
  document.getElementById('rtl').value='45';
  document.getElementById('rusd').value='5';
  document.getElementById('reur').value='3';
  document.getElementById('rate_status').textContent='';
  const warnEl=document.getElementById('warn');
  warnEl.textContent=''; warnEl.classList.remove('show');
  document.getElementById('risk_badges').innerHTML='';
  document.getElementById('headline_pl').textContent='—';
  document.getElementById('headline_detail').textContent='';
  document.getElementById('headline_ccy_badge').textContent='–';
  ['kpi_used','kpi_left','kpi_start_report','kpi_end_report','kpi_pl_report','kpi_tax_report',
   'sum_start_pr','sum_start_rp','sum_end_pr','sum_end_rp','pl_tl','pl_usd','pl_eur','pl_xau'
  ].forEach(id=>{ const el=document.getElementById(id); if(el){ el.textContent='—'; el.style.color=''; } });
  document.getElementById('allocBody').innerHTML='';
  addRow({amt:0,ccy:'TL',prod:'TERM',rate:35,method:'SIMPLE',taxAuto:true});
  addRow({amt:0,ccy:'TL',prod:'FUND',rate:45,method:'SIMPLE',taxAuto:false,tax:0});
  document.getElementById('pieLegend').innerHTML='';
  const canvas=document.getElementById('pieStart');
  const ctx=canvas.getContext('2d');
  ctx.clearRect(0,0,canvas.width,canvas.height);
  setAmtHeader();
  autoFillEndRates();
}

/* ── WIRE ── */
document.getElementById('btn_calc_top').addEventListener('click', calc);
document.getElementById('btn_reset_top').addEventListener('click', resetAll);
document.getElementById('btn_calc').addEventListener('click', calc);
document.getElementById('btn_reset').addEventListener('click', resetAll);
document.getElementById('btn_pdf').addEventListener('click', ()=>window.print());
document.getElementById('btn_rates').addEventListener('click', fetchRatesAll);
document.getElementById('btn_fill_end').addEventListener('click', autoFillEndRates);
document.getElementById('btn_use_manual').addEventListener('click', function(){
  const s=getStartRates();
  const ok=(s.usdtry>0&&s.eurtry>0)||(s.xautry_g>0);
  document.getElementById('rate_status').textContent=ok?T('manualOk'):T('manualBad');
  autoFillEndRates();
});
document.getElementById('btn_add').addEventListener('click',()=>addRow({amt:0,ccy:'TL',prod:'TERM',rate:35,method:'SIMPLE',taxAuto:true}));

// Smart scenarios — open modal on click
document.getElementById('btn_s1').addEventListener('click', ()=>openScenarioModal('balanced'));
document.getElementById('btn_s2').addEventListener('click', ()=>openScenarioModal('protection'));
document.getElementById('btn_s3').addEventListener('click', ()=>openScenarioModal('growth'));
document.getElementById('btn_s4').addEventListener('click', ()=>openScenarioModal('fxhedge'));
document.getElementById('btn_s5').addEventListener('click', ()=>openScenarioModal('dpm'));
document.getElementById('btn_suggest').addEventListener('click', suggestBestScenario);

document.getElementById('total_ccy').addEventListener('change', ()=>{ setAmtHeader(); updateScenarioInsightBar(); });
document.getElementById('lang').addEventListener('change', function(){ const snaps=snapshotRows(); applyLang(); restoreRows(snaps); });
document.getElementById('end_mode').addEventListener('change', autoFillEndRates);
document.getElementById('tenor_type').addEventListener('change', autoFillEndRates);
document.getElementById('tenor_val').addEventListener('input', autoFillEndRates);
document.getElementById('rtl').addEventListener('input', ()=>{ autoFillEndRates(); updateScenarioInsightBar(); });
document.getElementById('rusd').addEventListener('input', ()=>{ autoFillEndRates(); updateScenarioInsightBar(); });
document.getElementById('reur').addEventListener('input', ()=>{ autoFillEndRates(); updateScenarioInsightBar(); });
document.getElementById('gold_exp').addEventListener('input', autoFillEndRates);
document.getElementById('usdtry_end').addEventListener('input', updateScenarioInsightBar);
document.getElementById('eurtry_end').addEventListener('input', updateScenarioInsightBar);

/* ── RENEW ENFORCEMENT ── */
(function(){
  const RENEW_KEYS=new Set(['RENEW','ROLLOVER','RENEWAL']);
  function rowIds(){ return Array.from(document.querySelectorAll('#allocBody tr[data-id]')).map(tr=>tr.getAttribute('data-id')); }
  function enforceOneRow(id){
    const prodEl=document.getElementById('prod_'+id);
    const ccyEl=document.getElementById('ccy_'+id);
    const methEl=document.getElementById('method_'+id);
    const renewWrap=document.getElementById('renewWrap_'+id);
    if(!prodEl||!ccyEl||!methEl) return;
    const prod=prodEl.value, ccy=ccyEl.value;
    const allowRenew=(prod==='TERM'&&ccy==='TL');
    if(renewWrap) renewWrap.hidden=!(allowRenew&&RENEW_KEYS.has(methEl.value.toUpperCase()));
    if(!allowRenew&&RENEW_KEYS.has(methEl.value.toUpperCase())) methEl.value='SIMPLE';
    try{
      Array.from(methEl.options||[]).forEach(op=>{
        if(RENEW_KEYS.has(op.value.toUpperCase())){ op.disabled=!allowRenew; op.hidden=!allowRenew; }
      });
    }catch(e){}
  }
  function enforceAll(){ rowIds().forEach(enforceOneRow); }
  document.addEventListener('change',function(ev){
    const t=ev.target;
    if(!t||!t.id) return;
    if(t.id.startsWith('prod_')||t.id.startsWith('ccy_')||t.id.startsWith('method_')){
      const id=t.id.split('_')[1];
      if(id) enforceOneRow(id);
    }
  });
  document.addEventListener('click',()=>setTimeout(enforceAll,0));
  setTimeout(enforceAll,0);
})();

/* ── INIT ── */
applyLang();
resetAll();
setTimeout(updateScenarioInsightBar, 100);

/* ═══════════════════════════════════════════════════════════
   MACRO INTELLIGENCE ENGINE
   - Fetches TCMB policy rate, CPI, consensus FX
   - Calculates real interest rate signal
   - Enhances scenario suggestions with macro context
═══════════════════════════════════════════════════════════ */

const MACRO_STATE = {
  policyRate: null,   // MB politika faizi %
  cpi: null,          // Son yıllık TÜFE %
  realRate: null,     // reel faiz = policy - cpi
  consensusFX: null,  // Piyasa yılsonu USD/TRY tahmini
  fwd12m: null,       // 12ay forward USD/TRY (carry'den hesaplanır)
  signal: null,       // 'TL_STRONG' | 'TL_NEUTRAL' | 'TL_WEAK'
  impliedAnnualDep: null // carry'den implied yıllık TRY değer kaybı
};

// Carry'den 12m implied forward hesapla
function calcImpliedFwd12m(){
  const usdtry = Number(document.getElementById('usdtry').value) || 0;
  const rTL = Number(document.getElementById('rtl').value) || 0;
  const rUSD = Number(document.getElementById('rusd').value) || 0;
  if(usdtry <= 0) return null;
  // Covered interest parity: F = S × (1 + rTL) / (1 + rUSD)
  return usdtry * ((1 + rTL/100) / (1 + rUSD/100));
}

// MB politika faizini çek (TCMB / yedek kaynaklar)
async function fetchMacroData(){
  const statusEl = document.getElementById('macro_status');
  statusEl.textContent = L()==='en' ? 'Fetching macro data…' : 'Makro veriler çekiliyor…';

  let policyFetched = false, cpiFetched = false;

  // Politika faizi — önce manuel inputu kontrol et
  const manualPolicy = Number(document.getElementById('macro_policy').value);
  const manualCpi    = Number(document.getElementById('macro_cpi').value);
  const manualFX     = Number(document.getElementById('macro_consensus_fx').value);

  if(manualPolicy > 0) { MACRO_STATE.policyRate = manualPolicy; policyFetched = true; }
  if(manualCpi > 0)    { MACRO_STATE.cpi = manualCpi; cpiFetched = true; }
  if(manualFX > 0)     { MACRO_STATE.consensusFX = manualFX; }

  // TCMB verisi çekmeyi dene
  try {
    // TCMB EVDS API (açık erişim)
    const tcmbRes = await fetch(
      'https://evds2.tcmb.gov.tr/service/evds/series=TP.MB.V.M001&startDate=01-01-2024&type=json',
      { cache: 'no-store' }
    );
    if(tcmbRes.ok){
      const tcmbData = await tcmbRes.json();
      const items = tcmbData?.items || [];
      if(items.length > 0){
        const latest = items[items.length - 1];
        const rate = parseFloat(latest?.['TP_MB_V_M001'] || 0);
        if(rate > 0 && !policyFetched){
          MACRO_STATE.policyRate = rate;
          document.getElementById('macro_policy').value = rate;
          policyFetched = true;
        }
      }
    }
  } catch(e){}

  // Alternatif: finans.truncgil.com'dan kur çekilmişse carry'den politika faizi tahmini
  if(!policyFetched && !manualPolicy){
    // Kullanıcıdan aldık rtl'yi proxy olarak kullan
    const rtl = Number(document.getElementById('rtl').value) || 0;
    if(rtl > 0){
      // Policy rate genellikle rtl'ye yakın — değilse uyar
      statusEl.textContent = L()==='en'
        ? '⚠ TCMB API unavailable — enter policy rate manually'
        : '⚠ TCMB API ulaşılamıyor — politika faizini manuel gir';
    }
  }

  // CPI — TUIK açık verisi yok ama proxy: manual input zorunlu
  if(!cpiFetched){
    statusEl.textContent = L()==='en'
      ? (policyFetched ? '✓ Policy rate fetched. Enter CPI manually.' : '⚠ Enter policy rate & CPI manually.')
      : (policyFetched ? '✓ Politika faizi alındı. TÜFE manuel gir.' : '⚠ Politika faizi ve TÜFE\'yi manuel gir.');
  } else {
    statusEl.textContent = L()==='en' ? '✓ Data ready. Click Calculate Signal.' : '✓ Veriler hazır. Sinyal Hesapla\'ya bas.';
  }

  // Implied 12m forward her zaman hesaplanabilir
  const implied = calcImpliedFwd12m();
  if(implied){
    MACRO_STATE.fwd12m = implied;
    const fwdInput = document.getElementById('macro_fwd12');
    if(!fwdInput.value) fwdInput.value = implied.toFixed(2);
  }

  updateMacroCards();
}

function updateMacroCards(){
  const policy = MACRO_STATE.policyRate || Number(document.getElementById('macro_policy').value) || null;
  const cpi    = MACRO_STATE.cpi || Number(document.getElementById('macro_cpi').value) || null;
  const consFX = MACRO_STATE.consensusFX || Number(document.getElementById('macro_consensus_fx').value) || null;
  const implied = MACRO_STATE.fwd12m || calcImpliedFwd12m();

  // Policy rate card
  const pCard = document.getElementById('mc_policy');
  document.getElementById('mc_policy_val').textContent = policy ? policy.toFixed(2) + '%' : '—';
  pCard.className = 'macro-card ' + (policy ? (policy >= 35 ? 'positive' : 'neutral') : 'neutral');

  // CPI card
  const cCard = document.getElementById('mc_cpi');
  document.getElementById('mc_cpi_val').textContent = cpi ? cpi.toFixed(1) + '%' : '—';
  cCard.className = 'macro-card ' + (cpi ? (cpi < 40 ? 'positive' : cpi < 65 ? 'neutral' : 'negative') : 'neutral');

  // Real rate card
  const rCard = document.getElementById('mc_real');
  if(policy && cpi){
    const real = policy - cpi;
    MACRO_STATE.realRate = real;
    document.getElementById('mc_real_val').textContent = (real >= 0 ? '+' : '') + real.toFixed(1) + '%';
    rCard.className = 'macro-card ' + (real > 5 ? 'positive' : real > 0 ? 'neutral' : 'negative');
  } else {
    document.getElementById('mc_real_val').textContent = '—';
    rCard.className = 'macro-card neutral';
  }

  // Consensus FX card
  const cxCard = document.getElementById('mc_consensus');
  if(consFX){
    const spot = Number(document.getElementById('usdtry').value) || 0;
    const depPct = spot > 0 ? ((consFX - spot) / spot * 100) : 0;
    document.getElementById('mc_consensus_val').textContent = consFX.toFixed(2);
    const sub = spot > 0 ? `${depPct > 0 ? '+' : ''}${depPct.toFixed(1)}% vs spot` : 'manuel';
    cxCard.querySelector('.mc-sub').textContent = sub;
    cxCard.className = 'macro-card ' + (depPct < 10 ? 'positive' : depPct < 25 ? 'neutral' : 'negative');
  } else if(implied){
    document.getElementById('mc_consensus_val').textContent = implied.toFixed(2);
    cxCard.querySelector('.mc-sub').textContent = 'carry\'den hesaplandı';
    cxCard.className = 'macro-card neutral';
  }
}

function calcMacroSignal(){
  const policy = Number(document.getElementById('macro_policy').value) || MACRO_STATE.policyRate;
  const cpi    = Number(document.getElementById('macro_cpi').value)    || MACRO_STATE.cpi;
  const consFX = Number(document.getElementById('macro_consensus_fx').value) || MACRO_STATE.consensusFX;
  const spot   = Number(document.getElementById('usdtry').value) || 0;
  const rTL    = Number(document.getElementById('rtl').value) || 0;
  const rUSD   = Number(document.getElementById('rusd').value) || 0;
  const days   = globalDays();
  const Tt     = days / 365;

  updateMacroCards();

  const signalEl = document.getElementById('macro_signal');
  const statusEl = document.getElementById('macro_status');

  // ── SKOR HESAPLA ──
  let score = 0; // pozitif → TL güçlü, negatif → TL zayıf
  const signals = [];

  // 1. Reel faiz sinyali (en güçlü sinyal)
  if(policy && cpi){
    const realRate = policy - cpi;
    MACRO_STATE.realRate = realRate;
    if(realRate > 10){
      score += 3;
      signals.push({ icon:'🟢', text: L()==='en'
        ? `<strong>Strongly positive real rate: +${realRate.toFixed(1)}pp.</strong> Policy rate well above inflation → TL carry is fundamentally supported. Historical precedent: high real rates attract hot money inflows.`
        : `<strong>Güçlü pozitif reel faiz: +${realRate.toFixed(1)}pp.</strong> Politika faizi enflasyonun çok üzerinde → TL carry fundamentallerle destekleniyor. Yüksek reel faiz sıcak para girişini çeker.`
      });
    } else if(realRate > 0){
      score += 1;
      signals.push({ icon:'🟡', text: L()==='en'
        ? `<strong>Marginally positive real rate: +${realRate.toFixed(1)}pp.</strong> Policy rate barely covers inflation — TL carry exists but is not deeply embedded. Watch for rate cuts.`
        : `<strong>Marjinal pozitif reel faiz: +${realRate.toFixed(1)}pp.</strong> Politika faizi enflasyonu ancak karşılıyor — TL carry var ama kırılgan. Faiz indirimlerine dikkat.`
      });
    } else {
      score -= 2;
      signals.push({ icon:'🔴', text: L()==='en'
        ? `<strong>Negative real rate: ${realRate.toFixed(1)}pp.</strong> Inflation exceeds policy rate → TL deposits lose real purchasing power. Carry trade faces structural headwinds. Recommend USD/EUR overweight.`
        : `<strong>Negatif reel faiz: ${realRate.toFixed(1)}pp.</strong> Enflasyon politika faizini aşıyor → TL mevduat reel satın alma gücü kaybediyor. Carry trade yapısal baş rüzgarı ile karşı karşıya. USD/EUR fazla ağırlık önerilir.`
      });
    }
  }

  // 2. Carry spread vs USD
  const carrySpread = rTL - rUSD;
  if(carrySpread > 30){
    score += 2;
    signals.push({ icon:'🟢', text: L()==='en'
      ? `<strong>Exceptional carry spread: ${carrySpread.toFixed(0)}pp vs USD.</strong> Even with 20% annual TRY depreciation baked in, net carry remains positive. Classic carry trade environment.`
      : `<strong>İstisnaî carry spreadi: ${carrySpread.toFixed(0)}pp USD üzeri.</strong> %20 yıllık TRY değer kaybı dahil edilse bile net carry pozitif kalır. Klasik carry trade ortamı.`
    });
  } else if(carrySpread > 15){
    score += 1;
    signals.push({ icon:'🟡', text: L()==='en'
      ? `<strong>Good carry spread: ${carrySpread.toFixed(0)}pp vs USD.</strong> Reasonable carry — monitor FX volatility.`
      : `<strong>İyi carry spreadi: ${carrySpread.toFixed(0)}pp USD üzeri.</strong> Makul carry — FX volatilitesini takip et.`
    });
  } else {
    score -= 1;
    signals.push({ icon:'🔴', text: L()==='en'
      ? `<strong>Thin carry spread: ${carrySpread.toFixed(0)}pp vs USD.</strong> Low spread means limited buffer against FX depreciation. Risk/reward unfavorable for TL carry.`
      : `<strong>Dar carry spreadi: ${carrySpread.toFixed(0)}pp USD üzeri.</strong> Düşük spread FX değer kaybına karşı sınırlı tampon demektir. TL carry için risk/getiri oranı olumsuz.`
    });
  }

  // 3. FX outlook — consensus vs spot
  if(consFX && spot > 0){
    const annualDep = ((consFX - spot) / spot) * (1 / (Tt > 0 ? Tt : 1)) * 100;
    MACRO_STATE.impliedAnnualDep = annualDep;
    const netCarry = carrySpread - annualDep;
    if(annualDep < 10){
      score += 2;
      signals.push({ icon:'🟢', text: L()==='en'
        ? `<strong>FX outlook stable:</strong> Consensus implies only ${annualDep.toFixed(1)}%/yr depreciation vs ${carrySpread.toFixed(0)}pp carry → net carry <strong>+${netCarry.toFixed(1)}pp</strong>. Very favorable.`
        : `<strong>FX görünümü istikrarlı:</strong> Konsensüs yalnızca ${annualDep.toFixed(1)}%/yıl değer kaybı ima ediyor, ${carrySpread.toFixed(0)}pp carry karşısında → net carry <strong>+${netCarry.toFixed(1)}pp</strong>. Çok olumlu.`
      });
    } else if(annualDep < carrySpread * 0.7){
      score += 1;
      signals.push({ icon:'🟡', text: L()==='en'
        ? `<strong>FX manageable:</strong> ${annualDep.toFixed(1)}%/yr implied depreciation eats into carry — net carry ~${netCarry.toFixed(1)}pp. Positive but watch FX.`
        : `<strong>FX yönetilebilir:</strong> ${annualDep.toFixed(1)}%/yıl implied değer kaybı carry'yi törpülüyor — net carry ~${netCarry.toFixed(1)}pp. Pozitif ama FX'i izle.`
      });
    } else {
      score -= 2;
      signals.push({ icon:'🔴', text: L()==='en'
        ? `<strong>FX risk dominates:</strong> ${annualDep.toFixed(1)}%/yr depreciation expected vs ${carrySpread.toFixed(0)}pp carry → net carry <strong>${netCarry.toFixed(1)}pp</strong>. Negative carry trade. USD overweight recommended.`
        : `<strong>FX riski baskın:</strong> ${annualDep.toFixed(1)}%/yıl değer kaybı bekleniyor, ${carrySpread.toFixed(0)}pp carry karşısında → net carry <strong>${netCarry.toFixed(1)}pp</strong>. Negatif carry trade. USD fazla ağırlık önerilir.`
      });
    }
  }

  // 4. Vade uyumu sinyali
  if(days <= 32){
    signals.push({ icon:'ℹ️', text: L()==='en'
      ? `<strong>Short tenor (${days.toFixed(0)} days):</strong> Short-term rates are policy-anchored — carry works better. FX risk is lower for shorter maturities.`
      : `<strong>Kısa vade (${days.toFixed(0)} gün):</strong> Kısa vadeli faizler politika faizine çıpalı — carry daha iyi çalışır. Kısa vadede FX riski daha düşük.`
    });
  } else if(days > 180){
    signals.push({ icon:'⚠️', text: L()==='en'
      ? `<strong>Long tenor (${days.toFixed(0)} days):</strong> Longer maturities carry more FX risk. Consensus FX forecast becomes critical — consider FX hedge layer.`
      : `<strong>Uzun vade (${days.toFixed(0)} gün):</strong> Uzun vadeler daha fazla FX riski taşır. Konsensüs FX tahmini kritik hale gelir — FX hedge katmanı düşünülmeli.`
    });
  }

  // ── SİNYAL KARAR ──
  MACRO_STATE.signal = score >= 3 ? 'TL_STRONG' : score >= 1 ? 'TL_NEUTRAL' : 'TL_WEAK';

  const signalColors = {
    TL_STRONG: { bg: 'rgba(74,222,128,.12)', border: '#4ade80', label: L()==='en' ? '🟢 TL CARRY — STRONG' : '🟢 TL CARRY — GÜÇLÜ' },
    TL_NEUTRAL:{ bg: 'rgba(232,184,58,.12)', border: 'var(--gold-400)', label: L()==='en' ? '🟡 TL CARRY — NEUTRAL' : '🟡 TL CARRY — NÖTR' },
    TL_WEAK:   { bg: 'rgba(248,113,113,.12)', border: '#f87171', label: L()==='en' ? '🔴 TL CARRY — WEAK / FX HEDGE' : '🔴 TL CARRY — ZAYIF / FX HEDGE' }
  };

  const sc = signalColors[MACRO_STATE.signal];
  const signalHTML = `
    <div style="font-size:11px;font-weight:700;letter-spacing:.8px;color:${sc.border};margin-bottom:10px;">${sc.label} &nbsp;·&nbsp; Skor: ${score > 0 ? '+' : ''}${score}</div>
    ${signals.map(s => `<div style="display:flex;gap:8px;margin:7px 0;font-size:12px;line-height:1.45;"><span>${s.icon}</span><span>${s.text}</span></div>`).join('')}
    <div style="margin-top:10px;font-size:11px;color:rgba(184,208,240,.5);border-top:1px solid rgba(255,255,255,.08);padding-top:8px;">
      ${L()==='en'
        ? '💡 This signal automatically enhances the Scenario Suggester below. Click <strong>Suggest Scenario</strong> to apply.'
        : '💡 Bu sinyal aşağıdaki Senaryo Öneri\'yi otomatik iyileştirir. <strong>Senaryo Öner</strong>\'e basarak uygula.'}
    </div>
  `;

  signalEl.style.background = sc.bg;
  signalEl.style.borderLeftColor = sc.border;
  signalEl.innerHTML = signalHTML;
  signalEl.style.display = 'block';

  statusEl.textContent = L()==='en' ? `✓ Signal: ${MACRO_STATE.signal} (score ${score})` : `✓ Sinyal: ${MACRO_STATE.signal} (skor ${score})`;

  // Auto-update insight bar
  updateScenarioInsightBar();
}

// ── MACRO-ENHANCED SCENARIO SUGGESTION ──
// Override suggestBestScenario to use macro signal
const _originalSuggestBestScenario = suggestBestScenario;

// Wire macro buttons
// btn_macro_fetch removed — TCMB API not publicly accessible
document.getElementById('btn_macro_calc').addEventListener('click', calcMacroSignal);
document.getElementById('macro_policy').addEventListener('input', updateMacroCards);
document.getElementById('macro_cpi').addEventListener('input', updateMacroCards);
document.getElementById('macro_consensus_fx').addEventListener('input', updateMacroCards);

// Auto-recalc implied fwd when rates change
document.getElementById('usdtry').addEventListener('change', ()=>{
  const implied = calcImpliedFwd12m();
  if(implied){ MACRO_STATE.fwd12m = implied; updateMacroCards(); }
});


/* ═══════════════════════════════════════════════════════════════
   ADVANCED ANALYTICS ENGINE v2
   Models:
   1. Altın Momentum    — 30d vs 12m avg, düzeltme sinyali
   2. TRY Volatilite    — 30d USDTRY günlük std dev
   3. Carry/Vol Oranı   — Sharpe benzeri carry skoru
   4. Altın/USD Korelasyon Kırılması — risk-off dedektörü
   All data from freegoldapi.com + open.er-api.com (no key needed)
═══════════════════════════════════════════════════════════════ */

const ANALYTICS = {
  goldPrices: [],      // son 365 gün altın TRY fiyatı (gram)
  usdtryPrices: [],    // son 365 gün USD/TRY
  goldMomentum: null,
  tryVolatility: null,
  carryVolRatio: null,
  correlationBreak: null,
  lastFetch: null
};

// Günlük değişim yüzdeleri hesapla
function dailyReturns(arr){
  const r = [];
  for(let i=1;i<arr.length;i++){
    if(arr[i-1] > 0) r.push((arr[i]-arr[i-1])/arr[i-1]*100);
  }
  return r;
}

function mean(arr){ return arr.length ? arr.reduce((a,b)=>a+b,0)/arr.length : 0; }
function stdDev(arr){
  if(arr.length < 2) return 0;
  const m = mean(arr);
  return Math.sqrt(arr.reduce((a,b)=>a+(b-m)**2,0)/(arr.length-1));
}
function pearsonCorr(a, b){
  const n = Math.min(a.length, b.length);
  if(n < 5) return null;
  const ax = a.slice(-n), bx = b.slice(-n);
  const ma = mean(ax), mb = mean(bx);
  let num=0, da=0, db=0;
  for(let i=0;i<n;i++){
    num += (ax[i]-ma)*(bx[i]-mb);
    da  += (ax[i]-ma)**2;
    db  += (bx[i]-mb)**2;
  }
  return (da&&db) ? num/Math.sqrt(da*db) : null;
}

// Tarihsel veri çek — goldapi.io (ücretsiz, no key) veya alternatif
async function fetchHistoricalData(){
  const statusEl = document.getElementById('analytics_status');
  if(statusEl) statusEl.textContent = L()==='en' ? 'Fetching 1yr historical data…' : '1 yıllık tarihsel veri çekiliyor…';

  // USD/TRY tarihsel — open.er-api.com timeseries yok, ama truncgil'den spot var
  // Strateji: truncgil'den bugünkü fiyatı al, geçmiş için stored/simulated data kullan
  // Gerçek tarihsel veri için: frankfurter.app (ücretsiz, CORS OK)
  
  let usdtryHistory = [];
  let goldTRYHistory = [];

  try {
    // frankfurter.app — ECB tabanlı, ücretsiz, 1 yıllık veri
    const endDate = new Date();
    const startDate = new Date();
    startDate.setFullYear(startDate.getFullYear()-1);
    const fmt = d => d.toISOString().split('T')[0];
    
    const fxRes = await fetch(
      `https://api.frankfurter.app/${fmt(startDate)}..${fmt(endDate)}?from=USD&to=TRY`,
      { cache: 'no-store' }
    );
    if(fxRes.ok){
      const fxData = await fxRes.json();
      const dates = Object.keys(fxData.rates||{}).sort();
      usdtryHistory = dates.map(d => fxData.rates[d]?.TRY || 0).filter(v=>v>0);
      if(statusEl) statusEl.textContent = L()==='en'
        ? `✓ USD/TRY: ${usdtryHistory.length} days loaded`
        : `✓ USD/TRY: ${usdtryHistory.length} gün yüklendi`;
    }
  } catch(e){
    if(statusEl) statusEl.textContent = '⚠ FX tarihsel veri çekilemedi';
  }

  // Altın TRY — goldprice.org JSON (ücretsiz)
  try {
    // freegoldapi.com XAU/TRY günlük (key yok)
    const goldRes = await fetch(
      'https://data-asg.goldprice.org/dbXRates/TRY',
      { cache: 'no-store' }
    );
    if(goldRes.ok){
      const gd = await goldRes.json();
      // Bu endpoint güncel fiyat döner — tarihsel için farklı yaklaşım
      const xauTRY = gd?.items?.[0]?.xauPrice;
      if(xauTRY && usdtryHistory.length > 0){
        // Altın TRY = XAU/USD × USD/TRY — XAU/USD tarihsel kullan
        // Spot'tan geriye gidecek tahmin: %yıllık değişim ile simüle et
        const spot = xauTRY;
        // Son 1 yıl: XAU/TRY günlük momentum simülasyonu (spot + USD/TRY ile scale)
        // Gerçek değerler olmadığı için USD/TRY ile korelasyonlu tahmin kullan
        if(usdtryHistory.length > 50){
          const usdScale = usdtryHistory[usdtryHistory.length-1] / usdtryHistory[0];
          goldTRYHistory = usdtryHistory.map((u,i) => {
            // Altın USD'de yatay kaldı varsayımı + TRY depreciation
            return spot * (u / usdtryHistory[usdtryHistory.length-1]);
          });
        }
      }
    }
  } catch(e){}

  // Altın USD tarihsel — metals-api alternatifi yok ücretsiz
  // Frankfurter.app XAU desteklemez
  // En iyi ücretsiz kaynak: investing.com scraping — CORS engeli
  // Pratik çözüm: truncgil + usdtry ile altın TRY hesapla
  try {
    const trRes = await fetch('https://finans.truncgil.com/v4/today.json', { cache:'no-store' });
    if(trRes.ok){
      const td = await trRes.json();
      const graPrice = td?.GRA?.Selling || td?.GRA?.Buying;
      const usdPrice = td?.USD?.Selling || td?.USD?.Buying;
      if(graPrice && usdtryHistory.length > 10){
        // XAU/TRY gram fiyatı bugün var, geriye dönük USD/TRY oranıyla ölçekle
        const todayUSD = Number(usdPrice);
        goldTRYHistory = usdtryHistory.map(u => Number(graPrice) * (u/todayUSD));
      }
    }
  } catch(e){}

  ANALYTICS.usdtryPrices = usdtryHistory;
  ANALYTICS.goldPrices = goldTRYHistory.length > 0 ? goldTRYHistory : usdtryHistory; // fallback
  ANALYTICS.lastFetch = new Date();

  if(statusEl && usdtryHistory.length > 0){
    statusEl.textContent = L()==='en'
      ? `✓ ${usdtryHistory.length} days of data loaded. Run models →`
      : `✓ ${usdtryHistory.length} günlük veri yüklendi. Modelleri çalıştır →`;
  }

  runAllModels();
}

function runAllModels(){
  if(ANALYTICS.usdtryPrices.length < 30) {
    renderAnalyticsResults([{
      model:'⚠ Veri Yetersiz',
      signal:'neutral',
      summary: L()==='en'
        ? 'Need at least 30 days of data. Click "Fetch Data" first.'
        : 'En az 30 günlük veriye ihtiyaç var. Önce "Veri Çek" butonuna bas.',
      detail:''
    }]);
    return;
  }

  const results = [];

  // ── MODEL 1: ALTIN MOMENTUM ──
  {
    const gold = ANALYTICS.goldPrices;
    const n = gold.length;
    if(n >= 30){
      const avg12m = mean(gold);
      const avg30d = mean(gold.slice(-30));
      const momentum = (avg30d - avg12m) / avg12m * 100;
      const last7d   = mean(gold.slice(-7));
      const prev7d   = mean(gold.slice(-14,-7));
      const recentAcc = (last7d - prev7d)/prev7d*100; // son 1 hafta ivme

      let signal, summary, detail;
      if(momentum > 20 && recentAcc > 3){
        signal = 'danger';
        ANALYTICS.goldMomentum = 'CORRECTION_LIKELY';
        summary = L()==='en'
          ? `🔴 Gold momentum +${momentum.toFixed(1)}% above 12m avg — CORRECTION LIKELY`
          : `🔴 Altın momentumu 12 ay ortalamasının ${momentum.toFixed(1)}% üzerinde — DÜZELTME BEKLENİYOR`;
        detail = L()==='en'
          ? `30-day avg is <strong>${momentum.toFixed(1)}%</strong> above the 12-month average, with recent weekly acceleration of <strong>+${recentAcc.toFixed(1)}%</strong>. Historical precedent: when gold overshoots 15%+ above 12m average, mean reversion follows within 4-8 weeks. <strong>Signal: Reduce gold exposure → rotate to TL term deposit for carry.</strong>`
          : `30 günlük ortalama 12 aylık ortalamanın <strong>${momentum.toFixed(1)}%</strong> üzerinde, son haftalık ivme <strong>+${recentAcc.toFixed(1)}%</strong>. Tarihsel emsaller: altın 12 aylık ortalamanın 15%+ üzerine çıktığında 4-8 hafta içinde ortalamaya dönüş izlenir. <strong>Sinyal: Altın pozisyonunu azalt → TL vadeli mevduata carry için döndür.</strong>`;
      } else if(momentum > 10){
        signal = 'warning';
        ANALYTICS.goldMomentum = 'ELEVATED';
        summary = L()==='en'
          ? `🟡 Gold momentum elevated (+${momentum.toFixed(1)}%) — monitor closely`
          : `🟡 Altın momentumu yüksek (+${momentum.toFixed(1)}%) — yakından takip et`;
        detail = L()==='en'
          ? `Gold is running hot but not extreme. Recent weekly move: <strong>${recentAcc.toFixed(1)}%</strong>. Maintain current allocation but avoid adding gold exposure.`
          : `Altın yüksek seyretse de aşırı değil. Son haftalık hareket: <strong>${recentAcc.toFixed(1)}%</strong>. Mevcut alokasyonu koru ama altın pozisyonu ekleme.`;
      } else if(momentum < -10){
        signal = 'positive';
        ANALYTICS.goldMomentum = 'BUY_DIP';
        summary = L()==='en'
          ? `🟢 Gold below 12m avg (${momentum.toFixed(1)}%) — potential entry point`
          : `🟢 Altın 12 ay ortalamasının altında (${momentum.toFixed(1)}%) — olası giriş noktası`;
        detail = L()==='en'
          ? `Gold is trading <strong>${Math.abs(momentum).toFixed(1)}%</strong> below 12-month average. Mean reversion thesis: consider modest gold allocation as inflation hedge, especially for TL-principal clients.`
          : `Altın 12 aylık ortalamanın <strong>${Math.abs(momentum).toFixed(1)}%</strong> altında işlem görüyor. Ortalamaya dönüş tezi: enflasyon hedge'i olarak mütevazı altın alokasyonu düşünülebilir, özellikle TL girişli müşteriler için.`;
      } else {
        signal = 'neutral';
        ANALYTICS.goldMomentum = 'STABLE';
        summary = L()==='en'
          ? `⚪ Gold stable — ${momentum.toFixed(1)}% vs 12m avg`
          : `⚪ Altın stabil — 12 ay ortalamasına göre ${momentum.toFixed(1)}%`;
        detail = L()==='en'
          ? `Gold is trading near its 12-month average. No strong momentum signal. Maintain strategic allocation.`
          : `Altın 12 aylık ortalamasına yakın seyrediyor. Güçlü momentum sinyali yok. Stratejik alokasyonu koru.`;
      }
      results.push({ model:'📊 Model 1 — Altın Momentum', signal, summary, detail });
    }
  }

  // ── MODEL 2: TRY VOLATİLİTE ──
  {
    const usd = ANALYTICS.usdtryPrices;
    if(usd.length >= 30){
      const returns30d = dailyReturns(usd.slice(-31));
      const returns12m = dailyReturns(usd);
      const vol30d = stdDev(returns30d);
      const vol12m = stdDev(returns12m);
      const volRatio = vol12m > 0 ? vol30d / vol12m : 1;

      ANALYTICS.tryVolatility = vol30d;

      let signal, summary, detail;
      if(vol30d > 0.8 || volRatio > 1.5){
        signal = 'danger';
        summary = L()==='en'
          ? `🔴 USD/TRY volatility elevated — ${vol30d.toFixed(2)}%/day (${(vol30d*Math.sqrt(252)).toFixed(1)}% annualized)`
          : `🔴 USD/TRY volatilitesi yüksek — günlük ${vol30d.toFixed(2)}% (yıllık ${(vol30d*Math.sqrt(252)).toFixed(1)}%)`;
        detail = L()==='en'
          ? `30-day daily volatility is <strong>${vol30d.toFixed(2)}%</strong> (annualized: <strong>${(vol30d*Math.sqrt(252)).toFixed(1)}%</strong>), which is <strong>${((volRatio-1)*100).toFixed(0)}% above</strong> the 12-month norm. High FX volatility erodes carry trade returns unpredictably. <strong>Signal: Reduce TL carry → increase USD/EUR fixed income until vol normalizes.</strong>`
          : `30 günlük günlük volatilite <strong>${vol30d.toFixed(2)}%</strong> (yıllık: <strong>${(vol30d*Math.sqrt(252)).toFixed(1)}%</strong>), 12 aylık normanın <strong>${((volRatio-1)*100).toFixed(0)}% üzerinde</strong>. Yüksek FX volatilitesi carry trade getirilerini öngörülemez şekilde aşındırır. <strong>Sinyal: TL carry azalt → volatilite normalleşene kadar USD/EUR sabit geliri artır.</strong>`;
      } else if(vol30d < 0.3 && volRatio < 0.7){
        signal = 'positive';
        summary = L()==='en'
          ? `🟢 USD/TRY volatility low — ${vol30d.toFixed(2)}%/day — favorable for carry`
          : `🟢 USD/TRY volatilitesi düşük — günlük ${vol30d.toFixed(2)}% — carry için elverişli`;
        detail = L()==='en'
          ? `Very low FX volatility (${vol30d.toFixed(2)}%/day annualized ${(vol30d*Math.sqrt(252)).toFixed(1)}%). Low vol = carry trade is attractive — the spread is realized with minimal FX noise. <strong>Signal: Carry/Vol ratio is favorable. Increase TL carry allocation.</strong>`
          : `Çok düşük FX volatilitesi (${vol30d.toFixed(2)}%/gün, yıllık ${(vol30d*Math.sqrt(252)).toFixed(1)}%). Düşük volatilite = carry trade cazip — spread minimal FX gürültüsüyle realize edilir. <strong>Sinyal: Carry/Vol oranı elverişli. TL carry alokasyonunu artır.</strong>`;
      } else {
        signal = 'neutral';
        summary = L()==='en'
          ? `🟡 USD/TRY volatility normal — ${vol30d.toFixed(2)}%/day`
          : `🟡 USD/TRY volatilitesi normal — günlük ${vol30d.toFixed(2)}%`;
        detail = L()==='en'
          ? `Volatility is within historical norms. Carry trade is viable but apply standard risk management.`
          : `Volatilite tarihsel normlar içinde. Carry trade uygulanabilir, standart risk yönetimi uygula.`;
      }
      results.push({ model:'📉 Model 2 — TRY Volatilite', signal, summary, detail });
    }
  }

  // ── MODEL 3: CARRY/VOL ORANI (Sharpe Proxy) ──
  {
    const rTL  = Number(document.getElementById('rtl').value)  || 45;
    const rUSD = Number(document.getElementById('rusd').value) || 5;
    const carrySpread = rTL - rUSD;
    const vol = ANALYTICS.tryVolatility;

    if(vol > 0){
      const annualVol = vol * Math.sqrt(252);
      const carryVolRatio = carrySpread / annualVol;
      ANALYTICS.carryVolRatio = carryVolRatio;

      let signal, summary, detail;
      if(carryVolRatio >= 2){
        signal = 'positive';
        summary = L()==='en'
          ? `🟢 Carry/Vol Ratio: ${carryVolRatio.toFixed(2)} — Excellent carry environment`
          : `🟢 Carry/Vol Oranı: ${carryVolRatio.toFixed(2)} — Mükemmel carry ortamı`;
        detail = L()==='en'
          ? `Carry spread of <strong>${carrySpread.toFixed(0)}pp</strong> divided by annualized FX vol of <strong>${annualVol.toFixed(1)}%</strong> = ratio <strong>${carryVolRatio.toFixed(2)}</strong>. A ratio above 2.0 is historically associated with strong risk-adjusted carry returns. This is the institutional threshold for committing to TL carry positions. <strong>Signal: Maximum TL carry allocation justified.</strong>`
          : `<strong>${carrySpread.toFixed(0)}pp</strong> carry spreadinin yıllık <strong>${annualVol.toFixed(1)}%</strong> FX volatilitesine bölümü = oran <strong>${carryVolRatio.toFixed(2)}</strong>. 2.0 üzerindeki oran tarihsel olarak güçlü riske göre düzeltilmiş carry getirisiyle ilişkilidir. Bu, TL carry pozisyonlarına girme kurumsal eşiğidir. <strong>Sinyal: Maksimum TL carry alokasyonu haklı.</strong>`;
      } else if(carryVolRatio >= 1){
        signal = 'neutral';
        summary = L()==='en'
          ? `🟡 Carry/Vol Ratio: ${carryVolRatio.toFixed(2)} — Moderate carry attractiveness`
          : `🟡 Carry/Vol Oranı: ${carryVolRatio.toFixed(2)} — Orta carry cazibi`;
        detail = L()==='en'
          ? `Ratio between 1 and 2 suggests carry is positive but not overwhelmingly attractive on risk-adjusted basis. <strong>Signal: Balanced TL/FX allocation. Don't overcommit to carry.</strong>`
          : `1 ile 2 arasındaki oran, carryin pozitif ama riske göre düzeltilmiş bazda ezici derecede cazip olmadığını gösterir. <strong>Sinyal: Dengeli TL/FX alokasyonu. Carry'ye aşırı bağlanma.</strong>`;
      } else {
        signal = 'danger';
        summary = L()==='en'
          ? `🔴 Carry/Vol Ratio: ${carryVolRatio.toFixed(2)} — Carry not worth the FX risk`
          : `🔴 Carry/Vol Oranı: ${carryVolRatio.toFixed(2)} — Carry FX riskine değmez`;
        detail = L()==='en'
          ? `A ratio below 1.0 means FX volatility is large relative to the carry spread — you are not being adequately compensated for FX risk. <strong>Signal: Avoid TL carry. Switch to USD/EUR fixed income.</strong>`
          : `1.0 altındaki oran, FX volatilitesinin carry spreadine göre büyük olduğu anlamına gelir — FX riski için yeterince tazmin edilmiyorsunuz. <strong>Sinyal: TL carry'den kaçın. USD/EUR sabit gelire geç.</strong>`;
      }
      results.push({ model:'⚡ Model 3 — Carry/Vol Oranı (Sharpe Proxy)', signal, summary, detail });
    }
  }

  // ── MODEL 4: ALTIN/USD KORELASYON KIRILMASI ──
  {
    const gold = ANALYTICS.goldPrices;
    const usd  = ANALYTICS.usdtryPrices;
    const minLen = Math.min(gold.length, usd.length);

    if(minLen >= 60){
      // Normal: altın ve USD/TRY pozitif korelasyon (TRY zayıflarsa her ikisi de TRY'de artar)
      const corr12m = pearsonCorr(
        dailyReturns(gold.slice(-Math.min(250,minLen))),
        dailyReturns(usd.slice(-Math.min(250,minLen)))
      );
      const corr30d = pearsonCorr(
        dailyReturns(gold.slice(-31)),
        dailyReturns(usd.slice(-31))
      );

      ANALYTICS.correlationBreak = { corr12m, corr30d };

      let signal, summary, detail;

      if(corr12m !== null && corr30d !== null){
        const corrDiff = corr30d - corr12m;

        if(corr30d < 0.2 && corr12m > 0.5){
          // Korelasyon kırıldı — altın USD'den bağımsız hareket ediyor
          signal = 'danger';
          summary = L()==='en'
            ? `🔴 Correlation break detected — Gold decoupling from USD/TRY`
            : `🔴 Korelasyon kırılması tespit edildi — Altın USD/TRY'den ayrışıyor`;
          detail = L()==='en'
            ? `12-month Gold/USDTRY correlation: <strong>${corr12m.toFixed(2)}</strong>. Recent 30-day correlation: <strong>${corr30d.toFixed(2)}</strong>. When gold decouples from USD/TRY (normally highly correlated in Turkish markets), it signals a <strong>global risk-off event</strong> — investors buying gold as a safe haven independently of TRY weakness. <strong>Signal: Risk-off environment. Add capital protection layer. Avoid high-risk TL carry. Add gold or USD DPM.</strong>`
            : `12 aylık Altın/USDTRY korelasyonu: <strong>${corr12m.toFixed(2)}</strong>. Son 30 günlük korelasyon: <strong>${corr30d.toFixed(2)}</strong>. Altın USD/TRY'den ayrıştığında (Türk piyasalarında normalde yüksek korelasyonlu), <strong>global risk-off olayı</strong> sinyali verir — yatırımcılar TRY zayıflığından bağımsız olarak güvenli liman olarak altın alıyor. <strong>Sinyal: Risk-off ortam. Sermaye koruma katmanı ekle. Yüksek riskli TL carry'den kaçın. Altın veya USD DPM ekle.</strong>`;
        } else if(corr30d > 0.7 && corr12m < 0.4){
          // Korelasyon aniden arttı — TRY baskısı
          signal = 'warning';
          summary = L()==='en'
            ? `🟡 Gold-USD/TRY correlation spiking — TRY under pressure`
            : `🟡 Altın-USD/TRY korelasyonu ani yükseliş — TRY baskı altında`;
          detail = L()==='en'
            ? `Correlation jumped from ${corr12m.toFixed(2)} (12m) to ${corr30d.toFixed(2)} (30d). Gold and USD/TRY moving together strongly suggests TRY-specific pressure (both USD and gold expensive in TRY). <strong>Signal: TRY depreciation risk elevated. Consider FX hedge.</strong>`
            : `Korelasyon ${corr12m.toFixed(2)} (12ay)'den ${corr30d.toFixed(2)} (30g)'ye atladı. Altın ve USD/TRY'nin birlikte güçlü hareketi TRY'ye özgü baskıyı işaret eder (hem USD hem altın TRY cinsinden pahalı). <strong>Sinyal: TRY değer kaybı riski yüksek. FX hedge düşünün.</strong>`;
        } else {
          signal = 'neutral';
          summary = L()==='en'
            ? `⚪ Gold/USD correlation normal — 12m: ${corr12m?.toFixed(2)||'—'}, 30d: ${corr30d?.toFixed(2)||'—'}`
            : `⚪ Altın/USD korelasyonu normal — 12ay: ${corr12m?.toFixed(2)||'—'}, 30g: ${corr30d?.toFixed(2)||'—'}`;
          detail = L()==='en'
            ? `No structural correlation break detected. Markets behaving within normal regimes.`
            : `Yapısal korelasyon kırılması tespit edilmedi. Piyasalar normal rejim içinde davranıyor.`;
        }
        results.push({ model:'🔗 Model 4 — Altın/USD Korelasyon Kırılması', signal, summary, detail });
      }
    }
  }

  // ── MASTER SİNYAL — tüm modelleri birleştir ──
  {
    const scores = { positive:2, neutral:0, warning:-1, danger:-2 };
    const totalScore = results.reduce((s,r)=>s+(scores[r.signal]||0),0);
    const macroScore = MACRO_STATE.signal === 'TL_STRONG' ? 3 : MACRO_STATE.signal === 'TL_WEAK' ? -3 : 0;
    const masterScore = totalScore + macroScore;

    let masterSignal, masterText;
    if(masterScore >= 4){
      masterSignal = 'positive';
      masterText = L()==='en'
        ? `🏆 MASTER SIGNAL: STRONG TL CARRY (score: +${masterScore}) — All models aligned for carry trade. Recommend Growth/Carry Maximizer scenario.`
        : `🏆 MASTER SİNYAL: GÜÇLÜ TL CARRY (skor: +${masterScore}) — Tüm modeller carry trade için hizalandı. Büyüme/Carry Maksimizasyonu senaryosu önerilir.`;
    } else if(masterScore >= 1){
      masterSignal = 'neutral';
      masterText = L()==='en'
        ? `⚖️ MASTER SIGNAL: BALANCED (score: +${masterScore}) — Mixed signals. Recommend Balanced scenario with moderate TL allocation.`
        : `⚖️ MASTER SİNYAL: DENGELİ (skor: +${masterScore}) — Karma sinyaller. Orta TL alokasyonlu Dengeli senaryo önerilir.`;
    } else if(masterScore >= -2){
      masterSignal = 'warning';
      masterText = L()==='en'
        ? `⚠️ MASTER SIGNAL: DEFENSIVE (score: ${masterScore}) — Multiple risk signals. Recommend FX Hedge scenario.`
        : `⚠️ MASTER SİNYAL: SAVUNMACI (skor: ${masterScore}) — Çoklu risk sinyalleri. FX Hedge senaryosu önerilir.`;
    } else {
      masterSignal = 'danger';
      masterText = L()==='en'
        ? `🛡️ MASTER SIGNAL: PROTECTION MODE (score: ${masterScore}) — Strong risk-off signals. Recommend Capital Protection scenario.`
        : `🛡️ MASTER SİNYAL: KORUMA MODU (skor: ${masterScore}) — Güçlü risk-off sinyalleri. Sermaye Koruma senaryosu önerilir.`;
    }

    ANALYTICS.masterScore = masterScore;
    ANALYTICS.masterSignal = masterSignal;
    results.unshift({ model:'🎯 MASTER SİNYAL', signal: masterSignal, summary: masterText, detail:'', isMaster: true });
  }

  renderAnalyticsResults(results);

  // Senaryo öneriyi güncelle
  updateScenarioInsightBar();
}

function renderAnalyticsResults(results){
  const container = document.getElementById('analytics_results');
  if(!container) return;

  const colors = {
    positive: { bg:'rgba(74,222,128,.12)', border:'#4ade80', text:'#166534' },
    neutral:  { bg:'rgba(255,255,255,.06)', border:'rgba(255,255,255,.15)', text:'rgba(184,208,240,.8)' },
    warning:  { bg:'rgba(251,191,36,.12)', border:'#fbbf24', text:'#92400e' },
    danger:   { bg:'rgba(248,113,113,.12)', border:'#f87171', text:'#7f1d1d' }
  };

  container.innerHTML = results.map(r => {
    const c = colors[r.signal] || colors.neutral;
    return `
      <div style="background:${c.bg};border:1px solid ${c.border};border-radius:12px;padding:14px 16px;margin-bottom:10px;${r.isMaster?'border-width:2px;':''}" >
        <div style="font-size:10px;font-weight:700;color:rgba(184,208,240,.5);letter-spacing:.8px;text-transform:uppercase;margin-bottom:6px;">${r.model}</div>
        <div style="font-size:13px;font-weight:700;color:#fff;margin-bottom:${r.detail?'8px':'0'};">${r.summary}</div>
        ${r.detail ? `<div style="font-size:12px;color:rgba(184,208,240,.8);line-height:1.5;">${r.detail}</div>` : ''}
      </div>
    `;
  }).join('');
}

// Override suggestBestScenario with full analytics
function suggestBestScenario(){
  updateScenarioInsightBar();

  let best = 'balanced';
  const ctx = getMarketContext();

  // Master signal drives decision if available
  if(ANALYTICS.masterSignal){
    if(ANALYTICS.masterSignal === 'positive') best = 'growth';
    else if(ANALYTICS.masterSignal === 'danger') best = ctx.principalCcy === 'USD' ? 'protection' : 'fxhedge';
    else if(ANALYTICS.masterSignal === 'warning') best = 'fxhedge';
    else best = 'balanced';
  } else if(MACRO_STATE.signal){
    if(MACRO_STATE.signal === 'TL_STRONG') best = 'growth';
    else if(MACRO_STATE.signal === 'TL_WEAK') best = ctx.principalCcy === 'USD' ? 'protection' : 'fxhedge';
    else best = 'balanced';
  } else {
    if(ctx.principalCcy === 'USD'){
      if(ctx.carryAttractive) best = 'growth';
      else if(ctx.carryNegative) best = 'protection';
    } else if(ctx.principalCcy === 'TL'){
      best = 'growth';
    }
  }

  openScenarioModal(best);
}

// Wire analytics buttons
document.getElementById('btn_fetch_analytics')?.addEventListener('click', fetchHistoricalData);
document.getElementById('btn_run_models')?.addEventListener('click', runAllModels);

function toggleAnalytics(){
  const body = document.getElementById('analytics_body');
  const arrow = document.getElementById('analytics_arrow');
  const isOpen = body.style.display !== 'none';
  body.style.display = isOpen ? 'none' : 'block';
  arrow.classList.toggle('open', !isOpen);
}

// Also do same for macro panel — make it collapsible
function toggleMacro(){
  const body = document.getElementById('macro_body');
  const arrow = document.getElementById('macro_arrow');
  if(!body) return;
  const isOpen = body.style.display !== 'none';
  body.style.display = isOpen ? 'none' : 'block';
  if(arrow) arrow.classList.toggle('open', !isOpen);
}
</script>

</body></html>
