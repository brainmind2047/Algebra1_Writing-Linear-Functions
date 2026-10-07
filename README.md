<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Sopaan · Writing Linear Functions</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,500;9..144,700&family=Source+Sans+3:wght@400;600;700&family=IBM+Plex+Mono:wght@500;600&display=swap">
<style>
  html,body{margin:0;} img{max-width:100%;} [hidden]{display:none !important;}
  :root{
    --navy:#16264A; --navy-2:#1F3B6B; --gold:#C79A3E; --gold-soft:#F3E7C9;
    --paper:#FBF9F4; --paper-2:#F1EAD8; --card:#FFFFFF;
    --ink:#211E1A; --ink-soft:#655D4C; --rule:#E4DCC8;
    --success:#2E8B57; --success-soft:#E1F2E7;
    --danger:#BF4B45; --danger-soft:#FAE3E1;
    --locked:#C7BEA9;
    --focus:#1F3B6B;
    --accent-text:#1F3B6B; --retry-text:#8A661F;
    color-scheme:light;
  }
  @media (prefers-color-scheme: dark){
    :root:not([data-theme="light"]){
      --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
      --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
      --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
      --success:#7BC79A; --success-soft:#1B2E22;
      --danger:#E38884; --danger-soft:#331D1B;
      --locked:#4A4436;
      --focus:#E0B75B;
      --accent-text:#E0B75B; --retry-text:#E0B75B;
      color-scheme:dark;
    }
  }
  :root[data-theme="dark"]{
    --navy:#0E1830; --navy-2:#16264A; --gold:#E0B75B; --gold-soft:#3A2F16;
    --paper:#141210; --paper-2:#1C1914; --card:#1C1914;
    --ink:#EDE7DA; --ink-soft:#B2A996; --rule:#3A342A;
    --success:#7BC79A; --success-soft:#1B2E22;
    --danger:#E38884; --danger-soft:#331D1B;
    --locked:#4A4436;
    --focus:#E0B75B;
    --accent-text:#E0B75B; --retry-text:#E0B75B;
    color-scheme:dark;
  }

  *{box-sizing:border-box;}
  body{background:var(--paper); color:var(--ink); font-family:'Source Sans 3',-apple-system,'Segoe UI',sans-serif; padding-inline:0; padding-block:0;}
  h1,h2,h3{font-family:'Fraunces',Georgia,serif; text-wrap:balance; margin:0;}
  .num{font-family:'IBM Plex Mono',ui-monospace,monospace; font-variant-numeric:tabular-nums;}

  header.brand{
    background:linear-gradient(155deg,var(--navy) 0%, var(--navy-2) 100%);
    color:#F4EFDF; padding-block:calc(20px + env(safe-area-inset-top,0px)) 18px; padding-inline:20px;
  }
  .brand-row{display:flex; align-items:center; gap:12px; max-width:900px; margin:0 auto;}
  .crest{
    width:42px; height:42px; border-radius:10px; background:var(--gold); color:var(--navy);
    display:flex; align-items:center; justify-content:center; font-family:'Fraunces',serif; font-weight:700; font-size:18px; flex-shrink:0;
  }
  .brand-name{font-size:12px; letter-spacing:.08em; text-transform:uppercase; color:var(--gold); font-weight:700;}
  .series-name{font-size:19px; font-weight:700; font-family:'Fraunces',serif;}
  .chapter-eyebrow{max-width:900px; margin:14px auto 0; font-size:12px; letter-spacing:.06em; text-transform:uppercase; color:#AEB9D6;}
  .chapter-title{font-size:28px; max-width:900px; margin:2px auto 0;}
  .chapter-sub{font-size:14.5px; color:var(--gold); font-weight:700; max-width:900px; margin:3px auto 0;}

  .chapter-progress{max-width:900px; margin:14px auto 0; display:flex; align-items:center; gap:10px;}
  .cp-track{flex:1; height:6px; border-radius:99px; background:rgba(255,255,255,.18); overflow:hidden;}
  .cp-fill{height:100%; background:var(--gold); border-radius:99px; transition:width .3s ease;}
  .cp-label{font-size:11.5px; color:#CFD7EA; white-space:nowrap;}

  .tabbar{position:sticky; top:env(safe-area-inset-top,0px); z-index:15; background:var(--paper); border-bottom:1px solid var(--rule); overflow-x:auto; white-space:nowrap;}
  .tabbar-inner{max-width:900px; margin:0 auto; display:flex; padding-inline:16px;}
  .tab-btn{font-family:inherit; font-size:14px; font-weight:600; color:var(--ink-soft); background:none; border:none; padding:13px 16px; cursor:pointer; position:relative; flex-shrink:0;}
  .tab-btn.active{color:var(--accent-text);}
  .tab-btn.active::after{content:''; position:absolute; left:12px; right:12px; bottom:0; height:3px; background:var(--gold); border-radius:3px 3px 0 0;}
  .tab-count{font-size:11px; color:var(--ink-soft); margin-left:5px;}

  .slide-progress{max-width:900px; margin:0 auto; padding:10px 16px 0; display:flex; align-items:center; gap:10px;}
  .sp-track{flex:1; height:5px; border-radius:99px; background:var(--rule); overflow:hidden;}
  .sp-fill{height:100%; background:var(--accent-text); border-radius:99px; transition:width .3s ease;}
  .sp-label{font-size:12px; color:var(--ink-soft); white-space:nowrap; font-weight:600;}

  .wrap{max-width:900px; margin:0 auto; padding:16px 16px calc(110px + env(safe-area-inset-bottom,0px));}

  .qcard{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px;}
  .qhead{display:flex; align-items:flex-start; gap:10px; margin-bottom:10px;}
  .qnum{width:32px; height:32px; border-radius:8px; background:var(--gold-soft); color:var(--accent-text); display:flex; align-items:center; justify-content:center; font-weight:700; font-family:'Fraunces',serif; flex-shrink:0; font-size:14px;}
  .qtext{font-size:16px; line-height:1.55; flex:1;}
  .qtag{font-size:10.5px; color:var(--gold); background:var(--gold-soft); padding:2px 7px; border-radius:99px; font-weight:700; margin-left:6px; white-space:nowrap;}
  .marks-pill{font-size:11px; font-weight:700; color:var(--ink-soft); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; margin-left:auto; flex-shrink:0; white-space:nowrap;}
  .step-badge{font-size:11px; font-weight:700; color:var(--accent-text); background:var(--paper-2); border:1px solid var(--rule); padding:3px 9px; border-radius:99px; display:inline-block; margin-bottom:12px;}

  .options{display:flex; flex-direction:column; gap:8px; margin-top:10px;}
  .opt{display:flex; align-items:center; gap:10px; padding:11px 12px; border:1.5px solid var(--rule); border-radius:10px; cursor:pointer; font-size:15px; background:var(--paper);}
  .opt input{accent-color:var(--navy-2);}
  .opt.is-correct{border-color:var(--success); background:var(--success-soft);}
  .opt.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .opt.locked{cursor:not-allowed;}

  .subpart-label{font-weight:700; font-size:12.5px; color:var(--accent-text); text-transform:uppercase; letter-spacing:.03em; margin:14px 0 6px;}
  .or-divider{text-align:center; font-size:11px; font-weight:700; letter-spacing:.08em; color:var(--ink-soft); margin:8px 0;}

  .steps{display:flex; flex-direction:column; gap:10px;}
  .step-line{font-size:14.5px; line-height:1.9; background:var(--paper); border:1px dashed var(--rule); border-radius:10px; padding:9px 12px;}
  .step-line.resolved{opacity:.9;}
  .blank-input{font-family:'IBM Plex Mono',monospace; font-size:14px; border:1.5px solid var(--rule); border-radius:6px; padding:3px 8px; width:120px; background:var(--card); color:var(--ink); margin:0 2px;}
  .blank-input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .blank-input.is-correct{border-color:var(--success); background:var(--success-soft);}
  .blank-input.is-wrong{border-color:var(--danger); background:var(--danger-soft);}
  .blank-input[disabled]{opacity:.85;}
  .reveal-note{font-size:12px; color:var(--danger); padding-left:2px; margin-top:-2px;}

  .feedback{font-size:13.5px; padding:10px 12px; border-radius:9px; margin-top:14px; display:none;}
  .feedback.show{display:block;}
  .feedback.ok{background:var(--success-soft); color:var(--success);}
  .feedback.retry{background:var(--gold-soft); color:var(--retry-text);}
  .feedback.reveal{background:var(--danger-soft); color:var(--danger);}
  .feedback.err{background:var(--danger-soft); color:var(--danger);}
  .attempts-dots{display:inline-flex; gap:4px; margin-left:2px;}
  .attempts-dots span{width:6px; height:6px; border-radius:50%; background:var(--ink-soft); opacity:.3; display:inline-block;}
  .attempts-dots span.used{opacity:1; background:var(--danger);}

  .ar-box{background:var(--paper-2); border-radius:10px; padding:10px 12px; margin-bottom:12px; font-size:13px; color:var(--ink-soft);}

  .navbar{
    position:fixed; left:0; right:0; bottom:0; z-index:30; background:var(--paper);
    border-top:1px solid var(--rule); padding:10px 16px calc(10px + env(safe-area-inset-bottom,0px));
  }
  .navbar-inner{max-width:900px; margin:0 auto; display:flex; gap:8px; flex-wrap:wrap; align-items:center;}
  .btn{font-family:inherit; font-size:13.5px; font-weight:700; padding:10px 14px; border-radius:9px; border:1.5px solid var(--rule); background:var(--card); color:var(--ink); cursor:pointer;}
  .btn:hover{border-color:var(--navy-2);}
  .btn:disabled{opacity:.4; cursor:not-allowed;}
  .btn-primary{background:var(--navy-2); color:#fff; border-color:var(--navy-2);}
  .navbar .spacer{flex:1;}

  .fab{position:fixed; right:16px; bottom:calc(74px + env(safe-area-inset-bottom,0px)); background:var(--gold); color:var(--navy); border:none; border-radius:999px; padding:11px 16px; font-family:inherit; font-weight:700; font-size:13px; display:flex; align-items:center; gap:7px; cursor:pointer; box-shadow:0 6px 16px rgba(0,0,0,.18); z-index:35;}
  .fab-badge{background:rgba(255,255,255,.55); border-radius:99px; padding:1px 7px; font-size:11px;}

  .overlay{position:fixed; inset:0; background:rgba(20,18,14,.45); z-index:50; display:none; align-items:flex-end; justify-content:center;}
  .overlay.show{display:flex;}
  .palette{background:var(--card); width:min(480px,100%); max-height:78vh; overflow-y:auto; border-radius:18px 18px 0 0; padding:18px 18px calc(18px + env(safe-area-inset-bottom,0px)); border:1px solid var(--rule); border-bottom:none;}
  @media (min-width:640px){ .overlay{align-items:center;} .palette{border-radius:18px; border-bottom:1px solid var(--rule); max-height:74vh;} }
  .palette-head{display:flex; align-items:center; justify-content:space-between; margin-bottom:6px;}
  .palette-head h2{font-size:16px;}
  .palette-close{background:none; border:none; font-size:20px; color:var(--ink-soft); cursor:pointer; padding:4px;}
  .palette-legend{display:flex; gap:12px; flex-wrap:wrap; font-size:11px; color:var(--ink-soft); margin:10px 0 14px;}
  .palette-legend span{display:inline-flex; align-items:center; gap:5px;}
  .dot{width:9px; height:9px; border-radius:50%; display:inline-block;}
  .dot.correct{background:var(--success);} .dot.revealed{background:var(--danger);}
  .dot.skipped{background:var(--gold);} .dot.locked{background:var(--locked);}
  .dot.current{background:var(--navy-2);}
  .chip-grid{display:grid; grid-template-columns:repeat(auto-fill,minmax(48px,1fr)); gap:8px;}
  .chip{border:1.5px solid var(--rule); border-radius:9px; padding:8px 4px; text-align:center; font-family:'IBM Plex Mono',monospace; font-size:12.5px; font-weight:600; cursor:pointer; background:var(--paper); color:var(--ink);}
  .chip[data-status="correct"]{border-color:var(--success); background:var(--success-soft); color:var(--success);}
  .chip[data-status="revealed"]{border-color:var(--danger); background:var(--danger-soft); color:var(--danger);}
  .chip[data-status="skipped"]{border-color:var(--gold); background:var(--gold-soft); color:var(--retry-text);}
  .chip[data-status="locked"]{border-color:var(--rule); color:var(--locked); cursor:not-allowed; background:var(--paper-2);}
  .chip[data-status="current"]{outline:2px solid var(--navy-2); outline-offset:1px;}

  .toast{position:fixed; left:50%; bottom:calc(140px + env(safe-area-inset-bottom,0px)); transform:translateX(-50%); background:var(--ink); color:var(--paper); padding:9px 16px; border-radius:99px; font-size:13px; opacity:0; pointer-events:none; transition:opacity .25s ease; z-index:60;}
  .toast.show{opacity:1;}

  .done-card{text-align:center; padding:36px 20px;}
  .done-card .big{font-size:38px; margin-bottom:6px;}
  .score-pills{display:flex; gap:10px; justify-content:center; flex-wrap:wrap; margin:16px 0;}
  .score-pill{padding:8px 16px; border-radius:99px; font-size:13px; font-weight:700;}

  footer.brandfoot{max-width:900px; margin:14px auto 0; padding:0 16px calc(110px + env(safe-area-inset-bottom,0px)); text-align:center; font-size:12px; color:var(--ink-soft);}

  .mode-pill{font-family:inherit; font-size:12.5px; font-weight:700; color:var(--navy); background:var(--gold); border:none; border-radius:99px; padding:6px 14px; cursor:pointer; margin-top:12px; display:inline-flex; align-items:center; gap:6px;}
  .mode-pick{display:flex; flex-direction:column; gap:14px; padding:8px 0 24px;}
  .mode-card{background:var(--card); border:1.5px solid var(--rule); border-radius:16px; padding:22px; cursor:pointer; text-align:left;}
  .mode-card:hover{border-color:var(--navy-2);}
  .mode-card .mode-icon{font-size:26px; margin-bottom:8px;}
  .mode-card h3{font-size:18px; margin-bottom:6px;}
  .mode-card p{font-size:13.5px; color:var(--ink-soft); line-height:1.5; margin:0;}
  .quiz-hint{font-size:12.5px; color:var(--ink-soft); background:var(--paper-2); border-radius:9px; padding:8px 12px; margin-bottom:14px;}
  .review-row{border:1px solid var(--rule); border-radius:10px; padding:11px 13px; margin-bottom:10px;}
  .review-tag{font-size:11.5px; font-weight:700; margin-bottom:4px; display:block;}
  .review-tag.ok{color:var(--success);} .review-tag.bad{color:var(--danger);} .review-tag.na{color:var(--ink-soft);}
  .review-q{font-size:13.5px; margin-bottom:6px; color:var(--ink-soft);}
  .review-ans{font-size:13px; margin-bottom:2px;}

  .who-row{max-width:900px; margin:12px auto 0; display:flex; flex-wrap:wrap; gap:8px; align-items:center;}
  .who-row .mode-pill{margin-top:0;}
  .who{display:inline-flex; flex-wrap:wrap; align-items:center; gap:6px; font-size:12.5px; color:#CFD7EA;}
  .who b{color:#F4EFDF;}
  .who button{font-family:inherit; font-size:12px; font-weight:700; color:#F4EFDF; background:rgba(255,255,255,.12); border:1px solid rgba(255,255,255,.22); border-radius:99px; padding:5px 11px; cursor:pointer;}
  .who button:hover{background:rgba(255,255,255,.2);}
  .login-card{max-width:460px; margin:8px auto 0; background:var(--card); border:1px solid var(--rule); border-radius:16px; padding:22px;}
  .login-card h2{font-size:21px; margin-bottom:4px;}
  .login-card p.lead{font-size:13.5px; color:var(--ink-soft); margin:0 0 16px; line-height:1.5;}
  .fld{display:flex; flex-direction:column; gap:5px; margin-bottom:12px;}
  .fld label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .fld input{font-family:inherit; font-size:15px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:9px; background:var(--paper); color:var(--ink);}
  .fld input:focus{outline:none; border-color:var(--focus); box-shadow:0 0 0 3px var(--gold-soft);}
  .fld-row{display:grid; grid-template-columns:1fr 1fr; gap:10px;}
  .login-err{font-size:13px; color:var(--danger); background:var(--danger-soft); border-radius:8px; padding:8px 10px; margin-bottom:12px;}
  .login-note{font-size:12px; color:var(--ink-soft); margin-top:12px; line-height:1.5;}
  .known{margin:0 0 16px; display:flex; flex-direction:column; gap:6px;}
  .known-label{font-size:12px; font-weight:700; letter-spacing:.04em; text-transform:uppercase; color:var(--ink-soft);}
  .known-btn{display:flex; justify-content:space-between; align-items:center; gap:10px; text-align:left; font-family:inherit; font-size:14.5px; padding:10px 12px; border:1.5px solid var(--rule); border-radius:10px; background:var(--paper); color:var(--ink); cursor:pointer;}
  .known-btn:hover{border-color:var(--navy-2);}
  .known-btn small{font-size:12px; color:var(--ink-soft);}
  .rec-card{background:var(--card); border:1px solid var(--rule); border-radius:14px; padding:18px; margin-bottom:14px;}
  .rec-card h2{font-size:19px; margin-bottom:10px;}
  .rec-card h3{font-size:15px; margin:4px 0 8px;}
  .rec-table-wrap{overflow-x:auto;}
  .rec-table{width:100%; border-collapse:collapse; font-size:13.5px; font-variant-numeric:tabular-nums;}
  .rec-table th{text-align:left; font-size:11.5px; text-transform:uppercase; letter-spacing:.04em; color:var(--ink-soft); padding:6px 8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-table td{padding:8px; border-bottom:1px solid var(--rule); white-space:nowrap;}
  .rec-bar{display:inline-block; width:70px; height:6px; border-radius:99px; background:var(--rule); overflow:hidden; vertical-align:middle; margin-right:6px;}
  .rec-bar i{display:block; height:100%; background:var(--success);}
  .rec-empty{font-size:13.5px; color:var(--ink-soft);}
  .sec-sub{max-width:900px; margin:0 auto; padding:10px 16px 0; font-size:12.5px; font-weight:700; color:var(--accent-text); letter-spacing:.02em;}
  .opt{flex-wrap:wrap;}
  .opt-l{font-family:'IBM Plex Mono',monospace; font-size:13px; font-weight:600; color:var(--ink-soft);}
  .opt-t{flex:1; min-width:0;}
  .opt.is-chosen:not(.is-correct):not(.is-wrong){border-color:var(--navy-2); background:var(--gold-soft);}
  .opt-tag{font-size:11px; font-weight:700; padding:2px 8px; border-radius:99px; background:var(--card); border:1px solid currentColor; white-space:nowrap;}
  .opt.is-correct .opt-tag{color:var(--success);} .opt.is-wrong .opt-tag{color:var(--danger);} .opt.is-chosen:not(.is-correct):not(.is-wrong) .opt-tag{color:var(--accent-text);}
  .chosen{font-size:13.5px; margin-top:10px; padding:8px 12px; border-radius:9px;}
  .chosen.ok{background:var(--success-soft); color:var(--success);} .chosen.bad{background:var(--danger-soft); color:var(--danger);}
  .chosen + .chosen{margin-top:6px;}
  .solution{margin-top:14px; border:1px solid var(--rule); border-left:4px solid var(--gold); background:var(--paper-2); border-radius:10px; padding:12px 14px;}
  .sol-h{font-family:'Fraunces',Georgia,serif; font-weight:700; font-size:14px; color:var(--accent-text); margin-bottom:6px;}
  .sol-line{font-size:14.5px; line-height:1.7;}
  .rev-sol summary{cursor:pointer; font-size:12.5px; font-weight:700; color:var(--accent-text); margin-top:6px;}
  .rev-sol .solution{margin-top:8px;}
  .chapter-credit{max-width:900px; margin:4px auto 0; font-size:12px; color:#CFD7EA;}
  footer.brandfoot a{color:inherit;}
  .blank-input.wide{width:260px; max-width:100%; font-family:'Source Sans 3',sans-serif;}
  .blank-input.expr{width:170px; max-width:100%;}
  /*fix-layout*/ .cp-fill,.sp-fill{width:0;} .fld{min-width:0;} .fld input{width:100%; min-width:0; box-sizing:border-box;}
  .fig{margin:6px 0 10px; display:flex; justify-content:center;}
  .figsvg{width:100%; max-width:340px; height:auto; overflow:visible;}
  .figsvg .ln,.figsvg .arm{stroke:var(--ink); stroke-width:1.6; fill:none;}
  .figsvg .arm{stroke:var(--accent-text); stroke-width:2;}
  .figsvg .pt{fill:var(--ink);}
  .figsvg .lb{fill:var(--ink); font:600 13px 'Source Sans 3',sans-serif;}
  .figsvg .al{fill:var(--accent-text); font:700 12px 'Source Sans 3',sans-serif;}
  .figsvg .wg{fill:var(--gold-soft); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .wg2{fill:rgba(199,154,62,.35); stroke:var(--gold); stroke-width:1.2;}
  .figsvg .ra{fill:none; stroke:var(--ink); stroke-width:1.2;}
  .figsvg .ahd{fill:var(--ink);}
  .figsvg .pr{fill:var(--paper-2); stroke:var(--ink-soft); stroke-width:1.2;}
  .figsvg .tk{stroke:var(--ink-soft); stroke-width:.8;}
  .figsvg .po{fill:var(--ink); font:600 8.5px 'IBM Plex Mono',monospace;}
  .figsvg .pi{fill:var(--danger); font:600 7.5px 'IBM Plex Mono',monospace;}
  .figsvg .sh{fill:var(--gold-soft); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh2{fill:rgba(199,154,62,.38); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .sh3{fill:rgba(199,154,62,.22); stroke:var(--ink); stroke-width:1.5; stroke-linejoin:round;}
  .figsvg .none{fill:none;}
  .figsvg .hid{stroke-dasharray:5 4; fill:none;}
  .figsvg .tick{stroke:var(--ink); stroke-width:1.4; fill:none;}
  .figsvg .shd{fill:var(--accent-text); fill-opacity:.55;}
  .figsvg .cell{fill:var(--card); stroke:var(--ink); stroke-width:1.1;}
  .figsvg .dr{fill:var(--danger);} .figsvg .dw{fill:var(--card); stroke:var(--ink); stroke-width:1.2;}
  .figsvg .dotfill{fill:var(--danger);}
  .tt{border-collapse:collapse; font-size:13.5px; margin:4px auto; font-variant-numeric:tabular-nums;} .tt th,.tt td{border:1px solid var(--rule); padding:4px 9px; text-align:left;} .tt th{background:var(--paper-2); font-weight:700;} .ttw{overflow-x:auto; max-width:100%;}
  .fq{display:inline-flex; flex-direction:column; vertical-align:middle; text-align:center; font-size:.82em; line-height:1.12; margin:0 2px;}
  .fq>span:first-child{border-bottom:1.5px solid currentColor; padding:0 2px;}
  .fq>span:last-child{padding:0 2px;}
  .mx{white-space:nowrap;}
  .blank-input.fr{width:110px;}
  @media (prefers-reduced-motion:reduce){ *{transition:none !important;} }
.datline{display:block;margin-top:8px;padding:8px 10px;border-radius:8px;background:var(--paper-2);font:500 14px/1.7 'IBM Plex Mono',monospace;word-spacing:2px;overflow-wrap:anywhere;}

  .theory{display:flex;flex-direction:column;gap:16px;padding-bottom:40px;}
  .hub{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .hub{grid-template-columns:repeat(3,1fr);} }
  .hub-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:16px;display:flex;flex-direction:column;gap:8px;}
  .hub-card h3{font-family:'Fraunces',serif;font-size:18px;margin:0;color:var(--accent-text);}
  .hub-card p{margin:0;font-size:14px;color:var(--ink-soft);line-height:1.5;}
  .hub-btns{display:flex;flex-wrap:wrap;gap:8px;margin-top:auto;}
  .hub-btn{min-height:40px;border:1.5px solid var(--rule);background:var(--paper-2);color:var(--ink);border-radius:10px;padding:8px 12px;font:600 14px 'Source Sans 3',sans-serif;cursor:pointer;text-align:left;}
  .hub-btn:hover{border-color:var(--gold);}
  .hub-btn.primary{background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .note{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:18px;scroll-margin-top:120px;}
  .note h2{font-family:'Fraunces',serif;font-size:22px;margin:0 0 4px;color:var(--ink);}
  .note .lt{font-size:13.5px;color:var(--ink-soft);margin:0 0 12px;}
  .note .lt b{color:var(--accent-text);}
  .note h4{font:700 15px 'Source Sans 3',sans-serif;margin:16px 0 6px;color:var(--accent-text);}
  .note p,.note li{font-size:15.5px;line-height:1.6;}
  .note ul{padding-left:20px;margin:6px 0;}
  .keybox{background:var(--gold-soft);border-left:4px solid var(--gold);border-radius:8px;padding:10px 12px;margin:10px 0;font-size:15px;line-height:1.6;}
  .keybox b{color:var(--ink);}
  .ex{background:var(--paper-2);border-radius:10px;padding:12px;margin:10px 0;}
  .ex .exh{font-family:'Fraunces',serif;font-weight:700;color:var(--accent-text);margin-bottom:4px;}
  .ex .exl{font-size:15px;line-height:1.7;}
  .ttab{width:100%;border-collapse:collapse;font-size:14.5px;margin:8px 0;}
  .ttab th,.ttab td{border:1px solid var(--rule);padding:7px 8px;text-align:left;vertical-align:top;}
  .ttab th{background:var(--paper-2);}
  .tscroll{overflow-x:auto;}
  .mono{font-family:'IBM Plex Mono',monospace;font-size:.92em;}
  @media (max-width:480px){ .ttab{font-size:13.5px;} .ttab th,.ttab td{padding:6px;} }
  .note .figsvg{max-width:100%;height:auto;display:block;margin:8px auto;}


  .rep-top{display:flex;flex-wrap:wrap;gap:18px;align-items:center;justify-content:center;margin-top:8px;}
  .rep-legend{flex:1;min-width:220px;display:flex;flex-direction:column;gap:8px;}
  .rep-cap{font:700 13px 'Source Sans 3',sans-serif;color:var(--ink-soft);text-transform:uppercase;letter-spacing:.05em;}
  .rep-li{display:flex;align-items:center;gap:6px;font-size:15px;}
  .rep-n{margin-left:auto;white-space:nowrap;padding-left:8px;font-family:'IBM Plex Mono',monospace;font-weight:600;}
  .sw{display:inline-block;width:12px;height:12px;border-radius:3px;flex:none;}
  .rep-grid{display:grid;grid-template-columns:1fr;gap:12px;}
  @media (min-width:640px){ .rep-grid{grid-template-columns:1fr 1fr;} }
  .rep-card{background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:14px;display:flex;flex-direction:column;gap:10px;}
  .rep-h{display:flex;align-items:center;gap:8px;font:700 16px 'Source Sans 3',sans-serif;}
  .crit{display:inline-grid;place-items:center;width:28px;height:28px;border-radius:50%;color:var(--card);font:700 15px Fraunces,serif;flex:none;}
  .rep-row{display:flex;gap:14px;align-items:center;}
  .rep-stats{display:flex;flex-direction:column;gap:5px;font-size:14.5px;}
  .rep-stats div{display:flex;align-items:center;gap:6px;}
  .rep-lvl{margin-top:4px;color:var(--accent-text);} .rep-lvl span{color:var(--ink-soft);font-size:13px;}
  .rep-note{font-size:13px;color:var(--ink-soft);}


  .skip-chips{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin:12px 0;}
  .skip-chips .chip{min-width:48px;min-height:40px;cursor:pointer;border:1.5px solid var(--gold);background:var(--gold-soft);color:var(--retry-text);border-radius:10px;font:600 14px 'IBM Plex Mono',monospace;}
  .skip-btns{display:flex;flex-wrap:wrap;gap:10px;justify-content:center;margin-top:12px;}


  .kb-toggle{border:none;background:transparent;font-size:15px;cursor:pointer;padding:0 2px;vertical-align:middle;opacity:.7;}
  .vkb{position:fixed;left:0;right:0;bottom:0;z-index:80;background:var(--paper-2);border-top:1px solid var(--rule);box-shadow:0 -6px 20px rgba(0,0,0,.12);padding:6px 6px 8px;display:none;}
  .vkb.show{display:block;}
  .vkb-top{display:flex;justify-content:space-between;align-items:center;max-width:640px;margin:0 auto 4px;font:600 12px 'Source Sans 3',sans-serif;color:var(--ink-soft);}
  .vkb-link{border:none;background:none;color:var(--accent-text);font:600 12px 'Source Sans 3',sans-serif;cursor:pointer;text-decoration:underline;}
  .vkb-row{display:flex;gap:5px;max-width:640px;margin:0 auto 5px;}
  .vkb-k{flex:1;min-height:42px;border:1px solid var(--rule);border-radius:8px;background:var(--card);color:var(--ink);font:600 17px 'IBM Plex Mono',monospace;cursor:pointer;padding:0;}
  .vkb-k.fn{font:600 13px 'Source Sans 3',sans-serif;background:var(--gold-soft);}
  .vkb-k.done{background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .vkb-k:active{transform:scale(.96);}
  body.kb-open .wrap{padding-bottom:360px;}
  body.kb-open .fab{display:none;}
  .tool-bar{display:flex;gap:8px;flex-wrap:wrap;margin:-4px 0 10px;}
  .tool-btn{min-height:36px;border:1.5px solid var(--gold);background:var(--gold-soft);color:var(--ink);border-radius:18px;padding:4px 12px;font:600 13.5px 'Source Sans 3',sans-serif;cursor:pointer;}
  .tool-panel{position:fixed;z-index:85;background:var(--card);border:1px solid var(--rule);border-radius:14px;box-shadow:0 10px 30px rgba(0,0,0,.25);display:none;}
  .tool-panel.show{display:block;}
  .tp-head{display:flex;align-items:center;gap:8px;padding:8px 10px;border-bottom:1px solid var(--rule);font:600 14px 'Source Sans 3',sans-serif;}
  .tp-note{font-size:12px;color:var(--ink-soft);font-weight:500;}
  .tp-x{margin-left:auto;border:1px solid var(--rule);background:var(--paper-2);color:var(--ink);border-radius:8px;min-height:32px;padding:2px 10px;cursor:pointer;font:600 13px 'Source Sans 3',sans-serif;}
  .tp-x + .tp-x{margin-left:0;}
  .calc{right:12px;bottom:84px;width:min(330px,calc(100vw - 24px));}
  body.calc-open .wrap{padding-bottom:440px;}
  body.calc-open .fab{display:none;}
  @media (max-width:640px){ .calc{left:6px;right:6px;width:auto;} .calc-keys button{min-height:36px;} }
  .calc-disp{padding:8px 12px;text-align:right;background:var(--paper-2);}
  .calc-expr{font:500 13px 'IBM Plex Mono',monospace;color:var(--ink-soft);min-height:18px;word-break:break-all;}
  .calc-res{font:600 24px 'IBM Plex Mono',monospace;color:var(--ink);word-break:break-all;}
  .calc-keys{display:grid;grid-template-columns:repeat(6,1fr);gap:5px;padding:8px;}
  .calc-keys button{min-height:40px;border:1px solid var(--rule);border-radius:8px;background:var(--card);color:var(--ink);font:600 14px 'IBM Plex Mono',monospace;cursor:pointer;padding:0;}
  .calc-keys button.fn{background:var(--gold-soft);font-family:'Source Sans 3',sans-serif;font-size:13px;}
  .calc-keys button.eq{grid-column:span 2;background:var(--navy);color:#F4EFDF;border-color:var(--navy);}
  .desmos{left:50%;top:50%;transform:translate(-50%,-50%);width:min(760px,calc(100vw - 16px));height:min(560px,calc(100vh - 90px));flex-direction:column;}
  .desmos.show{display:flex;}
  #desmosBox{flex:1;min-height:0;border-radius:0 0 14px 14px;overflow:hidden;}
  .desmos-msg{padding:24px;text-align:center;color:var(--ink-soft);}
  .chip[data-status="skipped"]{cursor:pointer;}
  .chip[data-status="answered"]{border-color:var(--accent-text);color:var(--accent-text);}


  button.crest-home{border:none;padding:0;position:relative;cursor:pointer;transition:transform .15s ease;}
  button.crest-home:hover,button.crest-home:focus-visible{transform:scale(1.06);outline:2px solid var(--gold);outline-offset:2px;}
  .crest-h{position:absolute;right:-7px;bottom:-7px;width:18px;height:18px;border-radius:50%;background:#F4EFDF;color:var(--navy);font:700 12px/18px 'Source Sans 3',sans-serif;text-align:center;box-shadow:0 1px 3px rgba(0,0,0,.3);}
  .brand .brand-row{position:relative;}
  .bmasw{position:absolute;left:50%;top:50%;transform:translate(-50%,-50%);display:flex;flex-shrink:0;white-space:nowrap;align-items:center;gap:6px;background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.25);border-radius:99px;padding:5px 14px;color:#F4EFDF;}
  .bmasw-ic{font-size:16px;} .bmasw-t{font:600 20px 'IBM Plex Mono',monospace;letter-spacing:.02em;min-width:62px;text-align:center;}
  .bmasw-b{border:none;background:rgba(255,255,255,.18);color:#F4EFDF;border-radius:50%;width:30px;height:30px;cursor:pointer;font-size:13px;}
  .bmasw.off{display:none;}
  @media (max-width:560px){ .bmasw{position:static;transform:none;margin-left:auto;padding:4px 5px 4px 8px;gap:4px;} .bmasw-ic{display:none;} .bmasw-t{font-size:16px;min-width:48px;} .bmasw-b{width:26px;height:26px;} .brand .series-name{font-size:15px;} .brand .brand-name{font-size:10.5px;} .brand .brand-row>div:not(.bmasw){min-width:0;} }
  .bmasw-done{font:600 15px 'IBM Plex Mono',monospace;color:var(--accent-text);margin:4px 0 8px;}
  .sp-fab{position:fixed;left:14px;bottom:84px;z-index:60;border:1.5px solid var(--navy-2);background:var(--card);color:var(--ink);border-radius:99px;padding:9px 14px;font:700 14px 'Source Sans 3',sans-serif;box-shadow:0 4px 14px rgba(0,0,0,.15);cursor:pointer;}
  .sp-fab.on{background:var(--navy);color:#F4EFDF;}
  body.kb-open .sp-fab{display:none;}
  .sp-canvas{position:absolute;z-index:55;display:none;touch-action:none;cursor:crosshair;}
  .sp-canvas.passive{pointer-events:none;cursor:default;}
  .sp-bar{position:fixed;top:8px;left:8px;right:8px;margin:0 auto;width:max-content;z-index:90;display:none;align-items:center;gap:6px;background:var(--card);border:1px solid var(--rule);border-radius:14px;padding:6px 8px;box-shadow:0 6px 20px rgba(0,0,0,.2);max-width:calc(100vw - 16px);flex-wrap:wrap;justify-content:center;}
  .sp-lbl{font:700 13px 'Source Sans 3',sans-serif;color:var(--ink-soft);margin-right:2px;}
  .sp-pen,.sp-tool{width:38px;height:38px;border-radius:10px;border:1.5px solid var(--rule);background:var(--paper);cursor:pointer;display:inline-flex;align-items:center;justify-content:center;font-size:17px;padding:0;color:var(--ink);}
  .sp-pen i{width:20px;height:20px;border-radius:50%;display:block;}
  .sp-pen.on,.sp-tool.on{border-color:var(--navy-2);box-shadow:0 0 0 3px var(--gold-soft);}
  @media (max-width:560px){ .sp-lbl{display:none;} .sp-pen,.sp-tool{width:34px;height:34px;} .sp-fab span{display:none;} }

  /* larger reading sizes */
  .chapter-eyebrow{font-size:13.5px;}
  .chapter-title{font-size:36px;line-height:1.15;}
  .chapter-sub{font-size:16.5px;}
  .tab-btn{font-size:15.5px;}
  .sec-sub{font-size:15px;}
  .qtext{font-size:19px;line-height:1.55;}
  .qnum{width:36px;height:36px;font-size:16px;}
  .opt{font-size:17.5px;padding:12px 14px;}
  .step-line{font-size:17.5px;line-height:2;}
  .blank-input{font-size:16px;}
  .sol-line{font-size:16.5px;}
  .feedback{font-size:15px;}
  .note h2{font-size:28px;}
  .note h4{font-size:19px;}
  .note p,.note li{font-size:17.5px;line-height:1.65;}
  .note .lt{font-size:15.5px;}
  .ex .exh{font-size:18px;} .ex .exl{font-size:16.5px;}
  .keybox{font-size:16.5px;}
  .ttab{font-size:15.5px;}
  .hub-card h3{font-size:21px;} .hub-card p{font-size:15.5px;} .hub-btn{font-size:15px;}
  @media (max-width:480px){ .chapter-title{font-size:30px;} .qtext{font-size:18px;} .opt,.step-line{font-size:16.5px;} .note h2{font-size:24px;} .note p,.note li{font-size:16.5px;} }

  /* v4 celebration */
  .v4conf{position:fixed;inset:0;width:100vw;height:100vh;pointer-events:none;z-index:9999;}
  .v4ban{background:linear-gradient(135deg,var(--gold-soft),var(--card));border:2px solid var(--gold);border-radius:18px;padding:18px 14px 16px;margin:-4px 0 18px;text-align:center;animation:v4pop .55s cubic-bezier(.2,1.6,.4,1);}
  @keyframes v4pop{0%{transform:scale(.6);opacity:0}100%{transform:scale(1);opacity:1}}
  .v4trophy{font-size:54px;line-height:1;animation:v4bob 1.4s ease-in-out infinite;}
  @keyframes v4bob{0%,100%{transform:translateY(0) rotate(-6deg)}50%{transform:translateY(-6px) rotate(6deg)}}
  .v4h{font-size:28px;font-weight:800;color:var(--accent-text);margin-top:6px;}
  .v4m{font-size:19px;color:var(--ink);margin-top:4px;}
  .v4pills{display:flex;flex-wrap:wrap;gap:8px;justify-content:center;margin-top:12px;}
  .v4p{font-size:16px;font-weight:700;border-radius:999px;padding:6px 12px;}
  .v4p.g{background:var(--success-soft);color:var(--success);} .v4p.o{background:var(--gold-soft);color:var(--retry-text);}
  .v4p.r{background:var(--danger-soft);color:var(--danger);} .v4p.s{background:var(--rule);color:var(--ink);}
  .v4next{margin-top:14px;} .v4go{font-size:18px !important;padding:13px 20px !important;}
  .v4rec td.v4g{color:var(--success);font-weight:700;} .v4rec td.v4o{color:var(--retry-text);font-weight:700;} .v4rec td.v4r{color:var(--danger);font-weight:700;}
  .v4rec tr.v4tot td{font-weight:800;border-top:2px solid var(--rule);}
  .v4rec th{font-size:12.5px;padding:6px 3px !important;white-space:nowrap;} .v4rec td{font-size:15px;padding:7px 3px !important;text-align:center;}
  .v4rec td:first-child,.v4rec th:first-child{text-align:left;white-space:normal;min-width:92px;max-width:150px;font-size:14.5px;}
  @media(max-width:460px){ .v4left{display:none;} }
  .v4leg{font-size:14.5px;color:var(--ink-soft);margin:2px 0 8px;line-height:1.5;}
  body.v4done .fab-q,body.v4done #qFab{display:none;}
  .v4sum{font-size:16px;margin-top:10px;}
  /* v4 larger reading sizes */
  body{font-size:18px;}
  .chapter-title{font-size:38px !important;line-height:1.15;}
  .chapter-sub{font-size:17px !important;}
  .tab-btn{font-size:16.5px !important;}
  .sec-sub{font-size:16.5px !important;}
  .qtext{font-size:21px !important;line-height:1.6 !important;}
  .qnum{width:38px !important;height:38px !important;font-size:17px !important;}
  .opt{font-size:19.5px !important;padding:13px 15px !important;}
  .step-line{font-size:19.5px !important;line-height:2.1 !important;}
  .blank-input{font-size:18px !important;min-height:40px;}
  .sol-line{font-size:18px !important;line-height:1.6;}
  .feedback{font-size:16.5px !important;}
  .note h2{font-size:29px !important;}
  .note h3{font-size:22px !important;}
  .note h4{font-size:20px !important;}
  .note p,.note li,.note td,.note th{font-size:18.5px !important;line-height:1.7 !important;}
  .ex .exh{font-size:19px !important;} .ex .exl{font-size:18px !important;}
  .keybox{font-size:18px !important;}
  .hub-card p{font-size:17.5px !important;} .hub-btn{font-size:16.5px !important;}
  .review-q,.review-ans{font-size:17.5px !important;}
  .rec-table td{font-size:16px;}
  .vkb-k{font-size:19px !important;}
  .fq{font-size:0.95em;}
</style>
</head>
<body>
<header class="brand">
  <div class="brand-row">
    <div class="crest">BM</div>
    <div>
      <div class="brand-name">Brain &amp; Mind Academy</div>
      <div class="series-name">Sopaan <span style="font-weight:400;font-size:14px;color:#CFD7EA;">Practice Series</span></div>
    </div>
  </div>
  <div class="chapter-eyebrow">Algebra 1 · Chapter 4</div>
  <div class="chapter-title">Writing Linear Functions</div>
  <div class="chapter-sub">Theory Notes · Practice by Section · Learning Assessment</div><div class="chapter-credit">Follows the sections of Big Ideas Math Algebra 1, Chapter 4</div>
  <div class="chapter-progress">
    <div class="cp-track"><div class="cp-fill" id="cpFill"></div></div>
    <div class="cp-label" id="cpLabel">0% complete</div>
  </div>
  <div class="who-row"><button class="mode-pill" id="modePill" hidden>Choose a mode</button><span class="who" id="whoBar" hidden></span></div>
</header>

<nav class="tabbar"><div class="tabbar-inner" id="tabbar"></div></nav>
<div class="sec-sub" id="secSub"></div><div class="slide-progress"><div class="sp-track"><div class="sp-fill" id="spFill"></div></div><div class="sp-label" id="spLabel">Question 1 of 49</div></div>
<div class="wrap" id="wrap"></div>
<footer class="brandfoot">Brain &amp; Mind Academy · Sopaan Practice Series · Algebra 1 · Chapter 4<br>Lessons follow the chapter and section structure of <i>Big Ideas Math Algebra 1</i> (2015), Chapter 4. Theory notes, questions, learning assessments and worked solutions are written by Brain &amp; Mind Academy.</footer>

<div class="navbar"><div class="navbar-inner" id="navbarInner"></div></div>
<button class="fab" id="paletteFab"><span>Questions</span><span class="fab-badge" id="fabBadge">0/49</span></button>

<div class="overlay" id="overlay">
  <div class="palette" role="dialog" aria-label="Question palette">
    <div class="palette-head"><h2 id="paletteTitle">Question palette</h2><button class="palette-close" id="paletteClose">&times;</button></div>
    <div class="palette-legend">
      <span><i class="dot current"></i>Current</span><span><i class="dot correct"></i>Correct</span>
      <span><i class="dot revealed"></i>Revealed</span><span><i class="dot skipped"></i>Skipped</span>
      <span><i class="dot locked"></i>Locked</span>
    </div>
    <div class="chip-grid" id="paletteBody"></div>
  </div>
</div>
<div class="toast" id="toast"></div>

<script>
(function(){
"use strict";

/* ================= audio ================= */
var audioCtx=null;
function ensureAudio(){ if(!audioCtx){ try{ audioCtx=new (window.AudioContext||window.webkitAudioContext)(); }catch(e){} } return audioCtx; }
function playTone(freqs,dur,type){
  var ctx=ensureAudio(); if(!ctx) return;
  try{
    var t0=ctx.currentTime;
    freqs.forEach(function(f,i){
      var o=ctx.createOscillator(), g=ctx.createGain();
      o.type=type||'sine'; o.frequency.value=f;
      var start=t0+i*dur;
      g.gain.setValueAtTime(0.0001,start);
      g.gain.exponentialRampToValueAtTime(0.16,start+0.02);
      g.gain.exponentialRampToValueAtTime(0.0001,start+dur);
      o.connect(g); g.connect(ctx.destination);
      o.start(start); o.stop(start+dur+0.02);
    });
  }catch(e){}
}
function playSuccess(){ playTone([523.25,659.25,783.99],0.11,'sine'); }
function playWrong(){ playTone([220,185],0.14,'square'); }
function playReveal(){ playTone([300,220],0.16,'triangle'); }

/* ================= helpers ================= */
function norm(s){
  return String(s===undefined||s===null?'':s).trim().toLowerCase().replace(/\s+/g,'')
    .replace(/[×∗*·]/g,'x').replace(/÷/g,'/').replace(/–|—|−/g,'-')
    .replace(/[²]/g,'^2').replace(/[³]/g,'^3').replace(/[⁴]/g,'^4').replace(/[⁵]/g,'^5')
    .replace(/[⁶]/g,'^6').replace(/[⁷]/g,'^7').replace(/[⁸]/g,'^8').replace(/[⁹]/g,'^9')
    .replace(/\^/g,'');
}
function parseNum(s){
  if(s===undefined||s===null) return null;
  var t=String(s).trim().replace(/,/g,'').replace(/[−–—]/g,'-').replace(/\s+/g,''); if(t==='') return null;
  var neg=false; if(t[0]==='-'){neg=true;t=t.slice(1);}
  var m=t.match(/^(\d+)\/(\d+)$/);
  if(m){ var v=parseInt(m[1],10)/parseInt(m[2],10); return neg?-v:v; }
  if(/^\d+(\.\d+)?$/.test(t)){ var v2=parseFloat(t); return neg?-v2:v2; }
  return null;
}
/* ---- expression checker: compares answers like (P-2w)/2 and P/2-w at random values ---- */
function exprPrep(s){
  return String(s).toLowerCase().replace(/\s+/g,'').replace(/^[a-z]\(x\)=/i,'').replace(/^[a-z]=/i,'').replace(/[×∗·]/g,'*').replace(/÷/g,'/').replace(/[−–—]/g,'-')
    .replace(/²/g,'^2').replace(/³/g,'^3').replace(/⁴/g,'^4').replace(/⁵/g,'^5').replace(/⁶/g,'^6').replace(/⁷/g,'^7').replace(/⁸/g,'^8').replace(/⁹/g,'^9').replace(/π/g,'#').replace(/pi/gi,'#').replace(/½/g,'(1/2)');
}
function exprCompile(src){
  var s=exprPrep(src), i=0, toks=[], absDepth=0;
  while(i<s.length){
    var ch=s[i];
    if(/[0-9.]/.test(ch)){ var j=i; while(j<s.length && /[0-9.]/.test(s[j])) j++; toks.push({k:'n',v:parseFloat(s.slice(i,j))}); i=j; continue; }
    if(/[a-zA-Z#]/.test(ch)){ toks.push({k:'v',v:ch}); i++; continue; }
    if(ch==='|'){ var pv=toks[toks.length-1]; var opn=(absDepth===0)||!pv||('+-*/^(['.indexOf(pv.k)>=0); if(opn){ absDepth++; toks.push({k:'['}); } else { absDepth--; toks.push({k:']'}); } i++; continue; }
    if('+-*/^()'.indexOf(ch)>=0){ toks.push({k:ch}); i++; continue; }
    return null;
  }
  var out=[];
  for(var t=0;t<toks.length;t++){
    var a=toks[t], b=out[out.length-1];
    if(b && (b.k==='n'||b.k==='v'||b.k===')'||b.k===']') && (a.k==='n'||a.k==='v'||a.k==='('||a.k==='[')) out.push({k:'&'});
    out.push(a);
  }
  var p=0;
  function peek(){ return out[p]; }
  function parseE(){ var n=parseT(); while(peek() && (peek().k==='+'||peek().k==='-')){ var o=out[p++].k, r=parseT(); n=(function(l,r,o){return function(e){ return o==='+'?l(e)+r(e):l(e)-r(e); };})(n,r,o); } return n; }
  function parseI(){ var n=parseU(); while(peek() && peek().k==='&'){ p++; var r=parseP(); n=(function(l,r){return function(e){ return l(e)*r(e); };})(n,r); } return n; }
  function parseT(){ var n=parseI(); while(peek() && (peek().k==='*'||peek().k==='/')){ var o=out[p++].k, r=parseI(); n=(function(l,r,o){return function(e){ return o==='*'?l(e)*r(e):l(e)/r(e); };})(n,r,o); } return n; }
  function parseU(){ if(peek() && peek().k==='-'){ p++; var u=parseU(); return function(e){ return -u(e); }; } if(peek() && peek().k==='+'){ p++; return parseU(); } return parseP(); }
  function parseP(){ var b=parseA(); if(peek() && peek().k==='^'){ p++; var x=parseU(); return function(e){ return Math.pow(b(e),x(e)); }; } return b; }
  function parseA(){
    var t=out[p++]; if(!t) throw 0;
    if(t.k==='n') return function(){ return t.v; };
    if(t.k==='v') return t.v==='#' ? function(){ return Math.PI; } : function(e){ return e[t.v]; };
    if(t.k==='('){ var n=parseE(); if(!peek()||peek().k!==')') throw 0; p++; return n; }
    if(t.k==='['){ var m=parseE(); if(!peek()||peek().k!==']') throw 0; p++; return function(e){ return Math.abs(m(e)); }; }
    throw 0;
  }
  try{ var f=parseE(); if(p!==out.length) return null; return f; }catch(e){ return null; }
}
function exprEqual(input,answer){
  var f=exprCompile(input), g=exprCompile(answer); if(!f||!g) return false;
  var hits=0;
  for(var trial=0;trial<8;trial++){
    var env={}; 'abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(function(c){ env[c]=1.3+Math.random()*4.1; });
    var x=f(env), y=g(env);
    if(!isFinite(x)||!isFinite(y)) continue;
    if(Math.abs(x-y)>1e-7*Math.max(1,Math.abs(x),Math.abs(y))) return false;
    hits++;
  }
  return hits>=3;
}
function wordsNorm(s){ return String(s||'').toLowerCase().replace(/\band\b/g,' ').replace(/[^a-z]/g,''); }
function listNorm(s){ return (String(s||'').replace(/[−–—]/g,'-').replace(/(\d) (?=\d{3}\b)/g,'$1').match(/-?\d+(\.\d+)?/g)||[]).join(','); }
function powNorm(s){ return String(s||'').toLowerCase().replace(/\s+/g,'').replace(/[×∗*·.]/g,'x').replace(/[⁰¹²³⁴⁵⁶⁷⁸⁹]+/g,function(m){ return '^'+m.split('').map(function(c){ return '⁰¹²³⁴⁵⁶⁷⁸⁹'.indexOf(c); }).join(''); }).replace(/\^1(?!\d)/g,''); }
function fr(s){ return String(s).replace(/\{(\d+) (\d+)\/(\d+)\}/g,'<span class="mx">$1<span class="fq"><span>$2</span><span>$3</span></span></span>').replace(/\{(\d+)\/(\d+)\}/g,'<span class="fq"><span>$1</span><span>$2</span></span>'); }
function gcdI(a,b){ a=Math.abs(a); b=Math.abs(b); while(b){ var t=a%b; a=b; b=t; } return a; }
function fracParse(s){ s=String(s===undefined||s===null?'':s).trim().replace(/[\u2044\u2215\u00f7]/g,'/').replace(/\s+/g,' ').replace(/\s*\/\s*/g,'/'); var m;
  if((m=s.match(/^(-?\d+)$/))) return {v:+m[1],form:'int',n:+m[1],d:1};
  if((m=s.match(/^(-?\d+)\/(\d+)$/))){ if(+m[2]===0) return null; return {v:m[1]/m[2],form:'frac',n:+m[1],d:+m[2]}; }
  if((m=s.match(/^(-?)(\d+)(?: |\+)(\d+)\/(\d+)$/))){ if(+m[4]===0) return null; var sg=m[1]?-1:1; return {v:sg*(+m[2]+m[3]/m[4]),form:'mixed',w:sg*m[2],n:+m[3],d:+m[4]}; }
  if((m=s.match(/^-?\d*\.\d+$/))) return {v:parseFloat(s),form:'dec'};
  return null; }
function fracOK(mode,input,answer){
  if(mode==='flist'){ var A=String(input).split(/[,;]/).map(function(x){return x.trim();}).filter(Boolean), K=String(answer).split(/[,;]/).map(function(x){return x.trim();});
    if(A.length!==K.length) return false; return A.every(function(x,i){ var a=fracParse(x), k=fracParse(K[i]); return a&&k&&Math.abs(a.v-k.v)<1e-9; }); }
  var a=fracParse(input), k=fracParse(answer); if(!a||!k) return false;
  var same=Math.abs(a.v-k.v)<1e-9; if(!same) return false;
  if(mode==='fv') return true;
  if(mode==='dec') return a.form==='dec'||a.form==='int';
  if(mode==='fe') return (a.form==='frac'&&k.form==='frac'&&a.n===k.n&&a.d===k.d)||(a.form==='int'&&k.form==='int');
  if(mode==='fi') return a.form==='frac'||(a.form==='int'&&k.form==='int');
  if(mode==='fl') return a.form==='int'||(a.form==='frac'&&gcdI(a.n,a.d)===1)||(a.form==='mixed'&&a.n<a.d&&gcdI(a.n,a.d)===1);
  if(mode==='fm') return a.form==='int'||(a.form==='mixed'&&a.n>0&&a.n<a.d&&gcdI(a.n,a.d)===1);
  return false; }
function answerMatches(input,answer,accept,expr){
  if(expr==='dec'||expr==='fv'||expr==='fe'||expr==='fl'||expr==='fm'||expr==='fi'||expr==='flist'){ if(input===undefined||input===null||String(input).trim()==='') return false; return fracOK(expr,input,answer); }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  if(expr==='words'){ return [answer].concat(accept||[]).some(function(a){ if(/\d/.test(a)) return norm(a)===norm(input); var w=wordsNorm(a); return w!=='' && w===wordsNorm(input); }); }
  if(expr==='list'){ return [answer].concat(accept||[]).some(function(a){ return listNorm(a)===listNorm(input); }); }
  if(expr==='pow'){ return [answer].concat(accept||[]).some(function(a){ return powNorm(a)===powNorm(input); }); }
  if(expr==='time'){ var tn=function(x){ var t=String(x).toLowerCase().replace(/[\s.]/g,'').replace(/[:h]/g,''); if(/^\d{3}(am|pm)?$/.test(t)) t='0'+t; return t; }; return [answer].concat(accept||[]).some(function(a){ return tn(a)===tn(input); }); }
  if(expr==='glist'){ var gn=function(x){ return String(x).toUpperCase().split(/[\s,;]+/).filter(Boolean).sort().join(','); }; return [answer].concat(accept||[]).some(function(a){ return gn(a)===gn(input); }); }
  if(expr==='coord'){ var cn=function(x){ return String(x).replace(/[\u2212\u2013\u2014]/g,'-').replace(/[\s()\[\]]/g,''); }; return [answer].concat(accept||[]).some(function(a){ return cn(a)===cn(input); }); }
  if(expr==='dlist'){ var dn=function(x){ return (String(x).replace(/[−–—]/g,'-').match(/-?\d*\.?\d+/g)||[]).map(Number).join(','); }; return [answer].concat(accept||[]).some(function(a){ return dn(a)===dn(input); }); }
  if(expr==='set'){ var sn=function(x){ return (String(x).match(/-?\d+/g)||[]).map(Number).sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return sn(a)===sn(input); }); }
  if(expr==='primes'){ var pn=function(x){ var t=powNorm(x).replace(/[^0-9x^]/g,''); var out=[]; t.split('x').forEach(function(tok){ if(!tok) return; var m=tok.split('^'); var b=+m[0], e=m[1]?+m[1]:1; for(var i=0;i<e;i++) out.push(b); }); return out.sort(function(a,b){return a-b;}).join(','); }; return [answer].concat(accept||[]).some(function(a){ return pn(a)===pn(input); }); }
  if(expr==='angle'){ var an=function(x){ return String(x).toUpperCase().replace(/[^A-Z]/g,''); }; var k=an(answer), v=an(input); return v===k || v===k.split('').reverse().join(''); }
  if(expr==='trans'){ var tv=function(x){ var s=String(x).toLowerCase().replace(/[−–—]/g,'-').replace(/\b(units?|squares?|and|then|steps?|to|the|a)\b/g,' ').replace(/[,;.]/g,' '); var re=/(\d+)\s*(right|left|up|down|r|l|u|d)\b/g, m, dx=0, dy=0, n=0; while((m=re.exec(s))){ var v=+m[1], d=m[2][0]; if(d==='r')dx+=v; else if(d==='l')dx-=v; else if(d==='u')dy+=v; else dy-=v; n++; } if(!n||s.replace(re,'').replace(/\s+/g,'')!=='') return null; return dx+','+dy; }; var ti=tv(input); return ti!==null && [answer].concat(accept||[]).some(function(a){ return tv(a)===ti; }); }
  if(expr==='rot'){ var rv=function(x){ var s=String(x).toLowerCase().replace(/quarter[\s-]*turn/g,'90').replace(/half[\s-]*turn/g,'180').replace(/three[\s-]*quarter[\s-]*turn/g,'270'); var m=s.match(/\b(90|180|270)\b/); if(!m) return null; var a=+m[1]; if(a===180) return '180'; var dir=/anti|counter|acw|ccw/.test(s)?-1:(/clockwise|\bcw\b/.test(s)?1:0); if(!dir) return null; return String(((a*dir)%360+360)%360); }; var ri=rv(input); return ri!==null && ri===rv(answer); }
  if(expr==='expanded'){ var f=function(x){ return String(x).replace(/\s+/g,'').replace(/,/g,''); }; return [answer].concat(accept||[]).some(function(a){ return f(a)===f(input); }); }
  if(expr===true && input!==undefined && input!==null && String(input).trim()!==''){
    if(exprEqual(input,answer)) return true;
    var alt=String(input).replace(/\/\s*(\d+(?:\.\d+)?)\s*([a-zA-Z(])/g,'/$1*$2'); if(alt!==String(input) && exprEqual(alt,answer)) return true;
    return (accept||[]).some(function(a){ return exprEqual(input,a); });
  }
  if(input===undefined||input===null||String(input).trim()==='') return false;
  var n1=parseNum(input), n2=parseNum(answer);
  if(n1!==null && n2!==null){ if(Math.abs(n1-n2)<1e-3) return true; return (accept||[]).some(function(a){ var n3=parseNum(a); return n3!==null && Math.abs(n1-n3)<1e-3; }); }
  var cands=[answer].concat(accept||[]); var ni=norm(input);
  for(var i=0;i<cands.length;i++){ if(norm(cands[i])===ni) return true; }
  return false;
}
function esc(s){ return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;'); }

/* ================= DATA ================= */
var AR_OPTIONS = ["Both A and R are true, and R is the correct explanation of A","Both A and R are true, but R is NOT the correct explanation of A","A is true but R is false","A is false but R is true"];
var THEORY = "<div class=\"hub\"><div class=\"hub-card\"><h3>📖 Theory notes</h3><p>Explained notes for each section of the chapter, with rules, graphs, common mistakes and worked examples.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-jump=\"nintro\">Warm-up</button><button class=\"hub-btn\" data-jump=\"n41\">4.1 notes</button><button class=\"hub-btn\" data-jump=\"n42\">4.2 notes</button><button class=\"hub-btn\" data-jump=\"n43\">4.3 notes</button><button class=\"hub-btn\" data-jump=\"n44\">4.4 notes</button><button class=\"hub-btn\" data-jump=\"n45\">4.5 notes</button><button class=\"hub-btn\" data-jump=\"n46\">4.6 notes</button><button class=\"hub-btn\" data-jump=\"n47\">4.7 notes</button></div></div><div class=\"hub-card\"><h3>🎯 Practice by section</h3><p>One practice sheet for each section, mixing multiple-choice and fill-in-the-blank questions from easy to challenging, with real-life problems and error analysis.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s1\">4.1 · Writing Equations in Slope-Intercept Form</button><button class=\"hub-btn\" data-go=\"s2\">4.2 · Writing Equations in Point-Slope Form</button><button class=\"hub-btn\" data-go=\"s3\">4.3 · Writing Equations of Parallel and Perpendicular Lines</button><button class=\"hub-btn\" data-go=\"s4\">4.4 · Scatter Plots and Lines of Fit</button><button class=\"hub-btn\" data-go=\"s5\">4.5 · Analyzing Lines of Fit</button><button class=\"hub-btn\" data-go=\"s6\">4.6 · Arithmetic Sequences</button><button class=\"hub-btn\" data-go=\"s7\">4.7 · Piecewise Functions</button></div></div><div class=\"hub-card\"><h3>📝 Learning assessment</h3><p>Four short assessments that mix all the sections, one per skill area. Take them in Quiz mode and open the report to see your results as pie charts.</p><div class=\"hub-btns\"><button class=\"hub-btn\" data-go=\"s8\">A · Knowing and understanding</button><button class=\"hub-btn\" data-go=\"s9\">B · Investigating patterns</button><button class=\"hub-btn\" data-go=\"s10\">C · Communicating</button><button class=\"hub-btn\" data-go=\"s11\">D · Applying mathematics in real-life contexts</button><button class=\"hub-btn primary\" data-go=\"report\">📊 View my report</button></div></div></div><section class=\"note\" id=\"nintro\"><h2>About this chapter</h2><p>In Chapter 3 you graphed linear functions from their equations. In Chapter 4 you work the other way round: you start from information about a line (a graph, a slope and a point, two points, a table or a story) and <b>write its equation</b>. You then use lines to model data, see that arithmetic sequences are linear functions, and join pieces of lines into piecewise functions.</p><h4>Maintaining mathematical proficiency · warm-up</h4><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Skill</th><th>Quick example</th></tr><tr><td>Slope from two points</td><td>(1, 2) and (4, 11): m = (11 − 2) ÷ (4 − 1) = 9 ÷ 3 = 3</td></tr><tr><td>Slope from a graph</td><td>count rise ÷ run between two grid points; a line falling left to right has a negative slope</td></tr><tr><td>Solving an equation for y</td><td>6x + 2y = 10 → 2y = −6x + 10 → y = −3x + 5</td></tr><tr><td>Evaluating a function</td><td>f(x) = 4x − 7, f(3) = 4(3) − 7 = 5</td></tr><tr><td>Simplifying expressions</td><td>−2(x − 5) + 3 = −2x + 10 + 3 = −2x + 13</td></tr><tr><td>Absolute value</td><td>|−6| = 6, |3 − 8| = 5</td></tr></table></div><div class=\"ex\"><div class=\"exh\">Warm-up example · Slope, then solve for y</div><div class=\"exl\">Find the slope through (−2, 7) and (3, −3): m = (−3 − 7) ÷ (3 − (−2)) = −10 ÷ 5 = <b>−2</b>.<br>Solve 4x − 2y = 6 for y: −2y = −4x + 6, so <b>y = 2x − 3</b>.</div></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Sheet</th><th>Section</th><th>Learning target</th></tr><tr><td>4.1</td><td>Writing Equations in Slope-Intercept Form</td><td>Write an equation of a line in slope-intercept form from its graph, from its slope and y-intercept, from its slope and a point, or from two points.</td></tr><tr><td>4.2</td><td>Writing Equations in Point-Slope Form</td><td>Write an equation of a line in point-slope form, change it to slope-intercept form, and use it to model real-life rates.</td></tr><tr><td>4.3</td><td>Writing Equations of Parallel and Perpendicular Lines</td><td>Identify parallel and perpendicular lines from their slopes and write equations of lines parallel or perpendicular to a given line.</td></tr><tr><td>4.4</td><td>Scatter Plots and Lines of Fit</td><td>Describe the correlation shown in a scatter plot, write an equation of a line of fit and use it to make predictions.</td></tr><tr><td>4.5</td><td>Analyzing Lines of Fit</td><td>Use residuals to judge a line of fit, find the line of best fit and the correlation coefficient with technology, and tell correlation from causation.</td></tr><tr><td>4.6</td><td>Arithmetic Sequences</td><td>Recognise arithmetic sequences, find the common difference and write the nth term as a linear function of n.</td></tr><tr><td>4.7</td><td>Piecewise Functions</td><td>Evaluate, graph and write piecewise functions, including step functions and absolute value functions.</td></tr></table></div><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Assessment</th><th>Skill area</th><th>What it checks</th></tr><tr><td>A</td><td>Knowing and understanding</td><td>Using the forms of a linear equation and the rules of the chapter correctly.</td></tr><tr><td>B</td><td>Investigating patterns</td><td>Constant differences, slope relationships and patterns in data and residuals.</td></tr><tr><td>C</td><td>Communicating</td><td>Vocabulary, notation, interpreting slopes and intercepts, and spotting errors.</td></tr><tr><td>D</td><td>Applying mathematics in real-life contexts</td><td>Fares, bills, savings, data and growth problems.</td></tr></table></div><p><b>Tools:</b> ⏱ at the top shows your time. ✏️ opens a scratchpad for rough work. Some questions have a 📈 Desmos button for graphing or regression. Tap the BM badge to come back to this page.</p><p><b>Typing answers:</b> type equations as <span class=\"mono\">y = 3x - 2</span> or just <span class=\"mono\">3x - 2</span> (any equivalent form is accepted). Type fractions as <span class=\"mono\">-2/3</span>; inside an equation put a fraction coefficient in parentheses, e.g. <span class=\"mono\">(2/3)x + 1</span>. When a slope is a fraction, most questions ask for the slope and the y-intercept in separate blanks. Correlation coefficients and regression values are rounded as the question states.</p></section><section class=\"note\" id=\"n41\"><h2>4.1 Writing Equations in Slope-Intercept Form</h2><p class=\"lt\"><b>Learning target:</b> Write an equation of a line in slope-intercept form from its graph, from its slope and y-intercept, from its slope and a point, or from two points.</p><p>A linear equation written as <b class=\"mono\">y = mx + b</b> is in <b>slope-intercept form</b>. The number m is the <b>slope</b> (the change in y for each increase of 1 in x) and b is the <b>y-intercept</b> (the value of y where the line crosses the y-axis, that is, when x = 0).</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>You know</th><th>What to do</th></tr><tr><td>the slope m and the y-intercept b</td><td>substitute them into y = mx + b</td></tr><tr><td>a graph</td><td>read b where the line meets the y-axis; count rise ÷ run for m</td></tr><tr><td>the slope m and a point (x₁, y₁)</td><td>substitute m, x₁ and y₁ into y = mx + b and solve for b</td></tr><tr><td>two points</td><td>find m = (y₂ − y₁) ÷ (x₂ − x₁), then use one point to find b</td></tr><tr><td>two values f(p) and f(q) of a linear function</td><td>use the points (p, f(p)) and (q, f(q))</td></tr></table></div><svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"150.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">From (0, 4) to (2, −2): rise −6, run 2</text><line x1=\"16.0\" y1=\"214.0\" x2=\"16.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"45.8\" y1=\"214.0\" x2=\"45.8\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"75.6\" y1=\"214.0\" x2=\"75.6\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.3\" y1=\"214.0\" x2=\"105.3\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"135.1\" y1=\"214.0\" x2=\"135.1\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"164.9\" y1=\"214.0\" x2=\"164.9\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"194.7\" y1=\"214.0\" x2=\"194.7\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"224.4\" y1=\"214.0\" x2=\"224.4\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"254.2\" y1=\"214.0\" x2=\"254.2\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"284.0\" y1=\"214.0\" x2=\"284.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"214.0\" x2=\"284.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"198.9\" x2=\"284.0\" y2=\"198.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"183.8\" x2=\"284.0\" y2=\"183.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"168.8\" x2=\"284.0\" y2=\"168.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"153.7\" x2=\"284.0\" y2=\"153.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"138.6\" x2=\"284.0\" y2=\"138.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"123.5\" x2=\"284.0\" y2=\"123.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"108.5\" x2=\"284.0\" y2=\"108.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"93.4\" x2=\"284.0\" y2=\"93.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"78.3\" x2=\"284.0\" y2=\"78.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"63.2\" x2=\"284.0\" y2=\"63.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"48.2\" x2=\"284.0\" y2=\"48.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"33.1\" x2=\"284.0\" y2=\"33.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"18.0\" x2=\"284.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"123.5\" x2=\"284.0\" y2=\"123.5\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"135.1\" y1=\"214.0\" x2=\"135.1\" y2=\"18.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"16.0\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"75.6\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"194.7\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"254.2\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"131.1\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"131.1\" y=\"183.8\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"131.1\" y=\"153.7\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"131.1\" y=\"93.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"131.1\" y=\"63.2\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"131.1\" y=\"33.1\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"280.0\" y=\"115.5\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"143.1\" y=\"24.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"c50574\"><rect x=\"16.0\" y=\"18.0\" width=\"268.0\" height=\"196.0\"/></clipPath><path d=\"M16.0,-117.7 L16.7,-116.7 L17.3,-115.7 L18.0,-114.6 L18.7,-113.6 L19.3,-112.6 L20.0,-111.6 L20.7,-110.6 L21.4,-109.6 L22.0,-108.5 L22.7,-107.5 L23.4,-106.5 L24.0,-105.5 L24.7,-104.5 L25.4,-103.4 L26.0,-102.4 L26.7,-101.4 L27.4,-100.4 L28.1,-99.4 L28.7,-98.4 L29.4,-97.3 L30.1,-96.3 L30.7,-95.3 L31.4,-94.3 L32.1,-93.3 L32.8,-92.2 L33.4,-91.2 L34.1,-90.2 L34.8,-89.2 L35.4,-88.2 L36.1,-87.2 L36.8,-86.1 L37.4,-85.1 L38.1,-84.1 L38.8,-83.1 L39.5,-82.1 L40.1,-81.1 L40.8,-80.0 L41.5,-79.0 L42.1,-78.0 L42.8,-77.0 L43.5,-76.0 L44.1,-74.9 L44.8,-73.9 L45.5,-72.9 L46.2,-71.9 L46.8,-70.9 L47.5,-69.9 L48.2,-68.8 L48.8,-67.8 L49.5,-66.8 L50.2,-65.8 L50.8,-64.8 L51.5,-63.8 L52.2,-62.7 L52.8,-61.7 L53.5,-60.7 L54.2,-59.7 L54.9,-58.7 L55.5,-57.6 L56.2,-56.6 L56.9,-55.6 L57.5,-54.6 L58.2,-53.6 L58.9,-52.6 L59.5,-51.5 L60.2,-50.5 L60.9,-49.5 L61.6,-48.5 L62.2,-47.5 L62.9,-46.5 L63.6,-45.4 L64.2,-44.4 L64.9,-43.4 L65.6,-42.4 L66.2,-41.4 L66.9,-40.3 L67.6,-39.3 L68.3,-38.3 L68.9,-37.3 L69.6,-36.3 L70.3,-35.3 L70.9,-34.2 L71.6,-33.2 L72.3,-32.2 L73.0,-31.2 L73.6,-30.2 L74.3,-29.2 L75.0,-28.1 L75.6,-27.1 L76.3,-26.1 L77.0,-25.1 L77.6,-24.1 L78.3,-23.0 L79.0,-22.0 L79.7,-21.0 L80.3,-20.0 L81.0,-19.0 L81.7,-18.0 L82.3,-16.9 L83.0,-15.9 L83.7,-14.9 L84.3,-13.9 L85.0,-12.9 L85.7,-11.9 L86.3,-10.8 L87.0,-9.8 L87.7,-8.8 L88.4,-7.8 L89.0,-6.8 L89.7,-5.7 L90.4,-4.7 L91.0,-3.7 L91.7,-2.7 L92.4,-1.7 L93.0,-0.7 L93.7,0.4 L94.4,1.4 L95.1,2.4 L95.7,3.4 L96.4,4.4 L97.1,5.4 L97.7,6.5 L98.4,7.5 L99.1,8.5 L99.8,9.5 L100.4,10.5 L101.1,11.6 L101.8,12.6 L102.4,13.6 L103.1,14.6 L103.8,15.6 L104.4,16.6 L105.1,17.7 L105.8,18.7 L106.5,19.7 L107.1,20.7 L107.8,21.7 L108.5,22.7 L109.1,23.8 L109.8,24.8 L110.5,25.8 L111.1,26.8 L111.8,27.8 L112.5,28.9 L113.2,29.9 L113.8,30.9 L114.5,31.9 L115.2,32.9 L115.8,33.9 L116.5,35.0 L117.2,36.0 L117.8,37.0 L118.5,38.0 L119.2,39.0 L119.8,40.0 L120.5,41.1 L121.2,42.1 L121.9,43.1 L122.5,44.1 L123.2,45.1 L123.9,46.2 L124.5,47.2 L125.2,48.2 L125.9,49.2 L126.5,50.2 L127.2,51.2 L127.9,52.3 L128.6,53.3 L129.2,54.3 L129.9,55.3 L130.6,56.3 L131.2,57.4 L131.9,58.4 L132.6,59.4 L133.2,60.4 L133.9,61.4 L134.6,62.4 L135.3,63.5 L135.9,64.5 L136.6,65.5 L137.3,66.5 L137.9,67.5 L138.6,68.5 L139.3,69.6 L139.9,70.6 L140.6,71.6 L141.3,72.6 L142.0,73.6 L142.6,74.7 L143.3,75.7 L144.0,76.7 L144.6,77.7 L145.3,78.7 L146.0,79.7 L146.7,80.8 L147.3,81.8 L148.0,82.8 L148.7,83.8 L149.3,84.8 L150.0,85.8 L150.7,86.9 L151.3,87.9 L152.0,88.9 L152.7,89.9 L153.3,90.9 L154.0,92.0 L154.7,93.0 L155.4,94.0 L156.0,95.0 L156.7,96.0 L157.4,97.0 L158.0,98.1 L158.7,99.1 L159.4,100.1 L160.1,101.1 L160.7,102.1 L161.4,103.1 L162.1,104.2 L162.7,105.2 L163.4,106.2 L164.1,107.2 L164.7,108.2 L165.4,109.3 L166.1,110.3 L166.8,111.3 L167.4,112.3 L168.1,113.3 L168.8,114.3 L169.4,115.4 L170.1,116.4 L170.8,117.4 L171.4,118.4 L172.1,119.4 L172.8,120.4 L173.4,121.5 L174.1,122.5 L174.8,123.5 L175.5,124.5 L176.1,125.5 L176.8,126.6 L177.5,127.6 L178.1,128.6 L178.8,129.6 L179.5,130.6 L180.2,131.6 L180.8,132.7 L181.5,133.7 L182.2,134.7 L182.8,135.7 L183.5,136.7 L184.2,137.7 L184.8,138.8 L185.5,139.8 L186.2,140.8 L186.8,141.8 L187.5,142.8 L188.2,143.9 L188.9,144.9 L189.5,145.9 L190.2,146.9 L190.9,147.9 L191.5,148.9 L192.2,150.0 L192.9,151.0 L193.6,152.0 L194.2,153.0 L194.9,154.0 L195.6,155.0 L196.2,156.1 L196.9,157.1 L197.6,158.1 L198.2,159.1 L198.9,160.1 L199.6,161.2 L200.2,162.2 L200.9,163.2 L201.6,164.2 L202.3,165.2 L202.9,166.2 L203.6,167.3 L204.3,168.3 L204.9,169.3 L205.6,170.3 L206.3,171.3 L206.9,172.3 L207.6,173.4 L208.3,174.4 L209.0,175.4 L209.6,176.4 L210.3,177.4 L211.0,178.5 L211.6,179.5 L212.3,180.5 L213.0,181.5 L213.7,182.5 L214.3,183.5 L215.0,184.6 L215.7,185.6 L216.3,186.6 L217.0,187.6 L217.7,188.6 L218.3,189.7 L219.0,190.7 L219.7,191.7 L220.3,192.7 L221.0,193.7 L221.7,194.7 L222.4,195.8 L223.0,196.8 L223.7,197.8 L224.4,198.8 L225.0,199.8 L225.7,200.8 L226.4,201.9 L227.1,202.9 L227.7,203.9 L228.4,204.9 L229.1,205.9 L229.7,207.0 L230.4,208.0 L231.1,209.0 L231.7,210.0 L232.4,211.0 L233.1,212.0 L233.8,213.1 L234.4,214.1 L235.1,215.1 L235.8,216.1 L236.4,217.1 L237.1,218.1 L237.8,219.2 L238.4,220.2 L239.1,221.2 L239.8,222.2 L240.4,223.2 L241.1,224.3 L241.8,225.3 L242.5,226.3 L243.1,227.3 L243.8,228.3 L244.5,229.3 L245.1,230.4 L245.8,231.4 L246.5,232.4 L247.2,233.4 L247.8,234.4 L248.5,235.4 L249.2,236.5 L249.8,237.5 L250.5,238.5 L251.2,239.5 L251.8,240.5 L252.5,241.6 L253.2,242.6 L253.8,243.6 L254.5,244.6 L255.2,245.6 L255.9,246.6 L256.5,247.7 L257.2,248.7 L257.9,249.7 L258.5,250.7 L259.2,251.7 L259.9,252.7 L260.6,253.8 L261.2,254.8 L261.9,255.8 L262.6,256.8 L263.2,257.8 L263.9,258.9 L264.6,259.9 L265.2,260.9 L265.9,261.9 L266.6,262.9 L267.2,263.9 L267.9,265.0 L268.6,266.0 L269.3,267.0 L269.9,268.0 L270.6,269.0 L271.3,270.0 L271.9,271.1 L272.6,272.1 L273.3,273.1 L273.9,274.1 L274.6,275.1 L275.3,276.2 L276.0,277.2 L276.6,278.2 L277.3,279.2 L278.0,280.2 L278.6,281.2 L279.3,282.3 L280.0,283.3 L280.6,284.3 L281.3,285.3 L282.0,286.3 L282.7,287.3 L283.3,288.4 L284.0,289.4\" clip-path=\"url(#c50574)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><circle cx=\"135.1\" cy=\"63.2\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"141.1\" y=\"54.2\" text-anchor=\"start\" dominant-baseline=\"middle\">(0, 4)</text><circle cx=\"194.7\" cy=\"153.7\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"200.7\" y=\"144.7\" text-anchor=\"start\" dominant-baseline=\"middle\">(2, −2)</text></svg><div class=\"ex\"><div class=\"exh\">Worked example 1 · From a graph</div><div class=\"exl\">The line crosses the y-axis at (0, 4), so b = 4.<br>From (0, 4) to (2, −2) the rise is −6 and the run is 2, so m = −6 ÷ 2 = −3.<br>Equation: <b>y = −3x + 4</b>. Check (2, −2): −3(2) + 4 = −2 ✓</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Slope and a point</div><div class=\"exl\">Slope 5, through (−1, 3).<br>3 = 5(−1) + b → 3 = −5 + b → b = 8.<br>Equation: <b>y = 5x + 8</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Two points</div><div class=\"exl\">Through (−2, −4) and (4, 5).<br>m = (5 − (−4)) ÷ (4 − (−2)) = 9 ÷ 6 = {3/2}.<br>Use (4, 5): 5 = {3/2}(4) + b = 6 + b → b = −1. Equation: <b>y = {3/2}x − 1</b>.</div></div><h4>Linear models</h4><p>In a real-life problem the slope is a <b>rate</b> (dollars per hour, gallons per minute) and the y-intercept is the <b>starting value</b> (a fixed fee, an initial amount). A horizontal line has slope 0, so its equation is y = b.</p><div class=\"keybox\"><b>Common mistakes:</b> writing the slope as run ÷ rise, subtracting the coordinates in different orders on top and bottom, and using the y-coordinate of any point as b. b is the y-value only at x = 0. Always check your equation with a second point.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s1\">Practise 4.1 →</button></div></section><section class=\"note\" id=\"n42\"><h2>4.2 Writing Equations in Point-Slope Form</h2><p class=\"lt\"><b>Learning target:</b> Write an equation of a line in point-slope form, change it to slope-intercept form, and use it to model real-life rates.</p><p>If a line has slope m and passes through (x₁, y₁), then for any other point (x, y) on the line, (y − y₁) ÷ (x − x₁) = m. Multiplying by (x − x₁) gives the <b>point-slope form</b>:</p><p style=\"text-align:center\"><b class=\"mono\">y − y₁ = m(x − x₁)</b></p><svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"150.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Slope from (x₁, y₁) to any point (x, y) is m</text><line x1=\"16.0\" y1=\"214.0\" x2=\"16.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"42.8\" y1=\"214.0\" x2=\"42.8\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"69.6\" y1=\"214.0\" x2=\"69.6\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"96.4\" y1=\"214.0\" x2=\"96.4\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"123.2\" y1=\"214.0\" x2=\"123.2\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"150.0\" y1=\"214.0\" x2=\"150.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"176.8\" y1=\"214.0\" x2=\"176.8\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"203.6\" y1=\"214.0\" x2=\"203.6\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"230.4\" y1=\"214.0\" x2=\"230.4\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"257.2\" y1=\"214.0\" x2=\"257.2\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"284.0\" y1=\"214.0\" x2=\"284.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"214.0\" x2=\"284.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"198.9\" x2=\"284.0\" y2=\"198.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"183.8\" x2=\"284.0\" y2=\"183.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"168.8\" x2=\"284.0\" y2=\"168.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"153.7\" x2=\"284.0\" y2=\"153.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"138.6\" x2=\"284.0\" y2=\"138.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"123.5\" x2=\"284.0\" y2=\"123.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"108.5\" x2=\"284.0\" y2=\"108.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"93.4\" x2=\"284.0\" y2=\"93.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"78.3\" x2=\"284.0\" y2=\"78.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"63.2\" x2=\"284.0\" y2=\"63.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"48.2\" x2=\"284.0\" y2=\"48.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"33.1\" x2=\"284.0\" y2=\"33.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"18.0\" x2=\"284.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"123.5\" x2=\"284.0\" y2=\"123.5\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"123.2\" y1=\"214.0\" x2=\"123.2\" y2=\"18.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"16.0\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"69.6\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"176.8\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"230.4\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"284.0\" y=\"132.5\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"119.2\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"119.2\" y=\"183.8\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"119.2\" y=\"153.7\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"119.2\" y=\"93.4\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"119.2\" y=\"63.2\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"119.2\" y=\"33.1\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"280.0\" y=\"115.5\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"131.2\" y=\"24.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"c29006\"><rect x=\"16.0\" y=\"18.0\" width=\"268.0\" height=\"196.0\"/></clipPath><path d=\"M16.0,289.4 L16.7,288.6 L17.3,287.9 L18.0,287.1 L18.7,286.4 L19.4,285.6 L20.0,284.9 L20.7,284.1 L21.4,283.4 L22.0,282.6 L22.7,281.8 L23.4,281.1 L24.0,280.3 L24.7,279.6 L25.4,278.8 L26.0,278.1 L26.7,277.3 L27.4,276.6 L28.1,275.8 L28.7,275.1 L29.4,274.3 L30.1,273.6 L30.7,272.8 L31.4,272.0 L32.1,271.3 L32.8,270.5 L33.4,269.8 L34.1,269.0 L34.8,268.3 L35.4,267.5 L36.1,266.8 L36.8,266.0 L37.4,265.3 L38.1,264.5 L38.8,263.8 L39.5,263.0 L40.1,262.2 L40.8,261.5 L41.5,260.7 L42.1,260.0 L42.8,259.2 L43.5,258.5 L44.1,257.7 L44.8,257.0 L45.5,256.2 L46.2,255.5 L46.8,254.7 L47.5,254.0 L48.2,253.2 L48.8,252.4 L49.5,251.7 L50.2,250.9 L50.8,250.2 L51.5,249.4 L52.2,248.7 L52.9,247.9 L53.5,247.2 L54.2,246.4 L54.9,245.7 L55.5,244.9 L56.2,244.2 L56.9,243.4 L57.5,242.6 L58.2,241.9 L58.9,241.1 L59.6,240.4 L60.2,239.6 L60.9,238.9 L61.6,238.1 L62.2,237.4 L62.9,236.6 L63.6,235.9 L64.2,235.1 L64.9,234.4 L65.6,233.6 L66.2,232.8 L66.9,232.1 L67.6,231.3 L68.3,230.6 L68.9,229.8 L69.6,229.1 L70.3,228.3 L70.9,227.6 L71.6,226.8 L72.3,226.1 L72.9,225.3 L73.6,224.6 L74.3,223.8 L75.0,223.0 L75.6,222.3 L76.3,221.5 L77.0,220.8 L77.6,220.0 L78.3,219.3 L79.0,218.5 L79.7,217.8 L80.3,217.0 L81.0,216.3 L81.7,215.5 L82.3,214.8 L83.0,214.0 L83.7,213.2 L84.3,212.5 L85.0,211.7 L85.7,211.0 L86.4,210.2 L87.0,209.5 L87.7,208.7 L88.4,208.0 L89.0,207.2 L89.7,206.5 L90.4,205.7 L91.0,205.0 L91.7,204.2 L92.4,203.4 L93.0,202.7 L93.7,201.9 L94.4,201.2 L95.1,200.4 L95.7,199.7 L96.4,198.9 L97.1,198.2 L97.7,197.4 L98.4,196.7 L99.1,195.9 L99.8,195.2 L100.4,194.4 L101.1,193.6 L101.8,192.9 L102.4,192.1 L103.1,191.4 L103.8,190.6 L104.4,189.9 L105.1,189.1 L105.8,188.4 L106.5,187.6 L107.1,186.9 L107.8,186.1 L108.5,185.4 L109.1,184.6 L109.8,183.8 L110.5,183.1 L111.1,182.3 L111.8,181.6 L112.5,180.8 L113.1,180.1 L113.8,179.3 L114.5,178.6 L115.2,177.8 L115.8,177.1 L116.5,176.3 L117.2,175.6 L117.8,174.8 L118.5,174.0 L119.2,173.3 L119.9,172.5 L120.5,171.8 L121.2,171.0 L121.9,170.3 L122.5,169.5 L123.2,168.8 L123.9,168.0 L124.5,167.3 L125.2,166.5 L125.9,165.8 L126.5,165.0 L127.2,164.2 L127.9,163.5 L128.6,162.7 L129.2,162.0 L129.9,161.2 L130.6,160.5 L131.2,159.7 L131.9,159.0 L132.6,158.2 L133.2,157.5 L133.9,156.7 L134.6,156.0 L135.3,155.2 L135.9,154.4 L136.6,153.7 L137.3,152.9 L137.9,152.2 L138.6,151.4 L139.3,150.7 L139.9,149.9 L140.6,149.2 L141.3,148.4 L142.0,147.7 L142.6,146.9 L143.3,146.2 L144.0,145.4 L144.6,144.6 L145.3,143.9 L146.0,143.1 L146.7,142.4 L147.3,141.6 L148.0,140.9 L148.7,140.1 L149.3,139.4 L150.0,138.6 L150.7,137.9 L151.3,137.1 L152.0,136.4 L152.7,135.6 L153.3,134.8 L154.0,134.1 L154.7,133.3 L155.4,132.6 L156.0,131.8 L156.7,131.1 L157.4,130.3 L158.0,129.6 L158.7,128.8 L159.4,128.1 L160.0,127.3 L160.7,126.6 L161.4,125.8 L162.1,125.0 L162.7,124.3 L163.4,123.5 L164.1,122.8 L164.7,122.0 L165.4,121.3 L166.1,120.5 L166.8,119.8 L167.4,119.0 L168.1,118.3 L168.8,117.5 L169.4,116.8 L170.1,116.0 L170.8,115.2 L171.4,114.5 L172.1,113.7 L172.8,113.0 L173.5,112.2 L174.1,111.5 L174.8,110.7 L175.5,110.0 L176.1,109.2 L176.8,108.5 L177.5,107.7 L178.1,107.0 L178.8,106.2 L179.5,105.4 L180.2,104.7 L180.8,103.9 L181.5,103.2 L182.2,102.4 L182.8,101.7 L183.5,100.9 L184.2,100.2 L184.8,99.4 L185.5,98.7 L186.2,97.9 L186.8,97.2 L187.5,96.4 L188.2,95.6 L188.9,94.9 L189.5,94.1 L190.2,93.4 L190.9,92.6 L191.5,91.9 L192.2,91.1 L192.9,90.4 L193.5,89.6 L194.2,88.9 L194.9,88.1 L195.6,87.4 L196.2,86.6 L196.9,85.8 L197.6,85.1 L198.2,84.3 L198.9,83.6 L199.6,82.8 L200.2,82.1 L200.9,81.3 L201.6,80.6 L202.3,79.8 L202.9,79.1 L203.6,78.3 L204.3,77.6 L204.9,76.8 L205.6,76.0 L206.3,75.3 L207.0,74.5 L207.6,73.8 L208.3,73.0 L209.0,72.3 L209.6,71.5 L210.3,70.8 L211.0,70.0 L211.6,69.3 L212.3,68.5 L213.0,67.8 L213.7,67.0 L214.3,66.2 L215.0,65.5 L215.7,64.7 L216.3,64.0 L217.0,63.2 L217.7,62.5 L218.3,61.7 L219.0,61.0 L219.7,60.2 L220.3,59.5 L221.0,58.7 L221.7,58.0 L222.4,57.2 L223.0,56.4 L223.7,55.7 L224.4,54.9 L225.0,54.2 L225.7,53.4 L226.4,52.7 L227.0,51.9 L227.7,51.2 L228.4,50.4 L229.1,49.7 L229.7,48.9 L230.4,48.2 L231.1,47.4 L231.7,46.6 L232.4,45.9 L233.1,45.1 L233.8,44.4 L234.4,43.6 L235.1,42.9 L235.8,42.1 L236.4,41.4 L237.1,40.6 L237.8,39.9 L238.4,39.1 L239.1,38.4 L239.8,37.6 L240.5,36.8 L241.1,36.1 L241.8,35.3 L242.5,34.6 L243.1,33.8 L243.8,33.1 L244.5,32.3 L245.1,31.6 L245.8,30.8 L246.5,30.1 L247.2,29.3 L247.8,28.6 L248.5,27.8 L249.2,27.0 L249.8,26.3 L250.5,25.5 L251.2,24.8 L251.8,24.0 L252.5,23.3 L253.2,22.5 L253.8,21.8 L254.5,21.0 L255.2,20.3 L255.9,19.5 L256.5,18.8 L257.2,18.0 L257.9,17.2 L258.5,16.5 L259.2,15.7 L259.9,15.0 L260.5,14.2 L261.2,13.5 L261.9,12.7 L262.6,12.0 L263.2,11.2 L263.9,10.5 L264.6,9.7 L265.2,9.0 L265.9,8.2 L266.6,7.4 L267.2,6.7 L267.9,5.9 L268.6,5.2 L269.3,4.4 L269.9,3.7 L270.6,2.9 L271.3,2.2 L271.9,1.4 L272.6,0.7 L273.3,-0.1 L273.9,-0.8 L274.6,-1.6 L275.3,-2.4 L276.0,-3.1 L276.6,-3.9 L277.3,-4.6 L278.0,-5.4 L278.6,-6.1 L279.3,-6.9 L280.0,-7.6 L280.7,-8.4 L281.3,-9.1 L282.0,-9.9 L282.7,-10.6 L283.3,-11.4 L284.0,-12.2\" clip-path=\"url(#c29006)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><circle cx=\"150.0\" cy=\"138.6\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"156.0\" y=\"129.6\" text-anchor=\"start\" dominant-baseline=\"middle\">(x₁, y₁) = (1, −1)</text><circle cx=\"230.4\" cy=\"48.2\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"236.4\" y=\"39.2\" text-anchor=\"start\" dominant-baseline=\"middle\">(x, y)</text></svg><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Equation</th><th>Slope</th><th>Point</th></tr><tr><td class=\"mono\">y − 7 = 4(x − 2)</td><td>4</td><td>(2, 7)</td></tr><tr><td class=\"mono\">y + 3 = −2(x − 5)</td><td>−2</td><td>(5, −3)</td></tr><tr><td class=\"mono\">y − 1 = {2/5}(x + 6)</td><td>{2/5}</td><td>(−6, 1)</td></tr></table></div><div class=\"keybox\"><b>Watch the signs.</b> The form contains <i>minus</i> signs, so y + 3 means y₁ = −3 and x + 6 means x₁ = −6.</div><div class=\"ex\"><div class=\"exh\">Worked example 1 · Slope and a point</div><div class=\"exl\">Slope −4, through (3, −2).<br>y − (−2) = −4(x − 3) → <b>y + 2 = −4(x − 3)</b>.<br>Slope-intercept form: y + 2 = −4x + 12 → <b>y = −4x + 10</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Two points</div><div class=\"exl\">Through (2, 9) and (6, 1): m = (1 − 9) ÷ (6 − 2) = −8 ÷ 4 = −2.<br>Using (2, 9): <b>y − 9 = −2(x − 2)</b>. Using (6, 1) gives y − 1 = −2(x − 6): the same line.<br>Both simplify to y = −2x + 13.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · A rate and one data value</div><div class=\"exl\">A bike rental costs $6 per hour, and a 3-hour rental costs $26.<br>C − 26 = 6(h − 3) → C = 6h − 18 + 26 → <b>C = 6h + 8</b>.<br>So there is an $8 fixed fee; 5 hours cost 6(5) + 8 = $38.</div></div><p>Point-slope form is the quickest form when you know a point that is <b>not</b> the y-intercept, or a rate and one data value.</p><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s2\">Practise 4.2 →</button></div></section><section class=\"note\" id=\"n43\"><h2>4.3 Writing Equations of Parallel and Perpendicular Lines</h2><p class=\"lt\"><b>Learning target:</b> Identify parallel and perpendicular lines from their slopes and write equations of lines parallel or perpendicular to a given line.</p><p>Two different lines in the same plane that never meet are <b>parallel</b>. Two lines that meet at a right angle are <b>perpendicular</b>.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Lines</th><th>Slopes</th><th>Example</th></tr><tr><td>parallel</td><td>equal slopes (different y-intercepts)</td><td>y = 2x + 1 and y = 2x − 3</td></tr><tr><td>perpendicular</td><td>slopes are <b>negative reciprocals</b>: m₁ × m₂ = −1</td><td>y = 2x + 1 and y = −{1/2}x + 2</td></tr><tr><td>vertical and horizontal</td><td>always perpendicular</td><td>x = 3 and y = −1</td></tr></table></div><svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"150.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Parallel (solid) and perpendicular (dashed)</text><line x1=\"16.0\" y1=\"214.0\" x2=\"16.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"38.3\" y1=\"214.0\" x2=\"38.3\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"60.7\" y1=\"214.0\" x2=\"60.7\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"83.0\" y1=\"214.0\" x2=\"83.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.3\" y1=\"214.0\" x2=\"105.3\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"127.7\" y1=\"214.0\" x2=\"127.7\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"150.0\" y1=\"214.0\" x2=\"150.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"172.3\" y1=\"214.0\" x2=\"172.3\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"194.7\" y1=\"214.0\" x2=\"194.7\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"217.0\" y1=\"214.0\" x2=\"217.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"239.3\" y1=\"214.0\" x2=\"239.3\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"261.7\" y1=\"214.0\" x2=\"261.7\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"284.0\" y1=\"214.0\" x2=\"284.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"214.0\" x2=\"284.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"197.7\" x2=\"284.0\" y2=\"197.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"181.3\" x2=\"284.0\" y2=\"181.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"165.0\" x2=\"284.0\" y2=\"165.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"148.7\" x2=\"284.0\" y2=\"148.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"132.3\" x2=\"284.0\" y2=\"132.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"116.0\" x2=\"284.0\" y2=\"116.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"99.7\" x2=\"284.0\" y2=\"99.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"83.3\" x2=\"284.0\" y2=\"83.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"67.0\" x2=\"284.0\" y2=\"67.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"50.7\" x2=\"284.0\" y2=\"50.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"34.3\" x2=\"284.0\" y2=\"34.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"18.0\" x2=\"284.0\" y2=\"18.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"132.3\" x2=\"284.0\" y2=\"132.3\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"150.0\" y1=\"214.0\" x2=\"150.0\" y2=\"18.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"16.0\" y=\"141.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"60.7\" y=\"141.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"105.3\" y=\"141.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"194.7\" y=\"141.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"239.3\" y=\"141.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"284.0\" y=\"141.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"146.0\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−5</text><text class=\"po\" x=\"146.0\" y=\"181.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−3</text><text class=\"po\" x=\"146.0\" y=\"148.7\" text-anchor=\"end\" dominant-baseline=\"middle\">−1</text><text class=\"po\" x=\"146.0\" y=\"116.0\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"146.0\" y=\"83.3\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"146.0\" y=\"50.7\" text-anchor=\"end\" dominant-baseline=\"middle\">5</text><text class=\"po\" x=\"146.0\" y=\"18.0\" text-anchor=\"end\" dominant-baseline=\"middle\">7</text><text class=\"po\" x=\"280.0\" y=\"124.3\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"158.0\" y=\"24.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"c97875\"><rect x=\"16.0\" y=\"18.0\" width=\"268.0\" height=\"196.0\"/></clipPath><path d=\"M16.0,312.0 L16.7,311.0 L17.3,310.0 L18.0,309.1 L18.7,308.1 L19.4,307.1 L20.0,306.1 L20.7,305.1 L21.4,304.2 L22.0,303.2 L22.7,302.2 L23.4,301.2 L24.0,300.2 L24.7,299.3 L25.4,298.3 L26.1,297.3 L26.7,296.3 L27.4,295.3 L28.1,294.4 L28.7,293.4 L29.4,292.4 L30.1,291.4 L30.7,290.4 L31.4,289.5 L32.1,288.5 L32.8,287.5 L33.4,286.5 L34.1,285.5 L34.8,284.6 L35.4,283.6 L36.1,282.6 L36.8,281.6 L37.4,280.6 L38.1,279.7 L38.8,278.7 L39.4,277.7 L40.1,276.7 L40.8,275.7 L41.5,274.8 L42.1,273.8 L42.8,272.8 L43.5,271.8 L44.1,270.8 L44.8,269.9 L45.5,268.9 L46.1,267.9 L46.8,266.9 L47.5,265.9 L48.2,265.0 L48.8,264.0 L49.5,263.0 L50.2,262.0 L50.8,261.0 L51.5,260.1 L52.2,259.1 L52.9,258.1 L53.5,257.1 L54.2,256.1 L54.9,255.2 L55.5,254.2 L56.2,253.2 L56.9,252.2 L57.5,251.2 L58.2,250.3 L58.9,249.3 L59.6,248.3 L60.2,247.3 L60.9,246.3 L61.6,245.4 L62.2,244.4 L62.9,243.4 L63.6,242.4 L64.2,241.4 L64.9,240.5 L65.6,239.5 L66.2,238.5 L66.9,237.5 L67.6,236.5 L68.3,235.6 L68.9,234.6 L69.6,233.6 L70.3,232.6 L70.9,231.6 L71.6,230.7 L72.3,229.7 L72.9,228.7 L73.6,227.7 L74.3,226.7 L75.0,225.8 L75.6,224.8 L76.3,223.8 L77.0,222.8 L77.6,221.8 L78.3,220.9 L79.0,219.9 L79.7,218.9 L80.3,217.9 L81.0,216.9 L81.7,216.0 L82.3,215.0 L83.0,214.0 L83.7,213.0 L84.3,212.0 L85.0,211.1 L85.7,210.1 L86.4,209.1 L87.0,208.1 L87.7,207.1 L88.4,206.2 L89.0,205.2 L89.7,204.2 L90.4,203.2 L91.0,202.2 L91.7,201.3 L92.4,200.3 L93.1,199.3 L93.7,198.3 L94.4,197.3 L95.1,196.4 L95.7,195.4 L96.4,194.4 L97.1,193.4 L97.7,192.4 L98.4,191.5 L99.1,190.5 L99.8,189.5 L100.4,188.5 L101.1,187.5 L101.8,186.6 L102.4,185.6 L103.1,184.6 L103.8,183.6 L104.4,182.6 L105.1,181.7 L105.8,180.7 L106.4,179.7 L107.1,178.7 L107.8,177.7 L108.5,176.8 L109.1,175.8 L109.8,174.8 L110.5,173.8 L111.1,172.8 L111.8,171.9 L112.5,170.9 L113.1,169.9 L113.8,168.9 L114.5,167.9 L115.2,167.0 L115.8,166.0 L116.5,165.0 L117.2,164.0 L117.8,163.0 L118.5,162.1 L119.2,161.1 L119.9,160.1 L120.5,159.1 L121.2,158.1 L121.9,157.2 L122.5,156.2 L123.2,155.2 L123.9,154.2 L124.5,153.2 L125.2,152.3 L125.9,151.3 L126.6,150.3 L127.2,149.3 L127.9,148.3 L128.6,147.4 L129.2,146.4 L129.9,145.4 L130.6,144.4 L131.2,143.4 L131.9,142.5 L132.6,141.5 L133.2,140.5 L133.9,139.5 L134.6,138.5 L135.3,137.6 L135.9,136.6 L136.6,135.6 L137.3,134.6 L137.9,133.6 L138.6,132.7 L139.3,131.7 L139.9,130.7 L140.6,129.7 L141.3,128.7 L142.0,127.8 L142.6,126.8 L143.3,125.8 L144.0,124.8 L144.6,123.8 L145.3,122.9 L146.0,121.9 L146.7,120.9 L147.3,119.9 L148.0,118.9 L148.7,118.0 L149.3,117.0 L150.0,116.0 L150.7,115.0 L151.3,114.0 L152.0,113.1 L152.7,112.1 L153.4,111.1 L154.0,110.1 L154.7,109.1 L155.4,108.2 L156.0,107.2 L156.7,106.2 L157.4,105.2 L158.0,104.2 L158.7,103.3 L159.4,102.3 L160.0,101.3 L160.7,100.3 L161.4,99.3 L162.1,98.4 L162.7,97.4 L163.4,96.4 L164.1,95.4 L164.7,94.4 L165.4,93.5 L166.1,92.5 L166.8,91.5 L167.4,90.5 L168.1,89.5 L168.8,88.6 L169.4,87.6 L170.1,86.6 L170.8,85.6 L171.4,84.6 L172.1,83.7 L172.8,82.7 L173.5,81.7 L174.1,80.7 L174.8,79.7 L175.5,78.8 L176.1,77.8 L176.8,76.8 L177.5,75.8 L178.1,74.8 L178.8,73.9 L179.5,72.9 L180.1,71.9 L180.8,70.9 L181.5,69.9 L182.2,69.0 L182.8,68.0 L183.5,67.0 L184.2,66.0 L184.8,65.0 L185.5,64.1 L186.2,63.1 L186.9,62.1 L187.5,61.1 L188.2,60.1 L188.9,59.2 L189.5,58.2 L190.2,57.2 L190.9,56.2 L191.5,55.2 L192.2,54.3 L192.9,53.3 L193.5,52.3 L194.2,51.3 L194.9,50.3 L195.6,49.4 L196.2,48.4 L196.9,47.4 L197.6,46.4 L198.2,45.4 L198.9,44.5 L199.6,43.5 L200.2,42.5 L200.9,41.5 L201.6,40.5 L202.3,39.6 L202.9,38.6 L203.6,37.6 L204.3,36.6 L204.9,35.6 L205.6,34.7 L206.3,33.7 L207.0,32.7 L207.6,31.7 L208.3,30.7 L209.0,29.8 L209.6,28.8 L210.3,27.8 L211.0,26.8 L211.6,25.8 L212.3,24.9 L213.0,23.9 L213.6,22.9 L214.3,21.9 L215.0,20.9 L215.7,20.0 L216.3,19.0 L217.0,18.0 L217.7,17.0 L218.3,16.0 L219.0,15.1 L219.7,14.1 L220.4,13.1 L221.0,12.1 L221.7,11.1 L222.4,10.2 L223.0,9.2 L223.7,8.2 L224.4,7.2 L225.0,6.2 L225.7,5.3 L226.4,4.3 L227.0,3.3 L227.7,2.3 L228.4,1.3 L229.1,0.4 L229.7,-0.6 L230.4,-1.6 L231.1,-2.6 L231.7,-3.6 L232.4,-4.5 L233.1,-5.5 L233.8,-6.5 L234.4,-7.5 L235.1,-8.5 L235.8,-9.4 L236.4,-10.4 L237.1,-11.4 L237.8,-12.4 L238.4,-13.4 L239.1,-14.3 L239.8,-15.3 L240.5,-16.3 L241.1,-17.3 L241.8,-18.3 L242.5,-19.2 L243.1,-20.2 L243.8,-21.2 L244.5,-22.2 L245.1,-23.2 L245.8,-24.1 L246.5,-25.1 L247.1,-26.1 L247.8,-27.1 L248.5,-28.1 L249.2,-29.0 L249.8,-30.0 L250.5,-31.0 L251.2,-32.0 L251.8,-33.0 L252.5,-33.9 L253.2,-34.9 L253.9,-35.9 L254.5,-36.9 L255.2,-37.9 L255.9,-38.8 L256.5,-39.8 L257.2,-40.8 L257.9,-41.8 L258.5,-42.8 L259.2,-43.7 L259.9,-44.7 L260.5,-45.7 L261.2,-46.7 L261.9,-47.7 L262.6,-48.6 L263.2,-49.6 L263.9,-50.6 L264.6,-51.6 L265.2,-52.6 L265.9,-53.5 L266.6,-54.5 L267.2,-55.5 L267.9,-56.5 L268.6,-57.5 L269.3,-58.4 L269.9,-59.4 L270.6,-60.4 L271.3,-61.4 L271.9,-62.4 L272.6,-63.3 L273.3,-64.3 L273.9,-65.3 L274.6,-66.3 L275.3,-67.3 L276.0,-68.2 L276.6,-69.2 L277.3,-70.2 L278.0,-71.2 L278.6,-72.2 L279.3,-73.1 L280.0,-74.1 L280.6,-75.1 L281.3,-76.1 L282.0,-77.1 L282.7,-78.0 L283.3,-79.0 L284.0,-80.0\" clip-path=\"url(#c97875)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"107.6\" y=\"171.1\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = 2x + 1</text><path d=\"M16.0,377.3 L16.7,376.4 L17.3,375.4 L18.0,374.4 L18.7,373.4 L19.4,372.4 L20.0,371.5 L20.7,370.5 L21.4,369.5 L22.0,368.5 L22.7,367.5 L23.4,366.6 L24.0,365.6 L24.7,364.6 L25.4,363.6 L26.1,362.6 L26.7,361.7 L27.4,360.7 L28.1,359.7 L28.7,358.7 L29.4,357.7 L30.1,356.8 L30.7,355.8 L31.4,354.8 L32.1,353.8 L32.8,352.8 L33.4,351.9 L34.1,350.9 L34.8,349.9 L35.4,348.9 L36.1,347.9 L36.8,347.0 L37.4,346.0 L38.1,345.0 L38.8,344.0 L39.4,343.0 L40.1,342.1 L40.8,341.1 L41.5,340.1 L42.1,339.1 L42.8,338.1 L43.5,337.2 L44.1,336.2 L44.8,335.2 L45.5,334.2 L46.1,333.2 L46.8,332.3 L47.5,331.3 L48.2,330.3 L48.8,329.3 L49.5,328.3 L50.2,327.4 L50.8,326.4 L51.5,325.4 L52.2,324.4 L52.9,323.4 L53.5,322.5 L54.2,321.5 L54.9,320.5 L55.5,319.5 L56.2,318.5 L56.9,317.6 L57.5,316.6 L58.2,315.6 L58.9,314.6 L59.6,313.6 L60.2,312.7 L60.9,311.7 L61.6,310.7 L62.2,309.7 L62.9,308.7 L63.6,307.8 L64.2,306.8 L64.9,305.8 L65.6,304.8 L66.2,303.8 L66.9,302.9 L67.6,301.9 L68.3,300.9 L68.9,299.9 L69.6,298.9 L70.3,298.0 L70.9,297.0 L71.6,296.0 L72.3,295.0 L72.9,294.0 L73.6,293.1 L74.3,292.1 L75.0,291.1 L75.6,290.1 L76.3,289.1 L77.0,288.2 L77.6,287.2 L78.3,286.2 L79.0,285.2 L79.7,284.2 L80.3,283.3 L81.0,282.3 L81.7,281.3 L82.3,280.3 L83.0,279.3 L83.7,278.4 L84.3,277.4 L85.0,276.4 L85.7,275.4 L86.4,274.4 L87.0,273.5 L87.7,272.5 L88.4,271.5 L89.0,270.5 L89.7,269.5 L90.4,268.6 L91.0,267.6 L91.7,266.6 L92.4,265.6 L93.1,264.6 L93.7,263.7 L94.4,262.7 L95.1,261.7 L95.7,260.7 L96.4,259.7 L97.1,258.8 L97.7,257.8 L98.4,256.8 L99.1,255.8 L99.8,254.8 L100.4,253.9 L101.1,252.9 L101.8,251.9 L102.4,250.9 L103.1,249.9 L103.8,249.0 L104.4,248.0 L105.1,247.0 L105.8,246.0 L106.4,245.0 L107.1,244.1 L107.8,243.1 L108.5,242.1 L109.1,241.1 L109.8,240.1 L110.5,239.2 L111.1,238.2 L111.8,237.2 L112.5,236.2 L113.1,235.2 L113.8,234.3 L114.5,233.3 L115.2,232.3 L115.8,231.3 L116.5,230.3 L117.2,229.4 L117.8,228.4 L118.5,227.4 L119.2,226.4 L119.9,225.4 L120.5,224.5 L121.2,223.5 L121.9,222.5 L122.5,221.5 L123.2,220.5 L123.9,219.6 L124.5,218.6 L125.2,217.6 L125.9,216.6 L126.6,215.6 L127.2,214.7 L127.9,213.7 L128.6,212.7 L129.2,211.7 L129.9,210.7 L130.6,209.8 L131.2,208.8 L131.9,207.8 L132.6,206.8 L133.2,205.8 L133.9,204.9 L134.6,203.9 L135.3,202.9 L135.9,201.9 L136.6,200.9 L137.3,200.0 L137.9,199.0 L138.6,198.0 L139.3,197.0 L139.9,196.0 L140.6,195.1 L141.3,194.1 L142.0,193.1 L142.6,192.1 L143.3,191.1 L144.0,190.2 L144.6,189.2 L145.3,188.2 L146.0,187.2 L146.7,186.2 L147.3,185.3 L148.0,184.3 L148.7,183.3 L149.3,182.3 L150.0,181.3 L150.7,180.4 L151.3,179.4 L152.0,178.4 L152.7,177.4 L153.4,176.4 L154.0,175.5 L154.7,174.5 L155.4,173.5 L156.0,172.5 L156.7,171.5 L157.4,170.6 L158.0,169.6 L158.7,168.6 L159.4,167.6 L160.0,166.6 L160.7,165.7 L161.4,164.7 L162.1,163.7 L162.7,162.7 L163.4,161.7 L164.1,160.8 L164.7,159.8 L165.4,158.8 L166.1,157.8 L166.8,156.8 L167.4,155.9 L168.1,154.9 L168.8,153.9 L169.4,152.9 L170.1,151.9 L170.8,151.0 L171.4,150.0 L172.1,149.0 L172.8,148.0 L173.5,147.0 L174.1,146.1 L174.8,145.1 L175.5,144.1 L176.1,143.1 L176.8,142.1 L177.5,141.2 L178.1,140.2 L178.8,139.2 L179.5,138.2 L180.1,137.2 L180.8,136.3 L181.5,135.3 L182.2,134.3 L182.8,133.3 L183.5,132.3 L184.2,131.4 L184.8,130.4 L185.5,129.4 L186.2,128.4 L186.9,127.4 L187.5,126.5 L188.2,125.5 L188.9,124.5 L189.5,123.5 L190.2,122.5 L190.9,121.6 L191.5,120.6 L192.2,119.6 L192.9,118.6 L193.5,117.6 L194.2,116.7 L194.9,115.7 L195.6,114.7 L196.2,113.7 L196.9,112.7 L197.6,111.8 L198.2,110.8 L198.9,109.8 L199.6,108.8 L200.2,107.8 L200.9,106.9 L201.6,105.9 L202.3,104.9 L202.9,103.9 L203.6,102.9 L204.3,102.0 L204.9,101.0 L205.6,100.0 L206.3,99.0 L207.0,98.0 L207.6,97.1 L208.3,96.1 L209.0,95.1 L209.6,94.1 L210.3,93.1 L211.0,92.2 L211.6,91.2 L212.3,90.2 L213.0,89.2 L213.6,88.2 L214.3,87.3 L215.0,86.3 L215.7,85.3 L216.3,84.3 L217.0,83.3 L217.7,82.4 L218.3,81.4 L219.0,80.4 L219.7,79.4 L220.4,78.4 L221.0,77.5 L221.7,76.5 L222.4,75.5 L223.0,74.5 L223.7,73.5 L224.4,72.6 L225.0,71.6 L225.7,70.6 L226.4,69.6 L227.0,68.6 L227.7,67.7 L228.4,66.7 L229.1,65.7 L229.7,64.7 L230.4,63.7 L231.1,62.8 L231.7,61.8 L232.4,60.8 L233.1,59.8 L233.8,58.8 L234.4,57.9 L235.1,56.9 L235.8,55.9 L236.4,54.9 L237.1,53.9 L237.8,53.0 L238.4,52.0 L239.1,51.0 L239.8,50.0 L240.5,49.0 L241.1,48.1 L241.8,47.1 L242.5,46.1 L243.1,45.1 L243.8,44.1 L244.5,43.2 L245.1,42.2 L245.8,41.2 L246.5,40.2 L247.1,39.2 L247.8,38.3 L248.5,37.3 L249.2,36.3 L249.8,35.3 L250.5,34.3 L251.2,33.4 L251.8,32.4 L252.5,31.4 L253.2,30.4 L253.9,29.4 L254.5,28.5 L255.2,27.5 L255.9,26.5 L256.5,25.5 L257.2,24.5 L257.9,23.6 L258.5,22.6 L259.2,21.6 L259.9,20.6 L260.5,19.6 L261.2,18.7 L261.9,17.7 L262.6,16.7 L263.2,15.7 L263.9,14.7 L264.6,13.8 L265.2,12.8 L265.9,11.8 L266.6,10.8 L267.2,9.8 L267.9,8.9 L268.6,7.9 L269.3,6.9 L269.9,5.9 L270.6,4.9 L271.3,4.0 L271.9,3.0 L272.6,2.0 L273.3,1.0 L273.9,0.0 L274.6,-0.9 L275.3,-1.9 L276.0,-2.9 L276.6,-3.9 L277.3,-4.9 L278.0,-5.8 L278.6,-6.8 L279.3,-7.8 L280.0,-8.8 L280.6,-9.8 L281.3,-10.7 L282.0,-11.7 L282.7,-12.7 L283.3,-13.7 L284.0,-14.7\" clip-path=\"url(#c97875)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><text x=\"230.4\" y=\"56.7\" text-anchor=\"middle\" style=\"fill:var(--danger);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = 2x − 3</text><path d=\"M16.0,50.7 L16.7,50.9 L17.3,51.2 L18.0,51.4 L18.7,51.6 L19.4,51.9 L20.0,52.1 L20.7,52.4 L21.4,52.6 L22.0,52.9 L22.7,53.1 L23.4,53.4 L24.0,53.6 L24.7,53.9 L25.4,54.1 L26.1,54.3 L26.7,54.6 L27.4,54.8 L28.1,55.1 L28.7,55.3 L29.4,55.6 L30.1,55.8 L30.7,56.1 L31.4,56.3 L32.1,56.5 L32.8,56.8 L33.4,57.0 L34.1,57.3 L34.8,57.5 L35.4,57.8 L36.1,58.0 L36.8,58.3 L37.4,58.5 L38.1,58.8 L38.8,59.0 L39.4,59.2 L40.1,59.5 L40.8,59.7 L41.5,60.0 L42.1,60.2 L42.8,60.5 L43.5,60.7 L44.1,61.0 L44.8,61.2 L45.5,61.4 L46.1,61.7 L46.8,61.9 L47.5,62.2 L48.2,62.4 L48.8,62.7 L49.5,62.9 L50.2,63.2 L50.8,63.4 L51.5,63.7 L52.2,63.9 L52.9,64.1 L53.5,64.4 L54.2,64.6 L54.9,64.9 L55.5,65.1 L56.2,65.4 L56.9,65.6 L57.5,65.9 L58.2,66.1 L58.9,66.3 L59.6,66.6 L60.2,66.8 L60.9,67.1 L61.6,67.3 L62.2,67.6 L62.9,67.8 L63.6,68.1 L64.2,68.3 L64.9,68.6 L65.6,68.8 L66.2,69.0 L66.9,69.3 L67.6,69.5 L68.3,69.8 L68.9,70.0 L69.6,70.3 L70.3,70.5 L70.9,70.8 L71.6,71.0 L72.3,71.2 L72.9,71.5 L73.6,71.7 L74.3,72.0 L75.0,72.2 L75.6,72.5 L76.3,72.7 L77.0,73.0 L77.6,73.2 L78.3,73.5 L79.0,73.7 L79.7,73.9 L80.3,74.2 L81.0,74.4 L81.7,74.7 L82.3,74.9 L83.0,75.2 L83.7,75.4 L84.3,75.7 L85.0,75.9 L85.7,76.1 L86.4,76.4 L87.0,76.6 L87.7,76.9 L88.4,77.1 L89.0,77.4 L89.7,77.6 L90.4,77.9 L91.0,78.1 L91.7,78.4 L92.4,78.6 L93.1,78.8 L93.7,79.1 L94.4,79.3 L95.1,79.6 L95.7,79.8 L96.4,80.1 L97.1,80.3 L97.7,80.6 L98.4,80.8 L99.1,81.0 L99.8,81.3 L100.4,81.5 L101.1,81.8 L101.8,82.0 L102.4,82.3 L103.1,82.5 L103.8,82.8 L104.4,83.0 L105.1,83.3 L105.8,83.5 L106.4,83.7 L107.1,84.0 L107.8,84.2 L108.5,84.5 L109.1,84.7 L109.8,85.0 L110.5,85.2 L111.1,85.5 L111.8,85.7 L112.5,85.9 L113.1,86.2 L113.8,86.4 L114.5,86.7 L115.2,86.9 L115.8,87.2 L116.5,87.4 L117.2,87.7 L117.8,87.9 L118.5,88.2 L119.2,88.4 L119.9,88.6 L120.5,88.9 L121.2,89.1 L121.9,89.4 L122.5,89.6 L123.2,89.9 L123.9,90.1 L124.5,90.4 L125.2,90.6 L125.9,90.8 L126.6,91.1 L127.2,91.3 L127.9,91.6 L128.6,91.8 L129.2,92.1 L129.9,92.3 L130.6,92.6 L131.2,92.8 L131.9,93.1 L132.6,93.3 L133.2,93.5 L133.9,93.8 L134.6,94.0 L135.3,94.3 L135.9,94.5 L136.6,94.8 L137.3,95.0 L137.9,95.3 L138.6,95.5 L139.3,95.7 L139.9,96.0 L140.6,96.2 L141.3,96.5 L142.0,96.7 L142.6,97.0 L143.3,97.2 L144.0,97.5 L144.6,97.7 L145.3,98.0 L146.0,98.2 L146.7,98.4 L147.3,98.7 L148.0,98.9 L148.7,99.2 L149.3,99.4 L150.0,99.7 L150.7,99.9 L151.3,100.2 L152.0,100.4 L152.7,100.6 L153.4,100.9 L154.0,101.1 L154.7,101.4 L155.4,101.6 L156.0,101.9 L156.7,102.1 L157.4,102.4 L158.0,102.6 L158.7,102.9 L159.4,103.1 L160.0,103.3 L160.7,103.6 L161.4,103.8 L162.1,104.1 L162.7,104.3 L163.4,104.6 L164.1,104.8 L164.7,105.1 L165.4,105.3 L166.1,105.5 L166.8,105.8 L167.4,106.0 L168.1,106.3 L168.8,106.5 L169.4,106.8 L170.1,107.0 L170.8,107.3 L171.4,107.5 L172.1,107.8 L172.8,108.0 L173.5,108.2 L174.1,108.5 L174.8,108.7 L175.5,109.0 L176.1,109.2 L176.8,109.5 L177.5,109.7 L178.1,110.0 L178.8,110.2 L179.5,110.4 L180.1,110.7 L180.8,110.9 L181.5,111.2 L182.2,111.4 L182.8,111.7 L183.5,111.9 L184.2,112.2 L184.8,112.4 L185.5,112.7 L186.2,112.9 L186.9,113.1 L187.5,113.4 L188.2,113.6 L188.9,113.9 L189.5,114.1 L190.2,114.4 L190.9,114.6 L191.5,114.9 L192.2,115.1 L192.9,115.3 L193.5,115.6 L194.2,115.8 L194.9,116.1 L195.6,116.3 L196.2,116.6 L196.9,116.8 L197.6,117.1 L198.2,117.3 L198.9,117.6 L199.6,117.8 L200.2,118.0 L200.9,118.3 L201.6,118.5 L202.3,118.8 L202.9,119.0 L203.6,119.3 L204.3,119.5 L204.9,119.8 L205.6,120.0 L206.3,120.2 L207.0,120.5 L207.6,120.7 L208.3,121.0 L209.0,121.2 L209.6,121.5 L210.3,121.7 L211.0,122.0 L211.6,122.2 L212.3,122.5 L213.0,122.7 L213.6,122.9 L214.3,123.2 L215.0,123.4 L215.7,123.7 L216.3,123.9 L217.0,124.2 L217.7,124.4 L218.3,124.7 L219.0,124.9 L219.7,125.1 L220.4,125.4 L221.0,125.6 L221.7,125.9 L222.4,126.1 L223.0,126.4 L223.7,126.6 L224.4,126.9 L225.0,127.1 L225.7,127.4 L226.4,127.6 L227.0,127.8 L227.7,128.1 L228.4,128.3 L229.1,128.6 L229.7,128.8 L230.4,129.1 L231.1,129.3 L231.7,129.6 L232.4,129.8 L233.1,130.0 L233.8,130.3 L234.4,130.5 L235.1,130.8 L235.8,131.0 L236.4,131.3 L237.1,131.5 L237.8,131.8 L238.4,132.0 L239.1,132.3 L239.8,132.5 L240.5,132.7 L241.1,133.0 L241.8,133.2 L242.5,133.5 L243.1,133.7 L243.8,134.0 L244.5,134.2 L245.1,134.5 L245.8,134.7 L246.5,134.9 L247.1,135.2 L247.8,135.4 L248.5,135.7 L249.2,135.9 L249.8,136.2 L250.5,136.4 L251.2,136.7 L251.8,136.9 L252.5,137.2 L253.2,137.4 L253.9,137.6 L254.5,137.9 L255.2,138.1 L255.9,138.4 L256.5,138.6 L257.2,138.9 L257.9,139.1 L258.5,139.4 L259.2,139.6 L259.9,139.8 L260.5,140.1 L261.2,140.3 L261.9,140.6 L262.6,140.8 L263.2,141.1 L263.9,141.3 L264.6,141.6 L265.2,141.8 L265.9,142.1 L266.6,142.3 L267.2,142.5 L267.9,142.8 L268.6,143.0 L269.3,143.3 L269.9,143.5 L270.6,143.8 L271.3,144.0 L271.9,144.3 L272.6,144.5 L273.3,144.7 L273.9,145.0 L274.6,145.2 L275.3,145.5 L276.0,145.7 L276.6,146.0 L277.3,146.2 L278.0,146.5 L278.6,146.7 L279.3,147.0 L280.0,147.2 L280.6,147.4 L281.3,147.7 L282.0,147.9 L282.7,148.2 L283.3,148.4 L284.0,148.7\" clip-path=\"url(#c97875)\" style=\"fill:none;stroke:var(--accent-text);stroke-width:2.2;stroke-dasharray:6 4\"/><text x=\"51.7\" y=\"56.7\" text-anchor=\"middle\" style=\"fill:var(--accent-text);font:700 12px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">y = −½x + 2</text></svg><p>To compare lines, first write each equation in slope-intercept form so you can read the slope.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Classify the lines</div><div class=\"exl\">a) 3x + y = 5 → y = −3x + 5 (slope −3).<br>b) x − 3y = 6 → −3y = −x + 6 → y = {1/3}x − 2 (slope {1/3}).<br>−3 × {1/3} = −1, so the lines are <b>perpendicular</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · A parallel line</div><div class=\"exl\">Parallel to y = −4x + 1, through (2, 3): slope −4.<br>3 = −4(2) + b → b = 11. Equation: <b>y = −4x + 11</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · A perpendicular line</div><div class=\"exl\">Perpendicular to y = {2/3}x − 5, through (4, −1).<br>Negative reciprocal of {2/3} is −{3/2}. −1 = −{3/2}(4) + b = −6 + b → b = 5.<br>Equation: <b>y = −{3/2}x + 5</b>.</div></div><div class=\"keybox\"><b>Common mistake:</b> for a perpendicular slope, changing only the sign (2 → −2) or only flipping the fraction (2 → {1/2}). You must do <b>both</b>: 2 → −{1/2}. Check that the product of the slopes is −1.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s3\">Practise 4.3 →</button></div></section><section class=\"note\" id=\"n44\"><h2>4.4 Scatter Plots and Lines of Fit</h2><p class=\"lt\"><b>Learning target:</b> Describe the correlation shown in a scatter plot, write an equation of a line of fit and use it to make predictions.</p><p>A <b>scatter plot</b> is a graph of paired data (x, y) shown as points. It lets you see whether there is a relationship, or <b>correlation</b>, between the two variables.</p><div style=\"display:flex;flex-wrap:wrap;gap:10px;justify-content:center\"><div style=\"flex:1 1 180px;max-width:220px;text-align:center\"><svg class=\"figsvg\" viewBox=\"0 0 200 160\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"51.1\" y1=\"130.0\" x2=\"51.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"51.1\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"68.2\" y1=\"130.0\" x2=\"68.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"68.2\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"85.3\" y1=\"130.0\" x2=\"85.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"85.3\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"102.4\" y1=\"130.0\" x2=\"102.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"102.4\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"119.6\" y1=\"130.0\" x2=\"119.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"119.6\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"136.7\" y1=\"130.0\" x2=\"136.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"136.7\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"153.8\" y1=\"130.0\" x2=\"153.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"153.8\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"170.9\" y1=\"130.0\" x2=\"170.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"170.9\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"188.0\" y1=\"130.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"188.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"130.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"106.0\" x2=\"188.0\" y2=\"106.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"106.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"82.0\" x2=\"188.0\" y2=\"82.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"82.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line x1=\"34.0\" y1=\"58.0\" x2=\"188.0\" y2=\"58.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"58.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line x1=\"34.0\" y1=\"34.0\" x2=\"188.0\" y2=\"34.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"34.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line x1=\"34.0\" y1=\"10.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"188.0\" y=\"153.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><circle cx=\"51.1\" cy=\"94.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"68.2\" cy=\"82.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"85.3\" cy=\"82.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"102.4\" cy=\"58.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"119.6\" cy=\"58.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"136.7\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"153.8\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"170.9\" cy=\"22.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg><p style=\"margin:2px 0 6px\"><b>Positive correlation</b><br>as x increases, y tends to increase</p></div><div style=\"flex:1 1 180px;max-width:220px;text-align:center\"><svg class=\"figsvg\" viewBox=\"0 0 200 160\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"51.1\" y1=\"130.0\" x2=\"51.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"51.1\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"68.2\" y1=\"130.0\" x2=\"68.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"68.2\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"85.3\" y1=\"130.0\" x2=\"85.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"85.3\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"102.4\" y1=\"130.0\" x2=\"102.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"102.4\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"119.6\" y1=\"130.0\" x2=\"119.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"119.6\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"136.7\" y1=\"130.0\" x2=\"136.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"136.7\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"153.8\" y1=\"130.0\" x2=\"153.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"153.8\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"170.9\" y1=\"130.0\" x2=\"170.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"170.9\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"188.0\" y1=\"130.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"188.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"130.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"106.0\" x2=\"188.0\" y2=\"106.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"106.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"82.0\" x2=\"188.0\" y2=\"82.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"82.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line x1=\"34.0\" y1=\"58.0\" x2=\"188.0\" y2=\"58.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"58.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line x1=\"34.0\" y1=\"34.0\" x2=\"188.0\" y2=\"34.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"34.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line x1=\"34.0\" y1=\"10.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"188.0\" y=\"153.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><circle cx=\"51.1\" cy=\"22.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"68.2\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"85.3\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"102.4\" cy=\"58.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"119.6\" cy=\"70.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"136.7\" cy=\"82.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"153.8\" cy=\"94.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"170.9\" cy=\"106.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg><p style=\"margin:2px 0 6px\"><b>Negative correlation</b><br>as x increases, y tends to decrease</p></div><div style=\"flex:1 1 180px;max-width:220px;text-align:center\"><svg class=\"figsvg\" viewBox=\"0 0 200 160\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"51.1\" y1=\"130.0\" x2=\"51.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"51.1\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"68.2\" y1=\"130.0\" x2=\"68.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"68.2\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"85.3\" y1=\"130.0\" x2=\"85.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"85.3\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"102.4\" y1=\"130.0\" x2=\"102.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"102.4\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"119.6\" y1=\"130.0\" x2=\"119.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"119.6\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"136.7\" y1=\"130.0\" x2=\"136.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"136.7\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"153.8\" y1=\"130.0\" x2=\"153.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"153.8\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"170.9\" y1=\"130.0\" x2=\"170.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"170.9\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"188.0\" y1=\"130.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"188.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"130.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"106.0\" x2=\"188.0\" y2=\"106.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"106.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"82.0\" x2=\"188.0\" y2=\"82.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"82.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line x1=\"34.0\" y1=\"58.0\" x2=\"188.0\" y2=\"58.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"58.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line x1=\"34.0\" y1=\"34.0\" x2=\"188.0\" y2=\"34.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"34.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line x1=\"34.0\" y1=\"10.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"188.0\" y=\"153.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><circle cx=\"51.1\" cy=\"70.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"68.2\" cy=\"22.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"85.3\" cy=\"106.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"102.4\" cy=\"46.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"119.6\" cy=\"94.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"136.7\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"153.8\" cy=\"82.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"170.9\" cy=\"58.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg><p style=\"margin:2px 0 6px\"><b>No correlation</b><br>no clear pattern</p></div></div><p>When the points lie close to a line, the correlation is <b>strong</b>; when they are spread out, it is <b>weak</b>.</p><h4>Lines of fit</h4><p>A <b>line of fit</b> is a line drawn on a scatter plot close to most of the points, with about as many points above it as below it. To use one:</p><ul><li><b>1.</b> Make a scatter plot and check that the data look linear.</li><li><b>2.</b> Draw a line that follows the trend.</li><li><b>3.</b> Choose two points <i>on the line</i> (they need not be data points) and write its equation.</li><li><b>4.</b> Interpret the slope and y-intercept and use the equation to predict.</li></ul><svg class=\"figsvg\" viewBox=\"0 0 300 210\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"180.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"65.8\" y1=\"180.0\" x2=\"65.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"65.8\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"97.5\" y1=\"180.0\" x2=\"97.5\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"97.5\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"129.2\" y1=\"180.0\" x2=\"129.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"129.2\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"161.0\" y1=\"180.0\" x2=\"161.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"161.0\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"192.8\" y1=\"180.0\" x2=\"192.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"192.8\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"224.5\" y1=\"180.0\" x2=\"224.5\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"224.5\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"256.2\" y1=\"180.0\" x2=\"256.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"256.2\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"288.0\" y1=\"180.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"288.0\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"34.0\" y1=\"180.0\" x2=\"288.0\" y2=\"180.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"180.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"137.5\" x2=\"288.0\" y2=\"137.5\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"137.5\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"95.0\" x2=\"288.0\" y2=\"95.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"95.0\" text-anchor=\"end\" dominant-baseline=\"middle\">20</text><line x1=\"34.0\" y1=\"52.5\" x2=\"288.0\" y2=\"52.5\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"52.5\" text-anchor=\"end\" dominant-baseline=\"middle\">30</text><line x1=\"34.0\" y1=\"10.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">40</text><line x1=\"34.0\" y1=\"180.0\" x2=\"288.0\" y2=\"180.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"180.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"288.0\" y=\"203.0\" text-anchor=\"end\" dominant-baseline=\"middle\">weeks</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">height (in.)</text><line x1=\"34.0\" y1=\"135.8\" x2=\"288.0\" y2=\"13.4\" style=\"stroke:var(--danger);stroke-width:2\"/><circle cx=\"65.8\" cy=\"120.5\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"97.5\" cy=\"99.2\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"129.2\" cy=\"90.8\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"161.0\" cy=\"65.2\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"192.8\" cy=\"56.8\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"224.5\" cy=\"35.5\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"256.2\" cy=\"27.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg><div class=\"ex\"><div class=\"exh\">Worked example · A sunflower</div><div class=\"exl\">The plot shows a sunflower's height (inches) over 7 weeks. The line passes close to (1, 14) and (6, 32).<br>m = (32 − 14) ÷ (6 − 1) = 18 ÷ 5 = 3.6; 14 = 3.6(1) + b → b = 10.4. So y = 3.6x + 10.4.<br>Slope: the plant grows about <b>3.6 in. per week</b>. y-intercept: about <b>10.4 in.</b> tall at week 0.<br>Prediction for week 9: y = 3.6(9) + 10.4 = <b>42.8 in.</b></div></div><div class=\"keybox\"><b>Common mistake:</b> a line of fit does not have to pass through the first and last data points, or through any data point. Aim for a line that balances the points above and below it.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s4\">Practise 4.4 →</button></div></section><section class=\"note\" id=\"n45\"><h2>4.5 Analyzing Lines of Fit</h2><p class=\"lt\"><b>Learning target:</b> Use residuals to judge a line of fit, find the line of best fit and the correlation coefficient with technology, and tell correlation from causation.</p><p>A <b>residual</b> is the difference between an observed y-value and the y-value predicted by the model:</p><p style=\"text-align:center\"><b>residual = observed y − predicted y</b></p><p>A positive residual means the data point is above the line; a negative residual means it is below. A <b>residual plot</b> graphs the residuals against x.</p><svg class=\"figsvg\" viewBox=\"0 0 300 190\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"160.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"62.2\" y1=\"160.0\" x2=\"62.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"62.2\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"90.4\" y1=\"160.0\" x2=\"90.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"90.4\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"118.7\" y1=\"160.0\" x2=\"118.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"118.7\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"146.9\" y1=\"160.0\" x2=\"146.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"146.9\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"175.1\" y1=\"160.0\" x2=\"175.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"175.1\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"203.3\" y1=\"160.0\" x2=\"203.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"203.3\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"231.6\" y1=\"160.0\" x2=\"231.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"231.6\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"259.8\" y1=\"160.0\" x2=\"259.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"259.8\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"288.0\" y1=\"160.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"288.0\" y=\"171.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line x1=\"34.0\" y1=\"160.0\" x2=\"288.0\" y2=\"160.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"160.0\" text-anchor=\"end\" dominant-baseline=\"middle\">-2</text><line x1=\"34.0\" y1=\"122.5\" x2=\"288.0\" y2=\"122.5\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"122.5\" text-anchor=\"end\" dominant-baseline=\"middle\">-1</text><line x1=\"34.0\" y1=\"85.0\" x2=\"288.0\" y2=\"85.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"85.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"47.5\" x2=\"288.0\" y2=\"47.5\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"47.5\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><line x1=\"34.0\" y1=\"10.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"160.0\" x2=\"288.0\" y2=\"160.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"160.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"288.0\" y=\"183.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">residual</text><line x1=\"34.0\" y1=\"85.0\" x2=\"288.0\" y2=\"85.0\" style=\"stroke:var(--danger);stroke-width:2\"/><circle cx=\"62.2\" cy=\"62.5\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"90.4\" cy=\"115.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"118.7\" cy=\"73.8\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"146.9\" cy=\"92.5\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"175.1\" cy=\"58.8\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"203.3\" cy=\"107.5\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"231.6\" cy=\"81.2\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"259.8\" cy=\"100.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg><ul><li>Residuals spread evenly above and below 0 with <b>no pattern</b> (as above): the line is a good fit.</li><li>Residuals that form a pattern (a U-shape, or mostly one sign): the line is not a good model.</li></ul><div class=\"ex\"><div class=\"exh\">Worked example 1 · Residuals</div><div class=\"exl\">Model y = 2x + 5, data (1, 8), (2, 8), (3, 12).<br>Predicted: 7, 9, 11. Residuals: 8 − 7 = <b>1</b>, 8 − 9 = <b>−1</b>, 12 − 11 = <b>1</b>.</div></div><h4>Line of best fit and correlation coefficient</h4><p>Technology uses <b>linear regression</b> to find the <b>line of best fit</b>, the line that makes the sum of the squares of the residuals as small as possible. In Desmos, enter the data in a table (x₁, y₁) and type <span class=\"mono\">y₁ ~ mx₁ + b</span>. Desmos also shows the <b>correlation coefficient r</b>, a number from −1 to 1.</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>r</th><th>Meaning</th></tr><tr><td>close to 1</td><td>strong positive correlation</td></tr><tr><td>close to −1</td><td>strong negative correlation</td></tr><tr><td>close to 0</td><td>weak or no linear correlation</td></tr></table></div><p>Using a model to predict inside the range of the data is <b>interpolation</b>; predicting outside it is <b>extrapolation</b>, which is less reliable.</p><div class=\"ex\"><div class=\"exh\">Worked example 2 · Regression</div><div class=\"exl\">Data x: 1, 2, 3, 4, 5 and y: 4, 7, 9, 12, 13.<br>Desmos gives y = 2.3x + 2.1 with r ≈ 0.99, a strong positive correlation.<br>For x = 3.5 (interpolation): y = 2.3(3.5) + 2.1 = <b>10.15</b>.</div></div><h4>Correlation and causation</h4><p><b>Causation</b> means a change in one variable <i>causes</i> a change in the other. A strong correlation does not prove causation: both variables may depend on a third factor, or the link may be a coincidence.</p><div class=\"keybox\"><b>Common mistakes:</b> computing residuals as predicted − observed (the sign is reversed), and reading a strong correlation as proof that one variable causes the other.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s5\">Practise 4.5 →</button></div></section><section class=\"note\" id=\"n46\"><h2>4.6 Arithmetic Sequences</h2><p class=\"lt\"><b>Learning target:</b> Recognise arithmetic sequences, find the common difference and write the nth term as a linear function of n.</p><p>A <b>sequence</b> is an ordered list of numbers; each number is a <b>term</b>, written a₁, a₂, a₃, … In an <b>arithmetic sequence</b> the difference between consecutive terms is always the same. This number is the <b>common difference</b> d.</p><p>3, 7, 11, 15, … is arithmetic with d = 4. &nbsp; 20, 14, 8, 2, … is arithmetic with d = −6. &nbsp; 2, 4, 8, 16, … is <b>not</b> (the differences are 2, 4, 8).</p><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Rule for the nth term</th></tr><tr><td class=\"mono\"><b>aₙ = a₁ + (n − 1)d</b></td></tr></table></div><p>The graph of an arithmetic sequence is a set of points on a line with slope d, so an arithmetic sequence is a <b>linear function</b> whose domain is the natural numbers 1, 2, 3, …</p><svg class=\"figsvg\" viewBox=\"0 0 260 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"130.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">aₙ = 4n − 1: points on a line</text><line x1=\"35.0\" y1=\"214.0\" x2=\"35.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"73.0\" y1=\"214.0\" x2=\"73.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"111.0\" y1=\"214.0\" x2=\"111.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"149.0\" y1=\"214.0\" x2=\"149.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"187.0\" y1=\"214.0\" x2=\"187.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"225.0\" y1=\"214.0\" x2=\"225.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"214.0\" x2=\"244.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"203.2\" x2=\"244.0\" y2=\"203.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"192.4\" x2=\"244.0\" y2=\"192.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"181.7\" x2=\"244.0\" y2=\"181.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"170.9\" x2=\"244.0\" y2=\"170.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"160.1\" x2=\"244.0\" y2=\"160.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"149.3\" x2=\"244.0\" y2=\"149.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"138.6\" x2=\"244.0\" y2=\"138.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"127.8\" x2=\"244.0\" y2=\"127.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"117.0\" x2=\"244.0\" y2=\"117.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"106.2\" x2=\"244.0\" y2=\"106.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"95.4\" x2=\"244.0\" y2=\"95.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"84.7\" x2=\"244.0\" y2=\"84.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"73.9\" x2=\"244.0\" y2=\"73.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"63.1\" x2=\"244.0\" y2=\"63.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"52.3\" x2=\"244.0\" y2=\"52.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"41.6\" x2=\"244.0\" y2=\"41.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"30.8\" x2=\"244.0\" y2=\"30.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"20.0\" x2=\"244.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"203.2\" x2=\"244.0\" y2=\"203.2\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"35.0\" y1=\"214.0\" x2=\"35.0\" y2=\"20.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"111.0\" y=\"212.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"187.0\" y=\"212.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"31.0\" y=\"181.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"31.0\" y=\"160.1\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"31.0\" y=\"138.6\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"31.0\" y=\"117.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"31.0\" y=\"95.4\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><text class=\"po\" x=\"31.0\" y=\"73.9\" text-anchor=\"end\" dominant-baseline=\"middle\">12</text><text class=\"po\" x=\"31.0\" y=\"52.3\" text-anchor=\"end\" dominant-baseline=\"middle\">14</text><text class=\"po\" x=\"31.0\" y=\"30.8\" text-anchor=\"end\" dominant-baseline=\"middle\">16</text><text class=\"po\" x=\"240.0\" y=\"195.2\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"43.0\" y=\"26.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b4g462140\"><rect x=\"16.0\" y=\"20.0\" width=\"228.0\" height=\"194.0\"/></clipPath><circle cx=\"73.0\" cy=\"170.9\" r=\"4\" style=\"fill:var(--accent-text)\"/><circle cx=\"111.0\" cy=\"127.8\" r=\"4\" style=\"fill:var(--accent-text)\"/><circle cx=\"149.0\" cy=\"84.7\" r=\"4\" style=\"fill:var(--accent-text)\"/><circle cx=\"187.0\" cy=\"41.6\" r=\"4\" style=\"fill:var(--accent-text)\"/></svg><div class=\"ex\"><div class=\"exh\">Worked example 1 · Write a rule</div><div class=\"exl\">3, 7, 11, 15, …: a₁ = 3, d = 4.<br>aₙ = 3 + (n − 1)(4) = 4n − 1. Then a₂₀ = 4(20) − 1 = <b>79</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 2 · Which term?</div><div class=\"exl\">Which term of 62, 57, 52, … is 2? d = −5, aₙ = 62 − 5(n − 1) = 67 − 5n.<br>67 − 5n = 2 → 5n = 65 → n = <b>13</b>.</div></div><div class=\"ex\"><div class=\"exh\">Worked example 3 · Two terms known</div><div class=\"exl\">a₃ = 14 and a₈ = 39: from term 3 to term 8 there are 5 steps, so 5d = 25 and d = 5.<br>a₁ = 14 − 2(5) = 4, so aₙ = 4 + 5(n − 1) = <b>5n − 1</b>.</div></div><div class=\"keybox\"><b>Common mistake:</b> writing aₙ = a₁ + nd. Only (n − 1) steps are needed to get from term 1 to term n. Check: n = 1 must give back a₁.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s6\">Practise 4.6 →</button></div></section><section class=\"note\" id=\"n47\"><h2>4.7 Piecewise Functions</h2><p class=\"lt\"><b>Learning target:</b> Evaluate, graph and write piecewise functions, including step functions and absolute value functions.</p><p>A <b>piecewise function</b> is defined by two or more equations, each used on a different part of the domain.</p><p style=\"text-align:center\" class=\"mono\">f(x) = x + 2, if x &lt; 1<br>f(x) = −2x + 4, if x ≥ 1</p><svg class=\"figsvg\" viewBox=\"0 0 280 250\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"140.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">f(x) = x + 2 if x < 1; −2x + 4 if x ≥ 1</text><line x1=\"16.0\" y1=\"234.0\" x2=\"16.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"40.8\" y1=\"234.0\" x2=\"40.8\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"65.6\" y1=\"234.0\" x2=\"65.6\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"90.4\" y1=\"234.0\" x2=\"90.4\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"115.2\" y1=\"234.0\" x2=\"115.2\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"140.0\" y1=\"234.0\" x2=\"140.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"164.8\" y1=\"234.0\" x2=\"164.8\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"189.6\" y1=\"234.0\" x2=\"189.6\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"214.4\" y1=\"234.0\" x2=\"214.4\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"239.2\" y1=\"234.0\" x2=\"239.2\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"264.0\" y1=\"234.0\" x2=\"264.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"234.0\" x2=\"264.0\" y2=\"234.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"214.5\" x2=\"264.0\" y2=\"214.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"195.1\" x2=\"264.0\" y2=\"195.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"175.6\" x2=\"264.0\" y2=\"175.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"156.2\" x2=\"264.0\" y2=\"156.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"136.7\" x2=\"264.0\" y2=\"136.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"117.3\" x2=\"264.0\" y2=\"117.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"97.8\" x2=\"264.0\" y2=\"97.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"78.4\" x2=\"264.0\" y2=\"78.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"58.9\" x2=\"264.0\" y2=\"58.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"39.5\" x2=\"264.0\" y2=\"39.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"20.0\" x2=\"264.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"136.7\" x2=\"264.0\" y2=\"136.7\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"140.0\" y1=\"234.0\" x2=\"140.0\" y2=\"20.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"40.8\" y=\"145.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"90.4\" y=\"145.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"189.6\" y=\"145.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"239.2\" y=\"145.7\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"136.0\" y=\"214.5\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"136.0\" y=\"175.6\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"136.0\" y=\"97.8\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"136.0\" y=\"58.9\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"136.0\" y=\"20.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"260.0\" y=\"128.7\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"148.0\" y=\"26.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b4g395023\"><rect x=\"16.0\" y=\"20.0\" width=\"248.0\" height=\"214.0\"/></clipPath><path d=\"M16.0,195.1 L16.7,194.5 L17.5,193.9 L18.2,193.3 L19.0,192.8 L19.7,192.2 L20.5,191.6 L21.2,191.0 L22.0,190.4 L22.7,189.8 L23.4,189.3 L24.2,188.7 L24.9,188.1 L25.7,187.5 L26.4,186.9 L27.2,186.3 L27.9,185.8 L28.6,185.2 L29.4,184.6 L30.1,184.0 L30.9,183.4 L31.6,182.8 L32.4,182.3 L33.1,181.7 L33.9,181.1 L34.6,180.5 L35.3,179.9 L36.1,179.3 L36.8,178.7 L37.6,178.2 L38.3,177.6 L39.1,177.0 L39.8,176.4 L40.6,175.8 L41.3,175.2 L42.0,174.7 L42.8,174.1 L43.5,173.5 L44.3,172.9 L45.0,172.3 L45.8,171.7 L46.5,171.2 L47.2,170.6 L48.0,170.0 L48.7,169.4 L49.5,168.8 L50.2,168.2 L51.0,167.7 L51.7,167.1 L52.5,166.5 L53.2,165.9 L53.9,165.3 L54.7,164.7 L55.4,164.2 L56.2,163.6 L56.9,163.0 L57.7,162.4 L58.4,161.8 L59.2,161.2 L59.9,160.7 L60.6,160.1 L61.4,159.5 L62.1,158.9 L62.9,158.3 L63.6,157.7 L64.4,157.2 L65.1,156.6 L65.8,156.0 L66.6,155.4 L67.3,154.8 L68.1,154.2 L68.8,153.7 L69.6,153.1 L70.3,152.5 L71.1,151.9 L71.8,151.3 L72.5,150.7 L73.3,150.2 L74.0,149.6 L74.8,149.0 L75.5,148.4 L76.3,147.8 L77.0,147.2 L77.8,146.6 L78.5,146.1 L79.2,145.5 L80.0,144.9 L80.7,144.3 L81.5,143.7 L82.2,143.1 L83.0,142.6 L83.7,142.0 L84.4,141.4 L85.2,140.8 L85.9,140.2 L86.7,139.6 L87.4,139.1 L88.2,138.5 L88.9,137.9 L89.7,137.3 L90.4,136.7 L91.1,136.1 L91.9,135.6 L92.6,135.0 L93.4,134.4 L94.1,133.8 L94.9,133.2 L95.6,132.6 L96.4,132.1 L97.1,131.5 L97.8,130.9 L98.6,130.3 L99.3,129.7 L100.1,129.1 L100.8,128.6 L101.6,128.0 L102.3,127.4 L103.0,126.8 L103.8,126.2 L104.5,125.6 L105.3,125.1 L106.0,124.5 L106.8,123.9 L107.5,123.3 L108.3,122.7 L109.0,122.1 L109.7,121.6 L110.5,121.0 L111.2,120.4 L112.0,119.8 L112.7,119.2 L113.5,118.6 L114.2,118.1 L115.0,117.5 L115.7,116.9 L116.4,116.3 L117.2,115.7 L117.9,115.1 L118.7,114.5 L119.4,114.0 L120.2,113.4 L120.9,112.8 L121.6,112.2 L122.4,111.6 L123.1,111.0 L123.9,110.5 L124.6,109.9 L125.4,109.3 L126.1,108.7 L126.9,108.1 L127.6,107.5 L128.3,107.0 L129.1,106.4 L129.8,105.8 L130.6,105.2 L131.3,104.6 L132.1,104.0 L132.8,103.5 L133.6,102.9 L134.3,102.3 L135.0,101.7 L135.8,101.1 L136.5,100.5 L137.3,100.0 L138.0,99.4 L138.8,98.8 L139.5,98.2 L140.2,97.6 L141.0,97.0 L141.7,96.5 L142.5,95.9 L143.2,95.3 L144.0,94.7 L144.7,94.1 L145.5,93.5 L146.2,93.0 L146.9,92.4 L147.7,91.8 L148.4,91.2 L149.2,90.6 L149.9,90.0 L150.7,89.5 L151.4,88.9 L152.2,88.3 L152.9,87.7 L153.6,87.1 L154.4,86.5 L155.1,86.0 L155.9,85.4 L156.6,84.8 L157.4,84.2 L158.1,83.6 L158.8,83.0 L159.6,82.4 L160.3,81.9 L161.1,81.3 L161.8,80.7 L162.6,80.1 L163.3,79.5 L164.1,78.9 L164.8,78.4\" clip-path=\"url(#b4g395023)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><path d=\"M164.8,97.8 L165.3,98.6 L165.8,99.4 L166.3,100.2 L166.8,100.9 L167.3,101.7 L167.8,102.5 L168.3,103.3 L168.8,104.0 L169.3,104.8 L169.8,105.6 L170.3,106.4 L170.8,107.2 L171.2,107.9 L171.7,108.7 L172.2,109.5 L172.7,110.3 L173.2,111.0 L173.7,111.8 L174.2,112.6 L174.7,113.4 L175.2,114.2 L175.7,114.9 L176.2,115.7 L176.7,116.5 L177.2,117.3 L177.7,118.1 L178.2,118.8 L178.7,119.6 L179.2,120.4 L179.7,121.2 L180.2,121.9 L180.7,122.7 L181.2,123.5 L181.7,124.3 L182.2,125.1 L182.7,125.8 L183.2,126.6 L183.6,127.4 L184.1,128.2 L184.6,128.9 L185.1,129.7 L185.6,130.5 L186.1,131.3 L186.6,132.1 L187.1,132.8 L187.6,133.6 L188.1,134.4 L188.6,135.2 L189.1,135.9 L189.6,136.7 L190.1,137.5 L190.6,138.3 L191.1,139.1 L191.6,139.8 L192.1,140.6 L192.6,141.4 L193.1,142.2 L193.6,143.0 L194.1,143.7 L194.6,144.5 L195.1,145.3 L195.6,146.1 L196.0,146.8 L196.5,147.6 L197.0,148.4 L197.5,149.2 L198.0,150.0 L198.5,150.7 L199.0,151.5 L199.5,152.3 L200.0,153.1 L200.5,153.8 L201.0,154.6 L201.5,155.4 L202.0,156.2 L202.5,157.0 L203.0,157.7 L203.5,158.5 L204.0,159.3 L204.5,160.1 L205.0,160.9 L205.5,161.6 L206.0,162.4 L206.5,163.2 L207.0,164.0 L207.5,164.7 L208.0,165.5 L208.4,166.3 L208.9,167.1 L209.4,167.9 L209.9,168.6 L210.4,169.4 L210.9,170.2 L211.4,171.0 L211.9,171.7 L212.4,172.5 L212.9,173.3 L213.4,174.1 L213.9,174.9 L214.4,175.6 L214.9,176.4 L215.4,177.2 L215.9,178.0 L216.4,178.7 L216.9,179.5 L217.4,180.3 L217.9,181.1 L218.4,181.9 L218.9,182.6 L219.4,183.4 L219.9,184.2 L220.4,185.0 L220.8,185.8 L221.3,186.5 L221.8,187.3 L222.3,188.1 L222.8,188.9 L223.3,189.6 L223.8,190.4 L224.3,191.2 L224.8,192.0 L225.3,192.8 L225.8,193.5 L226.3,194.3 L226.8,195.1 L227.3,195.9 L227.8,196.6 L228.3,197.4 L228.8,198.2 L229.3,199.0 L229.8,199.8 L230.3,200.5 L230.8,201.3 L231.3,202.1 L231.8,202.9 L232.3,203.7 L232.8,204.4 L233.2,205.2 L233.7,206.0 L234.2,206.8 L234.7,207.5 L235.2,208.3 L235.7,209.1 L236.2,209.9 L236.7,210.7 L237.2,211.4 L237.7,212.2 L238.2,213.0 L238.7,213.8 L239.2,214.5 L239.7,215.3 L240.2,216.1 L240.7,216.9 L241.2,217.7 L241.7,218.4 L242.2,219.2 L242.7,220.0 L243.2,220.8 L243.7,221.5 L244.2,222.3 L244.7,223.1 L245.2,223.9 L245.6,224.7 L246.1,225.4 L246.6,226.2 L247.1,227.0 L247.6,227.8 L248.1,228.6 L248.6,229.3 L249.1,230.1 L249.6,230.9 L250.1,231.7 L250.6,232.4 L251.1,233.2 L251.6,234.0 L252.1,234.8 L252.6,235.6 L253.1,236.3 L253.6,237.1 L254.1,237.9 L254.6,238.7 L255.1,239.4 L255.6,240.2 L256.1,241.0 L256.6,241.8 L257.1,242.6 L257.6,243.3 L258.0,244.1 L258.5,244.9 L259.0,245.7 L259.5,246.5 L260.0,247.2 L260.5,248.0 L261.0,248.8 L261.5,249.6 L262.0,250.3 L262.5,251.1 L263.0,251.9 L263.5,252.7 L264.0,253.5\" clip-path=\"url(#b4g395023)\" style=\"fill:none;stroke:var(--accent-text);stroke-width:2.4;stroke-dasharray:6 4\"/><circle cx=\"164.8\" cy=\"97.8\" r=\"4\" style=\"fill:var(--accent-text)\"/><circle cx=\"164.8\" cy=\"78.4\" r=\"4\" style=\"fill:var(--card);stroke:var(--danger);stroke-width:2\"/></svg><p>An <b>open circle</b> ○ shows an endpoint that is <i>not</i> included (&lt; or &gt;). A <b>closed circle</b> ● shows an endpoint that is included (≤ or ≥).</p><h4>Evaluating</h4><p>First find which interval the input is in, then use <b>only</b> that equation.</p><div class=\"ex\"><div class=\"exh\">Worked example 1 · Evaluate f above</div><div class=\"exl\">f(−3): −3 &lt; 1, use x + 2: f(−3) = <b>−1</b>.<br>f(1): 1 ≥ 1, use −2x + 4: f(1) = <b>2</b> (the closed circle).<br>f(3): use −2x + 4: f(3) = <b>−2</b>.</div></div><h4>Step functions</h4><p>A <b>step function</b> is a piecewise function that is constant on each interval, so its graph looks like a set of stairs. Parking fees and shipping rates are often step functions.</p><svg class=\"figsvg\" viewBox=\"0 0 260 220\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><text class=\"lb\" x=\"130.0\" y=\"10.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">Cost ($) of x hours of parking</text><line x1=\"36.7\" y1=\"204.0\" x2=\"36.7\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"78.2\" y1=\"204.0\" x2=\"78.2\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"119.6\" y1=\"204.0\" x2=\"119.6\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"161.1\" y1=\"204.0\" x2=\"161.1\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"202.5\" y1=\"204.0\" x2=\"202.5\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"244.0\" y1=\"204.0\" x2=\"244.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"194.3\" x2=\"244.0\" y2=\"194.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"174.9\" x2=\"244.0\" y2=\"174.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"155.6\" x2=\"244.0\" y2=\"155.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"136.2\" x2=\"244.0\" y2=\"136.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"116.8\" x2=\"244.0\" y2=\"116.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"97.5\" x2=\"244.0\" y2=\"97.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"78.1\" x2=\"244.0\" y2=\"78.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"58.7\" x2=\"244.0\" y2=\"58.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"39.4\" x2=\"244.0\" y2=\"39.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"20.0\" x2=\"244.0\" y2=\"20.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"194.3\" x2=\"244.0\" y2=\"194.3\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"36.7\" y1=\"204.0\" x2=\"36.7\" y2=\"20.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"78.2\" y=\"203.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"119.6\" y=\"203.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"161.1\" y=\"203.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"202.5\" y=\"203.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"244.0\" y=\"203.3\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><text class=\"po\" x=\"32.7\" y=\"174.9\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"32.7\" y=\"155.6\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"32.7\" y=\"136.2\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"32.7\" y=\"116.8\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"32.7\" y=\"97.5\" text-anchor=\"end\" dominant-baseline=\"middle\">5</text><text class=\"po\" x=\"32.7\" y=\"78.1\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"32.7\" y=\"58.7\" text-anchor=\"end\" dominant-baseline=\"middle\">7</text><text class=\"po\" x=\"32.7\" y=\"39.4\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"32.7\" y=\"20.0\" text-anchor=\"end\" dominant-baseline=\"middle\">9</text><text class=\"po\" x=\"240.0\" y=\"186.3\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"44.7\" y=\"26.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b4g104710\"><rect x=\"16.0\" y=\"20.0\" width=\"228.0\" height=\"184.0\"/></clipPath><path d=\"M36.7,155.6 L36.9,155.6 L37.1,155.6 L37.3,155.6 L37.6,155.6 L37.8,155.6 L38.0,155.6 L38.2,155.6 L38.4,155.6 L38.6,155.6 L38.8,155.6 L39.0,155.6 L39.2,155.6 L39.4,155.6 L39.6,155.6 L39.8,155.6 L40.0,155.6 L40.3,155.6 L40.5,155.6 L40.7,155.6 L40.9,155.6 L41.1,155.6 L41.3,155.6 L41.5,155.6 L41.7,155.6 L41.9,155.6 L42.1,155.6 L42.3,155.6 L42.5,155.6 L42.7,155.6 L42.9,155.6 L43.2,155.6 L43.4,155.6 L43.6,155.6 L43.8,155.6 L44.0,155.6 L44.2,155.6 L44.4,155.6 L44.6,155.6 L44.8,155.6 L45.0,155.6 L45.2,155.6 L45.4,155.6 L45.6,155.6 L45.8,155.6 L46.1,155.6 L46.3,155.6 L46.5,155.6 L46.7,155.6 L46.9,155.6 L47.1,155.6 L47.3,155.6 L47.5,155.6 L47.7,155.6 L47.9,155.6 L48.1,155.6 L48.3,155.6 L48.5,155.6 L48.7,155.6 L49.0,155.6 L49.2,155.6 L49.4,155.6 L49.6,155.6 L49.8,155.6 L50.0,155.6 L50.2,155.6 L50.4,155.6 L50.6,155.6 L50.8,155.6 L51.0,155.6 L51.2,155.6 L51.4,155.6 L51.7,155.6 L51.9,155.6 L52.1,155.6 L52.3,155.6 L52.5,155.6 L52.7,155.6 L52.9,155.6 L53.1,155.6 L53.3,155.6 L53.5,155.6 L53.7,155.6 L53.9,155.6 L54.1,155.6 L54.3,155.6 L54.6,155.6 L54.8,155.6 L55.0,155.6 L55.2,155.6 L55.4,155.6 L55.6,155.6 L55.8,155.6 L56.0,155.6 L56.2,155.6 L56.4,155.6 L56.6,155.6 L56.8,155.6 L57.0,155.6 L57.2,155.6 L57.5,155.6 L57.7,155.6 L57.9,155.6 L58.1,155.6 L58.3,155.6 L58.5,155.6 L58.7,155.6 L58.9,155.6 L59.1,155.6 L59.3,155.6 L59.5,155.6 L59.7,155.6 L59.9,155.6 L60.1,155.6 L60.4,155.6 L60.6,155.6 L60.8,155.6 L61.0,155.6 L61.2,155.6 L61.4,155.6 L61.6,155.6 L61.8,155.6 L62.0,155.6 L62.2,155.6 L62.4,155.6 L62.6,155.6 L62.8,155.6 L63.1,155.6 L63.3,155.6 L63.5,155.6 L63.7,155.6 L63.9,155.6 L64.1,155.6 L64.3,155.6 L64.5,155.6 L64.7,155.6 L64.9,155.6 L65.1,155.6 L65.3,155.6 L65.5,155.6 L65.7,155.6 L66.0,155.6 L66.2,155.6 L66.4,155.6 L66.6,155.6 L66.8,155.6 L67.0,155.6 L67.2,155.6 L67.4,155.6 L67.6,155.6 L67.8,155.6 L68.0,155.6 L68.2,155.6 L68.4,155.6 L68.6,155.6 L68.9,155.6 L69.1,155.6 L69.3,155.6 L69.5,155.6 L69.7,155.6 L69.9,155.6 L70.1,155.6 L70.3,155.6 L70.5,155.6 L70.7,155.6 L70.9,155.6 L71.1,155.6 L71.3,155.6 L71.5,155.6 L71.8,155.6 L72.0,155.6 L72.2,155.6 L72.4,155.6 L72.6,155.6 L72.8,155.6 L73.0,155.6 L73.2,155.6 L73.4,155.6 L73.6,155.6 L73.8,155.6 L74.0,155.6 L74.2,155.6 L74.5,155.6 L74.7,155.6 L74.9,155.6 L75.1,155.6 L75.3,155.6 L75.5,155.6 L75.7,155.6 L75.9,155.6 L76.1,155.6 L76.3,155.6 L76.5,155.6 L76.7,155.6 L76.9,155.6 L77.1,155.6 L77.4,155.6 L77.6,155.6 L77.8,155.6 L78.0,155.6 L78.2,155.6\" clip-path=\"url(#b4g104710)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><path d=\"M78.2,116.8 L78.4,116.8 L78.6,116.8 L78.8,116.8 L79.0,116.8 L79.2,116.8 L79.4,116.8 L79.6,116.8 L79.8,116.8 L80.0,116.8 L80.3,116.8 L80.5,116.8 L80.7,116.8 L80.9,116.8 L81.1,116.8 L81.3,116.8 L81.5,116.8 L81.7,116.8 L81.9,116.8 L82.1,116.8 L82.3,116.8 L82.5,116.8 L82.7,116.8 L82.9,116.8 L83.2,116.8 L83.4,116.8 L83.6,116.8 L83.8,116.8 L84.0,116.8 L84.2,116.8 L84.4,116.8 L84.6,116.8 L84.8,116.8 L85.0,116.8 L85.2,116.8 L85.4,116.8 L85.6,116.8 L85.9,116.8 L86.1,116.8 L86.3,116.8 L86.5,116.8 L86.7,116.8 L86.9,116.8 L87.1,116.8 L87.3,116.8 L87.5,116.8 L87.7,116.8 L87.9,116.8 L88.1,116.8 L88.3,116.8 L88.5,116.8 L88.8,116.8 L89.0,116.8 L89.2,116.8 L89.4,116.8 L89.6,116.8 L89.8,116.8 L90.0,116.8 L90.2,116.8 L90.4,116.8 L90.6,116.8 L90.8,116.8 L91.0,116.8 L91.2,116.8 L91.4,116.8 L91.7,116.8 L91.9,116.8 L92.1,116.8 L92.3,116.8 L92.5,116.8 L92.7,116.8 L92.9,116.8 L93.1,116.8 L93.3,116.8 L93.5,116.8 L93.7,116.8 L93.9,116.8 L94.1,116.8 L94.3,116.8 L94.6,116.8 L94.8,116.8 L95.0,116.8 L95.2,116.8 L95.4,116.8 L95.6,116.8 L95.8,116.8 L96.0,116.8 L96.2,116.8 L96.4,116.8 L96.6,116.8 L96.8,116.8 L97.0,116.8 L97.3,116.8 L97.5,116.8 L97.7,116.8 L97.9,116.8 L98.1,116.8 L98.3,116.8 L98.5,116.8 L98.7,116.8 L98.9,116.8 L99.1,116.8 L99.3,116.8 L99.5,116.8 L99.7,116.8 L99.9,116.8 L100.2,116.8 L100.4,116.8 L100.6,116.8 L100.8,116.8 L101.0,116.8 L101.2,116.8 L101.4,116.8 L101.6,116.8 L101.8,116.8 L102.0,116.8 L102.2,116.8 L102.4,116.8 L102.6,116.8 L102.8,116.8 L103.1,116.8 L103.3,116.8 L103.5,116.8 L103.7,116.8 L103.9,116.8 L104.1,116.8 L104.3,116.8 L104.5,116.8 L104.7,116.8 L104.9,116.8 L105.1,116.8 L105.3,116.8 L105.5,116.8 L105.7,116.8 L106.0,116.8 L106.2,116.8 L106.4,116.8 L106.6,116.8 L106.8,116.8 L107.0,116.8 L107.2,116.8 L107.4,116.8 L107.6,116.8 L107.8,116.8 L108.0,116.8 L108.2,116.8 L108.4,116.8 L108.7,116.8 L108.9,116.8 L109.1,116.8 L109.3,116.8 L109.5,116.8 L109.7,116.8 L109.9,116.8 L110.1,116.8 L110.3,116.8 L110.5,116.8 L110.7,116.8 L110.9,116.8 L111.1,116.8 L111.3,116.8 L111.6,116.8 L111.8,116.8 L112.0,116.8 L112.2,116.8 L112.4,116.8 L112.6,116.8 L112.8,116.8 L113.0,116.8 L113.2,116.8 L113.4,116.8 L113.6,116.8 L113.8,116.8 L114.0,116.8 L114.2,116.8 L114.5,116.8 L114.7,116.8 L114.9,116.8 L115.1,116.8 L115.3,116.8 L115.5,116.8 L115.7,116.8 L115.9,116.8 L116.1,116.8 L116.3,116.8 L116.5,116.8 L116.7,116.8 L116.9,116.8 L117.1,116.8 L117.4,116.8 L117.6,116.8 L117.8,116.8 L118.0,116.8 L118.2,116.8 L118.4,116.8 L118.6,116.8 L118.8,116.8 L119.0,116.8 L119.2,116.8 L119.4,116.8 L119.6,116.8\" clip-path=\"url(#b4g104710)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><path d=\"M119.6,78.1 L119.8,78.1 L120.1,78.1 L120.3,78.1 L120.5,78.1 L120.7,78.1 L120.9,78.1 L121.1,78.1 L121.3,78.1 L121.5,78.1 L121.7,78.1 L121.9,78.1 L122.1,78.1 L122.3,78.1 L122.5,78.1 L122.7,78.1 L123.0,78.1 L123.2,78.1 L123.4,78.1 L123.6,78.1 L123.8,78.1 L124.0,78.1 L124.2,78.1 L124.4,78.1 L124.6,78.1 L124.8,78.1 L125.0,78.1 L125.2,78.1 L125.4,78.1 L125.6,78.1 L125.9,78.1 L126.1,78.1 L126.3,78.1 L126.5,78.1 L126.7,78.1 L126.9,78.1 L127.1,78.1 L127.3,78.1 L127.5,78.1 L127.7,78.1 L127.9,78.1 L128.1,78.1 L128.3,78.1 L128.5,78.1 L128.8,78.1 L129.0,78.1 L129.2,78.1 L129.4,78.1 L129.6,78.1 L129.8,78.1 L130.0,78.1 L130.2,78.1 L130.4,78.1 L130.6,78.1 L130.8,78.1 L131.0,78.1 L131.2,78.1 L131.5,78.1 L131.7,78.1 L131.9,78.1 L132.1,78.1 L132.3,78.1 L132.5,78.1 L132.7,78.1 L132.9,78.1 L133.1,78.1 L133.3,78.1 L133.5,78.1 L133.7,78.1 L133.9,78.1 L134.1,78.1 L134.4,78.1 L134.6,78.1 L134.8,78.1 L135.0,78.1 L135.2,78.1 L135.4,78.1 L135.6,78.1 L135.8,78.1 L136.0,78.1 L136.2,78.1 L136.4,78.1 L136.6,78.1 L136.8,78.1 L137.0,78.1 L137.3,78.1 L137.5,78.1 L137.7,78.1 L137.9,78.1 L138.1,78.1 L138.3,78.1 L138.5,78.1 L138.7,78.1 L138.9,78.1 L139.1,78.1 L139.3,78.1 L139.5,78.1 L139.7,78.1 L139.9,78.1 L140.2,78.1 L140.4,78.1 L140.6,78.1 L140.8,78.1 L141.0,78.1 L141.2,78.1 L141.4,78.1 L141.6,78.1 L141.8,78.1 L142.0,78.1 L142.2,78.1 L142.4,78.1 L142.6,78.1 L142.9,78.1 L143.1,78.1 L143.3,78.1 L143.5,78.1 L143.7,78.1 L143.9,78.1 L144.1,78.1 L144.3,78.1 L144.5,78.1 L144.7,78.1 L144.9,78.1 L145.1,78.1 L145.3,78.1 L145.5,78.1 L145.8,78.1 L146.0,78.1 L146.2,78.1 L146.4,78.1 L146.6,78.1 L146.8,78.1 L147.0,78.1 L147.2,78.1 L147.4,78.1 L147.6,78.1 L147.8,78.1 L148.0,78.1 L148.2,78.1 L148.4,78.1 L148.7,78.1 L148.9,78.1 L149.1,78.1 L149.3,78.1 L149.5,78.1 L149.7,78.1 L149.9,78.1 L150.1,78.1 L150.3,78.1 L150.5,78.1 L150.7,78.1 L150.9,78.1 L151.1,78.1 L151.3,78.1 L151.6,78.1 L151.8,78.1 L152.0,78.1 L152.2,78.1 L152.4,78.1 L152.6,78.1 L152.8,78.1 L153.0,78.1 L153.2,78.1 L153.4,78.1 L153.6,78.1 L153.8,78.1 L154.0,78.1 L154.3,78.1 L154.5,78.1 L154.7,78.1 L154.9,78.1 L155.1,78.1 L155.3,78.1 L155.5,78.1 L155.7,78.1 L155.9,78.1 L156.1,78.1 L156.3,78.1 L156.5,78.1 L156.7,78.1 L156.9,78.1 L157.2,78.1 L157.4,78.1 L157.6,78.1 L157.8,78.1 L158.0,78.1 L158.2,78.1 L158.4,78.1 L158.6,78.1 L158.8,78.1 L159.0,78.1 L159.2,78.1 L159.4,78.1 L159.6,78.1 L159.8,78.1 L160.1,78.1 L160.3,78.1 L160.5,78.1 L160.7,78.1 L160.9,78.1 L161.1,78.1\" clip-path=\"url(#b4g104710)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><path d=\"M161.1,39.4 L161.3,39.4 L161.5,39.4 L161.7,39.4 L161.9,39.4 L162.1,39.4 L162.3,39.4 L162.5,39.4 L162.7,39.4 L163.0,39.4 L163.2,39.4 L163.4,39.4 L163.6,39.4 L163.8,39.4 L164.0,39.4 L164.2,39.4 L164.4,39.4 L164.6,39.4 L164.8,39.4 L165.0,39.4 L165.2,39.4 L165.4,39.4 L165.7,39.4 L165.9,39.4 L166.1,39.4 L166.3,39.4 L166.5,39.4 L166.7,39.4 L166.9,39.4 L167.1,39.4 L167.3,39.4 L167.5,39.4 L167.7,39.4 L167.9,39.4 L168.1,39.4 L168.3,39.4 L168.6,39.4 L168.8,39.4 L169.0,39.4 L169.2,39.4 L169.4,39.4 L169.6,39.4 L169.8,39.4 L170.0,39.4 L170.2,39.4 L170.4,39.4 L170.6,39.4 L170.8,39.4 L171.0,39.4 L171.2,39.4 L171.5,39.4 L171.7,39.4 L171.9,39.4 L172.1,39.4 L172.3,39.4 L172.5,39.4 L172.7,39.4 L172.9,39.4 L173.1,39.4 L173.3,39.4 L173.5,39.4 L173.7,39.4 L173.9,39.4 L174.1,39.4 L174.4,39.4 L174.6,39.4 L174.8,39.4 L175.0,39.4 L175.2,39.4 L175.4,39.4 L175.6,39.4 L175.8,39.4 L176.0,39.4 L176.2,39.4 L176.4,39.4 L176.6,39.4 L176.8,39.4 L177.1,39.4 L177.3,39.4 L177.5,39.4 L177.7,39.4 L177.9,39.4 L178.1,39.4 L178.3,39.4 L178.5,39.4 L178.7,39.4 L178.9,39.4 L179.1,39.4 L179.3,39.4 L179.5,39.4 L179.7,39.4 L180.0,39.4 L180.2,39.4 L180.4,39.4 L180.6,39.4 L180.8,39.4 L181.0,39.4 L181.2,39.4 L181.4,39.4 L181.6,39.4 L181.8,39.4 L182.0,39.4 L182.2,39.4 L182.4,39.4 L182.6,39.4 L182.9,39.4 L183.1,39.4 L183.3,39.4 L183.5,39.4 L183.7,39.4 L183.9,39.4 L184.1,39.4 L184.3,39.4 L184.5,39.4 L184.7,39.4 L184.9,39.4 L185.1,39.4 L185.3,39.4 L185.5,39.4 L185.8,39.4 L186.0,39.4 L186.2,39.4 L186.4,39.4 L186.6,39.4 L186.8,39.4 L187.0,39.4 L187.2,39.4 L187.4,39.4 L187.6,39.4 L187.8,39.4 L188.0,39.4 L188.2,39.4 L188.5,39.4 L188.7,39.4 L188.9,39.4 L189.1,39.4 L189.3,39.4 L189.5,39.4 L189.7,39.4 L189.9,39.4 L190.1,39.4 L190.3,39.4 L190.5,39.4 L190.7,39.4 L190.9,39.4 L191.1,39.4 L191.4,39.4 L191.6,39.4 L191.8,39.4 L192.0,39.4 L192.2,39.4 L192.4,39.4 L192.6,39.4 L192.8,39.4 L193.0,39.4 L193.2,39.4 L193.4,39.4 L193.6,39.4 L193.8,39.4 L194.0,39.4 L194.3,39.4 L194.5,39.4 L194.7,39.4 L194.9,39.4 L195.1,39.4 L195.3,39.4 L195.5,39.4 L195.7,39.4 L195.9,39.4 L196.1,39.4 L196.3,39.4 L196.5,39.4 L196.7,39.4 L196.9,39.4 L197.2,39.4 L197.4,39.4 L197.6,39.4 L197.8,39.4 L198.0,39.4 L198.2,39.4 L198.4,39.4 L198.6,39.4 L198.8,39.4 L199.0,39.4 L199.2,39.4 L199.4,39.4 L199.6,39.4 L199.9,39.4 L200.1,39.4 L200.3,39.4 L200.5,39.4 L200.7,39.4 L200.9,39.4 L201.1,39.4 L201.3,39.4 L201.5,39.4 L201.7,39.4 L201.9,39.4 L202.1,39.4 L202.3,39.4 L202.5,39.4\" clip-path=\"url(#b4g104710)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><circle cx=\"78.2\" cy=\"155.6\" r=\"4\" style=\"fill:var(--danger)\"/><circle cx=\"119.6\" cy=\"116.8\" r=\"4\" style=\"fill:var(--danger)\"/><circle cx=\"161.1\" cy=\"78.1\" r=\"4\" style=\"fill:var(--danger)\"/><circle cx=\"202.5\" cy=\"39.4\" r=\"4\" style=\"fill:var(--danger)\"/><circle cx=\"36.7\" cy=\"155.6\" r=\"4\" style=\"fill:var(--card);stroke:var(--danger);stroke-width:2\"/><circle cx=\"78.2\" cy=\"116.8\" r=\"4\" style=\"fill:var(--card);stroke:var(--danger);stroke-width:2\"/><circle cx=\"119.6\" cy=\"78.1\" r=\"4\" style=\"fill:var(--card);stroke:var(--danger);stroke-width:2\"/><circle cx=\"161.1\" cy=\"39.4\" r=\"4\" style=\"fill:var(--card);stroke:var(--danger);stroke-width:2\"/></svg><p>Here parking costs $2 for up to 1 hour, $4 for more than 1 and up to 2 hours, and so on: 2.5 hours cost <b>$6</b>.</p><h4>Absolute value functions</h4><p>Because |u| = −u when u &lt; 0 and |u| = u when u ≥ 0, an absolute value function can be written as a piecewise function:</p><p style=\"text-align:center\" class=\"mono\">|x − 3| + 1 = −x + 4, if x &lt; 3<br>|x − 3| + 1 = x − 2, if x ≥ 3</p><div class=\"ex\"><div class=\"exh\">Worked example 2 · Write a piecewise function from a description</div><div class=\"exl\">A plumber charges $90 for the first hour or less, then $60 for each hour after that (billed exactly).<br>C(h) = 90 if 0 &lt; h ≤ 1; C(h) = 90 + 60(h − 1) = 60h + 30 if h &gt; 1.<br>C(2.5) = 60(2.5) + 30 = <b>$180</b>.</div></div><div class=\"keybox\"><b>Common mistakes:</b> using the wrong piece at a boundary value (check ≤ against &lt;), and in tiered charges applying the higher rate to <i>all</i> units instead of only the units above the first tier.</div><div class=\"hub-btns\" style=\"margin-top:12px\"><button class=\"hub-btn primary\" data-go=\"s7\">Practise 4.7 →</button></div></section><section class=\"note\" id=\"nsum\"><h2>Chapter checklist</h2><ul><li>4.1 · Write an equation of a line in slope-intercept form from its graph, from its slope and y-intercept, from its slope and a point, or from two points.</li><li>4.2 · Write an equation of a line in point-slope form, change it to slope-intercept form, and use it to model real-life rates.</li><li>4.3 · Identify parallel and perpendicular lines from their slopes and write equations of lines parallel or perpendicular to a given line.</li><li>4.4 · Describe the correlation shown in a scatter plot, write an equation of a line of fit and use it to make predictions.</li><li>4.5 · Use residuals to judge a line of fit, find the line of best fit and the correlation coefficient with technology, and tell correlation from causation.</li><li>4.6 · Recognise arithmetic sequences, find the common difference and write the nth term as a linear function of n.</li><li>4.7 · Evaluate, graph and write piecewise functions, including step functions and absolute value functions.</li></ul><div class=\"tscroll\"><table class=\"ttab\"><tr><th>Form or rule</th><th>Formula</th></tr><tr><td>Slope</td><td class=\"mono\">m = (y₂ − y₁) ÷ (x₂ − x₁)</td></tr><tr><td>Slope-intercept form</td><td class=\"mono\">y = mx + b</td></tr><tr><td>Point-slope form</td><td class=\"mono\">y − y₁ = m(x − x₁)</td></tr><tr><td>Parallel · perpendicular</td><td>m₁ = m₂ · m₁ × m₂ = −1</td></tr><tr><td>Residual</td><td>observed y − predicted y</td></tr><tr><td>Arithmetic sequence</td><td class=\"mono\">aₙ = a₁ + (n − 1)d</td></tr></table></div><div class=\"hub-btns\" style=\"margin-top:10px\"><button class=\"hub-btn\" data-go=\"s8\">Assessment A</button><button class=\"hub-btn\" data-go=\"s9\">Assessment B</button><button class=\"hub-btn\" data-go=\"s10\">Assessment C</button><button class=\"hub-btn\" data-go=\"s11\">Assessment D</button><button class=\"hub-btn primary\" data-go=\"report\">📊 Report</button></div></section>";
var REPORT = [["s8", "A", "Knowing and understanding"], ["s9", "B", "Investigating patterns"], ["s10", "C", "Communicating"], ["s11", "D", "Applying mathematics in real-life contexts"]];
var SECTIONS = [{"id": "s1", "label": "4.1 Writing Equations in Slope-Intercept Form", "sub": "Write an equation of a line in slope-intercept form from its graph, from its slope and y-intercept, from its slope and a point, or from two points.", "slides": [{"kind": "mcq", "text": "Which equation describes the line with slope 3 and y-intercept −5?", "opts": ["y = −3x − 5", "y = 3x − 5", "y = −5x + 3", "y = 3x + 5"], "correct": 1, "tag": "", "sol": "In y = mx + b, m is the slope and b is the y-intercept: m = 3 and b = −5 give y = 3x − 5."}, {"kind": "blank", "p": "Use the graph. A is on the y-axis and B is another point on the line.", "tag": "", "marks": "", "flat": [{"t": "y-intercept b = __B1__", "a": {"B1": "3"}}, {"t": "slope m = __B1__", "a": {"B1": "-2"}}, {"t": "Equation: y = __B1__", "a": {"B1": "-2x+3"}, "expr": true}], "sol": "The line meets the y-axis at A(0, 3), so b = 3.\nFrom A(0, 3) to B(2, −1): rise −4, run 2, m = −4 ÷ 2 = −2.\ny = −2x + 3. Check B: −2(2) + 3 = −1 ✓", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"16.0\" y1=\"214.0\" x2=\"16.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"45.8\" y1=\"214.0\" x2=\"45.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"75.6\" y1=\"214.0\" x2=\"75.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.3\" y1=\"214.0\" x2=\"105.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"135.1\" y1=\"214.0\" x2=\"135.1\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"164.9\" y1=\"214.0\" x2=\"164.9\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"194.7\" y1=\"214.0\" x2=\"194.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"224.4\" y1=\"214.0\" x2=\"224.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"254.2\" y1=\"214.0\" x2=\"254.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"284.0\" y1=\"214.0\" x2=\"284.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"214.0\" x2=\"284.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"196.8\" x2=\"284.0\" y2=\"196.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"179.7\" x2=\"284.0\" y2=\"179.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"162.5\" x2=\"284.0\" y2=\"162.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"145.3\" x2=\"284.0\" y2=\"145.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"128.2\" x2=\"284.0\" y2=\"128.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"111.0\" x2=\"284.0\" y2=\"111.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"93.8\" x2=\"284.0\" y2=\"93.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"76.7\" x2=\"284.0\" y2=\"76.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"59.5\" x2=\"284.0\" y2=\"59.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"42.3\" x2=\"284.0\" y2=\"42.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"25.2\" x2=\"284.0\" y2=\"25.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"8.0\" x2=\"284.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"128.2\" x2=\"284.0\" y2=\"128.2\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"135.1\" y1=\"214.0\" x2=\"135.1\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"16.0\" y=\"137.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"75.6\" y=\"137.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"194.7\" y=\"137.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"254.2\" y=\"137.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"131.1\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−5</text><text class=\"po\" x=\"131.1\" y=\"179.7\" text-anchor=\"end\" dominant-baseline=\"middle\">−3</text><text class=\"po\" x=\"131.1\" y=\"145.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−1</text><text class=\"po\" x=\"131.1\" y=\"111.0\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><text class=\"po\" x=\"131.1\" y=\"76.7\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><text class=\"po\" x=\"131.1\" y=\"42.3\" text-anchor=\"end\" dominant-baseline=\"middle\">5</text><text class=\"po\" x=\"131.1\" y=\"8.0\" text-anchor=\"end\" dominant-baseline=\"middle\">7</text><text class=\"po\" x=\"280.0\" y=\"120.2\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"143.1\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"c46457\"><rect x=\"16.0\" y=\"8.0\" width=\"268.0\" height=\"206.0\"/></clipPath><path d=\"M16.0,-60.7 L16.7,-59.9 L17.3,-59.1 L18.0,-58.3 L18.7,-57.6 L19.3,-56.8 L20.0,-56.0 L20.7,-55.3 L21.4,-54.5 L22.0,-53.7 L22.7,-52.9 L23.4,-52.2 L24.0,-51.4 L24.7,-50.6 L25.4,-49.9 L26.0,-49.1 L26.7,-48.3 L27.4,-47.5 L28.1,-46.8 L28.7,-46.0 L29.4,-45.2 L30.1,-44.4 L30.7,-43.7 L31.4,-42.9 L32.1,-42.1 L32.8,-41.4 L33.4,-40.6 L34.1,-39.8 L34.8,-39.0 L35.4,-38.3 L36.1,-37.5 L36.8,-36.7 L37.4,-35.9 L38.1,-35.2 L38.8,-34.4 L39.5,-33.6 L40.1,-32.9 L40.8,-32.1 L41.5,-31.3 L42.1,-30.5 L42.8,-29.8 L43.5,-29.0 L44.1,-28.2 L44.8,-27.4 L45.5,-26.7 L46.2,-25.9 L46.8,-25.1 L47.5,-24.4 L48.2,-23.6 L48.8,-22.8 L49.5,-22.0 L50.2,-21.3 L50.8,-20.5 L51.5,-19.7 L52.2,-19.0 L52.8,-18.2 L53.5,-17.4 L54.2,-16.6 L54.9,-15.9 L55.5,-15.1 L56.2,-14.3 L56.9,-13.5 L57.5,-12.8 L58.2,-12.0 L58.9,-11.2 L59.5,-10.5 L60.2,-9.7 L60.9,-8.9 L61.6,-8.1 L62.2,-7.4 L62.9,-6.6 L63.6,-5.8 L64.2,-5.0 L64.9,-4.3 L65.6,-3.5 L66.2,-2.7 L66.9,-2.0 L67.6,-1.2 L68.3,-0.4 L68.9,0.4 L69.6,1.1 L70.3,1.9 L70.9,2.7 L71.6,3.5 L72.3,4.2 L73.0,5.0 L73.6,5.8 L74.3,6.5 L75.0,7.3 L75.6,8.1 L76.3,8.9 L77.0,9.6 L77.6,10.4 L78.3,11.2 L79.0,11.9 L79.7,12.7 L80.3,13.5 L81.0,14.3 L81.7,15.0 L82.3,15.8 L83.0,16.6 L83.7,17.4 L84.3,18.1 L85.0,18.9 L85.7,19.7 L86.3,20.4 L87.0,21.2 L87.7,22.0 L88.4,22.8 L89.0,23.5 L89.7,24.3 L90.4,25.1 L91.0,25.9 L91.7,26.6 L92.4,27.4 L93.0,28.2 L93.7,28.9 L94.4,29.7 L95.1,30.5 L95.7,31.3 L96.4,32.0 L97.1,32.8 L97.7,33.6 L98.4,34.4 L99.1,35.1 L99.8,35.9 L100.4,36.7 L101.1,37.4 L101.8,38.2 L102.4,39.0 L103.1,39.8 L103.8,40.5 L104.4,41.3 L105.1,42.1 L105.8,42.8 L106.5,43.6 L107.1,44.4 L107.8,45.2 L108.5,45.9 L109.1,46.7 L109.8,47.5 L110.5,48.3 L111.1,49.0 L111.8,49.8 L112.5,50.6 L113.2,51.3 L113.8,52.1 L114.5,52.9 L115.2,53.7 L115.8,54.4 L116.5,55.2 L117.2,56.0 L117.8,56.8 L118.5,57.5 L119.2,58.3 L119.8,59.1 L120.5,59.8 L121.2,60.6 L121.9,61.4 L122.5,62.2 L123.2,62.9 L123.9,63.7 L124.5,64.5 L125.2,65.3 L125.9,66.0 L126.5,66.8 L127.2,67.6 L127.9,68.3 L128.6,69.1 L129.2,69.9 L129.9,70.7 L130.6,71.4 L131.2,72.2 L131.9,73.0 L132.6,73.7 L133.2,74.5 L133.9,75.3 L134.6,76.1 L135.3,76.8 L135.9,77.6 L136.6,78.4 L137.3,79.2 L137.9,79.9 L138.6,80.7 L139.3,81.5 L139.9,82.2 L140.6,83.0 L141.3,83.8 L142.0,84.6 L142.6,85.3 L143.3,86.1 L144.0,86.9 L144.6,87.7 L145.3,88.4 L146.0,89.2 L146.7,90.0 L147.3,90.7 L148.0,91.5 L148.7,92.3 L149.3,93.1 L150.0,93.8 L150.7,94.6 L151.3,95.4 L152.0,96.2 L152.7,96.9 L153.3,97.7 L154.0,98.5 L154.7,99.2 L155.4,100.0 L156.0,100.8 L156.7,101.6 L157.4,102.3 L158.0,103.1 L158.7,103.9 L159.4,104.6 L160.1,105.4 L160.7,106.2 L161.4,107.0 L162.1,107.7 L162.7,108.5 L163.4,109.3 L164.1,110.1 L164.7,110.8 L165.4,111.6 L166.1,112.4 L166.8,113.1 L167.4,113.9 L168.1,114.7 L168.8,115.5 L169.4,116.2 L170.1,117.0 L170.8,117.8 L171.4,118.6 L172.1,119.3 L172.8,120.1 L173.4,120.9 L174.1,121.6 L174.8,122.4 L175.5,123.2 L176.1,124.0 L176.8,124.7 L177.5,125.5 L178.1,126.3 L178.8,127.1 L179.5,127.8 L180.2,128.6 L180.8,129.4 L181.5,130.1 L182.2,130.9 L182.8,131.7 L183.5,132.5 L184.2,133.2 L184.8,134.0 L185.5,134.8 L186.2,135.5 L186.8,136.3 L187.5,137.1 L188.2,137.9 L188.9,138.6 L189.5,139.4 L190.2,140.2 L190.9,141.0 L191.5,141.7 L192.2,142.5 L192.9,143.3 L193.6,144.0 L194.2,144.8 L194.9,145.6 L195.6,146.4 L196.2,147.1 L196.9,147.9 L197.6,148.7 L198.2,149.5 L198.9,150.2 L199.6,151.0 L200.2,151.8 L200.9,152.5 L201.6,153.3 L202.3,154.1 L202.9,154.9 L203.6,155.6 L204.3,156.4 L204.9,157.2 L205.6,158.0 L206.3,158.7 L206.9,159.5 L207.6,160.3 L208.3,161.0 L209.0,161.8 L209.6,162.6 L210.3,163.4 L211.0,164.1 L211.6,164.9 L212.3,165.7 L213.0,166.4 L213.7,167.2 L214.3,168.0 L215.0,168.8 L215.7,169.5 L216.3,170.3 L217.0,171.1 L217.7,171.9 L218.3,172.6 L219.0,173.4 L219.7,174.2 L220.3,174.9 L221.0,175.7 L221.7,176.5 L222.4,177.3 L223.0,178.0 L223.7,178.8 L224.4,179.6 L225.0,180.4 L225.7,181.1 L226.4,181.9 L227.1,182.7 L227.7,183.4 L228.4,184.2 L229.1,185.0 L229.7,185.8 L230.4,186.5 L231.1,187.3 L231.7,188.1 L232.4,188.9 L233.1,189.6 L233.8,190.4 L234.4,191.2 L235.1,191.9 L235.8,192.7 L236.4,193.5 L237.1,194.3 L237.8,195.0 L238.4,195.8 L239.1,196.6 L239.8,197.3 L240.4,198.1 L241.1,198.9 L241.8,199.7 L242.5,200.4 L243.1,201.2 L243.8,202.0 L244.5,202.8 L245.1,203.5 L245.8,204.3 L246.5,205.1 L247.2,205.8 L247.8,206.6 L248.5,207.4 L249.2,208.2 L249.8,208.9 L250.5,209.7 L251.2,210.5 L251.8,211.3 L252.5,212.0 L253.2,212.8 L253.8,213.6 L254.5,214.3 L255.2,215.1 L255.9,215.9 L256.5,216.7 L257.2,217.4 L257.9,218.2 L258.5,219.0 L259.2,219.8 L259.9,220.5 L260.6,221.3 L261.2,222.1 L261.9,222.8 L262.6,223.6 L263.2,224.4 L263.9,225.2 L264.6,225.9 L265.2,226.7 L265.9,227.5 L266.6,228.2 L267.2,229.0 L267.9,229.8 L268.6,230.6 L269.3,231.3 L269.9,232.1 L270.6,232.9 L271.3,233.7 L271.9,234.4 L272.6,235.2 L273.3,236.0 L273.9,236.7 L274.6,237.5 L275.3,238.3 L276.0,239.1 L276.6,239.8 L277.3,240.6 L278.0,241.4 L278.6,242.2 L279.3,242.9 L280.0,243.7 L280.6,244.5 L281.3,245.2 L282.0,246.0 L282.7,246.8 L283.3,247.6 L284.0,248.3\" clip-path=\"url(#c46457)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><circle cx=\"135.1\" cy=\"76.7\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"141.1\" y=\"67.7\" text-anchor=\"start\" dominant-baseline=\"middle\">A</text><circle cx=\"194.7\" cy=\"145.3\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"200.7\" y=\"136.3\" text-anchor=\"start\" dominant-baseline=\"middle\">B</text></svg>"}, {"kind": "mcq", "text": "Which equation describes the line with slope 4 that passes through (2, 5)?", "opts": ["y = 4x + 13", "y = 4x − 3", "y = 4x + 3", "y = 4x + 5"], "correct": 1, "tag": "", "sol": "5 = 4(2) + b → 5 = 8 + b → b = −3, so y = 4x − 3. (b = 5 uses the y-coordinate as the intercept; b = 13 adds 8 instead of subtracting.)"}, {"kind": "blank", "p": "A line passes through (1, 1) and (4, 10).", "tag": "", "marks": "", "flat": [{"t": "slope m = __B1__", "a": {"B1": "3"}}, {"t": "y-intercept b = __B1__", "a": {"B1": "-2"}}, {"t": "Equation: y = __B1__", "a": {"B1": "3x-2"}, "expr": true}], "sol": "m = (10 − 1) ÷ (4 − 1) = 9 ÷ 3 = 3.\nUse (1, 1): 1 = 3(1) + b → b = −2.\ny = 3x − 2. Check (4, 10): 12 − 2 = 10 ✓"}, {"kind": "mcq", "text": "Which equation describes the line through (−3, 8) and (1, 0)?", "opts": ["y = −{1/2}x + {1/2}", "y = 2x − 2", "y = −2x + 14", "y = −2x + 2"], "correct": 3, "tag": "", "sol": "m = (0 − 8) ÷ (1 − (−3)) = −8 ÷ 4 = −2. Use (1, 0): 0 = −2(1) + b → b = 2. So y = −2x + 2. (−{1/2} is run ÷ rise; b = 14 comes from a sign slip with (−3, 8).)"}, {"kind": "blank", "p": "A line passes through (−6, −1) and (3, 5). Give the slope as a fraction in lowest terms.", "tag": "", "marks": "", "flat": [{"t": "slope m = __B1__", "a": {"B1": "2/3"}, "expr": "fl"}, {"t": "y-intercept b = __B1__", "a": {"B1": "3"}}], "sol": "m = (5 − (−1)) ÷ (3 − (−6)) = 6 ÷ 9 = {2/3}.\nUse (3, 5): 5 = {2/3}(3) + b = 2 + b → b = 3. The line is y = {2/3}x + 3."}, {"kind": "mcq", "text": "Which is an equation of the horizontal line through (−3, 6)?", "opts": ["x = −3", "x = 6", "y = −3", "y = 6"], "correct": 3, "tag": "", "sol": "A horizontal line has slope 0, so every point has the same y-value, 6: y = 0x + 6 = 6. (x = −3 is the vertical line through the point.)"}, {"kind": "blank", "p": "f is a linear function with f(2) = 9 and f(5) = 18.", "tag": "", "marks": "", "flat": [{"t": "slope m = __B1__", "a": {"B1": "3"}}, {"t": "f(x) = __B1__", "a": {"B1": "3x+3"}, "expr": true}, {"t": "f(10) = __B1__", "a": {"B1": "33"}}], "sol": "The points are (2, 9) and (5, 18): m = (18 − 9) ÷ (5 − 2) = 3.\n9 = 3(2) + b → b = 3, so f(x) = 3x + 3.\nf(10) = 3(10) + 3 = 33."}, {"kind": "mcq", "text": "<b>Gym.</b> A gym charges a $40 joining fee plus $25 per month. Which equation gives the total cost C (dollars) after m months?", "opts": ["C = 40m + 25", "C = 65m", "C = 25m + 40", "C = 25m − 40"], "correct": 2, "tag": "", "sol": "The rate, $25 per month, is the slope; the one-time $40 fee is the starting value (the intercept). C = 25m + 40."}, {"kind": "blank", "p": "<b>Phone plan.</b> A phone plan charges a one-time activation fee plus a fixed monthly amount. After 3 months Jada has paid $95 in total; after 7 months she has paid $175.", "tag": "", "marks": "", "flat": [{"t": "Monthly amount = $__B1__", "a": {"B1": "20"}}, {"t": "Activation fee = $__B1__", "a": {"B1": "35"}}, {"t": "Total paid after 12 months = $__B1__", "a": {"B1": "275"}}], "sol": "(175 − 95) ÷ (7 − 3) = 80 ÷ 4 = $20 per month.\n95 = 20(3) + b → b = 35.\nC = 20(12) + 35 = $275."}, {"kind": "mcq", "text": "<b>Error analysis.</b> Ethan writes an equation of the line with slope 3 through (2, 1): “1 = 3(2) + b, so b = 7 and y = 3x + 7.” What is the correct equation?", "opts": ["y = 3x + 7, there is no error", "y = 3x + 1, because b is the y-coordinate", "y = {1/3}x + {1/3}, because the slope is inverted", "y = 3x − 5, because 1 − 6 = −5"], "correct": 3, "tag": "", "sol": "From 1 = 6 + b, subtract 6 from both sides: b = 1 − 6 = −5. Ethan added 6. The equation is y = 3x − 5. Check (2, 1): 6 − 5 = 1 ✓"}, {"kind": "blank", "p": "A line passes through (−2, 11) and (4, −7).", "tag": "", "marks": "", "flat": [{"t": "Equation: y = __B1__", "a": {"B1": "-3x+5"}, "expr": true}, {"t": "x-intercept = __B1__ (the x-value where y = 0; a fraction is fine)", "a": {"B1": "5/3"}, "expr": "fv"}], "sol": "m = (−7 − 11) ÷ (4 − (−2)) = −18 ÷ 6 = −3; 11 = −3(−2) + b → b = 5, so y = −3x + 5.\n0 = −3x + 5 → x = {5/3}."}, {"kind": "mcq", "text": "<b>Reasoning.</b> Which equation describes the line with slope −{3/4} that passes through (8, −1)?", "opts": ["y = −{3/4}x − 1", "y = {4/3}x − {35/3}", "y = −{3/4}x + 5", "y = −{3/4}x − 7"], "correct": 2, "tag": "", "sol": "−1 = −{3/4}(8) + b → −1 = −6 + b → b = 5, so y = −{3/4}x + 5. (b = −7 subtracts 6 instead of adding; b = −1 uses the y-coordinate; {4/3} is the reciprocal slope.) Check: −{3/4}(8) + 5 = −1 ✓"}, {"kind": "blank", "p": "<b>Hiking.</b> A hiker walks downhill at a constant rate. After 2 hours she is at an elevation of 4,600 ft, and after 5 hours she is at 3,700 ft.", "tag": "", "marks": "", "flat": [{"t": "Rate of change = __B1__ ft per hour", "a": {"B1": "-300"}}, {"t": "Starting elevation (t = 0) = __B1__ ft", "a": {"B1": "5200"}}, {"t": "Elevation after t hours: e = __B1__ (use t)", "a": {"B1": "-300t+5200"}, "expr": true}, {"t": "She reaches the trailhead at 2,500 ft after __B1__ hours", "a": {"B1": "9"}}], "sol": "(3700 − 4600) ÷ (5 − 2) = −900 ÷ 3 = −300 ft per hour (she goes down 300 ft each hour).\n4600 = −300(2) + b → b = 4600 + 600 = 5200 ft.\ne = −300t + 5200.\n2500 = −300t + 5200 → −300t = −2700 → t = 9 hours."}]}, {"id": "s2", "label": "4.2 Writing Equations in Point-Slope Form", "sub": "Write an equation of a line in point-slope form, change it to slope-intercept form, and use it to model real-life rates.", "slides": [{"kind": "mcq", "text": "Which equation is in point-slope form for the line with slope 2 through (3, −4)?", "opts": ["y + 4 = 2(x − 3)", "y − 4 = 2(x + 3)", "y − 4 = 2(x − 3)", "y + 3 = 2(x − 4)"], "correct": 0, "tag": "", "sol": "y − y₁ = m(x − x₁) with x₁ = 3, y₁ = −4: y − (−4) = 2(x − 3), that is y + 4 = 2(x − 3)."}, {"kind": "blank", "p": "The line y − 5 = −3(x + 2) is written in point-slope form.", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "-3"}}, {"t": "the point (x₁, y₁) used = __B1__", "a": {"B1": "(-2, 5)"}, "expr": "coord"}], "sol": "The number in front of the bracket is the slope: −3.\nx + 2 = x − (−2) and y − 5, so (x₁, y₁) = (−2, 5)."}, {"kind": "mcq", "text": "Write the equation of the line with slope −4 through (1, −2) in slope-intercept form.", "opts": ["y = −4x − 3", "y = −4x + 2", "y = −4x − 6", "y = −4x + 6"], "correct": 1, "tag": "", "sol": "y + 2 = −4(x − 1) → y + 2 = −4x + 4 → y = −4x + 2. (−6 and +6 come from sign slips; −3 comes from not multiplying out the bracket.)"}, {"kind": "blank", "p": "A line passes through (4, 1) and (6, 7). Use the point (4, 1).", "tag": "", "marks": "", "flat": [{"t": "Point-slope form: y − __B1__ = __B2__(x − __B3__)", "a": {"B1": "1", "B2": "3", "B3": "4"}}, {"t": "Slope-intercept form: y = __B1__", "a": {"B1": "3x-11"}, "expr": true}], "sol": "m = (7 − 1) ÷ (6 − 4) = 3, and (x₁, y₁) = (4, 1): y − 1 = 3(x − 4).\ny − 1 = 3x − 12 → y = 3x − 11."}, {"kind": "mcq", "text": "Which equation describes the line in the graph?", "opts": ["y − 3 = 2(x + 1)", "y + 3 = {1/2}(x + 1)", "y + 3 = 2(x + 1)", "y − 1 = 2(x + 3)"], "correct": 2, "tag": "", "sol": "Slope from (−1, −3) to (2, 3): 6 ÷ 3 = 2. Using (−1, −3): y − (−3) = 2(x − (−1)), so y + 3 = 2(x + 1). The other options have the wrong point signs, the wrong slope, or a point that is not on the line.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 230\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"16.0\" y1=\"214.0\" x2=\"16.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"45.8\" y1=\"214.0\" x2=\"45.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"75.6\" y1=\"214.0\" x2=\"75.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"105.3\" y1=\"214.0\" x2=\"105.3\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"135.1\" y1=\"214.0\" x2=\"135.1\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"164.9\" y1=\"214.0\" x2=\"164.9\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"194.7\" y1=\"214.0\" x2=\"194.7\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"224.4\" y1=\"214.0\" x2=\"224.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"254.2\" y1=\"214.0\" x2=\"254.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"284.0\" y1=\"214.0\" x2=\"284.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"214.0\" x2=\"284.0\" y2=\"214.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"196.8\" x2=\"284.0\" y2=\"196.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"179.7\" x2=\"284.0\" y2=\"179.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"162.5\" x2=\"284.0\" y2=\"162.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"145.3\" x2=\"284.0\" y2=\"145.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"128.2\" x2=\"284.0\" y2=\"128.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"111.0\" x2=\"284.0\" y2=\"111.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"93.8\" x2=\"284.0\" y2=\"93.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"76.7\" x2=\"284.0\" y2=\"76.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"59.5\" x2=\"284.0\" y2=\"59.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"42.3\" x2=\"284.0\" y2=\"42.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"25.2\" x2=\"284.0\" y2=\"25.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"8.0\" x2=\"284.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"111.0\" x2=\"284.0\" y2=\"111.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"135.1\" y1=\"214.0\" x2=\"135.1\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"16.0\" y=\"120.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"75.6\" y=\"120.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"194.7\" y=\"120.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"254.2\" y=\"120.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"131.1\" y=\"214.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−6</text><text class=\"po\" x=\"131.1\" y=\"179.7\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"131.1\" y=\"145.3\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"131.1\" y=\"76.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"131.1\" y=\"42.3\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"131.1\" y=\"8.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"280.0\" y=\"103.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"143.1\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"c23029\"><rect x=\"16.0\" y=\"8.0\" width=\"268.0\" height=\"206.0\"/></clipPath><path d=\"M16.0,265.5 L16.7,264.7 L17.3,264.0 L18.0,263.2 L18.7,262.4 L19.3,261.6 L20.0,260.9 L20.7,260.1 L21.4,259.3 L22.0,258.5 L22.7,257.8 L23.4,257.0 L24.0,256.2 L24.7,255.5 L25.4,254.7 L26.0,253.9 L26.7,253.1 L27.4,252.4 L28.1,251.6 L28.7,250.8 L29.4,250.1 L30.1,249.3 L30.7,248.5 L31.4,247.7 L32.1,247.0 L32.8,246.2 L33.4,245.4 L34.1,244.6 L34.8,243.9 L35.4,243.1 L36.1,242.3 L36.8,241.6 L37.4,240.8 L38.1,240.0 L38.8,239.2 L39.5,238.5 L40.1,237.7 L40.8,236.9 L41.5,236.1 L42.1,235.4 L42.8,234.6 L43.5,233.8 L44.1,233.1 L44.8,232.3 L45.5,231.5 L46.2,230.7 L46.8,230.0 L47.5,229.2 L48.2,228.4 L48.8,227.6 L49.5,226.9 L50.2,226.1 L50.8,225.3 L51.5,224.6 L52.2,223.8 L52.8,223.0 L53.5,222.2 L54.2,221.5 L54.9,220.7 L55.5,219.9 L56.2,219.2 L56.9,218.4 L57.5,217.6 L58.2,216.8 L58.9,216.1 L59.5,215.3 L60.2,214.5 L60.9,213.7 L61.6,213.0 L62.2,212.2 L62.9,211.4 L63.6,210.7 L64.2,209.9 L64.9,209.1 L65.6,208.3 L66.2,207.6 L66.9,206.8 L67.6,206.0 L68.3,205.2 L68.9,204.5 L69.6,203.7 L70.3,202.9 L70.9,202.2 L71.6,201.4 L72.3,200.6 L73.0,199.8 L73.6,199.1 L74.3,198.3 L75.0,197.5 L75.6,196.7 L76.3,196.0 L77.0,195.2 L77.6,194.4 L78.3,193.7 L79.0,192.9 L79.7,192.1 L80.3,191.3 L81.0,190.6 L81.7,189.8 L82.3,189.0 L83.0,188.2 L83.7,187.5 L84.3,186.7 L85.0,185.9 L85.7,185.2 L86.3,184.4 L87.0,183.6 L87.7,182.8 L88.4,182.1 L89.0,181.3 L89.7,180.5 L90.4,179.8 L91.0,179.0 L91.7,178.2 L92.4,177.4 L93.0,176.7 L93.7,175.9 L94.4,175.1 L95.1,174.3 L95.7,173.6 L96.4,172.8 L97.1,172.0 L97.7,171.3 L98.4,170.5 L99.1,169.7 L99.8,168.9 L100.4,168.2 L101.1,167.4 L101.8,166.6 L102.4,165.8 L103.1,165.1 L103.8,164.3 L104.4,163.5 L105.1,162.8 L105.8,162.0 L106.5,161.2 L107.1,160.4 L107.8,159.7 L108.5,158.9 L109.1,158.1 L109.8,157.3 L110.5,156.6 L111.1,155.8 L111.8,155.0 L112.5,154.3 L113.2,153.5 L113.8,152.7 L114.5,151.9 L115.2,151.2 L115.8,150.4 L116.5,149.6 L117.2,148.9 L117.8,148.1 L118.5,147.3 L119.2,146.5 L119.8,145.8 L120.5,145.0 L121.2,144.2 L121.9,143.4 L122.5,142.7 L123.2,141.9 L123.9,141.1 L124.5,140.4 L125.2,139.6 L125.9,138.8 L126.5,138.0 L127.2,137.3 L127.9,136.5 L128.6,135.7 L129.2,134.9 L129.9,134.2 L130.6,133.4 L131.2,132.6 L131.9,131.9 L132.6,131.1 L133.2,130.3 L133.9,129.5 L134.6,128.8 L135.3,128.0 L135.9,127.2 L136.6,126.5 L137.3,125.7 L137.9,124.9 L138.6,124.1 L139.3,123.4 L139.9,122.6 L140.6,121.8 L141.3,121.0 L142.0,120.3 L142.6,119.5 L143.3,118.7 L144.0,118.0 L144.6,117.2 L145.3,116.4 L146.0,115.6 L146.7,114.9 L147.3,114.1 L148.0,113.3 L148.7,112.5 L149.3,111.8 L150.0,111.0 L150.7,110.2 L151.3,109.5 L152.0,108.7 L152.7,107.9 L153.3,107.1 L154.0,106.4 L154.7,105.6 L155.4,104.8 L156.0,104.0 L156.7,103.3 L157.4,102.5 L158.0,101.7 L158.7,101.0 L159.4,100.2 L160.1,99.4 L160.7,98.6 L161.4,97.9 L162.1,97.1 L162.7,96.3 L163.4,95.5 L164.1,94.8 L164.7,94.0 L165.4,93.2 L166.1,92.5 L166.8,91.7 L167.4,90.9 L168.1,90.1 L168.8,89.4 L169.4,88.6 L170.1,87.8 L170.8,87.1 L171.4,86.3 L172.1,85.5 L172.8,84.7 L173.4,84.0 L174.1,83.2 L174.8,82.4 L175.5,81.6 L176.1,80.9 L176.8,80.1 L177.5,79.3 L178.1,78.6 L178.8,77.8 L179.5,77.0 L180.2,76.2 L180.8,75.5 L181.5,74.7 L182.2,73.9 L182.8,73.1 L183.5,72.4 L184.2,71.6 L184.8,70.8 L185.5,70.1 L186.2,69.3 L186.8,68.5 L187.5,67.7 L188.2,67.0 L188.9,66.2 L189.5,65.4 L190.2,64.7 L190.9,63.9 L191.5,63.1 L192.2,62.3 L192.9,61.6 L193.6,60.8 L194.2,60.0 L194.9,59.2 L195.6,58.5 L196.2,57.7 L196.9,56.9 L197.6,56.2 L198.2,55.4 L198.9,54.6 L199.6,53.8 L200.2,53.1 L200.9,52.3 L201.6,51.5 L202.3,50.7 L202.9,50.0 L203.6,49.2 L204.3,48.4 L204.9,47.7 L205.6,46.9 L206.3,46.1 L206.9,45.3 L207.6,44.6 L208.3,43.8 L209.0,43.0 L209.6,42.2 L210.3,41.5 L211.0,40.7 L211.6,39.9 L212.3,39.2 L213.0,38.4 L213.7,37.6 L214.3,36.8 L215.0,36.1 L215.7,35.3 L216.3,34.5 L217.0,33.8 L217.7,33.0 L218.3,32.2 L219.0,31.4 L219.7,30.7 L220.3,29.9 L221.0,29.1 L221.7,28.3 L222.4,27.6 L223.0,26.8 L223.7,26.0 L224.4,25.3 L225.0,24.5 L225.7,23.7 L226.4,22.9 L227.1,22.2 L227.7,21.4 L228.4,20.6 L229.1,19.8 L229.7,19.1 L230.4,18.3 L231.1,17.5 L231.7,16.8 L232.4,16.0 L233.1,15.2 L233.8,14.4 L234.4,13.7 L235.1,12.9 L235.8,12.1 L236.4,11.3 L237.1,10.6 L237.8,9.8 L238.4,9.0 L239.1,8.3 L239.8,7.5 L240.4,6.7 L241.1,5.9 L241.8,5.2 L242.5,4.4 L243.1,3.6 L243.8,2.8 L244.5,2.1 L245.1,1.3 L245.8,0.5 L246.5,-0.2 L247.2,-1.0 L247.8,-1.8 L248.5,-2.6 L249.2,-3.3 L249.8,-4.1 L250.5,-4.9 L251.2,-5.6 L251.8,-6.4 L252.5,-7.2 L253.2,-8.0 L253.8,-8.7 L254.5,-9.5 L255.2,-10.3 L255.9,-11.1 L256.5,-11.8 L257.2,-12.6 L257.9,-13.4 L258.5,-14.1 L259.2,-14.9 L259.9,-15.7 L260.6,-16.5 L261.2,-17.2 L261.9,-18.0 L262.6,-18.8 L263.2,-19.6 L263.9,-20.3 L264.6,-21.1 L265.2,-21.9 L265.9,-22.6 L266.6,-23.4 L267.2,-24.2 L267.9,-25.0 L268.6,-25.7 L269.3,-26.5 L269.9,-27.3 L270.6,-28.1 L271.3,-28.8 L271.9,-29.6 L272.6,-30.4 L273.3,-31.1 L273.9,-31.9 L274.6,-32.7 L275.3,-33.5 L276.0,-34.2 L276.6,-35.0 L277.3,-35.8 L278.0,-36.5 L278.6,-37.3 L279.3,-38.1 L280.0,-38.9 L280.6,-39.6 L281.3,-40.4 L282.0,-41.2 L282.7,-42.0 L283.3,-42.7 L284.0,-43.5\" clip-path=\"url(#c23029)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.2\"/><circle cx=\"105.3\" cy=\"162.5\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"111.3\" y=\"153.5\" text-anchor=\"start\" dominant-baseline=\"middle\">(−1, −3)</text><circle cx=\"194.7\" cy=\"59.5\" r=\"3.4\" style=\"fill:var(--ink)\"/><text class=\"lb\" x=\"200.7\" y=\"50.5\" text-anchor=\"start\" dominant-baseline=\"middle\">(2, 3)</text></svg>"}, {"kind": "blank", "p": "f is a linear function with f(−2) = 10 and f(3) = −5.", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "-3"}}, {"t": "f(x) = __B1__", "a": {"B1": "-3x+4"}, "expr": true}, {"t": "f(6) = __B1__", "a": {"B1": "-14"}}], "sol": "m = (−5 − 10) ÷ (3 − (−2)) = −15 ÷ 5 = −3.\ny − 10 = −3(x + 2) → y = −3x − 6 + 10 = −3x + 4.\nf(6) = −18 + 4 = −14."}, {"kind": "mcq", "text": "Which equation models the table? x: 1, 3, 5, 7; y: 9, 15, 21, 27", "opts": ["y = 2x + 7", "y = 6x + 3", "y = 3x + 9", "y = 3x + 6"], "correct": 3, "tag": "", "sol": "Each increase of 2 in x adds 6 to y, so m = 6 ÷ 2 = 3. y − 9 = 3(x − 1) → y = 3x + 6. Check (7, 27): 21 + 6 = 27 ✓ (y = 2x + 7 fits only the first point)."}, {"kind": "blank", "p": "<b>Rideshare.</b> A rideshare charges a fixed booking fee plus $2.50 per mile. A 6-mile ride costs $19.", "tag": "", "marks": "", "flat": [{"t": "Cost C for a ride of d miles: C = __B1__ (use d)", "a": {"B1": "2.5d+4"}, "expr": true}, {"t": "Cost of a 10-mile ride = $__B1__", "a": {"B1": "29"}}], "sol": "C − 19 = 2.5(d − 6) → C = 2.5d − 15 + 19 = 2.5d + 4.\nC = 2.5(10) + 4 = $29."}, {"kind": "mcq", "text": "<b>Candle.</b> A candle burns down at a constant rate. After 2 hours it is 11 in. tall and after 6 hours it is 8 in. tall. Which equation gives its height h (in.) after t hours?", "opts": ["h = 0.75t + 9.5", "h = −0.75t + 11", "h = −1.33t + 13.67", "h = −0.75t + 12.5"], "correct": 3, "tag": "", "sol": "Rate = (8 − 11) ÷ (6 − 2) = −3 ÷ 4 = −0.75 in. per hour. h − 11 = −0.75(t − 2) → h = −0.75t + 1.5 + 11 = −0.75t + 12.5."}, {"kind": "blank", "p": "A line has slope {2/3} and passes through (−3, 2).", "tag": "", "marks": "", "flat": [{"t": "Point-slope form: y − __B1__ = {2/3}(x + __B2__)", "a": {"B1": "2", "B2": "3"}}, {"t": "y-intercept b = __B1__", "a": {"B1": "4"}}], "sol": "y₁ = 2 and x₁ = −3, so x − (−3) = x + 3: y − 2 = {2/3}(x + 3).\ny − 2 = {2/3}x + 2 → y = {2/3}x + 4, so b = 4."}, {"kind": "mcq", "text": "<b>Error analysis.</b> Nia writes an equation of the line with slope 4 through (−5, 3) as y − 3 = 4(x − 5). What should it be?", "opts": ["y + 3 = 4(x − 5)", "It is correct as written", "y − 3 = 4(x + 5)", "y − 3 = −4(x − 5)"], "correct": 2, "tag": "", "sol": "x₁ = −5, so x − x₁ = x − (−5) = x + 5. The correct equation is y − 3 = 4(x + 5)."}, {"kind": "blank", "p": "<b>Reasoning.</b> Do the points (2, 7), (5, 16) and (−1, −2) lie on one line?", "tag": "", "marks": "", "flat": [{"t": "Slope of the line through (2, 7) and (5, 16) = __B1__", "a": {"B1": "3"}}, {"t": "On that line, y at x = −1 is __B1__", "a": {"B1": "-2"}}, {"t": "So (−1, −2) is on the line: __B1__ (yes / no)", "a": {"B1": "yes"}, "expr": "words"}], "sol": "(16 − 7) ÷ (5 − 2) = 9 ÷ 3 = 3.\ny − 7 = 3(x − 2) → y = 3x + 1; at x = −1: y = −3 + 1 = −2.\nThe line gives exactly −2, so all three points are on the line y = 3x + 1: yes."}, {"kind": "mcq", "text": "A line passes through (1, 4) and (3, 10). Which equation does <b>not</b> describe this line?", "opts": ["y − 4 = 3(x − 1)", "y = 3x + 1", "y − 10 = 3(x − 1)", "y − 10 = 3(x − 3)"], "correct": 2, "tag": "", "sol": "m = (10 − 4) ÷ (3 − 1) = 3. Point-slope form must pair a point's x- and y-coordinates: y − 4 = 3(x − 1) and y − 10 = 3(x − 3) both simplify to y = 3x + 1. y − 10 = 3(x − 1) mixes the y of one point with the x of the other; it gives y = 3x + 7."}, {"kind": "blank", "p": "<b>Tree growth.</b> A young oak grows 1.5 ft each year. Four years after it was planted it is 9 ft tall. Let x be the years since planting and y the height in feet.", "tag": "", "marks": "", "flat": [{"t": "Point-slope form: y − __B1__ = __B2__(x − __B3__)", "a": {"B1": "9", "B2": "1.5", "B3": "4"}}, {"t": "Slope-intercept form: y = __B1__", "a": {"B1": "1.5x+3"}, "expr": true}, {"t": "Height when it was planted = __B1__ ft", "a": {"B1": "3"}}], "sol": "The rate 1.5 is the slope and (4, 9) is a point: y − 9 = 1.5(x − 4).\ny − 9 = 1.5x − 6 → y = 1.5x + 3.\nAt x = 0, y = 3 ft (the y-intercept)."}]}, {"id": "s3", "label": "4.3 Parallel and Perpendicular Lines", "sub": "Writing Equations of Parallel and Perpendicular Lines: identify parallel and perpendicular lines from their slopes and write equations of lines parallel or perpendicular to a given line.", "slides": [{"kind": "mcq", "text": "What is the slope of a line parallel to y = 5x − 2?", "opts": ["−{1/5}", "5", "−5", "{1/5}"], "correct": 1, "tag": "", "sol": "Parallel lines have equal slopes: 5."}, {"kind": "blank", "p": "Find the slope of a line perpendicular to each line. Use fractions where needed.", "tag": "", "marks": "", "flat": [{"t": "a) y = −{3/4}x + 1: __B1__", "a": {"B1": "4/3"}, "expr": "fv"}, {"t": "b) y = 6x: __B1__", "a": {"B1": "-1/6"}, "expr": "fv"}], "sol": "The negative reciprocal of −{3/4} is {4/3}; check −{3/4} × {4/3} = −1.\nThe negative reciprocal of 6 is −{1/6}."}, {"kind": "mcq", "text": "Which pair of lines is parallel?", "opts": ["y = 2x + 1 and y = 2x − 7", "y = 2x + 1 and y = −2x + 1", "y = x + 2 and y = 2x + 1", "y = 3x + 4 and y = −{1/3}x + 4"], "correct": 0, "tag": "", "sol": "Parallel lines have the same slope and different y-intercepts: 2 and 2. (3 and −{1/3} are perpendicular slopes.)"}, {"kind": "blank", "p": "Write an equation of the line parallel to y = −3x + 8 that passes through (2, 1).", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "-3"}}, {"t": "Equation: y = __B1__", "a": {"B1": "-3x+7"}, "expr": true}], "sol": "A parallel line has the same slope, −3.\n1 = −3(2) + b → b = 7, so y = −3x + 7."}, {"kind": "mcq", "text": "How are the lines 2x + y = 4 and x − 2y = 6 related?", "opts": ["perpendicular", "parallel", "they are the same line", "neither"], "correct": 0, "tag": "", "sol": "2x + y = 4 → y = −2x + 4 (slope −2). x − 2y = 6 → y = {1/2}x − 3 (slope {1/2}). −2 × {1/2} = −1, so they are perpendicular."}, {"kind": "blank", "p": "Write an equation of the line perpendicular to y = {1/2}x − 3 that passes through (4, −1).", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "-2"}}, {"t": "Equation: y = __B1__", "a": {"B1": "-2x+7"}, "expr": true}], "sol": "The negative reciprocal of {1/2} is −2.\n−1 = −2(4) + b → b = 7, so y = −2x + 7."}, {"kind": "mcq", "text": "Which line passes through (0, 3) and is parallel to 4x − 2y = 10?", "opts": ["y = −2x + 3", "y = 2x + 3", "y = 4x + 3", "y = −{1/2}x + 3"], "correct": 1, "tag": "", "sol": "4x − 2y = 10 → −2y = −4x + 10 → y = 2x − 5, slope 2. Through (0, 3): b = 3, so y = 2x + 3."}, {"kind": "blank", "p": "Classify each pair of lines as parallel, perpendicular or neither.", "tag": "", "marks": "", "flat": [{"t": "a) y = 4x − 1 and y − 3 = 4(x + 2): __B1__", "a": {"B1": "parallel"}, "expr": "words"}, {"t": "b) y = −{2/5}x + 1 and 5x − 2y = 8: __B1__", "a": {"B1": "perpendicular"}, "expr": "words"}, {"t": "c) y = 3x + 2 and y = −3x + 2: __B1__", "a": {"B1": "neither"}, "expr": "words"}], "sol": "Both slopes are 4; the second line is y = 4x + 11, a different intercept, so parallel.\n5x − 2y = 8 → y = {5/2}x − 4; −{2/5} × {5/2} = −1, so perpendicular.\n3 × (−3) = −9, not −1, and 3 ≠ −3: neither."}, {"kind": "mcq", "text": "<b>City map.</b> On a city grid, Main Street passes through (−2, 1) and (4, 4). Oak Avenue will be perpendicular to Main Street and pass through (2, 3). Which equation describes Oak Avenue?", "opts": ["y = {1/2}x + 2", "y = 2x − 1", "y = −2x + 7", "y = −{1/2}x + 4"], "correct": 2, "tag": "", "sol": "Main Street slope: (4 − 1) ÷ (4 − (−2)) = 3 ÷ 6 = {1/2}. Perpendicular slope −2. 3 = −2(2) + b → b = 7: y = −2x + 7. (All four lines pass through (2, 3); only one has slope −2.)"}, {"kind": "blank", "p": "<b>Geometry.</b> Quadrilateral ABCD has vertices A(0, 0), B(4, 2), C(3, 4) and D(−1, 2).", "tag": "", "marks": "", "flat": [{"t": "slope of AB = __B1__", "a": {"B1": "1/2"}, "expr": "fv"}, {"t": "slope of BC = __B1__", "a": {"B1": "-2"}}, {"t": "AB ∥ CD, BC ∥ DA and AB ⊥ BC, so ABCD is a __B1__ (square / rectangle / trapezoid)", "a": {"B1": "rectangle"}, "expr": "words"}], "sol": "(2 − 0) ÷ (4 − 0) = {1/2}.\n(4 − 2) ÷ (3 − 4) = −2. Also CD = (2 − 4) ÷ (−1 − 3) = {1/2} and DA = (0 − 2) ÷ (0 − (−1)) = −2.\nOpposite sides are parallel and {1/2} × (−2) = −1 gives right angles, so ABCD is a rectangle. AB is longer than BC (AB² = 20, BC² = 5), so it is not a square."}, {"kind": "mcq", "text": "<b>Error analysis.</b> Omar says y = 3x − 1 and y = −3x + 5 are perpendicular “because their slopes are opposites”. Which reply is correct?", "opts": ["Correct: opposite slopes give perpendicular lines", "Not perpendicular: 3 × (−3) = −9, not −1", "Not perpendicular: the lines are parallel", "Correct: any two crossing lines are perpendicular"], "correct": 1, "tag": "", "sol": "Perpendicular slopes multiply to −1. 3 × (−3) = −9, so the lines cross but not at a right angle. The negative reciprocal of 3 is −{1/3}."}, {"kind": "blank", "p": "<b>Reasoning.</b> Find the missing coefficients.", "tag": "", "marks": "", "flat": [{"t": "y = kx + 2 is perpendicular to 3x + 4y = 12: k = __B1__", "a": {"B1": "4/3"}, "expr": "fv"}, {"t": "ax + 2y = 5 is parallel to y = −3x + 1: a = __B1__", "a": {"B1": "6"}}], "sol": "3x + 4y = 12 → y = −{3/4}x + 3. The perpendicular slope is k = {4/3}.\nax + 2y = 5 → y = −{a/2}x + {5/2}. Parallel: −a ÷ 2 = −3, so a = 6."}, {"kind": "mcq", "text": "<b>Park paths.</b> On a park map (units in metres) a straight path runs along y = −{1/2}x + 6. A new path will start at a drinking fountain at (4, 1) and meet the old path at a right angle. Which equation describes the new path?", "opts": ["y = −{1/2}x + 3", "y = {1/2}x − 1", "y = −2x + 9", "y = 2x − 7"], "correct": 3, "tag": "", "sol": "The perpendicular slope is the negative reciprocal of −{1/2}, which is 2. 1 = 2(4) + b → b = −7, so y = 2x − 7. (−{1/2} gives a parallel path; −2 only flips the fraction; {1/2} only changes the sign.)"}, {"kind": "blank", "p": "<b>Park paths, continued.</b> The new path y = 2x − 7 meets the old path y = −{1/2}x + 6. Find where they meet by setting the right sides equal.", "tag": "", "marks": "", "flat": [{"t": "x-coordinate of the meeting point = __B1__", "a": {"B1": "5.2"}}, {"t": "y-coordinate of the meeting point = __B1__", "a": {"B1": "3.4"}}, {"t": "Product of the slopes of the two paths = __B1__", "a": {"B1": "-1"}}], "sol": "2x − 7 = −{1/2}x + 6 → 2.5x = 13 → x = 5.2.\ny = 2(5.2) − 7 = 3.4 (check: −{1/2}(5.2) + 6 = 3.4 ✓). On Desmos the two lines cross at (5.2, 3.4).\n2 × (−{1/2}) = −1, which confirms the paths are perpendicular.", "tools": ["desmos"], "desmos": ["y=-0.5x+6", "y=2x-7", "(4,1)"]}]}, {"id": "s4", "label": "4.4 Scatter Plots and Lines of Fit", "sub": "Describe the correlation shown in a scatter plot, write an equation of a line of fit and use it to make predictions.", "slides": [{"kind": "mcq", "text": "What type of correlation does the scatter plot show?", "opts": ["a perfect negative correlation", "negative correlation", "no correlation", "positive correlation"], "correct": 3, "tag": "", "sol": "As x increases, y tends to increase, so the correlation is positive.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 200 160\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"51.1\" y1=\"130.0\" x2=\"51.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"51.1\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"68.2\" y1=\"130.0\" x2=\"68.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"68.2\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"85.3\" y1=\"130.0\" x2=\"85.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"85.3\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"102.4\" y1=\"130.0\" x2=\"102.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"102.4\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"119.6\" y1=\"130.0\" x2=\"119.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"119.6\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"136.7\" y1=\"130.0\" x2=\"136.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"136.7\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"153.8\" y1=\"130.0\" x2=\"153.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"153.8\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"170.9\" y1=\"130.0\" x2=\"170.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"170.9\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"188.0\" y1=\"130.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"188.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"130.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"106.0\" x2=\"188.0\" y2=\"106.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"106.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"82.0\" x2=\"188.0\" y2=\"82.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"82.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line x1=\"34.0\" y1=\"58.0\" x2=\"188.0\" y2=\"58.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"58.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line x1=\"34.0\" y1=\"34.0\" x2=\"188.0\" y2=\"34.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"34.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line x1=\"34.0\" y1=\"10.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"188.0\" y=\"153.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><circle cx=\"51.1\" cy=\"94.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"68.2\" cy=\"82.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"85.3\" cy=\"82.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"102.4\" cy=\"58.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"119.6\" cy=\"58.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"136.7\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"153.8\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"170.9\" cy=\"22.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg>"}, {"kind": "blank", "p": "<b>Hot cocoa.</b> A café records the outdoor temperature and the cups of hot cocoa sold. (°F, cups): (40, 52), (45, 47), (50, 41), (55, 38), (60, 33), (70, 24), (75, 20)", "tag": "", "marks": "", "flat": [{"t": "The scatter plot shows a __B1__ correlation (positive / negative / no)", "a": {"B1": "negative"}, "expr": "words"}, {"t": "Cups sold on the 55 °F day = __B1__", "a": {"B1": "38"}}], "sol": "As the temperature rises the number of cups tends to fall: a negative correlation.\nThe data pair (55, 38) gives 38 cups.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 320 220\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"190.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">35</text><line x1=\"64.4\" y1=\"190.0\" x2=\"64.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"64.4\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">40</text><line x1=\"94.9\" y1=\"190.0\" x2=\"94.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"94.9\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">45</text><line x1=\"125.3\" y1=\"190.0\" x2=\"125.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"125.3\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">50</text><line x1=\"155.8\" y1=\"190.0\" x2=\"155.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"155.8\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">55</text><line x1=\"186.2\" y1=\"190.0\" x2=\"186.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"186.2\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">60</text><line x1=\"216.7\" y1=\"190.0\" x2=\"216.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"216.7\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">65</text><line x1=\"247.1\" y1=\"190.0\" x2=\"247.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"247.1\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">70</text><line x1=\"277.6\" y1=\"190.0\" x2=\"277.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"277.6\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">75</text><line x1=\"308.0\" y1=\"190.0\" x2=\"308.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"308.0\" y=\"201.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">80</text><line x1=\"34.0\" y1=\"190.0\" x2=\"308.0\" y2=\"190.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"190.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"160.0\" x2=\"308.0\" y2=\"160.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"160.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"130.0\" x2=\"308.0\" y2=\"130.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"130.0\" text-anchor=\"end\" dominant-baseline=\"middle\">20</text><line x1=\"34.0\" y1=\"100.0\" x2=\"308.0\" y2=\"100.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"100.0\" text-anchor=\"end\" dominant-baseline=\"middle\">30</text><line x1=\"34.0\" y1=\"70.0\" x2=\"308.0\" y2=\"70.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"70.0\" text-anchor=\"end\" dominant-baseline=\"middle\">40</text><line x1=\"34.0\" y1=\"40.0\" x2=\"308.0\" y2=\"40.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"40.0\" text-anchor=\"end\" dominant-baseline=\"middle\">50</text><line x1=\"34.0\" y1=\"10.0\" x2=\"308.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">60</text><line x1=\"34.0\" y1=\"190.0\" x2=\"308.0\" y2=\"190.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"190.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"308.0\" y=\"213.0\" text-anchor=\"end\" dominant-baseline=\"middle\">temperature (°F)</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">cups sold</text><circle cx=\"64.4\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"94.9\" cy=\"49.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"125.3\" cy=\"67.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"155.8\" cy=\"76.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"186.2\" cy=\"91.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"247.1\" cy=\"118.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"277.6\" cy=\"130.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg>"}, {"kind": "mcq", "text": "Which pair of variables is most likely to have a <b>negative</b> correlation?", "opts": ["a person's height and shoe size", "a student's shoe size and math test score", "the age of a car and its resale value", "hours worked and money earned"], "correct": 2, "tag": "", "sol": "Older cars tend to be worth less: as age increases, value decreases. Height and shoe size, and hours and pay, are positive; shoe size and test score have no correlation."}, {"kind": "blank", "p": "A line of fit passes through (2, 30) and (8, 60).", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "5"}}, {"t": "y-intercept = __B1__", "a": {"B1": "20"}}, {"t": "Predicted y when x = 6: __B1__", "a": {"B1": "50"}}], "sol": "(60 − 30) ÷ (8 − 2) = 30 ÷ 6 = 5.\n30 = 5(2) + b → b = 20, so y = 5x + 20.\ny = 5(6) + 20 = 50."}, {"kind": "mcq", "text": "A line of fit for the height y (inches) of a tomato plant after x weeks is y = 0.8x + 3. What does the slope mean?", "opts": ["The plant grows about 3 in. per week", "The plant grows about 0.8 in. per week", "After 3 weeks the plant is 0.8 in. tall", "The plant was about 0.8 in. tall at the start"], "correct": 1, "tag": "", "sol": "The slope is the rate of change of height with time: about 0.8 in. per week. The y-intercept 3 means it was about 3 in. tall at week 0."}, {"kind": "blank", "p": "<b>Store sales.</b> The scatter plot shows a store's yearly sales. A line of fit passes through (0, 42) and (5, 66).", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__ (thousand dollars per year)", "a": {"B1": "4.8"}}, {"t": "Predicted sales in 2025 (x = 7) = __B1__ thousand dollars", "a": {"B1": "75.6"}}], "sol": "(66 − 42) ÷ (5 − 0) = 24 ÷ 5 = 4.8, and b = 42, so y = 4.8x + 42.\ny = 4.8(7) + 42 = 33.6 + 42 = 75.6, about $75,600.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 210\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"180.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"70.3\" y1=\"180.0\" x2=\"70.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"70.3\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"106.6\" y1=\"180.0\" x2=\"106.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"106.6\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"142.9\" y1=\"180.0\" x2=\"142.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"142.9\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"179.1\" y1=\"180.0\" x2=\"179.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"179.1\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"215.4\" y1=\"180.0\" x2=\"215.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"215.4\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"251.7\" y1=\"180.0\" x2=\"251.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"251.7\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"288.0\" y1=\"180.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"288.0\" y=\"191.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"34.0\" y1=\"180.0\" x2=\"288.0\" y2=\"180.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"180.0\" text-anchor=\"end\" dominant-baseline=\"middle\">30</text><line x1=\"34.0\" y1=\"146.0\" x2=\"288.0\" y2=\"146.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"146.0\" text-anchor=\"end\" dominant-baseline=\"middle\">40</text><line x1=\"34.0\" y1=\"112.0\" x2=\"288.0\" y2=\"112.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"112.0\" text-anchor=\"end\" dominant-baseline=\"middle\">50</text><line x1=\"34.0\" y1=\"78.0\" x2=\"288.0\" y2=\"78.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"78.0\" text-anchor=\"end\" dominant-baseline=\"middle\">60</text><line x1=\"34.0\" y1=\"44.0\" x2=\"288.0\" y2=\"44.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"44.0\" text-anchor=\"end\" dominant-baseline=\"middle\">70</text><line x1=\"34.0\" y1=\"10.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">80</text><line x1=\"34.0\" y1=\"180.0\" x2=\"288.0\" y2=\"180.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"180.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"288.0\" y=\"203.0\" text-anchor=\"end\" dominant-baseline=\"middle\">years since 2018</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">sales ($1000s)</text><circle cx=\"34.0\" cy=\"139.2\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"70.3\" cy=\"122.2\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"106.6\" cy=\"108.6\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"142.9\" cy=\"88.2\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"179.1\" cy=\"78.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"215.4\" cy=\"57.6\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg>"}, {"kind": "mcq", "text": "Which is the best description of a good line of fit?", "opts": ["It passes through as many data points as possible, even if the rest are far away", "It always passes through the origin", "It always passes through the first and the last data point", "It lies close to the points, with about as many points above it as below it"], "correct": 3, "tag": "", "sol": "A line of fit follows the trend of the whole data set, balancing points above and below. It need not pass through any particular data point."}, {"kind": "blank", "p": "A line of fit for x = hours of TV watched per day and y = test score is y = −2.5x + 95.", "tag": "", "marks": "", "flat": [{"t": "Predicted score for 4 hours of TV = __B1__", "a": {"B1": "85"}}, {"t": "Hours of TV for a predicted score of 80 = __B1__", "a": {"B1": "6"}}], "sol": "y = −2.5(4) + 95 = −10 + 95 = 85.\n80 = −2.5x + 95 → −2.5x = −15 → x = 6."}, {"kind": "mcq", "text": "What type of correlation does the scatter plot show?", "opts": ["a strong positive correlation", "positive correlation", "negative correlation", "no correlation"], "correct": 3, "tag": "", "sol": "The points go up and down with no clear trend as x increases, so there is no correlation.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 200 160\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"51.1\" y1=\"130.0\" x2=\"51.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"51.1\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"68.2\" y1=\"130.0\" x2=\"68.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"68.2\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"85.3\" y1=\"130.0\" x2=\"85.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"85.3\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"102.4\" y1=\"130.0\" x2=\"102.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"102.4\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"119.6\" y1=\"130.0\" x2=\"119.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"119.6\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"136.7\" y1=\"130.0\" x2=\"136.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"136.7\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"153.8\" y1=\"130.0\" x2=\"153.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"153.8\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"170.9\" y1=\"130.0\" x2=\"170.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"170.9\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"188.0\" y1=\"130.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"188.0\" y=\"141.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"130.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"106.0\" x2=\"188.0\" y2=\"106.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"106.0\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"82.0\" x2=\"188.0\" y2=\"82.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"82.0\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line x1=\"34.0\" y1=\"58.0\" x2=\"188.0\" y2=\"58.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"58.0\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line x1=\"34.0\" y1=\"34.0\" x2=\"188.0\" y2=\"34.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"34.0\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line x1=\"34.0\" y1=\"10.0\" x2=\"188.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"130.0\" x2=\"188.0\" y2=\"130.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"130.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"188.0\" y=\"153.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><circle cx=\"51.1\" cy=\"70.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"68.2\" cy=\"22.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"85.3\" cy=\"106.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"102.4\" cy=\"46.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"119.6\" cy=\"94.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"136.7\" cy=\"34.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"153.8\" cy=\"82.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"170.9\" cy=\"58.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg>"}, {"kind": "blank", "p": "<b>Used cars.</b> For a model of used car, a line of fit for x = age (months) and y = price (thousands of dollars) passes through (10, 26) and (30, 20).", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "-0.3"}}, {"t": "y-intercept = __B1__", "a": {"B1": "29"}}, {"t": "Predicted price of a 24-month-old car = __B1__ thousand dollars", "a": {"B1": "21.8"}}], "sol": "(20 − 26) ÷ (30 − 10) = −6 ÷ 20 = −0.3: the price drops about $300 each month.\n26 = −0.3(10) + b → b = 29.\ny = −0.3(24) + 29 = −7.2 + 29 = 21.8, about $21,800."}, {"kind": "mcq", "text": "<b>Error analysis.</b> Lucia chooses the points (1, 5) and (3, 11) on her line of fit and writes “slope = (3 − 1) ÷ (11 − 5) = {1/3}”. What is the correct slope?", "opts": ["{1/3}, there is no error", "6, because 11 − 5 = 6", "2, because 3 − 1 = 2", "3, because slope is change in y ÷ change in x"], "correct": 3, "tag": "", "sol": "Slope = (11 − 5) ÷ (3 − 1) = 6 ÷ 2 = 3. Lucia divided the change in x by the change in y."}, {"kind": "blank", "p": "<b>Reasoning.</b> Data: (1, 8), (2, 11), (3, 13), (4, 17), (5, 19), (6, 22). Kai draws a line of fit through (1, 8) and (6, 22).", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "2.8"}}, {"t": "y-intercept = __B1__", "a": {"B1": "5.2"}}, {"t": "Predicted y at x = 8: __B1__", "a": {"B1": "27.6"}}], "sol": "(22 − 8) ÷ (6 − 1) = 14 ÷ 5 = 2.8.\n8 = 2.8(1) + b → b = 5.2.\ny = 2.8(8) + 5.2 = 22.4 + 5.2 = 27.6."}, {"kind": "mcq", "text": "Which equation is the most reasonable line of fit for the data in the scatter plot?", "opts": ["y = 1.5x + 8", "y = −1.5x + 2.6", "y = 1.5x + 2.6", "y = 3x + 1"], "correct": 2, "tag": "", "sol": "The points rise about 1.5 for each step of 1 in x, and a line through them would meet the y-axis near 2.6. y = −1.5x + 2.6 falls (wrong direction); y = 3x + 1 is far too steep (it gives 19 at x = 6); y = 1.5x + 8 lies above every point.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"170.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"67.4\" y1=\"170.0\" x2=\"67.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"67.4\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"100.9\" y1=\"170.0\" x2=\"100.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"100.9\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"134.3\" y1=\"170.0\" x2=\"134.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"134.3\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"167.7\" y1=\"170.0\" x2=\"167.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"167.7\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"201.1\" y1=\"170.0\" x2=\"201.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"201.1\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"234.6\" y1=\"170.0\" x2=\"234.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"234.6\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"268.0\" y1=\"170.0\" x2=\"268.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"268.0\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"34.0\" y1=\"170.0\" x2=\"268.0\" y2=\"170.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"170.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"147.1\" x2=\"268.0\" y2=\"147.1\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"147.1\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"124.3\" x2=\"268.0\" y2=\"124.3\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"124.3\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><line x1=\"34.0\" y1=\"101.4\" x2=\"268.0\" y2=\"101.4\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"101.4\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><line x1=\"34.0\" y1=\"78.6\" x2=\"268.0\" y2=\"78.6\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"78.6\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><line x1=\"34.0\" y1=\"55.7\" x2=\"268.0\" y2=\"55.7\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"55.7\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><line x1=\"34.0\" y1=\"32.9\" x2=\"268.0\" y2=\"32.9\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"32.9\" text-anchor=\"end\" dominant-baseline=\"middle\">12</text><line x1=\"34.0\" y1=\"10.0\" x2=\"268.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">14</text><line x1=\"34.0\" y1=\"170.0\" x2=\"268.0\" y2=\"170.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"170.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"268.0\" y=\"193.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><circle cx=\"67.4\" cy=\"124.3\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"100.9\" cy=\"101.4\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"134.3\" cy=\"90.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"167.7\" cy=\"67.1\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"201.1\" cy=\"55.7\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"234.6\" cy=\"32.9\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg>"}, {"kind": "blank", "p": "<b>Road trip.</b> Mia records the miles driven x and the gallons of gas left in the tank y on a long drive. Her line of fit passes through (50, 13) and (250, 5).", "tag": "", "marks": "", "flat": [{"t": "The data show a __B1__ correlation (positive / negative / no)", "a": {"B1": "negative"}, "expr": "words"}, {"t": "slope = __B1__ gallons per mile", "a": {"B1": "-0.04"}}, {"t": "y-intercept = __B1__ gallons", "a": {"B1": "15"}}, {"t": "Predicted miles driven when the tank is empty = __B1__", "a": {"B1": "375"}}], "sol": "The more miles she drives, the less gas is left: negative.\n(5 − 13) ÷ (250 − 50) = −8 ÷ 200 = −0.04: she uses about 0.04 gallon per mile.\n13 = −0.04(50) + b → b = 15: a full tank holds about 15 gallons.\n0 = −0.04x + 15 → x = 375 miles."}]}, {"id": "s5", "label": "4.5 Analyzing Lines of Fit", "sub": "Use residuals to judge a line of fit, find the line of best fit and the correlation coefficient with technology, and tell correlation from causation.", "slides": [{"kind": "mcq", "text": "A model predicts y = 15.5 for a data point whose observed value is y = 18. What is the residual?", "opts": ["2.5", "1.16", "−2.5", "33.5"], "correct": 0, "tag": "", "sol": "Residual = observed − predicted = 18 − 15.5 = 2.5. It is positive, so the point lies above the line."}, {"kind": "blank", "p": "The line y = 2x + 1 models the data (1, 4), (2, 4), (3, 8), (4, 8).", "tag": "", "marks": "", "flat": [{"t": "Predicted y-values in order: __B1__", "a": {"B1": "3, 5, 7, 9"}, "expr": "dlist"}, {"t": "Residuals in order: __B1__", "a": {"B1": "1, -1, 1, -1"}, "expr": "dlist"}], "sol": "2(1) + 1 = 3, 2(2) + 1 = 5, 7, 9.\n4 − 3 = 1, 4 − 5 = −1, 8 − 7 = 1, 8 − 9 = −1."}, {"kind": "mcq", "text": "What does this residual plot tell you about the line of fit?", "opts": ["It is not a good fit: the residuals form a U-shaped pattern", "It is a good fit: the residuals add up to about 0", "It is not a good fit: all the residuals are positive", "It is a good fit: the residuals are both positive and negative"], "correct": 0, "tag": "", "sol": "The residuals are positive at both ends and negative in the middle, a clear U-shape. A pattern in the residuals means a line does not model the data well.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 300 200\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"34.0\" y1=\"170.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"34.0\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">0</text><line x1=\"62.2\" y1=\"170.0\" x2=\"62.2\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"62.2\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">1</text><line x1=\"90.4\" y1=\"170.0\" x2=\"90.4\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"90.4\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><line x1=\"118.7\" y1=\"170.0\" x2=\"118.7\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"118.7\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">3</text><line x1=\"146.9\" y1=\"170.0\" x2=\"146.9\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"146.9\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><line x1=\"175.1\" y1=\"170.0\" x2=\"175.1\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"175.1\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">5</text><line x1=\"203.3\" y1=\"170.0\" x2=\"203.3\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"203.3\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">6</text><line x1=\"231.6\" y1=\"170.0\" x2=\"231.6\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"231.6\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">7</text><line x1=\"259.8\" y1=\"170.0\" x2=\"259.8\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"259.8\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">8</text><line x1=\"288.0\" y1=\"170.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"288.0\" y=\"181.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">9</text><line x1=\"34.0\" y1=\"170.0\" x2=\"288.0\" y2=\"170.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"170.0\" text-anchor=\"end\" dominant-baseline=\"middle\">-3</text><line x1=\"34.0\" y1=\"143.3\" x2=\"288.0\" y2=\"143.3\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"143.3\" text-anchor=\"end\" dominant-baseline=\"middle\">-2</text><line x1=\"34.0\" y1=\"116.7\" x2=\"288.0\" y2=\"116.7\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"116.7\" text-anchor=\"end\" dominant-baseline=\"middle\">-1</text><line x1=\"34.0\" y1=\"90.0\" x2=\"288.0\" y2=\"90.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"90.0\" text-anchor=\"end\" dominant-baseline=\"middle\">0</text><line x1=\"34.0\" y1=\"63.3\" x2=\"288.0\" y2=\"63.3\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"63.3\" text-anchor=\"end\" dominant-baseline=\"middle\">1</text><line x1=\"34.0\" y1=\"36.7\" x2=\"288.0\" y2=\"36.7\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"36.7\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><line x1=\"34.0\" y1=\"10.0\" x2=\"288.0\" y2=\"10.0\" style=\"stroke:var(--rule)\"/><text class=\"po\" x=\"29.0\" y=\"10.0\" text-anchor=\"end\" dominant-baseline=\"middle\">3</text><line x1=\"34.0\" y1=\"170.0\" x2=\"288.0\" y2=\"170.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"34.0\" y1=\"170.0\" x2=\"34.0\" y2=\"10.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"288.0\" y=\"193.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"38.0\" y=\"16.0\" text-anchor=\"start\" dominant-baseline=\"middle\">residual</text><line x1=\"34.0\" y1=\"90.0\" x2=\"288.0\" y2=\"90.0\" style=\"stroke:var(--danger);stroke-width:2\"/><circle cx=\"62.2\" cy=\"36.7\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"90.4\" cy=\"68.7\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"118.7\" cy=\"100.7\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"146.9\" cy=\"122.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"175.1\" cy=\"122.0\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"203.3\" cy=\"100.7\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"231.6\" cy=\"68.7\" r=\"3.6\" style=\"fill:var(--accent-text)\"/><circle cx=\"259.8\" cy=\"36.7\" r=\"3.6\" style=\"fill:var(--accent-text)\"/></svg>"}, {"kind": "blank", "p": "Use Desmos to find the line of best fit. Enter the table, then type <b>y₁ ~ mx₁ + b</b>. x: 1, 2, 3, 4, 5, 6; y: 3, 7, 8, 12, 14, 17", "tag": "", "marks": "", "flat": [{"t": "slope m = __B1__ (to 2 decimal places)", "a": {"B1": "2.71"}}, {"t": "y-intercept b = __B1__ (to 2 decimal places)", "a": {"B1": "0.67"}}, {"t": "correlation coefficient r = __B1__ (to 2 decimal places)", "a": {"B1": "0.99"}}], "sol": "Desmos gives m ≈ 2.7143, so m ≈ 2.71.\nb ≈ 0.6667 ≈ 0.67, so y ≈ 2.71x + 0.67.\nr ≈ 0.9927 ≈ 0.99: a strong positive correlation.", "tools": ["desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["1", "2", "3", "4", "5", "6"]}, {"latex": "y_1", "values": ["3", "7", "8", "12", "14", "17"]}]}]}, {"kind": "mcq", "text": "Which correlation coefficient shows the <b>strongest</b> linear relationship?", "opts": ["r = −0.97", "r = 0.42", "r = 0.85", "r = −0.05"], "correct": 0, "tag": "", "sol": "Strength depends on how close |r| is to 1. |−0.97| = 0.97 is the largest. The sign only shows the direction."}, {"kind": "blank", "p": "A line of best fit y = 1.5x + 6 was found from data with x-values from 2 to 10.", "tag": "", "marks": "", "flat": [{"t": "Predicting y at x = 7 is __B1__ (interpolation / extrapolation)", "a": {"B1": "interpolation"}, "expr": "words"}, {"t": "Predicted y at x = 15: __B1__", "a": {"B1": "28.5"}}, {"t": "Predicting y at x = 15 is __B1__ (interpolation / extrapolation)", "a": {"B1": "extrapolation"}, "expr": "words"}], "sol": "7 lies inside the data range 2 to 10: interpolation.\ny = 1.5(15) + 6 = 28.5.\n15 lies outside the data range: extrapolation, which is less reliable."}, {"kind": "mcq", "text": "In a study of towns, the number of fire stations and the number of fires each year have a strong positive correlation. Which conclusion is best?", "opts": ["The data must be wrong, because the variables are unrelated", "A third factor, town size, drives both; stations do not cause fires", "Fires cause fire stations to close, because the correlation is positive", "Fire stations cause fires, because the correlation is strong"], "correct": 1, "tag": "", "sol": "Larger towns have more fires and more fire stations. The correlation comes from town size, not from one variable causing the other."}, {"kind": "blank", "p": "The line y = −x + 10 models the data (2, 9), (4, 5), (6, 4), (8, 2).", "tag": "", "marks": "", "flat": [{"t": "Residuals in order: __B1__", "a": {"B1": "1, -1, 0, 0"}, "expr": "dlist"}, {"t": "Sum of the residuals = __B1__", "a": {"B1": "0"}}], "sol": "Predicted 8, 6, 4, 2. Residuals: 9 − 8 = 1, 5 − 6 = −1, 4 − 4 = 0, 2 − 2 = 0.\n1 − 1 + 0 + 0 = 0."}, {"kind": "mcq", "text": "<b>Phone value.</b> The resale value y (dollars) of a phone model x years after release is shown. Use Desmos regression to estimate r. x: 1, 2, 3, 4, 5, 6; y: 50, 44, 41, 35, 30, 26", "opts": ["r ≈ 0.104", "r ≈ −0.452", "r ≈ −0.997", "r ≈ 0.997"], "correct": 2, "tag": "", "sol": "The values fall steadily and lie very close to a line: Desmos gives y ≈ −4.8x + 54.47 with r ≈ −0.9974 ≈ −0.997, a strong negative correlation.", "tools": ["desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["1", "2", "3", "4", "5", "6"]}, {"latex": "y_1", "values": ["50", "44", "41", "35", "30", "26"]}]}]}, {"kind": "blank", "p": "<b>Lemonade stand.</b> Use Desmos regression (y₁ ~ mx₁ + b). temperature x (°F): 60, 65, 70, 75, 80, 85; cups sold y: 22, 30, 35, 44, 50, 57", "tag": "", "marks": "", "flat": [{"t": "slope m = __B1__ (to 2 decimal places)", "a": {"B1": "1.39"}}, {"t": "y-intercept b = __B1__ (to 2 decimal places)", "a": {"B1": "-61.42"}}, {"t": "Predicted cups sold at 78 °F (nearest whole number) = __B1__", "a": {"B1": "47"}}], "sol": "m ≈ 1.3943 ≈ 1.39 cups per degree.\nb ≈ −61.4190 ≈ −61.42.\nUsing the unrounded values: 1.3943(78) − 61.4190 ≈ 47.3, about 47 cups.", "tools": ["desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["60", "65", "70", "75", "80", "85"]}, {"latex": "y_1", "values": ["22", "30", "35", "44", "50", "57"]}]}]}, {"kind": "mcq", "text": "<b>Error analysis.</b> A model predicts 40 for a data point whose observed value is 43. Ben says the residual is −3. Which reply is correct?", "opts": ["The residual is 1.075, because 43 ÷ 40 = 1.075", "The residual is 3, because residual = observed − predicted", "The residual is 83, because the values are added", "Ben is right, because residual = predicted − observed"], "correct": 1, "tag": "", "sol": "Residual = observed − predicted = 43 − 40 = 3. It is positive because the point is above the line. Ben subtracted in the wrong order."}, {"kind": "blank", "p": "<b>Reasoning.</b> Describe each correlation coefficient.", "tag": "", "marks": "", "flat": [{"t": "r = −0.92 shows a __B1__ correlation (strong / weak)", "a": {"B1": "strong"}, "expr": "words"}, {"t": "r = −0.92 shows a __B1__ correlation (positive / negative)", "a": {"B1": "negative"}, "expr": "words"}, {"t": "r = 0.15 shows a __B1__ correlation (strong / weak)", "a": {"B1": "weak"}, "expr": "words"}], "sol": "|−0.92| is close to 1: strong.\nr is negative: as x increases, y tends to decrease.\n0.15 is close to 0: weak (almost no linear correlation)."}, {"kind": "mcq", "text": "Which pair of variables is most likely to show <b>causation</b>, not just correlation?", "opts": ["ice-cream sales and the number of sunburns at a beach", "the number of TVs per household in a country and its life expectancy", "minutes a pot of water is heated and the water's temperature", "children's shoe sizes and their reading levels"], "correct": 2, "tag": "", "sol": "Heating the water directly raises its temperature, so one variable causes the change in the other. The other pairs are linked through a third factor (hot weather, age, wealth)."}, {"kind": "blank", "p": "<b>Used car value.</b> Use Desmos regression (y₁ ~ mx₁ + b). age x (years): 1, 2, 3, 4, 5, 6; value y (thousands of dollars): 25, 21, 20, 15, 14, 11", "tag": "", "marks": "", "flat": [{"t": "slope m = __B1__ (to 2 decimal places)", "a": {"B1": "-2.74"}}, {"t": "y-intercept b = __B1__ (to 2 decimal places)", "a": {"B1": "27.27"}}, {"t": "correlation coefficient r = __B1__ (to 2 decimal places)", "a": {"B1": "-0.99"}}, {"t": "Predicted value at 7 years = __B1__ thousand dollars (to 1 decimal place)", "a": {"B1": "8.1"}}], "sol": "Desmos gives m ≈ −2.7429 ≈ −2.74: the car loses about $2,740 of value each year.\nb ≈ 27.2667 ≈ 27.27.\nr ≈ −0.9863 ≈ −0.99: a strong negative correlation.\nUsing the unrounded values: −2.7429(7) + 27.2667 ≈ 8.07, about 8.1 thousand dollars (extrapolation, so treat it with care).", "tools": ["desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["1", "2", "3", "4", "5", "6"]}, {"latex": "y_1", "values": ["25", "21", "20", "15", "14", "11"]}]}]}]}, {"id": "s6", "label": "4.6 Arithmetic Sequences", "sub": "Recognise arithmetic sequences, find the common difference and write the nth term as a linear function of n.", "slides": [{"kind": "mcq", "text": "Which sequence is arithmetic?", "opts": ["1, 4, 9, 16, …", "3, 6, 10, 15, …", "2, 4, 8, 16, …", "5, 9, 13, 17, …"], "correct": 3, "tag": "", "sol": "5, 9, 13, 17 has a constant difference of 4. The others have differences 2, 4, 8 / 3, 5, 7 / 3, 4, 5, which are not constant."}, {"kind": "blank", "p": "For the arithmetic sequence 23, 17, 11, 5, …", "tag": "", "marks": "", "flat": [{"t": "common difference d = __B1__", "a": {"B1": "-6"}}, {"t": "the next three terms: __B1__", "a": {"B1": "-1, -7, -13"}, "expr": "dlist"}], "sol": "17 − 23 = −6 (and 11 − 17 = −6, 5 − 11 = −6).\n5 − 6 = −1, −1 − 6 = −7, −7 − 6 = −13."}, {"kind": "mcq", "text": "Which rule gives the nth term of 4, 11, 18, 25, …?", "opts": ["aₙ = 7n + 4", "aₙ = 3n + 7", "aₙ = 4n + 7", "aₙ = 7n − 3"], "correct": 3, "tag": "", "sol": "a₁ = 4 and d = 7: aₙ = 4 + (n − 1)(7) = 7n − 3. Check n = 1: 7 − 3 = 4 ✓ (7n + 4 is the a₁ + nd mistake: it gives 11 for n = 1)."}, {"kind": "blank", "p": "An arithmetic sequence has aₙ = −2 + 5(n − 1).", "tag": "", "marks": "", "flat": [{"t": "first term a₁ = __B1__", "a": {"B1": "-2"}}, {"t": "a₂₀ = __B1__", "a": {"B1": "93"}}, {"t": "Simplified rule: aₙ = __B1__ (use n)", "a": {"B1": "5n-7"}, "expr": true}], "sol": "n = 1: −2 + 5(0) = −2.\n−2 + 5(19) = −2 + 95 = 93.\n−2 + 5n − 5 = 5n − 7."}, {"kind": "mcq", "text": "The graph shows the first four terms of an arithmetic sequence. Which rule describes it?", "opts": ["aₙ = −2n + 8", "aₙ = −2n + 10", "aₙ = 2n + 6", "aₙ = 8n − 2"], "correct": 1, "tag": "", "sol": "The points are (1, 8), (2, 6), (3, 4), (4, 2): a₁ = 8 and d = −2. aₙ = 8 − 2(n − 1) = −2n + 10.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 260 220\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"35.0\" y1=\"204.0\" x2=\"35.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"73.0\" y1=\"204.0\" x2=\"73.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"111.0\" y1=\"204.0\" x2=\"111.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"149.0\" y1=\"204.0\" x2=\"149.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"187.0\" y1=\"204.0\" x2=\"187.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"225.0\" y1=\"204.0\" x2=\"225.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"204.0\" x2=\"244.0\" y2=\"204.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"186.2\" x2=\"244.0\" y2=\"186.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"168.4\" x2=\"244.0\" y2=\"168.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"150.5\" x2=\"244.0\" y2=\"150.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"132.7\" x2=\"244.0\" y2=\"132.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"114.9\" x2=\"244.0\" y2=\"114.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"97.1\" x2=\"244.0\" y2=\"97.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"79.3\" x2=\"244.0\" y2=\"79.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"61.5\" x2=\"244.0\" y2=\"61.5\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"43.6\" x2=\"244.0\" y2=\"43.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"25.8\" x2=\"244.0\" y2=\"25.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"8.0\" x2=\"244.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"186.2\" x2=\"244.0\" y2=\"186.2\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"35.0\" y1=\"204.0\" x2=\"35.0\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"111.0\" y=\"195.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"187.0\" y=\"195.2\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"31.0\" y=\"150.5\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"31.0\" y=\"114.9\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"31.0\" y=\"79.3\" text-anchor=\"end\" dominant-baseline=\"middle\">6</text><text class=\"po\" x=\"31.0\" y=\"43.6\" text-anchor=\"end\" dominant-baseline=\"middle\">8</text><text class=\"po\" x=\"31.0\" y=\"8.0\" text-anchor=\"end\" dominant-baseline=\"middle\">10</text><text class=\"po\" x=\"240.0\" y=\"178.2\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"43.0\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b4g715868\"><rect x=\"16.0\" y=\"8.0\" width=\"228.0\" height=\"196.0\"/></clipPath><circle cx=\"73.0\" cy=\"43.6\" r=\"4\" style=\"fill:var(--accent-text)\"/><circle cx=\"111.0\" cy=\"79.3\" r=\"4\" style=\"fill:var(--accent-text)\"/><circle cx=\"149.0\" cy=\"114.9\" r=\"4\" style=\"fill:var(--accent-text)\"/><circle cx=\"187.0\" cy=\"150.5\" r=\"4\" style=\"fill:var(--accent-text)\"/></svg>"}, {"kind": "blank", "p": "The sequence 5, 9, 13, 17, … is arithmetic.", "tag": "", "marks": "", "flat": [{"t": "aₙ = __B1__ (use n)", "a": {"B1": "4n+1"}, "expr": true}, {"t": "The term equal to 101 is term number n = __B1__", "a": {"B1": "25"}}], "sol": "a₁ = 5, d = 4: aₙ = 5 + 4(n − 1) = 4n + 1.\n4n + 1 = 101 → 4n = 100 → n = 25."}, {"kind": "mcq", "text": "In an arithmetic sequence, a₄ = 20 and a₉ = 45. Which rule describes the sequence?", "opts": ["aₙ = 25n − 80", "aₙ = 20 + 5(n − 1)", "aₙ = 5n", "aₙ = 5n + 5"], "correct": 2, "tag": "", "sol": "From term 4 to term 9 there are 5 steps: 5d = 45 − 20 = 25, so d = 5. a₁ = 20 − 3(5) = 5, so aₙ = 5 + 5(n − 1) = 5n. (20 + 5(n − 1) treats a₄ as the first term.)"}, {"kind": "blank", "p": "<b>Theater.</b> Row 1 of a theater has 18 seats and each row after that has 3 more seats than the row in front of it.", "tag": "", "marks": "", "flat": [{"t": "Seats in row n: aₙ = __B1__ (use n)", "a": {"B1": "3n+15"}, "expr": true}, {"t": "Seats in row 15 = __B1__", "a": {"B1": "60"}}], "sol": "a₁ = 18, d = 3: aₙ = 18 + 3(n − 1) = 3n + 15.\na₁₅ = 3(15) + 15 = 60."}, {"kind": "mcq", "text": "<b>Savings.</b> Liam has $150 and adds $12 at the end of every week. At the end of which week will he first have at least $400?", "opts": ["week 34", "week 22", "week 20", "week 21"], "correct": 3, "tag": "", "sol": "After n weeks he has 150 + 12n. 150 + 12n ≥ 400 → 12n ≥ 250 → n ≥ 20.8…, so week 21 ($402). After week 20 he has only $390. (Week 34 ignores the starting $150.)"}, {"kind": "blank", "p": "The function f(n) = 3n − 8 gives the terms of an arithmetic sequence (n = 1, 2, 3, …).", "tag": "", "marks": "", "flat": [{"t": "first term = __B1__", "a": {"B1": "-5"}}, {"t": "common difference = __B1__", "a": {"B1": "3"}}, {"t": "10th term = __B1__", "a": {"B1": "22"}}], "sol": "f(1) = 3 − 8 = −5.\nThe coefficient of n is the slope, which is the common difference: 3.\nf(10) = 30 − 8 = 22."}, {"kind": "mcq", "text": "<b>Error analysis.</b> For the sequence 7, 4, 1, −2, …, Maya writes “d = 3, so aₙ = 7 + 3(n − 1)”. Which rule is correct?", "opts": ["aₙ = −3n + 4", "aₙ = −3n + 10", "aₙ = 3n + 4", "aₙ = −3n + 7"], "correct": 1, "tag": "", "sol": "The terms decrease, so d = 4 − 7 = −3. aₙ = 7 + (−3)(n − 1) = 7 − 3n + 3 = −3n + 10. Check n = 1: −3 + 10 = 7 ✓"}, {"kind": "blank", "p": "<b>Reasoning.</b> Is 250 a term of the arithmetic sequence 6, 13, 20, 27, …?", "tag": "", "marks": "", "flat": [{"t": "aₙ = __B1__ (use n)", "a": {"B1": "7n-1"}, "expr": true}, {"t": "The largest term less than 250 is __B1__", "a": {"B1": "244"}}, {"t": "Is 250 a term? __B1__ (yes / no)", "a": {"B1": "no"}, "expr": "words"}], "sol": "a₁ = 6, d = 7: aₙ = 6 + 7(n − 1) = 7n − 1.\n7n − 1 = 250 gives n = 35.86…; n = 35 gives 7(35) − 1 = 244 (the next term is 251).\nn must be a whole number, so 250 is not a term: no."}, {"kind": "mcq", "text": "What is the 8th term of the arithmetic sequence −11, −7, −3, 1, …?", "opts": ["13", "17", "−39", "21"], "correct": 1, "tag": "", "sol": "d = −7 − (−11) = 4. a₈ = −11 + (8 − 1)(4) = −11 + 28 = 17. (21 uses a₁ + 8d; 13 uses 6 steps; −39 takes d as −4.)"}, {"kind": "blank", "p": "<b>Stacking cups.</b> One plastic cup is 12 cm tall. Each extra cup added to the stack raises the height by 1.5 cm.", "tag": "", "marks": "", "flat": [{"t": "Height of a stack of n cups: aₙ = __B1__ (use n)", "a": {"B1": "1.5n+10.5"}, "expr": true}, {"t": "Height of a stack of 20 cups = __B1__ cm", "a": {"B1": "40.5"}}, {"t": "The greatest number of cups in a stack that is at most 30 cm tall = __B1__", "a": {"B1": "13"}}], "sol": "a₁ = 12, d = 1.5: aₙ = 12 + 1.5(n − 1) = 1.5n + 10.5.\na₂₀ = 1.5(20) + 10.5 = 30 + 10.5 = 40.5 cm.\n1.5n + 10.5 ≤ 30 → 1.5n ≤ 19.5 → n ≤ 13. A stack of 13 cups is exactly 30 cm; 14 cups would be 31.5 cm."}]}, {"id": "s7", "label": "4.7 Piecewise Functions", "sub": "Evaluate, graph and write piecewise functions, including step functions and absolute value functions.", "slides": [{"kind": "mcq", "text": "f(x) = 3x − 1 if x < 2, and f(x) = −x + 6 if x ≥ 2. What is f(2)?", "opts": ["−2", "6", "5", "4"], "correct": 3, "tag": "", "sol": "2 is not less than 2, so use the second piece (x ≥ 2): f(2) = −2 + 6 = 4. (Using 3x − 1 by mistake gives 5.)"}, {"kind": "blank", "p": "For the same function f (3x − 1 if x < 2; −x + 6 if x ≥ 2):", "tag": "", "marks": "", "flat": [{"t": "f(−1) = __B1__", "a": {"B1": "-4"}}, {"t": "f(0) = __B1__", "a": {"B1": "-1"}}, {"t": "f(5) = __B1__", "a": {"B1": "1"}}], "sol": "−1 < 2: f(−1) = 3(−1) − 1 = −4.\n0 < 2: f(0) = 3(0) − 1 = −1.\n5 ≥ 2: f(5) = −5 + 6 = 1."}, {"kind": "mcq", "text": "Which function is shown in the graph?", "opts": ["f(x) = x + 1 if x ≤ 1; −2 if x > 1", "f(x) = x − 1 if x < 1; −2 if x ≥ 1", "f(x) = −x + 1 if x < 1; 2 if x ≥ 1", "f(x) = x + 1 if x < 1; −2 if x ≥ 1"], "correct": 3, "tag": "", "sol": "Left piece: through (0, 1) and (−1, 0), slope 1 → x + 1, with an open circle at x = 1 (x < 1). Right piece: horizontal at y = −2 with a closed circle at x = 1 (x ≥ 1).", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 250\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"16.0\" y1=\"234.0\" x2=\"16.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"40.8\" y1=\"234.0\" x2=\"40.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"65.6\" y1=\"234.0\" x2=\"65.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"90.4\" y1=\"234.0\" x2=\"90.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"115.2\" y1=\"234.0\" x2=\"115.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"140.0\" y1=\"234.0\" x2=\"140.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"164.8\" y1=\"234.0\" x2=\"164.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"189.6\" y1=\"234.0\" x2=\"189.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"214.4\" y1=\"234.0\" x2=\"214.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"239.2\" y1=\"234.0\" x2=\"239.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"264.0\" y1=\"234.0\" x2=\"264.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"234.0\" x2=\"264.0\" y2=\"234.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"208.9\" x2=\"264.0\" y2=\"208.9\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"183.8\" x2=\"264.0\" y2=\"183.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"158.7\" x2=\"264.0\" y2=\"158.7\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"133.6\" x2=\"264.0\" y2=\"133.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"108.4\" x2=\"264.0\" y2=\"108.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"83.3\" x2=\"264.0\" y2=\"83.3\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"58.2\" x2=\"264.0\" y2=\"58.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"33.1\" x2=\"264.0\" y2=\"33.1\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"8.0\" x2=\"264.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"133.6\" x2=\"264.0\" y2=\"133.6\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"140.0\" y1=\"234.0\" x2=\"140.0\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"40.8\" y=\"142.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"90.4\" y=\"142.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"189.6\" y=\"142.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"239.2\" y=\"142.6\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"136.0\" y=\"234.0\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"136.0\" y=\"183.8\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"136.0\" y=\"83.3\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"136.0\" y=\"33.1\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"260.0\" y=\"125.6\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"148.0\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b4g724847\"><rect x=\"16.0\" y=\"8.0\" width=\"248.0\" height=\"226.0\"/></clipPath><path d=\"M16.0,234.0 L16.7,233.2 L17.5,232.5 L18.2,231.7 L19.0,231.0 L19.7,230.2 L20.5,229.5 L21.2,228.7 L22.0,228.0 L22.7,227.2 L23.4,226.5 L24.2,225.7 L24.9,225.0 L25.7,224.2 L26.4,223.5 L27.2,222.7 L27.9,221.9 L28.6,221.2 L29.4,220.4 L30.1,219.7 L30.9,218.9 L31.6,218.2 L32.4,217.4 L33.1,216.7 L33.9,215.9 L34.6,215.2 L35.3,214.4 L36.1,213.7 L36.8,212.9 L37.6,212.2 L38.3,211.4 L39.1,210.6 L39.8,209.9 L40.6,209.1 L41.3,208.4 L42.0,207.6 L42.8,206.9 L43.5,206.1 L44.3,205.4 L45.0,204.6 L45.8,203.9 L46.5,203.1 L47.2,202.4 L48.0,201.6 L48.7,200.9 L49.5,200.1 L50.2,199.3 L51.0,198.6 L51.7,197.8 L52.5,197.1 L53.2,196.3 L53.9,195.6 L54.7,194.8 L55.4,194.1 L56.2,193.3 L56.9,192.6 L57.7,191.8 L58.4,191.1 L59.2,190.3 L59.9,189.6 L60.6,188.8 L61.4,188.0 L62.1,187.3 L62.9,186.5 L63.6,185.8 L64.4,185.0 L65.1,184.3 L65.8,183.5 L66.6,182.8 L67.3,182.0 L68.1,181.3 L68.8,180.5 L69.6,179.8 L70.3,179.0 L71.1,178.3 L71.8,177.5 L72.5,176.7 L73.3,176.0 L74.0,175.2 L74.8,174.5 L75.5,173.7 L76.3,173.0 L77.0,172.2 L77.8,171.5 L78.5,170.7 L79.2,170.0 L80.0,169.2 L80.7,168.5 L81.5,167.7 L82.2,167.0 L83.0,166.2 L83.7,165.4 L84.4,164.7 L85.2,163.9 L85.9,163.2 L86.7,162.4 L87.4,161.7 L88.2,160.9 L88.9,160.2 L89.7,159.4 L90.4,158.7 L91.1,157.9 L91.9,157.2 L92.6,156.4 L93.4,155.7 L94.1,154.9 L94.9,154.1 L95.6,153.4 L96.4,152.6 L97.1,151.9 L97.8,151.1 L98.6,150.4 L99.3,149.6 L100.1,148.9 L100.8,148.1 L101.6,147.4 L102.3,146.6 L103.0,145.9 L103.8,145.1 L104.5,144.4 L105.3,143.6 L106.0,142.8 L106.8,142.1 L107.5,141.3 L108.3,140.6 L109.0,139.8 L109.7,139.1 L110.5,138.3 L111.2,137.6 L112.0,136.8 L112.7,136.1 L113.5,135.3 L114.2,134.6 L115.0,133.8 L115.7,133.1 L116.4,132.3 L117.2,131.5 L117.9,130.8 L118.7,130.0 L119.4,129.3 L120.2,128.5 L120.9,127.8 L121.6,127.0 L122.4,126.3 L123.1,125.5 L123.9,124.8 L124.6,124.0 L125.4,123.3 L126.1,122.5 L126.9,121.8 L127.6,121.0 L128.3,120.2 L129.1,119.5 L129.8,118.7 L130.6,118.0 L131.3,117.2 L132.1,116.5 L132.8,115.7 L133.6,115.0 L134.3,114.2 L135.0,113.5 L135.8,112.7 L136.5,112.0 L137.3,111.2 L138.0,110.5 L138.8,109.7 L139.5,108.9 L140.2,108.2 L141.0,107.4 L141.7,106.7 L142.5,105.9 L143.2,105.2 L144.0,104.4 L144.7,103.7 L145.5,102.9 L146.2,102.2 L146.9,101.4 L147.7,100.7 L148.4,99.9 L149.2,99.2 L149.9,98.4 L150.7,97.6 L151.4,96.9 L152.2,96.1 L152.9,95.4 L153.6,94.6 L154.4,93.9 L155.1,93.1 L155.9,92.4 L156.6,91.6 L157.4,90.9 L158.1,90.1 L158.8,89.4 L159.6,88.6 L160.3,87.9 L161.1,87.1 L161.8,86.3 L162.6,85.6 L163.3,84.8 L164.1,84.1 L164.8,83.3\" clip-path=\"url(#b4g724847)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><path d=\"M164.8,183.8 L165.3,183.8 L165.8,183.8 L166.3,183.8 L166.8,183.8 L167.3,183.8 L167.8,183.8 L168.3,183.8 L168.8,183.8 L169.3,183.8 L169.8,183.8 L170.3,183.8 L170.8,183.8 L171.2,183.8 L171.7,183.8 L172.2,183.8 L172.7,183.8 L173.2,183.8 L173.7,183.8 L174.2,183.8 L174.7,183.8 L175.2,183.8 L175.7,183.8 L176.2,183.8 L176.7,183.8 L177.2,183.8 L177.7,183.8 L178.2,183.8 L178.7,183.8 L179.2,183.8 L179.7,183.8 L180.2,183.8 L180.7,183.8 L181.2,183.8 L181.7,183.8 L182.2,183.8 L182.7,183.8 L183.2,183.8 L183.6,183.8 L184.1,183.8 L184.6,183.8 L185.1,183.8 L185.6,183.8 L186.1,183.8 L186.6,183.8 L187.1,183.8 L187.6,183.8 L188.1,183.8 L188.6,183.8 L189.1,183.8 L189.6,183.8 L190.1,183.8 L190.6,183.8 L191.1,183.8 L191.6,183.8 L192.1,183.8 L192.6,183.8 L193.1,183.8 L193.6,183.8 L194.1,183.8 L194.6,183.8 L195.1,183.8 L195.6,183.8 L196.0,183.8 L196.5,183.8 L197.0,183.8 L197.5,183.8 L198.0,183.8 L198.5,183.8 L199.0,183.8 L199.5,183.8 L200.0,183.8 L200.5,183.8 L201.0,183.8 L201.5,183.8 L202.0,183.8 L202.5,183.8 L203.0,183.8 L203.5,183.8 L204.0,183.8 L204.5,183.8 L205.0,183.8 L205.5,183.8 L206.0,183.8 L206.5,183.8 L207.0,183.8 L207.5,183.8 L208.0,183.8 L208.4,183.8 L208.9,183.8 L209.4,183.8 L209.9,183.8 L210.4,183.8 L210.9,183.8 L211.4,183.8 L211.9,183.8 L212.4,183.8 L212.9,183.8 L213.4,183.8 L213.9,183.8 L214.4,183.8 L214.9,183.8 L215.4,183.8 L215.9,183.8 L216.4,183.8 L216.9,183.8 L217.4,183.8 L217.9,183.8 L218.4,183.8 L218.9,183.8 L219.4,183.8 L219.9,183.8 L220.4,183.8 L220.8,183.8 L221.3,183.8 L221.8,183.8 L222.3,183.8 L222.8,183.8 L223.3,183.8 L223.8,183.8 L224.3,183.8 L224.8,183.8 L225.3,183.8 L225.8,183.8 L226.3,183.8 L226.8,183.8 L227.3,183.8 L227.8,183.8 L228.3,183.8 L228.8,183.8 L229.3,183.8 L229.8,183.8 L230.3,183.8 L230.8,183.8 L231.3,183.8 L231.8,183.8 L232.3,183.8 L232.8,183.8 L233.2,183.8 L233.7,183.8 L234.2,183.8 L234.7,183.8 L235.2,183.8 L235.7,183.8 L236.2,183.8 L236.7,183.8 L237.2,183.8 L237.7,183.8 L238.2,183.8 L238.7,183.8 L239.2,183.8 L239.7,183.8 L240.2,183.8 L240.7,183.8 L241.2,183.8 L241.7,183.8 L242.2,183.8 L242.7,183.8 L243.2,183.8 L243.7,183.8 L244.2,183.8 L244.7,183.8 L245.2,183.8 L245.6,183.8 L246.1,183.8 L246.6,183.8 L247.1,183.8 L247.6,183.8 L248.1,183.8 L248.6,183.8 L249.1,183.8 L249.6,183.8 L250.1,183.8 L250.6,183.8 L251.1,183.8 L251.6,183.8 L252.1,183.8 L252.6,183.8 L253.1,183.8 L253.6,183.8 L254.1,183.8 L254.6,183.8 L255.1,183.8 L255.6,183.8 L256.1,183.8 L256.6,183.8 L257.1,183.8 L257.6,183.8 L258.0,183.8 L258.5,183.8 L259.0,183.8 L259.5,183.8 L260.0,183.8 L260.5,183.8 L261.0,183.8 L261.5,183.8 L262.0,183.8 L262.5,183.8 L263.0,183.8 L263.5,183.8 L264.0,183.8\" clip-path=\"url(#b4g724847)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><circle cx=\"164.8\" cy=\"183.8\" r=\"4\" style=\"fill:var(--danger)\"/><circle cx=\"164.8\" cy=\"83.3\" r=\"4\" style=\"fill:var(--card);stroke:var(--danger);stroke-width:2\"/></svg>"}, {"kind": "blank", "p": "<b>Parking.</b> A garage charges $5 for the first hour or part of an hour, and $3 for each additional hour or part of an hour.", "tag": "", "marks": "", "flat": [{"t": "Cost for 45 minutes = $__B1__", "a": {"B1": "5"}}, {"t": "Cost for 2.5 hours = $__B1__", "a": {"B1": "11"}}, {"t": "Cost for exactly 4 hours = $__B1__", "a": {"B1": "14"}}], "sol": "45 minutes is part of the first hour: $5.\n2.5 hours counts as 3 hours: $5 + 2($3) = $11.\n4 hours: $5 + 3($3) = $14."}, {"kind": "mcq", "text": "Which piecewise function is the same as y = |x + 1| − 3?", "opts": ["y = x − 4 if x < −1; x − 2 if x ≥ −1", "y = −x − 2 if x < −1; x − 4 if x ≥ −1", "y = −x − 4 if x < −1; x − 2 if x ≥ −1", "y = −x − 4 if x < 1; x − 2 if x ≥ 1"], "correct": 2, "tag": "", "sol": "x + 1 < 0 when x < −1: y = −(x + 1) − 3 = −x − 4. When x ≥ −1: y = (x + 1) − 3 = x − 2. The pieces meet at the vertex (−1, −3)."}, {"kind": "blank", "p": "Write the piecewise function shown in the graph.", "tag": "", "marks": "", "flat": [{"t": "For x < −1: f(x) = __B1__", "a": {"B1": "2x+4"}, "expr": true}, {"t": "For x ≥ −1: f(x) = __B1__", "a": {"B1": "-x"}, "expr": true}], "sol": "Left piece through (−3, −2) and the open circle (−1, 2): slope 4 ÷ 2 = 2; −2 = 2(−3) + b → b = 4: 2x + 4.\nRight piece through the closed circle (−1, 1) and (3, −3): slope −4 ÷ 4 = −1; 1 = −1(−1) + b → b = 0: −x.", "fig": "<svg class=\"figsvg\" viewBox=\"0 0 280 250\" role=\"img\"><defs><marker id=\"ah\" viewBox=\"0 0 10 10\" refX=\"9\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M0,1 L10,5 L0,9 z\" class=\"ahd\"/></marker><marker id=\"ahs\" viewBox=\"0 0 10 10\" refX=\"1\" refY=\"5\" markerWidth=\"7\" markerHeight=\"7\" orient=\"auto\"><path d=\"M10,1 L0,5 L10,9 z\" class=\"ahd\"/></marker></defs><line x1=\"16.0\" y1=\"234.0\" x2=\"16.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"40.8\" y1=\"234.0\" x2=\"40.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"65.6\" y1=\"234.0\" x2=\"65.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"90.4\" y1=\"234.0\" x2=\"90.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"115.2\" y1=\"234.0\" x2=\"115.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"140.0\" y1=\"234.0\" x2=\"140.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"164.8\" y1=\"234.0\" x2=\"164.8\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"189.6\" y1=\"234.0\" x2=\"189.6\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"214.4\" y1=\"234.0\" x2=\"214.4\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"239.2\" y1=\"234.0\" x2=\"239.2\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"264.0\" y1=\"234.0\" x2=\"264.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"234.0\" x2=\"264.0\" y2=\"234.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"211.4\" x2=\"264.0\" y2=\"211.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"188.8\" x2=\"264.0\" y2=\"188.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"166.2\" x2=\"264.0\" y2=\"166.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"143.6\" x2=\"264.0\" y2=\"143.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"121.0\" x2=\"264.0\" y2=\"121.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"98.4\" x2=\"264.0\" y2=\"98.4\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"75.8\" x2=\"264.0\" y2=\"75.8\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"53.2\" x2=\"264.0\" y2=\"53.2\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"30.6\" x2=\"264.0\" y2=\"30.6\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"8.0\" x2=\"264.0\" y2=\"8.0\" style=\"stroke:var(--rule);stroke-width:.8\"/><line x1=\"16.0\" y1=\"121.0\" x2=\"264.0\" y2=\"121.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><line x1=\"140.0\" y1=\"234.0\" x2=\"140.0\" y2=\"8.0\" style=\"stroke:var(--ink-soft);stroke-width:1.3\"/><text class=\"po\" x=\"40.8\" y=\"130.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"90.4\" y=\"130.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"189.6\" y=\"130.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"239.2\" y=\"130.0\" text-anchor=\"middle\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"136.0\" y=\"211.4\" text-anchor=\"end\" dominant-baseline=\"middle\">−4</text><text class=\"po\" x=\"136.0\" y=\"166.2\" text-anchor=\"end\" dominant-baseline=\"middle\">−2</text><text class=\"po\" x=\"136.0\" y=\"75.8\" text-anchor=\"end\" dominant-baseline=\"middle\">2</text><text class=\"po\" x=\"136.0\" y=\"30.6\" text-anchor=\"end\" dominant-baseline=\"middle\">4</text><text class=\"po\" x=\"260.0\" y=\"113.0\" text-anchor=\"end\" dominant-baseline=\"middle\">x</text><text class=\"po\" x=\"148.0\" y=\"14.0\" text-anchor=\"start\" dominant-baseline=\"middle\">y</text><clipPath id=\"b4g668445\"><rect x=\"16.0\" y=\"8.0\" width=\"248.0\" height=\"226.0\"/></clipPath><path d=\"M16.0,256.6 L16.5,255.7 L17.0,254.8 L17.5,253.9 L18.0,253.0 L18.5,252.1 L19.0,251.2 L19.5,250.3 L20.0,249.4 L20.5,248.5 L21.0,247.6 L21.5,246.7 L22.0,245.8 L22.4,244.8 L22.9,243.9 L23.4,243.0 L23.9,242.1 L24.4,241.2 L24.9,240.3 L25.4,239.4 L25.9,238.5 L26.4,237.6 L26.9,236.7 L27.4,235.8 L27.9,234.9 L28.4,234.0 L28.9,233.1 L29.4,232.2 L29.9,231.3 L30.4,230.4 L30.9,229.5 L31.4,228.6 L31.9,227.7 L32.4,226.8 L32.9,225.9 L33.4,225.0 L33.9,224.1 L34.4,223.2 L34.8,222.2 L35.3,221.3 L35.8,220.4 L36.3,219.5 L36.8,218.6 L37.3,217.7 L37.8,216.8 L38.3,215.9 L38.8,215.0 L39.3,214.1 L39.8,213.2 L40.3,212.3 L40.8,211.4 L41.3,210.5 L41.8,209.6 L42.3,208.7 L42.8,207.8 L43.3,206.9 L43.8,206.0 L44.3,205.1 L44.8,204.2 L45.3,203.3 L45.8,202.4 L46.3,201.5 L46.8,200.6 L47.2,199.6 L47.7,198.7 L48.2,197.8 L48.7,196.9 L49.2,196.0 L49.7,195.1 L50.2,194.2 L50.7,193.3 L51.2,192.4 L51.7,191.5 L52.2,190.6 L52.7,189.7 L53.2,188.8 L53.7,187.9 L54.2,187.0 L54.7,186.1 L55.2,185.2 L55.7,184.3 L56.2,183.4 L56.7,182.5 L57.2,181.6 L57.7,180.7 L58.2,179.8 L58.7,178.9 L59.2,178.0 L59.6,177.0 L60.1,176.1 L60.6,175.2 L61.1,174.3 L61.6,173.4 L62.1,172.5 L62.6,171.6 L63.1,170.7 L63.6,169.8 L64.1,168.9 L64.6,168.0 L65.1,167.1 L65.6,166.2 L66.1,165.3 L66.6,164.4 L67.1,163.5 L67.6,162.6 L68.1,161.7 L68.6,160.8 L69.1,159.9 L69.6,159.0 L70.1,158.1 L70.6,157.2 L71.1,156.3 L71.6,155.4 L72.0,154.4 L72.5,153.5 L73.0,152.6 L73.5,151.7 L74.0,150.8 L74.5,149.9 L75.0,149.0 L75.5,148.1 L76.0,147.2 L76.5,146.3 L77.0,145.4 L77.5,144.5 L78.0,143.6 L78.5,142.7 L79.0,141.8 L79.5,140.9 L80.0,140.0 L80.5,139.1 L81.0,138.2 L81.5,137.3 L82.0,136.4 L82.5,135.5 L83.0,134.6 L83.5,133.7 L84.0,132.8 L84.4,131.8 L84.9,130.9 L85.4,130.0 L85.9,129.1 L86.4,128.2 L86.9,127.3 L87.4,126.4 L87.9,125.5 L88.4,124.6 L88.9,123.7 L89.4,122.8 L89.9,121.9 L90.4,121.0 L90.9,120.1 L91.4,119.2 L91.9,118.3 L92.4,117.4 L92.9,116.5 L93.4,115.6 L93.9,114.7 L94.4,113.8 L94.9,112.9 L95.4,112.0 L95.9,111.1 L96.4,110.2 L96.8,109.2 L97.3,108.3 L97.8,107.4 L98.3,106.5 L98.8,105.6 L99.3,104.7 L99.8,103.8 L100.3,102.9 L100.8,102.0 L101.3,101.1 L101.8,100.2 L102.3,99.3 L102.8,98.4 L103.3,97.5 L103.8,96.6 L104.3,95.7 L104.8,94.8 L105.3,93.9 L105.8,93.0 L106.3,92.1 L106.8,91.2 L107.3,90.3 L107.8,89.4 L108.3,88.5 L108.8,87.6 L109.2,86.6 L109.7,85.7 L110.2,84.8 L110.7,83.9 L111.2,83.0 L111.7,82.1 L112.2,81.2 L112.7,80.3 L113.2,79.4 L113.7,78.5 L114.2,77.6 L114.7,76.7 L115.2,75.8\" clip-path=\"url(#b4g668445)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><path d=\"M115.2,98.4 L115.9,99.1 L116.7,99.8 L117.4,100.4 L118.2,101.1 L118.9,101.8 L119.7,102.5 L120.4,103.1 L121.2,103.8 L121.9,104.5 L122.6,105.2 L123.4,105.9 L124.1,106.5 L124.9,107.2 L125.6,107.9 L126.4,108.6 L127.1,109.2 L127.8,109.9 L128.6,110.6 L129.3,111.3 L130.1,112.0 L130.8,112.6 L131.6,113.3 L132.3,114.0 L133.1,114.7 L133.8,115.3 L134.5,116.0 L135.3,116.7 L136.0,117.4 L136.8,118.1 L137.5,118.7 L138.3,119.4 L139.0,120.1 L139.8,120.8 L140.5,121.5 L141.2,122.1 L142.0,122.8 L142.7,123.5 L143.5,124.2 L144.2,124.8 L145.0,125.5 L145.7,126.2 L146.4,126.9 L147.2,127.6 L147.9,128.2 L148.7,128.9 L149.4,129.6 L150.2,130.3 L150.9,130.9 L151.7,131.6 L152.4,132.3 L153.1,133.0 L153.9,133.7 L154.6,134.3 L155.4,135.0 L156.1,135.7 L156.9,136.4 L157.6,137.0 L158.4,137.7 L159.1,138.4 L159.8,139.1 L160.6,139.8 L161.3,140.4 L162.1,141.1 L162.8,141.8 L163.6,142.5 L164.3,143.1 L165.0,143.8 L165.8,144.5 L166.5,145.2 L167.3,145.9 L168.0,146.5 L168.8,147.2 L169.5,147.9 L170.3,148.6 L171.0,149.2 L171.7,149.9 L172.5,150.6 L173.2,151.3 L174.0,152.0 L174.7,152.6 L175.5,153.3 L176.2,154.0 L177.0,154.7 L177.7,155.4 L178.4,156.0 L179.2,156.7 L179.9,157.4 L180.7,158.1 L181.4,158.7 L182.2,159.4 L182.9,160.1 L183.6,160.8 L184.4,161.5 L185.1,162.1 L185.9,162.8 L186.6,163.5 L187.4,164.2 L188.1,164.8 L188.9,165.5 L189.6,166.2 L190.3,166.9 L191.1,167.6 L191.8,168.2 L192.6,168.9 L193.3,169.6 L194.1,170.3 L194.8,170.9 L195.6,171.6 L196.3,172.3 L197.0,173.0 L197.8,173.7 L198.5,174.3 L199.3,175.0 L200.0,175.7 L200.8,176.4 L201.5,177.0 L202.2,177.7 L203.0,178.4 L203.7,179.1 L204.5,179.8 L205.2,180.4 L206.0,181.1 L206.7,181.8 L207.5,182.5 L208.2,183.2 L208.9,183.8 L209.7,184.5 L210.4,185.2 L211.2,185.9 L211.9,186.5 L212.7,187.2 L213.4,187.9 L214.2,188.6 L214.9,189.3 L215.6,189.9 L216.4,190.6 L217.1,191.3 L217.9,192.0 L218.6,192.6 L219.4,193.3 L220.1,194.0 L220.8,194.7 L221.6,195.4 L222.3,196.0 L223.1,196.7 L223.8,197.4 L224.6,198.1 L225.3,198.7 L226.1,199.4 L226.8,200.1 L227.5,200.8 L228.3,201.5 L229.0,202.1 L229.8,202.8 L230.5,203.5 L231.3,204.2 L232.0,204.8 L232.8,205.5 L233.5,206.2 L234.2,206.9 L235.0,207.6 L235.7,208.2 L236.5,208.9 L237.2,209.6 L238.0,210.3 L238.7,210.9 L239.4,211.6 L240.2,212.3 L240.9,213.0 L241.7,213.7 L242.4,214.3 L243.2,215.0 L243.9,215.7 L244.7,216.4 L245.4,217.1 L246.1,217.7 L246.9,218.4 L247.6,219.1 L248.4,219.8 L249.1,220.4 L249.9,221.1 L250.6,221.8 L251.4,222.5 L252.1,223.2 L252.8,223.8 L253.6,224.5 L254.3,225.2 L255.1,225.9 L255.8,226.5 L256.6,227.2 L257.3,227.9 L258.0,228.6 L258.8,229.3 L259.5,229.9 L260.3,230.6 L261.0,231.3 L261.8,232.0 L262.5,232.6 L263.3,233.3 L264.0,234.0\" clip-path=\"url(#b4g668445)\" style=\"fill:none;stroke:var(--danger);stroke-width:2.4\"/><circle cx=\"115.2\" cy=\"98.4\" r=\"4\" style=\"fill:var(--danger)\"/><circle cx=\"115.2\" cy=\"75.8\" r=\"4\" style=\"fill:var(--card);stroke:var(--danger);stroke-width:2\"/><circle cx=\"65.6\" cy=\"166.2\" r=\"3.6\" style=\"fill:var(--ink)\"/><text x=\"72.6\" y=\"158.2\" text-anchor=\"start\" style=\"fill:var(--ink);font:600 11.5px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(−3, −2)</text><circle cx=\"214.4\" cy=\"188.8\" r=\"3.6\" style=\"fill:var(--ink)\"/><text x=\"207.4\" y=\"180.8\" text-anchor=\"end\" style=\"fill:var(--ink);font:600 11.5px 'Source Sans 3',sans-serif;paint-order:stroke;stroke:var(--card);stroke-width:4px;stroke-linejoin:round\">(3, −3)</text></svg>"}, {"kind": "mcq", "text": "<b>Shipping.</b> A company charges $6 for packages up to 2 lb, $9 for more than 2 lb up to 5 lb, and $15 for more than 5 lb up to 10 lb. What does a 5 lb package cost?", "opts": ["$12", "$15", "$6", "$9"], "correct": 3, "tag": "", "sol": "5 lb is in the interval “more than 2 lb up to 5 lb” (2 < w ≤ 5), so it costs $9."}, {"kind": "blank", "p": "<b>Electric bill.</b> A power company charges $0.12 per kilowatt-hour (kWh) for the first 500 kWh and $0.15 per kWh for every kWh above 500.", "tag": "", "marks": "", "flat": [{"t": "Bill for 400 kWh = $__B1__", "a": {"B1": "48"}}, {"t": "Bill for 700 kWh = $__B1__", "a": {"B1": "90"}}, {"t": "For k > 500 kWh, bill B(k) = __B1__ (use k)", "a": {"B1": "0.15k-15"}, "expr": true}], "sol": "0.12(400) = $48.\n0.12(500) + 0.15(200) = 60 + 30 = $90.\n60 + 0.15(k − 500) = 0.15k − 75 + 60 = 0.15k − 15."}, {"kind": "mcq", "text": "f(x) = 2x if −3 ≤ x < 1, and f(x) = 5 if 1 < x ≤ 4. Which value of x is <b>not</b> in the domain of f?", "opts": ["0", "4", "−3", "1"], "correct": 3, "tag": "", "sol": "The first piece stops before 1 (x < 1) and the second starts after 1 (1 < x). Neither includes x = 1, so f(1) is not defined."}, {"kind": "blank", "p": "g(x) = 4 if x ≤ −2; x + 1 if −2 < x < 3; 2x − 3 if x ≥ 3. Evaluate.", "tag": "", "marks": "", "flat": [{"t": "g(−2) = __B1__", "a": {"B1": "4"}}, {"t": "g(0) = __B1__", "a": {"B1": "1"}}, {"t": "g(3) = __B1__", "a": {"B1": "3"}}, {"t": "g(6) = __B1__", "a": {"B1": "9"}}], "sol": "−2 ≤ −2: first piece, 4.\n−2 < 0 < 3: 0 + 1 = 1.\n3 ≥ 3: 2(3) − 3 = 3.\n2(6) − 3 = 9."}, {"kind": "mcq", "text": "<b>Error analysis.</b> h(x) = x + 5 if x < 3, and h(x) = 2x if x ≥ 3. Zoe says h(3) = 8. What is h(3)?", "opts": ["14, because both pieces are added", "It is not defined, because 3 is a boundary", "6, because x = 3 belongs to the piece x ≥ 3", "8, Zoe is correct"], "correct": 2, "tag": "", "sol": "x = 3 satisfies x ≥ 3, not x < 3, so h(3) = 2(3) = 6. Zoe used the first piece."}, {"kind": "blank", "p": "<b>Reasoning.</b> f(x) = 2x + k if x < 1, and f(x) = 5x − 1 if x ≥ 1. Find k so that the two pieces meet (the graph has no break).", "tag": "", "marks": "", "flat": [{"t": "f(1) = __B1__", "a": {"B1": "4"}}, {"t": "k = __B1__", "a": {"B1": "2"}}], "sol": "Use the second piece: 5(1) − 1 = 4.\nThe left piece must approach 4 at x = 1: 2(1) + k = 4 → k = 2."}, {"kind": "mcq", "text": "<b>Museum tickets.</b> Entry is free for children under 5, $8 for ages 5 through 17, and $15 for ages 18 and over. Which function gives the price C for a visitor of age a?", "opts": ["C(a) = 0 if a < 5; 15 if 5 ≤ a < 18; 8 if a ≥ 18", "C(a) = 0 if a ≤ 5; 8 if 5 < a < 18; 15 if a ≥ 18", "C(a) = 0 if a < 5; 8 if 5 ≤ a < 18; 15 if a ≥ 18", "C(a) = 0 if a < 5; 8 if 5 ≤ a ≤ 18; 15 if a > 18"], "correct": 2, "tag": "", "sol": "A 5-year-old pays $8, so 5 belongs to the middle piece (5 ≤ a). An 18-year-old pays $15, so 18 belongs to the last piece (a ≥ 18) and the middle piece stops before 18 (a < 18)."}, {"kind": "blank", "p": "<b>Overtime pay.</b> Rosa earns $18 per hour for the first 40 hours she works in a week and $27 per hour for each hour over 40.", "tag": "", "marks": "", "flat": [{"t": "Pay for 35 hours = $__B1__", "a": {"B1": "630"}}, {"t": "Pay for 46 hours = $__B1__", "a": {"B1": "882"}}, {"t": "For h > 40 hours, pay P(h) = __B1__ (use h)", "a": {"B1": "27h-360"}, "expr": true}], "sol": "35 ≤ 40: 18(35) = $630.\n18(40) + 27(6) = 720 + 162 = $882.\n720 + 27(h − 40) = 720 + 27h − 1080 = 27h − 360. Check h = 46: 1242 − 360 = 882 ✓"}]}, {"id": "s8", "label": "Assessment A", "sub": "Knowing and understanding", "slides": [{"kind": "mcq", "text": "Which equation describes the line with slope −5 and y-intercept 2?", "opts": ["y = −5x − 2", "y = 5x + 2", "y = −5x + 2", "y = 2x − 5"], "correct": 2, "tag": "", "sol": "y = mx + b with m = −5 and b = 2."}, {"kind": "blank", "p": "The line y + 6 = 4(x − 1) is in point-slope form.", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "4"}}, {"t": "point (x₁, y₁) = __B1__", "a": {"B1": "(1, -6)"}, "expr": "coord"}], "sol": "The coefficient in front of the bracket: 4.\ny + 6 = y − (−6), so (x₁, y₁) = (1, −6)."}, {"kind": "mcq", "text": "What is the slope of a line perpendicular to y = {2/7}x − 1?", "opts": ["−{2/7}", "{7/2}", "−{7/2}", "{2/7}"], "correct": 2, "tag": "", "sol": "The negative reciprocal of {2/7} is −{7/2}: {2/7} × (−{7/2}) = −1."}, {"kind": "blank", "p": "A line passes through (−1, 5) and (3, −3).", "tag": "", "marks": "", "flat": [{"t": "slope = __B1__", "a": {"B1": "-2"}}, {"t": "Equation: y = __B1__", "a": {"B1": "-2x+3"}, "expr": true}], "sol": "(−3 − 5) ÷ (3 − (−1)) = −8 ÷ 4 = −2.\n5 = −2(−1) + b → b = 3, so y = −2x + 3."}, {"kind": "mcq", "text": "A data point has observed value 12, and the line of fit predicts 14.5. What is the residual?", "opts": ["26.5", "0.83", "−2.5", "2.5"], "correct": 2, "tag": "", "sol": "12 − 14.5 = −2.5: the point is below the line."}, {"kind": "blank", "p": "For the arithmetic sequence 9, 5, 1, −3, …", "tag": "", "marks": "", "flat": [{"t": "d = __B1__", "a": {"B1": "-4"}}, {"t": "a₁₅ = __B1__", "a": {"B1": "-47"}}], "sol": "5 − 9 = −4.\na₁₅ = 9 + 14(−4) = 9 − 56 = −47."}, {"kind": "mcq", "text": "f(x) = 4 − x if x ≤ 0, and f(x) = 3x + 2 if x > 0. What is f(0)?", "opts": ["0", "4", "6", "2"], "correct": 1, "tag": "", "sol": "0 ≤ 0, so use the first piece: f(0) = 4 − 0 = 4."}, {"kind": "blank", "p": "A line has slope −{1/3} and passes through (6, 1).", "tag": "", "marks": "", "flat": [{"t": "y-intercept b = __B1__", "a": {"B1": "3"}}, {"t": "y-value on the line at x = −3: __B1__", "a": {"B1": "4"}}], "sol": "1 = −{1/3}(6) + b = −2 + b → b = 3.\ny = −{1/3}(−3) + 3 = 1 + 3 = 4."}, {"kind": "mcq", "text": "Which correlation coefficient shows almost <b>no</b> linear correlation?", "opts": ["r = 0.03", "r = −0.60", "r = −0.91", "r = 0.78"], "correct": 0, "tag": "", "sol": "r close to 0 means weak or no linear correlation: 0.03."}]}, {"id": "s9", "label": "Assessment B", "sub": "Investigating patterns", "slides": [{"kind": "mcq", "text": "Which equation fits the table? x: 0, 2, 4, 6; y: 5, 11, 17, 23", "opts": ["y = 5x + 3", "y = 3x + 5", "y = 6x + 5", "y = 2x + 5"], "correct": 1, "tag": "", "sol": "y goes up by 6 when x goes up by 2, so m = 3; at x = 0, y = 5. y = 3x + 5."}, {"kind": "blank", "p": "The sequence 2.5, 4, 5.5, 7, … is arithmetic.", "tag": "", "marks": "", "flat": [{"t": "d = __B1__", "a": {"B1": "1.5"}}, {"t": "a₁₀ = __B1__", "a": {"B1": "16"}}, {"t": "aₙ = __B1__ (use n)", "a": {"B1": "1.5n+1"}, "expr": true}], "sol": "4 − 2.5 = 1.5.\n2.5 + 9(1.5) = 2.5 + 13.5 = 16.\n2.5 + 1.5(n − 1) = 1.5n + 1."}, {"kind": "mcq", "text": "Which line is <b>not</b> parallel to y = −2x?", "opts": ["y = −2x + 5", "y = 2x − 2", "2x + y = 7", "y − 1 = −2(x + 3)"], "correct": 1, "tag": "", "sol": "2x + y = 7 is y = −2x + 7 and y − 1 = −2(x + 3) has slope −2, so they are parallel to y = −2x. y = 2x − 2 has slope 2."}, {"kind": "blank", "p": "The line y = 3x models the data (1, 4), (2, 5), (3, 8), (4, 13).", "tag": "", "marks": "", "flat": [{"t": "Residuals in order: __B1__", "a": {"B1": "1, -1, -1, 1"}, "expr": "dlist"}, {"t": "Do the residuals form a U-shaped pattern? __B1__ (yes / no)", "a": {"B1": "yes"}, "expr": "words"}], "sol": "Predicted 3, 6, 9, 12: 4 − 3 = 1, 5 − 6 = −1, 8 − 9 = −1, 13 − 12 = 1.\nPositive at both ends, negative in the middle: a U-shape, so a line is not the best model."}, {"kind": "mcq", "text": "<b>Postage.</b> A letter costs $0.70 for the first ounce and $0.25 for each additional ounce or part of an ounce. What does a 3.2 oz letter cost?", "opts": ["$1.20", "$1.45", "$0.95", "$1.50"], "correct": 1, "tag": "", "sol": "3.2 oz counts as 4 ounces: $0.70 + 3($0.25) = $1.45."}, {"kind": "blank", "p": "Explore perpendicular slopes.", "tag": "", "marks": "", "flat": [{"t": "Slope perpendicular to {3/5} = __B1__", "a": {"B1": "-5/3"}, "expr": "fv"}, {"t": "{3/5} × (that slope) = __B1__", "a": {"B1": "-1"}}], "sol": "Take the reciprocal and change the sign: −{5/3}.\n{3/5} × (−{5/3}) = −1. This is true for every pair of perpendicular slopes."}, {"kind": "mcq", "text": "Is the relationship in the table linear? x: 1, 2, 3, 4, 5; y: 2, 5, 9, 14, 20", "opts": ["Yes: the differences increase by 1 each time", "No: the differences 3, 4, 5, 6 are not constant", "No: the y-values are not all even", "Yes: y increases every time"], "correct": 1, "tag": "", "sol": "For a linear relationship, equal steps in x give equal changes in y. The changes 3, 4, 5, 6 are not equal."}, {"kind": "blank", "p": "The points (1, −3), (2, 1), (3, 5), (4, 9) show the terms of an arithmetic sequence.", "tag": "", "marks": "", "flat": [{"t": "d = slope of the line through the points = __B1__", "a": {"B1": "4"}}, {"t": "aₙ = __B1__ (use n)", "a": {"B1": "4n-7"}, "expr": true}, {"t": "a₁₂ = __B1__", "a": {"B1": "41"}}], "sol": "Each step in n raises the value by 4.\n−3 + 4(n − 1) = 4n − 7.\n4(12) − 7 = 41."}, {"kind": "mcq", "text": "Which piecewise function is the same as y = |x − 3|?", "opts": ["y = −x + 3 if x < 3; x − 3 if x ≥ 3", "y = x + 3 if x < 0; x − 3 if x ≥ 0", "y = −x − 3 if x < 3; x − 3 if x ≥ 3", "y = x − 3 if x < 3; −x + 3 if x ≥ 3"], "correct": 0, "tag": "", "sol": "When x < 3, x − 3 is negative, so |x − 3| = −(x − 3) = −x + 3. When x ≥ 3, |x − 3| = x − 3."}]}, {"id": "s10", "label": "Assessment C", "sub": "Communicating", "slides": [{"kind": "mcq", "text": "In y = mx + b, what does b represent?", "opts": ["the slope", "the y-intercept", "the x-intercept", "the residual"], "correct": 1, "tag": "", "sol": "b is the value of y when x = 0, where the line crosses the y-axis."}, {"kind": "blank", "p": "Complete the vocabulary.", "tag": "", "marks": "", "flat": [{"t": "The number r that measures how well a line fits the data is the __B1__ coefficient.", "a": {"B1": "correlation"}, "expr": "words"}, {"t": "Using a model to predict outside the range of the data is called __B1__.", "a": {"B1": "extrapolation"}, "expr": "words"}], "sol": "r is the correlation coefficient, from −1 to 1.\nPredicting outside the data range is extrapolation."}, {"kind": "mcq", "text": "<b>Error analysis.</b> Priya says the line through the origin perpendicular to y = 4x is y = −4x. Which is the correct line?", "opts": ["y = {1/4}x", "y = −{1/4}x", "y = −4x", "y = 4x"], "correct": 1, "tag": "", "sol": "Perpendicular slopes are negative reciprocals: 4 → −{1/4}. Priya only changed the sign."}, {"kind": "blank", "p": "A repair shop's charge is C = 45h + 120, where h is the number of hours of work.", "tag": "", "marks": "", "flat": [{"t": "Hourly rate (the slope) = $__B1__", "a": {"B1": "45"}}, {"t": "Fixed charge (the C-intercept) = $__B1__", "a": {"B1": "120"}}], "sol": "The coefficient of h is the rate: $45 per hour.\nWhen h = 0, C = 120: a fixed $120 charge."}, {"kind": "mcq", "text": "At a beach, the number of swimmers and the number of lifeguards on duty have a strong positive correlation. Which statement is justified?", "opts": ["More swimmers cause the correlation coefficient to be negative", "There is no relationship between the two variables", "More lifeguards cause more people to swim", "They tend to rise together, but the data do not show that one causes the other"], "correct": 3, "tag": "", "sol": "A strong correlation shows the variables change together. Correlation alone never proves causation (here hot, busy days drive both)."}, {"kind": "blank", "p": "Rewrite y − 2 = −3(x + 4) in slope-intercept form.", "tag": "", "marks": "", "flat": [{"t": "y = __B1__", "a": {"B1": "-3x-10"}, "expr": true}, {"t": "y-intercept = __B1__", "a": {"B1": "-10"}}], "sol": "y − 2 = −3x − 12 → y = −3x − 10.\nb = −10."}, {"kind": "mcq", "text": "On the graph of a piecewise function, what does an open circle at (2, 5) mean?", "opts": ["The graph has a y-intercept of 5", "The function is not defined for any x greater than 2", "The point (2, 5) is not part of the graph", "The point (2, 5) is part of the graph"], "correct": 2, "tag": "", "sol": "An open circle marks an endpoint that is not included (a strict inequality such as x < 2)."}, {"kind": "blank", "p": "A sequence has aₙ = 12 − 4n.", "tag": "", "marks": "", "flat": [{"t": "a₁ = __B1__", "a": {"B1": "8"}}, {"t": "common difference = __B1__", "a": {"B1": "-4"}}, {"t": "The sequence is __B1__ (increasing / decreasing).", "a": {"B1": "decreasing"}, "expr": "words"}], "sol": "12 − 4 = 8.\nThe coefficient of n is −4.\nA negative common difference makes each term smaller: decreasing."}, {"kind": "mcq", "text": "Jin claims his line of fit is good because it passes through two of the data points. Which reply is best?", "opts": ["A line of fit must pass through at least three data points", "Not enough: a good fit stays close to all points, balanced above and below", "He is right: any line through two data points is a good line of fit", "He is right only if the two points are the first and last points"], "correct": 1, "tag": "", "sol": "A line of fit should follow the whole data set. Residuals with no pattern, or an r close to ±1, show a good fit; passing through two points does not."}]}, {"id": "s11", "label": "Assessment D", "sub": "Applying mathematics in real-life contexts", "slides": [{"kind": "mcq", "text": "<b>Taxi.</b> A taxi charges $3.50 plus $2.25 per mile. What does an 8-mile ride cost?", "opts": ["$46.00", "$30.25", "$18.00", "$21.50"], "correct": 3, "tag": "", "sol": "C = 2.25(8) + 3.50 = 18 + 3.50 = $21.50. ($30.25 swaps the rate and the fee.)"}, {"kind": "blank", "p": "<b>Pool.</b> A full pool holds 18,000 gallons and is drained at a constant rate. After 3 hours, 13,500 gallons are left.", "tag": "", "marks": "", "flat": [{"t": "Gallons drained per hour = __B1__", "a": {"B1": "1500"}}, {"t": "Gallons left after t hours: V = __B1__ (use t)", "a": {"B1": "18000-1500t"}, "expr": true}, {"t": "Hours until the pool is empty = __B1__", "a": {"B1": "12"}}], "sol": "(18,000 − 13,500) ÷ 3 = 1500 gallons per hour.\nV = −1500t + 18,000.\n0 = 18,000 − 1500t → t = 12."}, {"kind": "mcq", "text": "<b>Bamboo.</b> A bamboo shoot grows the same amount each day. It is 14 in. tall on day 1 and 20 in. tall on day 4. How tall is it on day 10?", "opts": ["36 in.", "32 in.", "50 in.", "34 in."], "correct": 1, "tag": "", "sol": "3 steps from day 1 to day 4: 3d = 6, d = 2 in. per day. a₁₀ = 14 + 9(2) = 32 in."}, {"kind": "blank", "p": "<b>Study time.</b> Use Desmos regression (y₁ ~ mx₁ + b). hours studied x: 1, 2, 3, 4, 5, 6, 7; test score y: 62, 66, 71, 73, 79, 83, 86", "tag": "", "marks": "", "flat": [{"t": "slope m = __B1__ (to 2 decimal places)", "a": {"B1": "4.07"}}, {"t": "y-intercept b = __B1__ (to 2 decimal places)", "a": {"B1": "58"}}, {"t": "Predicted score for 8 hours (nearest whole number) = __B1__", "a": {"B1": "91"}}], "sol": "m ≈ 4.0714 ≈ 4.07 points per hour.\nb = 58.00.\n4.0714(8) + 58 ≈ 90.6, about 91.", "tools": ["desmos"], "desmos": [{"type": "table", "columns": [{"latex": "x_1", "values": ["1", "2", "3", "4", "5", "6", "7"]}, {"latex": "y_1", "values": ["62", "66", "71", "73", "79", "83", "86"]}]}]}, {"kind": "mcq", "text": "<b>Data plan.</b> A phone plan costs $30 a month for up to 5 GB, plus $10 for each GB above 5 GB (charged exactly). What is the bill for 7.5 GB?", "opts": ["$55", "$75", "$105", "$40"], "correct": 0, "tag": "", "sol": "Only the 2.5 GB above 5 GB costs extra: 30 + 10(7.5 − 5) = 30 + 25 = $55. ($105 charges $10 on all 7.5 GB.)"}, {"kind": "blank", "p": "<b>Bike path.</b> On a town map (units in miles) a road passes through (0, 2) and (4, 4). A new bike path will be parallel to the road and pass through (2, −1).", "tag": "", "marks": "", "flat": [{"t": "slope of the bike path = __B1__", "a": {"B1": "1/2"}, "expr": "fv"}, {"t": "y-intercept of the bike path = __B1__", "a": {"B1": "-2"}}], "sol": "Road slope (4 − 2) ÷ (4 − 0) = {1/2}; parallel lines have equal slopes.\n−1 = {1/2}(2) + b = 1 + b → b = −2, so y = {1/2}x − 2."}, {"kind": "mcq", "text": "A survey finds r = −0.88 between the hours students spend on video games each week and their grade point averages. Which conclusion is reasonable?", "opts": ["There is no relationship, because r is negative", "Students with higher GPAs tend to game more", "Gaming causes lower GPAs, because r is close to −1", "Students who game more tend to have lower GPAs, but this does not prove gaming causes lower GPAs"], "correct": 3, "tag": "", "sol": "r = −0.88 shows a strong negative correlation: as gaming time increases, GPA tends to decrease. Correlation alone does not prove causation."}, {"kind": "blank", "p": "<b>Arena.</b> Row 1 of a section in an arena has 24 seats, row 2 has 26 seats, row 3 has 28 seats, and so on.", "tag": "", "marks": "", "flat": [{"t": "Seats in row n: aₙ = __B1__ (use n)", "a": {"B1": "2n+22"}, "expr": true}, {"t": "Seats in row 30 = __B1__", "a": {"B1": "82"}}], "sol": "a₁ = 24, d = 2: 24 + 2(n − 1) = 2n + 22.\n2(30) + 22 = 82."}, {"kind": "mcq", "text": "<b>Scooter.</b> An e-scooter costs $1 to unlock plus $0.30 per minute. What is the greatest whole number of minutes you can ride with $10?", "opts": ["30 minutes", "36 minutes", "33 minutes", "29 minutes"], "correct": 0, "tag": "", "sol": "1 + 0.30t ≤ 10 → 0.30t ≤ 9 → t ≤ 30. (33 ignores the unlock fee.)"}, {"kind": "mcq", "text": "<b>Is this reasonable?</b> Using data for a puppy aged 2 to 8 months, Leo finds the line of fit y = 3.2x + 4, where y is the weight in pounds and x is the age in months. He predicts that at 10 years (120 months) the dog will weigh 3.2(120) + 4 = 388 lb. What should he conclude?", "opts": ["The prediction is reasonable, because the line of fit was found from real data", "The prediction is not reasonable, because he should have used x = 10 to get 36 lb", "Not reasonable: 120 months is far outside the data, and dogs stop growing", "The prediction is reasonable, because the correlation between age and weight is positive"], "correct": 2, "tag": "", "sol": "3.2(120) + 4 = 388 is correct arithmetic, but it is extrapolation far beyond 2–8 months. A puppy grows quickly at first and then stops, so a linear model cannot be trusted that far out. (Using x = 10 mixes up years and months.)"}]}];
/* ================= build slide lists ================= */
var SLIDES = {}; SECTIONS.forEach(function(sec){ SLIDES[sec.id]=sec.slides; });
var TAB_DEFS = SECTIONS.map(function(sec){ return {id:sec.id, label:sec.label, sub:sec.sub}; });

/* ================= state ================= */
function blankItem(slide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    return {status:'unanswered', attempts:0, choice:undefined};
  }
  return {status:'unanswered', curStep:0, stepStates: slide.flat.map(function(){ return {status:'unanswered', attempts:0, inputs:{}}; })};
}
function defaultState(){
  var s={tabs:{}};
  TAB_DEFS.forEach(function(td){
    s.tabs[td.id] = { idx:0, maxReached:0, items: SLIDES[td.id].map(function(sl){ return blankItem(sl); }) };
  });
  return s;
}
var appState = {mode:null, learning:null, quiz:null};
var state = null;      // alias for appState[appState.mode]
var MODE = null;
var activeTab=TAB_DEFS[0].id;

function setMode(m){
  appState.mode = m;
  if(!appState[m]) appState[m] = defaultState();
  state = appState[m];
  MODE = m;
}
/* ================= student accounts (saved on this device) ================= */
var SHEET_KEY='sopaan-bim-ch4';
var ACC_KEY='sopaan-students-v1';
var storageOK=true;
var MEM={};
function lsGet(k){ var r=null; try{ r=localStorage.getItem(k); }catch(e){ storageOK=false; }
  if(r===null||r===undefined) r=MEM[k]||null; try{ return r?JSON.parse(r):null; }catch(e){ return null; } }
function lsSet(k,v){ var j=JSON.stringify(v); MEM[k]=j; try{ localStorage.setItem(k,j); return true; }catch(e){ storageOK=false; return false; } }
try{ localStorage.setItem('sopaan-probe','1'); localStorage.removeItem('sopaan-probe'); }catch(e){ storageOK=false; }
function hashPin(pin,salt){ var h=2166136261, str=salt+'|'+pin; for(var i=0;i<str.length;i++){ h^=str.charCodeAt(i); h=Math.imul(h,16777619)>>>0; } return h.toString(36); }
function accKey(name,roll){ return (name.trim().toLowerCase().replace(/\s+/g,' ')+'#'+roll.trim().toLowerCase()); }
function accounts(){ return lsGet(ACC_KEY)||{students:{}}; }
var student=null; // {key,name,roll}
var records=[];   // finished-tab history for this student on this sheet
function progKey(){ return SHEET_KEY+'::'+student.key; }

function loadState(){
  appState = {mode:null, learning:null, quiz:null}; records=[]; activeTab=TAB_DEFS[0].id;
  var saved=lsGet(progKey());
  if(!saved) return;
  try{
    ['learning','quiz'].forEach(function(m){
      if(saved[m] && saved[m].tabs){
        var fresh = defaultState();
        TAB_DEFS.forEach(function(td){
          if(saved[m].tabs[td.id] && saved[m].tabs[td.id].items && saved[m].tabs[td.id].items.length===SLIDES[td.id].length){
            fresh.tabs[td.id] = saved[m].tabs[td.id];
          }
        });
        appState[m] = fresh;
      }
    });
    if(saved.mode==='learning' || saved.mode==='quiz') appState.mode = saved.mode;
    if(saved.activeTab && TAB_DEFS.some(function(t){ return t.id===saved.activeTab; })) activeTab = saved.activeTab;
    if(Array.isArray(saved.records)) records = saved.records;
  }catch(e){}
}
function saveState(){
  if(!student) return;
  lsSet(progKey(), {mode:appState.mode, learning:appState.learning, quiz:appState.quiz, activeTab:activeTab, records:records, updated:Date.now()});
  var acc=accounts(); if(acc.students[student.key]){ acc.students[student.key].last=Date.now(); lsSet(ACC_KEY,acc); }
}
function addRecord(mode, tabId, correct, revealed, skipped, total){
  records.unshift({at:Date.now(), mode:mode, tab:tabId, correct:correct, revealed:revealed, skipped:skipped, total:total});
  if(records.length>60) records.length=60;
  saveState();
}
function fmtDate(ms){ try{ return new Date(ms).toLocaleString(undefined,{day:'numeric',month:'short',hour:'2-digit',minute:'2-digit'}); }catch(e){ return ''; } }

function renderWho(){
  var el=document.getElementById('whoBar');
  if(!student){ el.hidden=true; el.innerHTML=''; return; }
  el.hidden=false;
  el.innerHTML='Signed in as <b>'+esc(student.name)+'</b> · Roll '+esc(student.roll)+
    ' <button id="btnRecord">My record</button> <button id="btnSignOut">Sign out</button>';
  document.getElementById('btnRecord').addEventListener('click', renderRecord);
  document.getElementById('btnSignOut').addEventListener('click', signOut);
}
function signOut(){
  saveState(); student=null; state=null; MODE=null;
  var acc=accounts(); delete acc.current; lsSet(ACC_KEY,acc);
  document.getElementById('modePill').hidden=true;
  renderWho(); renderLogin();
}
function signIn(key){
  var acc=accounts(); var st=acc.students[key]; if(!st) return;
  student={key:key, name:st.name, roll:st.roll};
  acc.current=key; st.last=Date.now(); lsSet(ACC_KEY,acc);
  loadState(); renderWho();
  if(appState.mode==='learning' || appState.mode==='quiz'){
    setMode(appState.mode); document.getElementById('modePill').hidden=false; updateModePill();
    showChrome(true); buildTabbar(); renderSlide();
    showToast('Welcome back, '+st.name.split(' ')[0]+'. Picking up where you left off.');
  } else {
    renderModePicker();
  }
}
function renderLogin(msg){
  showChrome(false);
  var acc=accounts(); var keys=Object.keys(acc.students).sort(function(a,b){ return (acc.students[b].last||0)-(acc.students[a].last||0); });
  var h='<div class="login-card"><h2>Student sign-in</h2>'+
    '<p class="lead">Sign in to save your answers, see your record and continue where you left off next time.</p>';
  if(!storageOK) h+='<div class="login-err">This browser is blocking saved data (for example, a private window). You can still practise, but progress will not be kept after you close the page.</div>';
  if(msg) h+='<div class="login-err">'+esc(msg)+'</div>';
  if(keys.length){
    h+='<div class="known"><span class="known-label">Continue as</span>';
    keys.slice(0,6).forEach(function(k){ var st=acc.students[k];
      h+='<button class="known-btn" data-k="'+esc(k)+'"><span>'+esc(st.name)+' <small>· Roll '+esc(st.roll)+'</small></span><small>'+(st.last?'Last active '+fmtDate(st.last):'')+'</small></button>'; });
    h+='</div>';
  }
  h+='<form id="loginForm" novalidate>'+
    '<div class="fld"><label for="lgName">Full name</label><input id="lgName" autocomplete="name" required></div>'+
    '<div class="fld-row"><div class="fld"><label for="lgRoll">Roll no.</label><input id="lgRoll" required></div>'+
    '<div class="fld"><label for="lgPin">4-digit PIN</label><input id="lgPin" type="password" inputmode="numeric" maxlength="4" autocomplete="off" required></div></div>'+
    '<button class="btn btn-primary" type="submit" style="width:100%;">Sign in</button>'+
    '<p class="login-note">New here? Enter your name, roll no. and a PIN you will remember, and your profile is created. Progress is saved on this device, so use the same device and browser to continue.</p>'+
    '</form></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  wrap.querySelectorAll('.known-btn').forEach(function(b){
    b.addEventListener('click', function(){
      var st=accounts().students[b.dataset.k];
      document.getElementById('lgName').value=st.name; document.getElementById('lgRoll').value=st.roll;
      document.getElementById('lgPin').focus();
    });
  });
  document.getElementById('loginForm').addEventListener('submit', function(e){
    e.preventDefault();
    var name=document.getElementById('lgName').value.trim(), roll=document.getElementById('lgRoll').value.trim(), pin=document.getElementById('lgPin').value.trim();
    if(!name||!roll){ renderLoginErr('Enter your name and roll no.'); return; }
    if(!/^\d{4}$/.test(pin)){ renderLoginErr('Your PIN must be exactly 4 digits.'); return; }
    var k=accKey(name,roll); var acc=accounts();
    if(acc.students[k]){
      if(acc.students[k].pin!==hashPin(pin,k)){ renderLoginErr('That PIN does not match this name and roll no. Try again.'); return; }
    } else {
      acc.students[k]={name:name.replace(/\s+/g,' '), roll:roll, pin:hashPin(pin,k), created:Date.now()};
      lsSet(ACC_KEY,acc);
    }
    signIn(k);
  });
}
function renderLoginErr(m){
  var n=document.getElementById('lgName').value, r=document.getElementById('lgRoll').value;
  renderLogin(m); document.getElementById('lgName').value=n; document.getElementById('lgRoll').value=r; document.getElementById('lgPin').focus();
}
function tabSummary(m){
  var st=appState[m]; if(!st) return null;
  return TAB_DEFS.map(function(td){
    var items=st.tabs[td.id].items, n=items.length;
    var c=items.filter(function(i){return i.status==='correct';}).length;
    var done=items.filter(function(i){return i.status!=='unanswered';}).length;
    return {label:td.label, n:n, done:done, correct:c};
  });
}
function renderRecord(){
  showChrome(false);
  var tabLabel=function(id){ var t=TAB_DEFS.find(function(x){return x.id===id;}); return t?t.label:id; };
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+' · Writing Linear Functions</p>';
  ['learning','quiz'].forEach(function(m){
    var sum=tabSummary(m);
    h+='<h3>'+(m==='learning'?'📘 Learning Sheet':'📝 Quiz Mode')+'</h3>';
    if(!sum){ h+='<p class="rec-empty">Not started yet.</p>'; return; }
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>Section</th><th>Progress</th><th>Correct first time</th></tr></thead><tbody>';
    sum.forEach(function(r){ var pct=Math.round(r.done/r.n*100);
      h+='<tr><td>'+r.label+'</td><td><span class="rec-bar"><i style="width:'+pct+'%"></i></span>'+r.done+' / '+r.n+'</td><td>'+(m==='quiz'?'—':r.correct+' / '+r.n)+'</td></tr>'; });
    h+='</tbody></table></div>';
  });
  h+='</div><div class="rec-card"><h3>Finished sections</h3>';
  if(!records.length){ h+='<p class="rec-empty">No sections finished yet. Each time you finish a tab, your score is recorded here.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table"><thead><tr><th>When</th><th>Mode</th><th>Section</th><th>Score</th></tr></thead><tbody>';
    records.forEach(function(r){ h+='<tr><td>'+fmtDate(r.at)+'</td><td>'+(r.mode==='quiz'?'Quiz':'Learning')+'</td><td>'+tabLabel(r.tab)+'</td><td>'+r.correct+' / '+r.total+(r.mode==='learning'?' <span class="rec-empty">('+r.revealed+' revealed, '+r.skipped+' skipped)</span>':'')+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><button class="btn btn-primary" id="btnBack">'+(MODE?'Back to practice':'Choose a mode')+'</button>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('btnBack').addEventListener('click', function(){
    if(MODE){ showChrome(true); buildTabbar(); renderSlide(); } else renderModePicker();
  });
  window.scrollTo({top:0});
}

/* ================= tab bar ================= */
function buildTabbar(){
  var el=document.getElementById('tabbar');
  el.innerHTML = '<button class="tab-btn'+(activeTab==='theory'?' active':'')+'" data-tab="theory">Theory<span class="tab-count">notes</span></button>' + TAB_DEFS.map(function(t){
    return '<button class="tab-btn'+(t.id===activeTab?' active':'')+'" data-tab="'+t.id+'">'+t.label+'<span class="tab-count">'+SLIDES[t.id].length+'</span></button>';
  }).join('') + '<button class="tab-btn'+(activeTab==='report'?' active':'')+'" data-tab="report">📊 Report<span class="tab-count">pie</span></button>';
  el.querySelectorAll('.tab-btn').forEach(function(btn){
    btn.addEventListener('click', function(){ activeTab=btn.dataset.tab; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); });
  });
}

/* ================= rendering ================= */
function canProceed(item){ return item.status==='correct'||item.status==='revealed'||item.status==='skipped'; }

function renderSlide(){
  if(!state.tabs[activeTab]){ activeTab=TAB_DEFS[0].id; }
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  if(ts.idx>=slides.length||ts.idx<0) ts.idx=0;
  var idx = ts.idx;
  var slide = slides[idx];
  var item = ts.items[idx];

  var tdef=TAB_DEFS.find(function(t){return t.id===activeTab;});
  document.getElementById('spLabel').textContent = tdef.label+' · Question '+(idx+1)+' of '+slides.length;
  document.getElementById('secSub').textContent = tdef.label+' — '+tdef.sub;
  document.getElementById('spFill').style.width = Math.round(((idx)/(Math.max(slides.length-1,1)))*100)+'%';

  var h='<div class="qcard">';
  if(slide.kind==='mcq' || slide.kind==='ar'){
    h += renderChoiceBody(slide, item, idx);
  } else {
    h += renderBlankBody(slide, item, idx);
  }
  h += '<div class="feedback" id="feedbackBox"></div>';
  if(MODE==='learning' && (item.status==='correct'||item.status==='revealed')) h += solutionHTML(slide);
  h += '</div>';

  document.getElementById('wrap').innerHTML = h;
  wireSlideEvents(slide, item, idx);
  restoreFeedback(item);
  renderNavbar(item);
  updateFab();
  saveState();
}

function solutionHTML(slide){
  if(!slide.sol) return '';
  return '<div class="solution"><div class="sol-h">Solution</div>'+slide.sol.split('\n').map(function(l){ return '<div class="sol-line">'+fr(esc(l))+'</div>'; }).join('')+'</div>';
}
var LETTERS=['a','b','c','d','e','f'];
function chosenHTML(slide,item){
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(item.choice===undefined) return '';
  var ok=item.choice===slide.correct;
  var h='<div class="chosen '+(ok?'ok':'bad')+'"><b>Your answer:</b> ('+LETTERS[item.choice]+') '+fr(esc(opts[item.choice]))+(ok?' ✓':' ✗')+'</div>';
  if(!ok) h+='<div class="chosen ok"><b>Correct answer:</b> ('+LETTERS[slide.correct]+') '+fr(esc(opts[slide.correct]))+'</div>';
  return h;
}
function renderChoiceBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div>';
  if(slide.kind==='mcq'){
    h += '<div class="qtext">'+fr(esc(slide.text))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  } else {
    h += '<div class="qtext"><span class="qtag" style="margin-left:0;margin-right:6px;">A / R</span>Assertion (A): '+fr(esc(slide.a))+'<br>Reason (R): '+fr(esc(slide.r))+(slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  }
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';
  var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
  if(MODE==='quiz') h += '<div class="quiz-hint">Quiz mode — pick an option. The correct answer is revealed once you finish this tab.</div>';
  var locked = MODE==='learning' && (item.status==='correct' || item.status==='revealed');
  h += '<div class="options">';
  opts.forEach(function(opt,i){
    var cls='opt';
    if(locked){
      if(i===slide.correct) cls+=' is-correct';
      else if(item.choice===i) cls+=' is-wrong';
      cls+=' locked';
    }
    if(item.choice===i) cls+=' is-chosen';
    h += '<label class="'+cls+'"><input type="radio" name="choice" value="'+i+'" '+(item.choice===i?'checked':'')+' '+(locked?'disabled':'')+'> <span class="opt-l">('+LETTERS[i]+')</span> <span class="opt-t">'+fr(esc(opt))+'</span>'+(item.choice===i?'<span class="opt-tag">'+(locked?(i===slide.correct?'Your answer ✓':'Your answer ✗'):'Selected')+'</span>':'')+'</label>';
  });
  h += '</div>';
  if(locked) h += chosenHTML(slide,item);
  return h;
}

function renderBlankBody(slide, item, idx){
  var h='<div class="qhead"><div class="qnum">'+(idx+1)+'</div><div class="qtext">';
  if(slide.kind==='case'){ h += '<b>'+esc(slide.title)+'.</b> '+esc(slide.body); }
  else { var pp=fr(esc(slide.p)).split('\n'); h += pp[0]+pp.slice(1).map(function(x){return '<span class="datline">'+x+'</span>';}).join(''); }
  h += (slide.tag?'<span class="qtag">'+esc(slide.tag)+'</span>':'')+'</div>';
  if(slide.marks) h += '<div class="marks-pill">'+slide.marks+'</div>';
  h += '</div>';
  if(slide.fig) h += '<div class="fig">'+slide.fig+'</div>';

  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  var blankCount=0; slide.flat.forEach(function(s){ blankCount+=Object.keys(s.a).length; });

  if(MODE==='quiz'){
    h += '<div class="step-badge">'+blankCount+' blank'+(blankCount===1?'':'s')+' in this question</div>';
    h += '<div class="quiz-hint">Quiz mode — fill in what you can. Correct answers are revealed once you finish this tab.</div>';
    if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
    if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
    h += '<div class="steps">';
    for(var qi=0; qi<total; qi++){
      var qstep = slide.flat[qi];
      var qss = item.stepStates[qi];
      if(qstep.partLabel) h += '<div class="subpart-label">'+esc(qstep.partLabel)+'</div>';
      if(qstep.orDivider) h += '<div class="or-divider">OR</div>';
      var qline = fr(qstep.t);
      Object.keys(qstep.a).forEach(function(bkey){
        var val = qss.inputs[bkey]||'';
        var inp='<input class="blank-input'+(['fv','fe','fl','fm','fi','dec'].indexOf(qstep.expr)>=0?' fr':(qstep.expr==='flist'||qstep.expr==='dlist'||qstep.expr==='glist')?' wide':qstep.expr===true?' expr':(qstep.expr==='words'||qstep.expr==='list'||qstep.expr==='expanded'||qstep.expr==='set'||qstep.expr==='primes'||qstep.expr==='trans'||qstep.expr==='rot'?' wide':''))+'" data-step="'+qi+'" data-bkey="'+bkey+'" value="'+esc(val)+'">';
        qline = qline.replace('__'+bkey+'__', inp);
      });
      if(qstep.fig) h += '<div class="fig">'+qstep.fig+'</div>';
      h += '<div class="step-line">'+qline+'</div>';
    }
    h += '</div>';
    return h;
  }

  if(hasFrac) h += '<div class="quiz-hint">Type fractions like <b>3/4</b> and mixed numbers like <b>2 3/4</b> (whole number, space, fraction).</div>';
  if(hasExpr) h += '<div class="quiz-hint">Type answers like <b>2x-5</b>, <b>x^2-4</b> or <b>3+2i</b>. Use ^ for powers, | | for absolute value and pi for π. Any equivalent form is accepted.</div>';
  var locked = item.status==='correct' || item.status==='revealed';
  var upto = locked ? total-1 : item.curStep;
  h += '<div class="step-badge">Step '+(Math.min(item.curStep,total-1)+1)+' of '+total+'</div>';
  h += '<div class="steps">';
  for(var i=0;i<=upto;i++){
    var step = slide.flat[i];
    var ss = item.stepStates[i];
    if(step.partLabel) h += '<div class="subpart-label">'+esc(step.partLabel)+'</div>';
    if(step.orDivider) h += '<div class="or-divider">OR</div>';
    var resolved = ss.status==='correct' || ss.status==='revealed';
    var line = fr(step.t);
    Object.keys(step.a).forEach(function(bkey){
      var fs = ss.inputs['fs_'+bkey];
      var cls = fs==='correct'?'is-correct':(fs==='wrong'?'is-wrong':'');
      var val = ss.inputs[bkey]||'';
      var dis = resolved ? 'disabled':'';
      var inp='<input class="blank-input '+cls+(['fv','fe','fl','fm','fi','dec'].indexOf(step.expr)>=0?' fr':(step.expr==='flist'||step.expr==='dlist'||step.expr==='glist')?' wide':step.expr===true?' expr':(step.expr==='words'||step.expr==='list'||step.expr==='expanded'||step.expr==='set'||step.expr==='primes'||step.expr==='trans'||step.expr==='rot'?' wide':''))+'" data-step="'+i+'" data-bkey="'+bkey+'" value="'+esc(val)+'" '+dis+'>';
      line = line.replace('__'+bkey+'__', inp);
    });
    if(step.fig) h += '<div class="fig">'+step.fig+'</div>';
    h += '<div class="step-line'+(resolved?' resolved':'')+'">'+line+'</div>';
    if(ss.status==='revealed'){
      var reveals=[];
      Object.keys(step.a).forEach(function(bkey){ reveals.push(bkey+' = '+esc(step.a[bkey])); });
      h += '<div class="reveal-note">correct: '+reveals.join(', ')+'</div>';
    }
  }
  h += '</div>';
  return h;
}

var __flash=null;
function restoreFeedback(item){
  var fb=document.getElementById('feedbackBox'); if(!fb) return;
  if(__flash){ fb.className='feedback show '+__flash.c; fb.innerHTML=__flash.h; __flash=null; return; }
  if(MODE==='quiz'){ fb.className='feedback'; fb.innerHTML=''; return; }
  if(item.status==='correct'){ fb.className='feedback show ok'; fb.innerHTML='<b>All done — correct!</b>'; }
  else if(item.status==='revealed'){ fb.className='feedback show reveal'; fb.innerHTML='<b>Answer revealed above.</b> Move on whenever you’re ready.'; }
  else if(item.status==='skipped'){ fb.className='feedback show retry'; fb.innerHTML='Skipped — you can answer it now and press <b>Check</b>, or come back later from the Question Palette.'; }
  else { fb.className='feedback'; fb.innerHTML=''; }
}

function slideIsAnswered(slide,item){
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return item.stepStates.some(function(ss){ return Object.keys(ss.inputs).some(function(k){ return k.indexOf('fs_')!==0 && ss.inputs[k] && String(ss.inputs[k]).trim()!==''; }); });
}
function renderNavbar(item){
  var ts = state.tabs[activeTab];
  var slides = SLIDES[activeTab];
  var slide = slides[ts.idx];
  var isLast = ts.idx === slides.length-1;
  var h='';
  h += '<button class="btn" id="btnPrev" '+(ts.idx===0?'disabled':'')+'>&larr; Previous</button>';

  if(MODE==='quiz'){
    h += '<button class="btn" id="btnSkip">Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnNext">'+(isLast?'Finish':'Next →')+'</button>';
  } else {
    h += '<button class="btn" id="btnSkip" '+(item.status!=='unanswered'?'disabled':'')+'>Skip</button>';
    h += '<span class="spacer"></span>';
    h += '<button class="btn btn-primary" id="btnCheck" '+((item.status!=='unanswered'&&item.status!=='skipped')?'disabled':'')+'>Check</button>';
    h += '<button class="btn btn-primary" id="btnNext" '+(canProceed(item)?'':'disabled')+'>'+(isLast?'Finish':'Next →')+'</button>';
  }
  document.getElementById('navbarInner').innerHTML = h;

  document.getElementById('btnPrev').addEventListener('click', function(){ if(ts.idx>0){ ts.idx--; renderSlide(); } });

  if(MODE==='quiz'){
    document.getElementById('btnSkip').addEventListener('click', function(){
      item.status='skipped';
      advanceQuiz(ts, slides);
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      item.status = slideIsAnswered(slide,item) ? 'answered' : 'unanswered';
      advanceQuiz(ts, slides);
    });
  } else {
    document.getElementById('btnSkip').addEventListener('click', function(){
      if(item.status==='unanswered'){ item.status='skipped'; renderSlide(); }
    });
    document.getElementById('btnNext').addEventListener('click', function(){
      if(!canProceed(item)) return;
      if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
      else { renderFinished(); }
    });
    document.getElementById('btnCheck').addEventListener('click', function(){ handleCheck(); });
  }
}
function advanceQuiz(ts, slides){
  if(ts.idx < slides.length-1){ ts.idx++; ts.maxReached=Math.max(ts.maxReached, ts.idx); renderSlide(); }
  else { renderFinished(); }
}

function wireSlideEvents(slide, item, idx){
  document.querySelectorAll('input[type="radio"][name="choice"]').forEach(function(r){
    r.addEventListener('change', function(){ item.choice=parseInt(r.value,10); saveState();
      document.querySelectorAll('.opt').forEach(function(l){ l.classList.remove('is-chosen'); var t=l.querySelector('.opt-tag'); if(t) t.remove(); });
      var lab=r.closest('.opt'); lab.classList.add('is-chosen'); var tg=document.createElement('span'); tg.className='opt-tag'; tg.textContent='Selected'; lab.appendChild(tg); });
  });
  document.querySelectorAll('.blank-input').forEach(function(inp){
    inp.addEventListener('input', function(){
      var si=parseInt(inp.dataset.step,10), bk=inp.dataset.bkey;
      item.stepStates[si].inputs[bk]=inp.value;
      saveState();
    });
  });
}

function handleCheck(){
  var ts = state.tabs[activeTab];
  var slide = SLIDES[activeTab][ts.idx];
  var item = ts.items[ts.idx];
  if(item.status==='skipped') item.status='unanswered';
  var fb = document.getElementById('feedbackBox');

  if(slide.kind==='mcq' || slide.kind==='ar'){
    if(item.choice===undefined){ fb.className='feedback show err'; fb.innerHTML='Please choose an option first.'; return; }
    var ok = item.choice===slide.correct;
    if(ok){
      item.status='correct'; playSuccess();
      fb.className='feedback show ok'; fb.innerHTML='<b>Correct!</b>';
    } else {
      item.attempts=(item.attempts||0)+1;
      if(item.attempts>=2){ item.status='revealed'; playReveal(); }
      else { playWrong(); fb.className='feedback show retry'; fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'}; }
    }
    renderSlide();
    return;
  }

  // blank / case
  var step = slide.flat[item.curStep];
  var ss = item.stepStates[item.curStep];
  var blanks = Object.keys(step.a);
  var missing = blanks.some(function(k){ return !ss.inputs[k] || String(ss.inputs[k]).trim()===''; });
  if(missing){ fb.className='feedback show err'; fb.innerHTML='Fill in every blank in this step before checking.'; return; }

  var allGood=true;
  blanks.forEach(function(k){
    var good=answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr);
    ss.inputs['fs_'+k]=good?'correct':'wrong';
    if(!good) allGood=false;
  });

  if(allGood){
    ss.status='correct'; playSuccess();
    advanceStepOrFinish(item, slide);
  } else {
    ss.attempts=(ss.attempts||0)+1;
    if(ss.attempts>=2){
      ss.status='revealed'; playReveal();
      advanceStepOrFinish(item, slide);
    } else {
      playWrong();
      fb.className='feedback show retry';
      fb.innerHTML='<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'; __flash={c:'retry',h:'<b>Not quite — try again</b> (attempt 1 of 2) <span class="attempts-dots"><span class="used"></span><span></span></span>'};
      renderSlide();
      return;
    }
  }
  renderSlide();
}

function advanceStepOrFinish(item, slide){
  var total = slide.flat.length;
  var hasExpr = slide.flat.some(function(s){ return s.expr===true; });
  var hasFrac = slide.flat.some(function(s){ return ['fv','fe','fl','fm','fi','flist'].indexOf(s.expr)>=0; });
  if(item.curStep < total-1){
    item.curStep++;
  } else {
    var anyRevealed = item.stepStates.some(function(ss){ return ss.status==='revealed'; });
    item.status = anyRevealed ? 'revealed' : 'correct';
  }
}

/* ================= palette ================= */
var overlay=document.getElementById('overlay');
function statusOf(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  return ts.items[i].status==='unanswered' ? 'locked' : ts.items[i].status;
}
function buildPalette(){
  var slides=SLIDES[activeTab];
  document.getElementById('paletteTitle').textContent = TAB_DEFS.find(function(t){return t.id===activeTab;}).label+' · Question palette';
  var body=document.getElementById('paletteBody');
  var html='';
  for(var i=0;i<slides.length;i++){
    html += '<div class="chip" data-status="'+statusOf(activeTab,i)+'" data-idx="'+i+'">'+(i+1)+'</div>';
  }
  body.innerHTML = html;
  body.querySelectorAll('.chip').forEach(function(chip){
    chip.addEventListener('click', function(){
      var i=parseInt(chip.dataset.idx,10);
      var ts=state.tabs[activeTab];
      if(i>ts.maxReached){ showToast('Finish the earlier questions to unlock this one.'); return; }
      ts.idx=i; closePalette(); renderSlide();
    });
  });
}
function openPalette(){ buildPalette(); overlay.classList.add('show'); }
function closePalette(){ overlay.classList.remove('show'); }
var toastTimer;
function showToast(msg){
  var t=document.getElementById('toast'); t.textContent=msg; t.classList.add('show');
  clearTimeout(toastTimer); toastTimer=setTimeout(function(){ t.classList.remove('show'); },2200);
}
document.getElementById('paletteFab').addEventListener('click', openPalette);
document.getElementById('paletteClose').addEventListener('click', closePalette);
overlay.addEventListener('click', function(e){ if(e.target===overlay) closePalette(); });

function updateFab(){
  var slides=SLIDES[activeTab];
  var done=state.tabs[activeTab].items.filter(function(it){ return it.status==='correct'||it.status==='revealed'||it.status==='skipped'; }).length;
  document.getElementById('fabBadge').textContent = done+'/'+slides.length;
}

/* ================= overall progress + finish ================= */
function updateChapterProgress(){
  var total=0, done=0;
  TAB_DEFS.forEach(function(td){
    state.tabs[td.id].items.forEach(function(it){
      total++;
      if(it.status==='correct'||it.status==='revealed'||it.status==='skipped') done++;
    });
  });
  var pct = total>0 ? Math.round((done/total)*100) : 0;
  document.getElementById('cpFill').style.width=pct+'%';
  document.getElementById('cpLabel').textContent=pct+'% complete';
}
function isSlideCorrect(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice===slide.correct;
  return slide.flat.every(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).every(function(k){ return answerMatches(ss.inputs[k], step.a[k], step.accept, step.expr); });
  });
}
function isSlideAttempted(tabId,i){
  var slide=SLIDES[tabId][i], item=state.tabs[tabId].items[i];
  if(slide.kind==='mcq'||slide.kind==='ar') return item.choice!==undefined;
  return slide.flat.some(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).some(function(k){ return ss.inputs[k] && String(ss.inputs[k]).trim()!==''; });
  });
}
function slideLabel(slide){
  var t = slide.kind==='case' ? slide.title : (slide.kind==='ar' ? slide.a : (slide.p||slide.text||''));
  t = String(t);
  return t.length>90 ? t.slice(0,90)+'…' : t;
}
function slideAnswerText(slide, item, correctSide){
  if(slide.kind==='mcq'||slide.kind==='ar'){
    var opts = slide.kind==='mcq' ? slide.opts : AR_OPTIONS;
    if(correctSide) return '('+LETTERS[slide.correct]+') '+opts[slide.correct];
    return item.choice!==undefined ? '('+LETTERS[item.choice]+') '+opts[item.choice] : '— not attempted —';
  }
  return slide.flat.map(function(step,si){
    var ss=item.stepStates[si];
    return Object.keys(step.a).map(function(k){
      return correctSide ? step.a[k] : (ss.inputs[k] || '—');
    }).join(', ');
  }).join('  |  ');
}

function renderFinished(){
  if(MODE==='quiz'){ renderQuizResults(); return; }
  var ts=state.tabs[activeTab];
  var correct=ts.items.filter(function(i){return i.status==='correct';}).length;
  var revealed=ts.items.filter(function(i){return i.status==='revealed';}).length;
  var skipped=ts.items.filter(function(i){return i.status==='skipped';}).length;
  var h='<div class="qcard done-card"><div class="big">✨</div><h2>Tab complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">You worked through all '+ts.items.length+' questions in this tab.</p>';
  if(!ts.recorded){ ts.recorded=true; addRecord('learning', activeTab, correct, revealed, skipped, ts.items.length); }
  h+='<div class="score-pills">'+
     '<span class="score-pill" style="background:var(--success-soft);color:var(--success);">'+correct+' correct</span>'+
     '<span class="score-pill" style="background:var(--danger-soft);color:var(--danger);">'+revealed+' revealed</span>'+
     '<span class="score-pill" style="background:var(--gold-soft);color:var(--retry-text);">'+skipped+' skipped</span></div>'+
     '<button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; ts.recorded=false; renderSlide(); });
  updateChapterProgress(); saveState();
}

function renderQuizResults(){
  var ts=state.tabs[activeTab];
  var slides=SLIDES[activeTab];
  var correctCount=0, attemptedCount=0;
  var rowsHtml = slides.map(function(slide,i){
    var item=ts.items[i];
    var ok=isSlideCorrect(activeTab,i);
    var att=isSlideAttempted(activeTab,i);
    if(ok) correctCount++;
    if(att) attemptedCount++;
    var tagCls = ok?'ok':(att?'bad':'na');
    var tagText = ok?'Correct':(att?'Incorrect':'Not attempted');
    var row='<div class="review-row">';
    row+='<span class="review-tag '+tagCls+'">Q'+(i+1)+' · '+tagText+'</span>';
    row+='<div class="review-q">'+fr(esc(slideLabel(slide)))+'</div>';
    row+='<div class="review-ans"><b>Your answer:</b> '+fr(esc(slideAnswerText(slide,item,false)))+'</div>';
    if(!ok) row+='<div class="review-ans" style="color:var(--success);"><b>Correct answer:</b> '+fr(esc(slideAnswerText(slide,item,true)))+'</div>';
    if(slide.sol) row+='<details class="rev-sol"><summary>Show solution</summary>'+solutionHTML(slide)+'</details>';
    row+='</div>';
    return row;
  }).join('');

  addRecord('quiz', activeTab, correctCount, 0, 0, slides.length);
  var h='<div class="qcard done-card" style="text-align:left;">';
  h+='<div style="text-align:center;"><div class="big">🏁</div><h2>Quiz complete</h2>';
  h+='<p style="color:var(--ink-soft);font-size:14px;">'+correctCount+' / '+slides.length+' correct · '+attemptedCount+' attempted</p></div>';
  h+='<div style="margin-top:16px;">'+rowsHtml+'</div>';
  h+='<div style="text-align:center;margin-top:6px;"><button class="btn btn-primary" id="btnReview">Review from question 1</button></div>';
  h+='</div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  document.getElementById('btnReview').addEventListener('click', function(){ ts.idx=0; renderSlide(); });
  playSuccess();
  updateChapterProgress(); saveState();
}

/* ================= mode picker ================= */
function updateModePill(){
  var btn=document.getElementById('modePill');
  if(!btn) return;
  btn.textContent = MODE==='quiz' ? '📝 Quiz Mode · switch' : '📘 Learning Sheet · switch';
}
function showChrome(show){
  document.querySelector('.tabbar').style.display = show?'':'none';
  document.querySelector('.slide-progress').style.display = show?'':'none';
  document.querySelector('.navbar').style.display = show?'':'none';
  document.getElementById('paletteFab').style.display = show?'':'none';
}
function renderModePicker(){
  showChrome(false);
  var wrap=document.getElementById('wrap');
  wrap.innerHTML =
    '<div class="mode-pick">'+
      '<div class="mode-card" data-pick="learning"><div class="mode-icon">📘</div><h3>Learning Sheet</h3>'+
      '<p>Work through each question step by step with instant feedback — two tries, then the correct value is revealed right there so you can keep moving.</p></div>'+
      '<div class="mode-card" data-pick="quiz"><div class="mode-icon">📝</div><h3>Quiz Mode</h3>'+
      '<p>Attempt every question with no hints along the way. Your score and the full answer key are shown together once you finish the tab — just like the real exam.</p></div>'+
    '</div>';
  wrap.querySelectorAll('[data-pick]').forEach(function(card){
    card.addEventListener('click', function(){
      setMode(card.dataset.pick); activeTab='theory';
      document.getElementById('modePill').hidden=false;
      updateModePill();
      showChrome(true);
      buildTabbar();
      renderSlide();
    });
  });
}
document.getElementById('modePill').addEventListener('click', function(){
  if(!appState.mode){ return; }
  setMode(appState.mode==='quiz' ? 'learning' : 'quiz');
  updateModePill();
  showChrome(true);
  buildTabbar();
  renderSlide();
});

/* ================= boot ================= */
var _origRenderSlide = renderSlide;
renderSlide = function(){ _origRenderSlide(); updateChapterProgress(); updateModePill(); };


/* ================= theory tab ================= */
function renderTheory(){
  var wrap=document.getElementById('wrap');
  wrap.innerHTML='<div class="theory">'+fr(THEORY)+'</div>';
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Theory — notes, key ideas and worked examples';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
  wrap.querySelectorAll('[data-jump]').forEach(function(b){ b.addEventListener('click',function(){ var t=document.getElementById(b.dataset.jump); if(t) t.scrollIntoView({behavior:'smooth',block:'start'}); }); });
}
var _rsTheory = renderSlide;
renderSlide = function(){
  if(activeTab==='theory'){ renderTheory(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  document.querySelector('.slide-progress').style.display='';
  document.querySelector('.navbar').style.display='';
  document.getElementById('paletteFab').style.display='';
  _rsTheory();
};


/* ================= MYP criterion report ================= */
var CRIT_COL={A:'var(--accent-text)',B:'var(--gold)',C:'#8A6FC4',D:'#2F9AA0'};
function critStats(){
  return REPORT.map(function(r){
    var tabId=r[0], slides=SLIDES[tabId], ts=state&&state.tabs[tabId];
    var c=0,w=0,n=0;
    slides.forEach(function(sl,i){
      if(!ts||!ts.items[i]){ n++; return; }
      var it=ts.items[i];
      if(MODE==='learning'){
        if(it.status==='correct') c++; else if(it.status==='revealed') w++; else n++;
      } else {
        if(isSlideCorrect(tabId,i)) c++; else if(isSlideAttempted(tabId,i)) w++; else n++;
      }
    });
    var tot=slides.length, pct=tot?Math.round(c/tot*100):0;
    var lvl=Math.round(c/Math.max(tot,1)*8);
    return {tab:tabId,letter:r[1],name:r[2],c:c,w:w,n:n,tot:tot,pct:pct,lvl:lvl};
  });
}
function arcPath(cx,cy,r,a0,a1){
  if(a1-a0>=Math.PI*2-1e-6){ return 'M'+(cx-r)+','+cy+' a'+r+','+r+' 0 1,0 '+(2*r)+',0 a'+r+','+r+' 0 1,0 '+(-2*r)+',0 Z'; }
  var x0=cx+r*Math.sin(a0), y0=cy-r*Math.cos(a0), x1=cx+r*Math.sin(a1), y1=cy-r*Math.cos(a1);
  return 'M'+cx+','+cy+' L'+x0.toFixed(2)+','+y0.toFixed(2)+' A'+r+','+r+' 0 '+((a1-a0)>Math.PI?1:0)+',1 '+x1.toFixed(2)+','+y1.toFixed(2)+' Z';
}
function pieSVG(parts,size,hole,center,sub){
  var tot=parts.reduce(function(s,p){return s+p.v;},0), cx=size/2, cy=size/2, r=size/2-4, a=0, h='';
  if(!tot){ h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+r+'" style="fill:var(--paper-2);stroke:var(--rule)"/>'; }
  parts.forEach(function(p){ if(!p.v) return; var b=a+p.v/tot*Math.PI*2; h+='<path d="'+arcPath(cx,cy,r,a,b)+'" style="fill:'+p.col+';stroke:var(--card);stroke-width:2"><title>'+esc(p.label)+': '+p.v+'</title></path>'; a=b; });
  if(hole) h+='<circle cx="'+cx+'" cy="'+cy+'" r="'+(r*hole)+'" style="fill:var(--card)"/>';
  if(center) h+='<text x="'+cx+'" y="'+(cy-(sub?4:0))+'" text-anchor="middle" dominant-baseline="middle" style="fill:var(--ink);font:700 '+(size>150?22:15)+'px Fraunces,serif">'+center+'</text>';
  if(sub) h+='<text x="'+cx+'" y="'+(cy+16)+'" text-anchor="middle" style="fill:var(--ink-soft);font:600 11px \'Source Sans 3\',sans-serif">'+sub+'</text>';
  return '<svg viewBox="0 0 '+size+' '+size+'" width="'+size+'" height="'+size+'" role="img">'+h+'</svg>';
}
function band(l){ return l===0?'0':(l<=2?'1–2':(l<=4?'3–4':(l<=6?'5–6':'7–8'))); }
function renderReport(){
  var st=critStats(), totC=0, totQ=0;
  st.forEach(function(s){ totC+=s.c; totQ+=s.tot; });
  var h='<div class="theory">';
  h+='<section class="note"><h2>Chapter test report</h2><p class="lt">'+(MODE==='quiz'?'<b>Quiz mode</b> results: answers are marked when you finish each test tab.':'<b>Learning mode</b> results: a question counts as correct only if you got it without the answer being revealed. Switch to Quiz mode for an exam-style score.')+'</p>';
  h+='<div class="rep-top"><div class="rep-pie">'+pieSVG(st.map(function(s){return {v:s.c,col:CRIT_COL[s.letter],label:'Criterion '+s.letter};}),200,0.55,totC+'/'+totQ,'correct')+'</div>';
  h+='<div class="rep-legend"><div class="rep-cap">Marks earned, by criterion</div>'+st.map(function(s){ return '<div class="rep-li"><span class="sw" style="background:'+CRIT_COL[s.letter]+'"></span><b>'+s.letter+'</b>&nbsp;'+esc(s.name)+'<span class="rep-n">'+s.c+' / '+s.tot+'</span></div>'; }).join('')+'</div></div></section>';
  h+='<div class="rep-grid">'+st.map(function(s){
    return '<div class="rep-card"><div class="rep-h"><span class="crit" style="background:'+CRIT_COL[s.letter]+'">'+s.letter+'</span>'+esc(s.name)+'</div>'+
      '<div class="rep-row">'+pieSVG([{v:s.c,col:'var(--success)',label:'Correct'},{v:s.w,col:'var(--danger)',label:'Incorrect'},{v:s.n,col:'var(--locked)',label:'Not attempted'}],120,0.5,s.pct+'%')+
      '<div class="rep-stats"><div><span class="sw" style="background:var(--success)"></span>Correct <b>'+s.c+'</b></div><div><span class="sw" style="background:var(--danger)"></span>Incorrect <b>'+s.w+'</b></div><div><span class="sw" style="background:var(--locked)"></span>Not attempted <b>'+s.n+'</b></div>'+
      '<div class="rep-lvl">Indicative level <b>'+s.lvl+'</b> / 8 <span>(band '+band(s.lvl)+')</span></div></div></div>'+
      '<button class="hub-btn" data-go="'+s.tab+'">Open Test '+s.letter+' →</button></div>';
  }).join('')+'</div>';
  h+='<p class="rep-note">Indicative level = fraction of questions correct × 8, rounded. It is a practice guide only; your teacher awards the real MYP criterion levels.</p></div>';
  var wrap=document.getElementById('wrap'); wrap.innerHTML=h;
  document.querySelector('.slide-progress').style.display='none';
  document.querySelector('.navbar').style.display='none';
  document.getElementById('paletteFab').style.display='none';
  document.getElementById('secSub').textContent='Report — chapter test results by MYP criterion';
  wrap.querySelectorAll('[data-go]').forEach(function(b){ b.addEventListener('click',function(){ activeTab=b.dataset.go; buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); });
}
var _rsReport = renderSlide;
renderSlide = function(){
  if(activeTab==='report'){ renderReport(); buildTabbar(); updateChapterProgress(); updateModePill(); saveState(); return; }
  _rsReport();
};


/* ================= skipped-question return ================= */
function firstSkippedIdx(ts){
  for(var i=0;i<ts.items.length;i++){
    var it=ts.items[i];
    if(MODE==='quiz'){ if(!isSlideAttempted(activeTab,i)) return i; }
    else if(it.status==='skipped'||it.status==='unanswered') return i;
  }
  return -1;
}
function skippedList(ts){
  var out=[]; for(var i=0;i<ts.items.length;i++){ var it=ts.items[i];
    if(MODE==='quiz' ? !isSlideAttempted(activeTab,i) : (it.status==='skipped'||it.status==='unanswered')) out.push(i); }
  return out;
}
function renderSkipGate(ts){
  var list=skippedList(ts);
  var h='<div class="qcard done-card"><div class="big">⏭️</div><h2>You skipped '+list.length+' question'+(list.length>1?'s':'')+'</h2>'+
    '<p style="color:var(--ink-soft);font-size:14px;">Answer them now, or submit the tab as it is. Answers are marked only when you submit.</p>'+
    '<div class="skip-chips">'+list.map(function(i){ return '<button class="chip skip-go" data-i="'+i+'">Q'+(i+1)+'</button>'; }).join('')+'</div>'+
    '<div class="skip-btns"><button class="btn btn-primary" id="btnGoSkipped">Answer skipped questions</button><button class="btn" id="btnSubmitAnyway">Submit anyway</button></div></div>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('navbarInner').innerHTML='';
  var go=function(i){ ts.idx=i; ts.maxReached=Math.max(ts.maxReached,i); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); };
  document.getElementById('btnGoSkipped').addEventListener('click',function(){ go(list[0]); });
  document.querySelectorAll('.skip-go').forEach(function(b){ b.addEventListener('click',function(){ go(parseInt(b.dataset.i,10)); }); });
  document.getElementById('btnSubmitAnyway').addEventListener('click',function(){ ts.submitOK=true; renderFinished(); ts.submitOK=false; });
  saveState();
}
var _rfSkip = renderFinished;
renderFinished = function(){
  var ts=state.tabs[activeTab];
  if(MODE==='quiz' && !ts.submitOK && skippedList(ts).length){ renderSkipGate(ts); return; }
  _rfSkip();
  if(MODE==='learning'){
    var list=skippedList(ts);
    if(list.length){
      var card=document.querySelector('.done-card');
      if(card){ var d=document.createElement('div'); d.className='skip-btns';
        d.innerHTML='<button class="btn btn-primary" id="btnGoSkipped">Attempt skipped questions ('+list.length+')</button>';
        card.appendChild(d);
        document.getElementById('btnGoSkipped').addEventListener('click',function(){ ts.idx=list[0]; ts.recorded=false; renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); }); }
    }
  }
};


/* ================= approx answers (physics: within 1%) ================= */
var _amTools = answerMatches;
answerMatches = function(input,answer,accept,expr){
  if(expr==='approx'){
    var n1=parseNum(input); if(n1===null) return false;
    return [answer].concat(accept||[]).some(function(a){ var n2=parseNum(a); if(n2===null) return false; return Math.abs(n1-n2) <= Math.max(0.011*Math.abs(n2), 1e-9); });
  }
  return _amTools(input,answer,accept,expr);
};

/* ================= palette: every question already reached can be opened ================= */
statusOf = function(tabId,i){
  var ts=state.tabs[tabId];
  if(i>ts.maxReached) return 'locked';
  if(i===ts.idx) return 'current';
  var s=ts.items[i].status;
  if(s==='unanswered') return 'skipped';
  return s;
};

/* ================= on-screen keyboard ================= */
var KB={on:true, page:'num', target:null};
try{ var kbp=localStorage.getItem('sopaan-kb-pref'); if(kbp==='off') KB.on=false; }catch(e){}
function kbSave(){ try{ localStorage.setItem('sopaan-kb-pref', KB.on?'on':'off'); }catch(e){} }
var KEYS_NUM=[['7','8','9','(',')'],['4','5','6','−','/'],['1','2','3','.',','],['0',':','%','°','⌫'],['abc','←','→','Clear','Done']];
var KEYS_FRAC=[['7','8','9','/'],['4','5','6','−'],['1','2','3','space'],['0',',','⌫','Clear'],['abc','←','→','Done']];
var KEYS_ALG=[['7','8','9','x','y','n'],['4','5','6','+','−','a'],['1','2','3','×','÷','b'],['0','.','(',')','^','²'],['/','π','|','t','⌫','Clear'],['abc','←','→','Done']];
function kbLayoutFor(inp){ try{ var ts=state.tabs[activeTab], sl=SLIDES[activeTab][ts.idx], stp=sl.flat[parseInt(inp.dataset.step,10)]; var m=stp.expr, key=String(stp.a[inp.dataset.bkey]||'');
  if(m==='words'||m==='glist'||m==='angle') return 'abc'; if(m===true||m==='pow'||m==='primes') return 'alg';
  if(['fv','fe','fl','fm','fi','flist'].indexOf(m)>=0) return 'frac'; if(m==='dec'||m==='approx'||m==='dlist'||m==='set'||m==='coord'||m==='list'||m==='time') return 'num';
  if(/^[\-−]?\d+ \d+\/\d+$/.test(key)||/^[\-−]?\d+\/\d+$/.test(key)) return 'frac'; if(/[a-df-z]/i.test(key.replace(/pi/gi,''))) return /\d/.test(key)?'alg':'abc'; return 'num'; }catch(e){ return 'num'; } }
var KEYS_CALC=[['7','8','9','x','(',')'],['4','5','6','+','−','^'],['1','2','3','×','/','²'],['0','.','e','eˣ','√','ln'],['sin','cos','tan','t','⌫','Clear'],['abc','←','→','Done']];
var KEYS_ABC=[['q','w','e','r','t','y','u','i','o','p'],['a','s','d','f','g','h','j','k','l','-'],['z','x','c','v','b','n','m',',',':','/'],['123','space','←','→','⌫','Done']];
function kbBuild(){
  var el=document.getElementById('vkb'); if(!el){ el=document.createElement('div'); el.id='vkb'; el.className='vkb'; document.body.appendChild(el);
    el.addEventListener('pointerdown',function(e){ var b=e.target.closest('button[data-k]'); e.preventDefault(); if(b) kbPress(b.dataset.k); });
    el.addEventListener('mousedown',function(e){ e.preventDefault(); }); }
  var rows={num:KEYS_NUM,frac:KEYS_FRAC,alg:KEYS_ALG,abc:KEYS_ABC,calc:KEYS_CALC}[KB.page]||KEYS_NUM;
  el.innerHTML='<div class="vkb-top"><span>⌨️ Keyboard</span><button data-k="device" class="vkb-link">Use device keyboard</button></div>'+
    rows.map(function(r){ return '<div class="vkb-row">'+r.map(function(k){
      var cls='vkb-k'+(/^(abc|123|Done|Clear|⌫|←|→|space)$/.test(k)?' fn':'')+(k==='Done'?' done':'');
      return '<button type="button" class="'+cls+'" data-k="'+k+'">'+(k==='space'?'space':k)+'</button>'; }).join('')+'</div>'; }).join('');
  return el;
}
function kbShow(inp){ KB.target=inp; KB.home=kbLayoutFor(inp); KB.page=KB.home; if(!KB.on) return; var cp=document.getElementById('calcPanel'); if(cp&&cp.classList.contains('show')) return; var el=kbBuild(); var nb=document.querySelector('.navbar'); el.style.bottom=(nb?nb.getBoundingClientRect().height:0)+'px'; el.classList.add('show'); document.body.classList.add('kb-open'); setTimeout(function(){ var r=inp.getBoundingClientRect(), top=el.getBoundingClientRect().top; if(r.bottom>top-12) window.scrollBy({top:r.bottom-top+60,behavior:'smooth'}); else if(r.top<60) window.scrollBy({top:r.top-80,behavior:'smooth'}); },30); }
function kbHide(){ var el=document.getElementById('vkb'); if(el) el.classList.remove('show'); document.body.classList.remove('kb-open'); }
function kbInsert(s){
  var t=KB.target; if(!t||t.disabled) return;
  var a=t.selectionStart==null?t.value.length:t.selectionStart, b=t.selectionEnd==null?a:t.selectionEnd;
  t.value=t.value.slice(0,a)+s+t.value.slice(b); var p=a+s.length; try{ t.setSelectionRange(p,p); }catch(e){}
  t.dispatchEvent(new Event('input',{bubbles:true}));
}
function kbPress(k){
  var t=KB.target; if(k==='device'){ KB.on=false; kbSave(); kbHide(); document.querySelectorAll('.blank-input').forEach(function(i){ i.removeAttribute('inputmode'); }); if(t){ t.blur(); setTimeout(function(){ t.focus(); },50); } showToast('Device keyboard on. Tap ⌨️ on any blank to bring the on-screen keyboard back.'); return; }
  if(k==='Done'){ kbHide(); if(t) t.blur(); return; }
  if(k==='abc'||k==='123'){ KB.page=(k==='abc')?'abc':(KB.home&&KB.home!=='abc'?KB.home:'num'); kbBuild(); return; }
  if(!t) return;
  if(k==='⌫'){ var a=t.selectionStart, b=t.selectionEnd; if(a===b&&a>0){ t.value=t.value.slice(0,a-1)+t.value.slice(b); try{t.setSelectionRange(a-1,a-1);}catch(e){} } else { t.value=t.value.slice(0,a)+t.value.slice(b); try{t.setSelectionRange(a,a);}catch(e){} } t.dispatchEvent(new Event('input',{bubbles:true})); return; }
  if(k==='Clear'){ t.value=''; t.dispatchEvent(new Event('input',{bubbles:true})); return; }
  if(k==='←'||k==='→'){ var p=(t.selectionStart||0)+(k==='←'?-1:1); p=Math.max(0,Math.min(t.value.length,p)); try{t.setSelectionRange(p,p);}catch(e){} return; }
  var map={'−':'-','space':' '}; kbInsert(map[k]!==undefined?map[k]:k);
}
function kbWire(){
  document.querySelectorAll('.blank-input').forEach(function(inp){
    if(inp.dataset.kb) return; inp.dataset.kb='1';
    if(KB.on) inp.setAttribute('inputmode','none');
    inp.addEventListener('focus',function(){ kbShow(inp); });
    var btn=document.createElement('button'); btn.type='button'; btn.className='kb-toggle'; btn.title='On-screen keyboard'; btn.textContent='⌨️'; btn.tabIndex=-1;
    btn.addEventListener('mousedown',function(e){ e.preventDefault(); });
    btn.addEventListener('click',function(){ KB.on=true; kbSave(); document.querySelectorAll('.blank-input').forEach(function(i){ i.setAttribute('inputmode','none'); }); inp.focus(); kbShow(inp); });
    if(!inp.disabled) inp.insertAdjacentElement('afterend',btn);
  });
}
document.addEventListener('focusout',function(e){ setTimeout(function(){ var a=document.activeElement; if(!a||!a.classList||!a.classList.contains('blank-input')){ if(!document.querySelector('#vkb:hover')) kbHide(); } },120); });

/* ================= calculator ================= */
var CALC={expr:'', ans:0};
function calcEval(src){
  var s=String(src).replace(/×/g,'*').replace(/÷/g,'/').replace(/−/g,'-').replace(/π/g,'(PI)').replace(/Ans/g,'('+CALC.ans+')').replace(/\^/g,'**').replace(/√\(/g,'sqrt(').replace(/²/g,'**2').replace(/E/g,'*10**');
  s=s.replace(/(^|[(*\/+\-,])-/g,'$1(-1)*');
  if(/[^0-9+\-*/().,a-z A-Z]/.test(s)) throw 0;
  var ok=s.replace(/sin|cos|tan|asin|acos|atan|sqrt|log|ln|PI|abs/g,''); if(/[a-zA-Z]/.test(ok)) throw 0;
  var f=new Function('sin','cos','tan','asin','acos','atan','sqrt','log','ln','PI','abs','return ('+s+');');
  var d=Math.PI/180;
  var v=f(function(x){return Math.sin(x*d);},function(x){return Math.cos(x*d);},function(x){return Math.tan(x*d);},
    function(x){return Math.asin(x)/d;},function(x){return Math.acos(x)/d;},function(x){return Math.atan(x)/d;},Math.sqrt,Math.log10,Math.log,Math.PI,Math.abs);
  if(typeof v!=='number'||!isFinite(v)) throw 0; return v;
}
function fmtNum(v){ if(Math.abs(v)>=1e10||(Math.abs(v)<1e-6&&v!==0)) return v.toExponential(6).replace(/\.?0+e/,'e'); return String(parseFloat(v.toPrecision(10))); }
var CKEYS=[['sin(','cos(','tan(','√(','^','²'],['asin(','acos(','atan(','(',')','π'],['7','8','9','÷','⌫','AC'],['4','5','6','×','E','Ans'],['1','2','3','−','(−)','Insert'],['0','.','=','+']];
function openCalc(){
  var p=document.getElementById('calcPanel');
  if(!p){ p=document.createElement('div'); p.id='calcPanel'; p.className='tool-panel calc';
    p.innerHTML='<div class="tp-head"><b>🧮 Calculator</b><span class="tp-note">degrees · tap a blank, then Insert</span><button class="tp-x" data-c="close">✕</button></div>'+
      '<div class="calc-disp"><div class="calc-expr" id="calcExpr"></div><div class="calc-res" id="calcRes">0</div></div>'+
      '<div class="calc-keys">'+CKEYS.map(function(r){ return r.map(function(k){ return '<button type="button" data-c="'+k+'" class="'+(k==='='?'eq':(/^(AC|⌫|Insert)$/.test(k)?'fn':''))+'">'+({'sin(':'sin','cos(':'cos','tan(':'tan','asin(':'sin⁻¹','acos(':'cos⁻¹','atan(':'tan⁻¹','√(':'√'}[k]||k)+'</button>'; }).join(''); }).join('')+'</div>';
    document.body.appendChild(p);
    p.addEventListener('mousedown',function(e){ if(e.target.closest('button')) e.preventDefault(); });
    p.addEventListener('click',function(e){ var b=e.target.closest('button[data-c]'); if(!b) return; calcKey(b.dataset.c); });
  }
  kbHide(); var nb=document.querySelector('.navbar'); p.style.bottom=((nb?nb.getBoundingClientRect().height:0)+8)+'px'; p.classList.add('show'); document.body.classList.add('calc-open'); calcShow();
}
function calcShow(res){ document.getElementById('calcExpr').textContent=CALC.expr||' '; if(res!==undefined) document.getElementById('calcRes').textContent=res; }
function calcKey(k){
  if(k==='close'){ document.getElementById('calcPanel').classList.remove('show'); document.body.classList.remove('calc-open'); return; }
  if(k==='AC'){ CALC.expr=''; calcShow('0'); return; }
  if(k==='⌫'){ CALC.expr=CALC.expr.replace(/(asin\(|acos\(|atan\(|sin\(|cos\(|tan\(|√\(|Ans|.)$/,''); calcShow(); return; }
  if(k==='='){ try{ var v=calcEval(CALC.expr); CALC.ans=v; calcShow(fmtNum(v)); }catch(e){ calcShow('Error'); } return; }
  if(k==='(−)'){ CALC.expr+='−'; calcShow(); return; }
  if(k==='Insert'){ var r=document.getElementById('calcRes').textContent; if(KB.target && !KB.target.disabled && r!=='Error'){ KB.target.value=r; KB.target.dispatchEvent(new Event('input',{bubbles:true})); showToast('Inserted '+r+' into the blank.'); } else showToast('Tap a blank first, then press Insert.'); return; }
  CALC.expr+=k; calcShow();
}

/* ================= Desmos ================= */
var DESMOS_KEY='dcb31709b452b1cf9dc26972add0fda6', desmosCalc=null, desmosLoading=false;
function openDesmos(exprs){
  var p=document.getElementById('desmosPanel');
  if(!p){ p=document.createElement('div'); p.id='desmosPanel'; p.className='tool-panel desmos';
    p.innerHTML='<div class="tp-head"><b>📈 Desmos graphing calculator</b><button class="tp-x" id="desmosReset">Reset graph</button><button class="tp-x" id="desmosClose">✕</button></div><div id="desmosBox"><div class="desmos-msg">Loading Desmos…</div></div>';
    document.body.appendChild(p);
    document.getElementById('desmosClose').addEventListener('click',function(){ p.classList.remove('show'); });
    document.getElementById('desmosReset').addEventListener('click',function(){ if(desmosCalc) desmosSet(p._exprs||[]); });
  }
  p._exprs=exprs||[]; p.classList.add('show');
  if(window.Desmos){ desmosInit(); desmosSet(p._exprs); return; }
  if(desmosLoading) return; desmosLoading=true;
  var sc=document.createElement('script'); sc.src='https://www.desmos.com/api/v1.9/calculator.js?apiKey='+DESMOS_KEY;
  sc.onload=function(){ desmosInit(); desmosSet(p._exprs); };
  sc.onerror=function(){ desmosLoading=false; document.getElementById('desmosBox').innerHTML='<div class="desmos-msg">Desmos needs an internet connection. <a href="https://www.desmos.com/calculator" target="_blank" rel="noopener">Open Desmos in a new tab</a>.</div>'; };
  document.head.appendChild(sc);
}
function desmosInit(){ if(desmosCalc) return; var box=document.getElementById('desmosBox'); box.innerHTML=''; desmosCalc=Desmos.GraphingCalculator(box,{expressionsCollapsed:false,settingsMenu:false,border:false,degreeMode:true}); }
function desmosSet(exprs){ if(!desmosCalc) return; desmosCalc.setBlank(); (exprs||[]).forEach(function(e,i){ if(typeof e==='string') desmosCalc.setExpression({id:'e'+i,latex:e}); else desmosCalc.setExpression(Object.assign({id:'e'+i},e)); }); }

/* ================= toolbar on each question ================= */
var _rsTools = renderSlide;
renderSlide = function(){
  _rsTools();
  kbHide();
  if(activeTab==='theory'||activeTab==='report') return;
  var ts=state.tabs[activeTab]; if(!ts) return;
  var slide=SLIDES[activeTab][ts.idx], card=document.querySelector('#wrap .qcard');
  if(card && slide && slide.tools && slide.tools.length && !card.querySelector('.tool-bar')){
    var bar=document.createElement('div'); bar.className='tool-bar';
    bar.innerHTML=(slide.tools.indexOf('calc')>=0?'<button type="button" class="tool-btn" data-t="calc">🧮 Calculator</button>':'')+
                  (slide.tools.indexOf('desmos')>=0?'<button type="button" class="tool-btn" data-t="desmos">📈 Desmos graph</button>':'');
    card.insertBefore(bar, card.firstChild);
    bar.addEventListener('click',function(e){ var b=e.target.closest('[data-t]'); if(!b) return; if(b.dataset.t==='calc') openCalc(); else openDesmos(slide.desmos||[]); });
  }
  kbWire();
};



/* ================= signed fractions in text: {−3/4}, {3/−4}, {−2 1/3}, {p/q} ================= */
fr = function(s){ return String(s).replace(/&lt;(\/?)(b|sup|sub|i)>/g,'<$1$2>')
  .replace(/\{([−-]?\d+) (\d+)\/(\d+)\}/g,'<span class="mx">$1<span class="fq"><span>$2</span><span>$3</span></span></span>')
  .replace(/\{([−-]?[A-Za-z0-9]+)\/([−-]?[A-Za-z0-9]+)\}/g,'<span class="fq"><span>$1</span><span>$2</span></span>'); };
/* ================= BMA badge → main page of this sheet (theory hub) ================= */
(function(){
  var c=document.querySelector('.brand .crest'); if(!c) return;
  var a=document.createElement('button'); a.type='button'; a.className='crest crest-home'; a.title='Back to the main page (theory notes)'; a.setAttribute('aria-label','Main page');
  a.innerHTML='BM<span class="crest-h">⌂</span>'; c.parentNode.replaceChild(a,c);
  a.addEventListener('click',function(){
    if(!student||!MODE){ window.scrollTo({top:0,behavior:'smooth'}); return; }
    if(typeof kbHide==='function') kbHide(); if(typeof SP!=='undefined'&&SP.on) spToggle(false);
    var cp=document.getElementById('calcPanel'); if(cp) cp.classList.remove('show'); document.body.classList.remove('calc-open');
    activeTab = (typeof THEORY!=='undefined') ? 'theory' : TAB_DEFS[0].id;
    buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'});
  });
})();

/* ================= session clock: starts at sign-in and keeps running ================= */
var CLK={t0:null};
(function(){
  var row=document.querySelector('.brand .brand-row'); if(!row) return;
  var d=document.createElement('div'); d.className='bmasw off'; d.id='swBox'; d.title='Time since you signed in';
  d.innerHTML='<span class="bmasw-ic">⏱</span><span class="bmasw-t" id="swT">00:00</span>';
  row.appendChild(d); setInterval(swTick,1000);
})();
function swFmt(s){ s=Math.floor(s||0); var h=Math.floor(s/3600), m=Math.floor(s%3600/60), x=s%60; return (h?h+':'+String(m).padStart(2,'0'):String(m).padStart(2,'0'))+':'+String(x).padStart(2,'0'); }
function swTick(){
  var box=document.getElementById('swBox'); if(!box) return;
  if(student && !CLK.t0) CLK.t0=Date.now();
  if(!student) CLK.t0=null;
  box.classList.toggle('off',!CLK.t0);
  document.getElementById('swT').textContent = CLK.t0 ? swFmt((Date.now()-CLK.t0)/1000) : '00:00';
}
function swTab(){ try{ if(!state||!state.tabs||activeTab==='theory'||activeTab==='report') return null; return state.tabs[activeTab]||null; }catch(e){ return null; } }
var _rsSW = renderSlide;
renderSlide = function(){ _rsSW(); swTick(); };
var _rfSW = renderFinished;
renderFinished = function(){ _rfSW(); var done=document.querySelector('#wrap .done-card'); if(CLK.t0 && done && !done.querySelector('.bmasw-done')){ var p=document.createElement('p'); p.className='bmasw-done'; p.textContent='⏱ Time since sign-in: '+swFmt((Date.now()-CLK.t0)/1000); var h2=done.querySelector('h2'); if(h2) h2.insertAdjacentElement('afterend',p); else done.appendChild(p); } };

/* ================= scratchpad (Khan-style, 4 pens) ================= */
var SP={on:false, draw:true, color:'ink', size:3, erase:false, store:{}, key:null, cv:null, ctx:null, down:false, last:null};
var SP_COL={ink:null, blue:'#2563EB', red:'#DC2626', green:'#16A34A'};
function spInk(){ return getComputedStyle(document.documentElement).getPropertyValue('--ink').trim()||'#211E1A'; }
function spKey(){ var ts=swTab(); return ts ? (MODE+'|'+activeTab+'|'+ts.idx) : null; }
function spBuild(){
  if(SP.cv) return;
  var cv=document.createElement('canvas'); cv.id='spCanvas'; cv.className='sp-canvas'; document.body.appendChild(cv);
  var bar=document.createElement('div'); bar.id='spBar'; bar.className='sp-bar';
  bar.innerHTML='<span class="sp-lbl">✏️ Scratchpad</span>'+
    ['ink','blue','red','green'].map(function(c){ return '<button type="button" class="sp-pen" data-c="'+c+'" title="'+(c==='ink'?'black':c)+' pen"><i style="background:'+(c==='ink'?'var(--ink)':SP_COL[c])+'"></i></button>'; }).join('')+
    '<button type="button" class="sp-tool" data-t="erase" title="Eraser">🧽</button><button type="button" class="sp-tool" data-t="size" title="Pen size">●</button><button type="button" class="sp-tool" data-t="scroll" title="Pause drawing to scroll or answer">✋</button>'+
    '<button type="button" class="sp-tool" data-t="clear" title="Clear page">🗑</button><button type="button" class="sp-tool" data-t="close" title="Close scratchpad">✕</button>';
  document.body.appendChild(bar);
  bar.addEventListener('click',function(e){ var b=e.target.closest('button'); if(!b) return;
    if(b.dataset.c){ SP.color=b.dataset.c; SP.erase=false; SP.draw=true; }
    else if(b.dataset.t==='erase'){ SP.erase=true; SP.draw=true; }
    else if(b.dataset.t==='size'){ SP.size = SP.size===3?6:(SP.size===6?1.5:3); b.textContent = SP.size===6?'⬤':(SP.size===1.5?'·':'●'); }
    else if(b.dataset.t==='scroll'){ SP.draw=!SP.draw; }
    else if(b.dataset.t==='clear'){ spClear(); }
    else if(b.dataset.t==='close'){ spToggle(false); return; }
    spUI(); });
  SP.cv=cv; SP.ctx=cv.getContext('2d');
  cv.addEventListener('pointerdown',function(e){ if(!SP.draw) return; e.preventDefault(); cv.setPointerCapture(e.pointerId); SP.down=true; SP.last=spPt(e); spDot(SP.last); });
  cv.addEventListener('pointermove',function(e){ if(!SP.down) return; e.preventDefault(); var p=spPt(e); spLine(SP.last,p); SP.last=p; });
  var up=function(){ if(SP.down){ SP.down=false; spSave(); } };
  cv.addEventListener('pointerup',up); cv.addEventListener('pointercancel',up); cv.addEventListener('pointerleave',up);
  window.addEventListener('resize',function(){ if(SP.on) spFit(true); });
}
function spPt(e){ var r=SP.cv.getBoundingClientRect(); return {x:e.clientX-r.left, y:e.clientY-r.top}; }
function spStyle(){ var c=SP.ctx; c.lineCap='round'; c.lineJoin='round'; c.globalCompositeOperation=SP.erase?'destination-out':'source-over'; c.strokeStyle=c.fillStyle=(SP.color==='ink'?spInk():SP_COL[SP.color]); c.lineWidth=SP.erase?22:SP.size; }
function spDot(p){ spStyle(); var c=SP.ctx; c.beginPath(); c.arc(p.x,p.y,(SP.erase?11:SP.size/2),0,Math.PI*2); c.fill(); }
function spLine(a,b){ spStyle(); var c=SP.ctx; c.beginPath(); c.moveTo(a.x,a.y); c.lineTo(b.x,b.y); c.stroke(); }
function spSave(){ if(SP.key&&SP.cv){ try{ SP.store[SP.key]=SP.cv.toDataURL(); }catch(e){} } }
function spClear(){ if(!SP.ctx) return; SP.ctx.save(); SP.ctx.setTransform(1,0,0,1,0,0); SP.ctx.clearRect(0,0,SP.cv.width,SP.cv.height); SP.ctx.restore(); if(SP.key) delete SP.store[SP.key]; }
function spFit(keep){
  var wrap=document.getElementById('wrap'); if(!wrap||!SP.cv) return;
  var r=wrap.getBoundingClientRect(), top=r.top+window.scrollY, h=Math.max(wrap.scrollHeight, window.innerHeight-r.top)+40, w=document.documentElement.clientWidth;
  var old=keep&&SP.key?SP.store[SP.key]:null, dpr=window.devicePixelRatio||1;
  SP.cv.style.top=top+'px'; SP.cv.style.left='0px'; SP.cv.style.width=w+'px'; SP.cv.style.height=h+'px';
  SP.cv.width=Math.round(w*dpr); SP.cv.height=Math.round(h*dpr); SP.ctx.setTransform(dpr,0,0,dpr,0,0);
  if(old){ var im=new Image(); im.onload=function(){ SP.ctx.save(); SP.ctx.setTransform(1,0,0,1,0,0); SP.ctx.drawImage(im,0,0); SP.ctx.restore(); }; im.src=old; }
}
function spLoad(){ spSave(); SP.key=spKey(); spFit(false); var d=SP.key&&SP.store[SP.key]; if(d){ var im=new Image(); im.onload=function(){ SP.ctx.save(); SP.ctx.setTransform(1,0,0,1,0,0); SP.ctx.drawImage(im,0,0); SP.ctx.restore(); }; im.src=d; } }
function spUI(){
  var bar=document.getElementById('spBar'); if(!bar) return;
  bar.querySelectorAll('.sp-pen').forEach(function(b){ b.classList.toggle('on', !SP.erase && SP.draw && b.dataset.c===SP.color); });
  bar.querySelector('[data-t=erase]').classList.toggle('on', SP.erase && SP.draw);
  bar.querySelector('[data-t=scroll]').classList.toggle('on', !SP.draw);
  SP.cv.classList.toggle('passive', !SP.draw);
  var fb=document.getElementById('spFab'); if(fb) fb.classList.toggle('on',SP.on);
}
function spToggle(on){
  spBuild(); SP.on=(on===undefined)?!SP.on:on;
  document.body.classList.toggle('sp-open',SP.on); SP.cv.style.display=SP.on?'block':'none'; document.getElementById('spBar').style.display=SP.on?'flex':'none';
  if(SP.on){ SP.draw=true; SP.erase=false; spLoad(); if(typeof kbHide==='function') kbHide(); } else { spSave(); }
  spUI();
}
(function(){ var f=document.createElement('button'); f.type='button'; f.id='spFab'; f.className='sp-fab'; f.innerHTML='✏️ <span>Scratchpad</span>'; f.title='Open a scratchpad to write your working'; f.addEventListener('click',function(){ spToggle(); }); document.body.appendChild(f); })();
var _rsSP = renderSlide;
renderSlide = function(){ _rsSP(); var fab=document.getElementById('spFab'); var q=!!swTab(); if(fab) fab.style.display=q?'':'none'; if(!q && SP.on) spToggle(false); if(SP.on) setTimeout(spLoad,30); };


/* ================= v4: attempt classification ================= */
function v4Class(item){
  if(!item) return 'un';
  if(item.status==='skipped') return 'sk';
  if(item.status==='unanswered') return 'un';
  if(item.stepStates){ // step question
    if(item.status!=='correct' && item.status!=='revealed') return 'un';
    if(item.status==='revealed' || item.stepStates.some(function(s){return s.status==='revealed';})) return 'w';
    return item.stepStates.some(function(s){return (s.attempts||0)>0;}) ? 'c2' : 'c1';
  }
  if(item.status==='revealed') return 'w';
  if(item.status==='correct') return (item.attempts||0)>0 ? 'c2' : 'c1';
  if(item.status==='wrong'||item.status==='incorrect') return 'w';
  return 'un';
}
function v4Counts(items){ var c={n:items.length,c1:0,c2:0,w:0,sk:0,un:0}; items.forEach(function(it){ c[v4Class(it)]++; }); return c; }

/* ================= v4: My record with attempt columns ================= */
renderRecord = function(){
  showChrome(false);
  var tabLabel=function(id){ var t=TAB_DEFS.find(function(x){return x.id===id;}); return t?t.label:id; };
  var title=(document.querySelector('.chapter-title')||{}).textContent||'';
  var h='<div class="rec-card"><h2>'+esc(student.name)+'’s record</h2><p class="rec-empty" style="margin:0 0 12px;">Roll '+esc(student.roll)+(title?' · '+esc(title):'')+'</p>';
  var st=appState.learning;
  h+='<h3>📘 Learning Sheet — attempts</h3><p class="v4leg"><b>1st ✓</b> correct on the first attempt · <b>2nd ✓</b> correct on the second attempt · <b>Wrong</b> still wrong after two attempts (answer revealed) · <b>Skip</b> skipped<span class="v4left"> · <b>Left</b> not done yet</span></p>';
  if(!st){ h+='<p class="rec-empty">Not started yet.</p>'; }
  else {
    var T={n:0,c1:0,c2:0,w:0,sk:0,un:0};
    h+='<div class="rec-table-wrap"><table class="rec-table v4rec"><thead><tr><th>Sheet</th><th>Qs</th><th>1st ✓</th><th>2nd ✓</th><th>Wrong</th><th>Skip</th><th class="v4left">Left</th></tr></thead><tbody>';
    TAB_DEFS.forEach(function(td){ var tt=st.tabs[td.id]; if(!tt||!tt.items||!tt.items.length) return; var c=v4Counts(tt.items);
      ['n','c1','c2','w','sk','un'].forEach(function(k){ T[k]+=c[k]; });
      h+='<tr><td>'+td.label+'</td><td>'+c.n+'</td><td class="v4g">'+c.c1+'</td><td class="v4o">'+c.c2+'</td><td class="v4r">'+c.w+'</td><td>'+c.sk+'</td><td class="v4left">'+c.un+'</td></tr>'; });
    h+='<tr class="v4tot"><td>Total</td><td>'+T.n+'</td><td class="v4g">'+T.c1+'</td><td class="v4o">'+T.c2+'</td><td class="v4r">'+T.w+'</td><td>'+T.sk+'</td><td class="v4left">'+T.un+'</td></tr>';
    h+='</tbody></table></div>';
    var doneN=T.c1+T.c2+T.w; if(doneN){ h+='<p class="v4sum">Of '+doneN+' questions answered: <b>'+Math.round(T.c1/doneN*100)+'%</b> right first time, <b>'+Math.round(T.c2/doneN*100)+'%</b> right on the second try, <b>'+Math.round(T.w/doneN*100)+'%</b> still wrong after two tries.</p>'; }
  }
  var q=appState.quiz;
  h+='<h3>📝 Quiz Mode</h3>';
  if(!q){ h+='<p class="rec-empty">Not started yet.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table v4rec"><thead><tr><th>Sheet</th><th>Qs</th><th>Status</th><th>Correct</th><th>Wrong</th></tr></thead><tbody>';
    TAB_DEFS.forEach(function(td){ var tt=q.tabs[td.id]; if(!tt||!tt.items||!tt.items.length) return; var n=tt.items.length, cor=0, att=0;
      tt.items.forEach(function(it){ if(it.status!=='unanswered'||it.choice!==undefined) att++; });
      var rec=records.filter(function(r){ return r.mode==='quiz'&&r.tab===td.id; })[0];
      if(rec){ cor=rec.correct; att=Math.max(att,rec.total); }
      h+='<tr><td>'+td.label+'</td><td>'+n+'</td><td>'+(rec?'Finished':att+' / '+n)+'</td><td class="v4g">'+(rec?cor:'—')+'</td><td class="v4r">'+(rec?(rec.total-cor):'—')+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><div class="rec-card"><h3>Finished sheets (latest first)</h3>';
  if(!records.length){ h+='<p class="rec-empty">No sheets finished yet. Each time you finish a sheet, your score is recorded here.</p>'; }
  else {
    h+='<div class="rec-table-wrap"><table class="rec-table v4rec"><thead><tr><th>When</th><th>Mode</th><th>Sheet</th><th>Score</th><th>1st ✓</th><th>2nd ✓</th><th>Wrong</th></tr></thead><tbody>';
    records.forEach(function(r){ h+='<tr><td>'+fmtDate(r.at)+'</td><td>'+(r.mode==='quiz'?'Quiz':'Learning')+'</td><td>'+tabLabel(r.tab)+'</td><td>'+r.correct+' / '+r.total+'</td><td>'+(r.c1!=null?r.c1:'—')+'</td><td>'+(r.c2!=null?r.c2:'—')+'</td><td>'+(r.w!=null?r.w:(r.mode==='quiz'?r.total-r.correct:'—'))+'</td></tr>'; });
    h+='</tbody></table></div>';
  }
  h+='</div><button class="btn btn-primary" id="btnBack">'+(MODE?'Back to practice':'Choose a mode')+'</button>';
  document.getElementById('wrap').innerHTML=h;
  document.getElementById('btnBack').addEventListener('click', function(){ if(MODE){ showChrome(true); buildTabbar(); renderSlide(); } else renderModePicker(); });
  window.scrollTo({top:0});
};
var _v4add = addRecord;
addRecord = function(mode, tabId, correct, revealed, skipped, total){
  _v4add(mode, tabId, correct, revealed, skipped, total);
  try{ if(mode==='learning'&&records[0]){ var c=v4Counts(state.tabs[tabId].items); records[0].c1=c.c1; records[0].c2=c.c2; records[0].w=c.w; saveState(); } }catch(e){}
};

/* ================= v4: celebration ================= */
function v4Cracker(){
  var ctx=ensureAudio(); if(!ctx) return; try{ if(ctx.state==='suspended') ctx.resume(); }catch(e){}
  var now=ctx.currentTime;
  function pop(t, vol, dur, hp){
    var len=Math.floor(ctx.sampleRate*dur), buf=ctx.createBuffer(1,len,ctx.sampleRate), d=buf.getChannelData(0);
    for(var i=0;i<len;i++){ d[i]=(Math.random()*2-1)*Math.pow(1-i/len,3); }
    var src=ctx.createBufferSource(); src.buffer=buf;
    var f=ctx.createBiquadFilter(); f.type='highpass'; f.frequency.value=hp;
    var g=ctx.createGain(); g.gain.setValueAtTime(vol,t); g.gain.exponentialRampToValueAtTime(0.001,t+dur);
    src.connect(f); f.connect(g); g.connect(ctx.destination); src.start(t); src.stop(t+dur+0.02);
  }
  pop(now,0.9,0.35,300);                                   // big bang
  for(var k=0;k<14;k++){ pop(now+0.35+Math.random()*1.3, 0.25+Math.random()*0.35, 0.05+Math.random()*0.08, 1500+Math.random()*2500); } // crackles
  [523.25,659.25,783.99,1046.5].forEach(function(fq,i){ var o=ctx.createOscillator(), g=ctx.createGain(); o.type='triangle'; o.frequency.value=fq;
    var t=now+0.15+i*0.12; g.gain.setValueAtTime(0.0001,t); g.gain.exponentialRampToValueAtTime(0.18,t+0.03); g.gain.exponentialRampToValueAtTime(0.001,t+0.5);
    o.connect(g); g.connect(ctx.destination); o.start(t); o.stop(t+0.55); });
}
function v4Confetti(){
  var cv=document.createElement('canvas'); cv.className='v4conf'; document.body.appendChild(cv);
  var W=cv.width=window.innerWidth*(window.devicePixelRatio||1), H=cv.height=window.innerHeight*(window.devicePixelRatio||1), s=(window.devicePixelRatio||1);
  var ctx=cv.getContext('2d'), cols=['#e8b13a','#d9534f','#2e86de','#27ae60','#9b59b6','#f39c12','#1abc9c','#ff6b9a'], P=[];
  function burst(x,y,n){ for(var i=0;i<n;i++){ var a=Math.random()*Math.PI*2, v=(4+Math.random()*9)*s;
    P.push({x:x,y:y,vx:Math.cos(a)*v,vy:Math.sin(a)*v-6*s,w:(6+Math.random()*7)*s,h:(4+Math.random()*5)*s,r:Math.random()*6,vr:(Math.random()-.5)*.4,c:cols[i%cols.length],life:0,flyer:Math.random()<.25}); } }
  burst(W*0.2,H*0.35,90); burst(W*0.8,H*0.35,90); setTimeout(function(){ burst(W*0.5,H*0.25,120); },380); setTimeout(function(){ burst(W*0.35,H*0.3,70); burst(W*0.65,H*0.3,70); },800);
  var t0=performance.now();
  (function frame(t){
    ctx.clearRect(0,0,W,H);
    P.forEach(function(p){ p.vy+=0.22*s; p.vx*=0.985; p.vy*=0.985; p.x+=p.vx; p.y+=p.vy; p.r+=p.vr; p.life++;
      ctx.save(); ctx.translate(p.x,p.y); ctx.rotate(p.r); ctx.fillStyle=p.c;
      if(p.flyer){ ctx.fillRect(-p.w*1.4,-1.5*s,p.w*2.8,3*s); } else { ctx.fillRect(-p.w/2,-p.h/2,p.w,p.h*Math.abs(Math.cos(p.life/6))); }
      ctx.restore(); });
    if(t-t0<4200) requestAnimationFrame(frame); else cv.remove();
  })(t0);
}
function v4NextTab(){
  var i=TAB_DEFS.findIndex(function(t){return t.id===activeTab;});
  for(var j=i+1;j<TAB_DEFS.length;j++){ var id=TAB_DEFS[j].id; if(id!=='theory' && SLIDES[id] && SLIDES[id].length) return TAB_DEFS[j]; }
  return null;
}
function v4Celebrate(){
  var done=document.querySelector('#wrap .done-card'); if(!done || done.dataset.v4) return; done.dataset.v4='1';
  var ts=state.tabs[activeTab], c=v4Counts(ts.items), n=ts.items.length;
  var first=(student&&student.name)?String(student.name).split(' ')[0]:'';
  var pct=MODE==='quiz'?null:Math.round((c.c1+c.c2)/Math.max(n,1)*100);
  var msg = pct===null ? 'You finished this sheet!' : (pct>=90?'Outstanding work!':pct>=75?'Excellent effort!':pct>=50?'Well done — keep going!':'Great persistence — every try makes you stronger!');
  var banner=document.createElement('div'); banner.className='v4ban';
  banner.innerHTML='<div class="v4trophy">🏆</div><div class="v4h">Congratulations'+(first?', '+esc(first):'')+'!</div><div class="v4m">'+msg+'</div>'+
    (MODE==='quiz'?'':'<div class="v4pills"><span class="v4p g">✅ '+c.c1+' first attempt</span><span class="v4p o">🔁 '+c.c2+' second attempt</span><span class="v4p r">❌ '+c.w+' finally wrong</span>'+(c.sk?'<span class="v4p s">⏭ '+c.sk+' skipped</span>':'')+'</div>');
  done.insertBefore(banner, done.firstChild);
  var nx=v4NextTab(), wrapB=document.createElement('div'); wrapB.className='v4next';
  if(nx){ wrapB.innerHTML='<button class="btn btn-primary v4go" id="v4Next">Next sheet: '+nx.label+' →</button>'; }
  else if(SLIDES.report!==undefined || TAB_DEFS.some(function(t){return t.id==='report';})){ wrapB.innerHTML='<button class="btn btn-primary v4go" id="v4Next">📊 View my report →</button>'; }
  else { wrapB.innerHTML='<button class="btn btn-primary v4go" id="v4Next">⌂ Back to the home page</button>'; }
  banner.appendChild(wrapB);
  document.getElementById('v4Next').addEventListener('click',function(){
    var t=nx?nx.id:(TAB_DEFS.some(function(x){return x.id==='report';})?'report':(TAB_DEFS[0]&&TAB_DEFS[0].id));
    activeTab=t; showChrome(true); buildTabbar(); renderSlide(); window.scrollTo({top:0,behavior:'smooth'}); });
  setTimeout(function(){ var r=banner.getBoundingClientRect(); window.scrollBy({top:r.top-110,behavior:'smooth'}); },60);
  v4Confetti(); v4Cracker();
}
var _v4rf = renderFinished;
renderFinished = function(){ _v4rf.apply(this,arguments); try{ v4Celebrate(); }catch(e){ console.log('v4',e); } };


/* ================= calculus answer mode ================= */
function calcCompile(src){
  var s=String(src).replace(/\s+/g,'').replace(/[×∗·]/g,'*').replace(/÷/g,'/').replace(/[−–—]/g,'-')
    .replace(/²/g,'^2').replace(/³/g,'^3').replace(/π/g,'#').replace(/eˣ/g,'e^x');
  if(s.indexOf('=')>=0) s=s.slice(s.lastIndexOf('=')+1);
  var FN=['sqrt','abs','ln','log','exp','sin','cos','tan','sec','csc','cot','pi'];
  var i=0,toks=[];
  while(i<s.length){
    var ch=s[i];
    if(/[0-9.]/.test(ch)){ var j=i; while(j<s.length&&/[0-9.]/.test(s[j])) j++; toks.push({k:'n',v:parseFloat(s.slice(i,j))}); i=j; continue; }
    if(ch==='√'){ toks.push({k:'f',v:'sqrt'}); i++; continue; }
    if(/[a-zA-Z#]/.test(ch)){
      var hit=null; for(var q=0;q<FN.length;q++){ if(s.substr(i,FN[q].length).toLowerCase()===FN[q]){ hit=FN[q]; break; } }
      if(hit==='pi'){ toks.push({k:'v',v:'#'}); i+=2; continue; }
      if(hit){ toks.push({k:'f',v:hit}); i+=hit.length; continue; }
      toks.push({k:'v',v:ch}); i++; continue; }
    if('+-*/^()|'.indexOf(ch)>=0){ toks.push({k:ch}); i++; continue; }
    return null;
  }
  // absolute value bars -> abs( )
  var t2=[],open=false; for(var a=0;a<toks.length;a++){ var tk=toks[a]; if(tk.k==='|'){ if(!open){ t2.push({k:'f',v:'abs'}); t2.push({k:'('}); open=true; } else { t2.push({k:')'}); open=false; } } else t2.push(tk); }
  toks=t2;
  var out=[];
  for(var t=0;t<toks.length;t++){ var A=toks[t], B=out[out.length-1];
    if(B&&(B.k==='n'||B.k==='v'||B.k===')')&&(A.k==='n'||A.k==='v'||A.k==='('||A.k==='f')) out.push({k:'&'});
    out.push(A); }
  var p=0; function pk(){ return out[p]; }
  var F={sqrt:Math.sqrt,ln:Math.log,log:function(x){return Math.log(x)/Math.LN10;},exp:Math.exp,sin:Math.sin,cos:Math.cos,tan:Math.tan,
    sec:function(x){return 1/Math.cos(x);},csc:function(x){return 1/Math.sin(x);},cot:function(x){return 1/Math.tan(x);},abs:Math.abs};
  function E(){ var n=T(); while(pk()&&(pk().k==='+'||pk().k==='-')){ var o=out[p++].k,r=T(); n=(function(l,r,o){return function(e){return o==='+'?l(e)+r(e):l(e)-r(e);};})(n,r,o);} return n; }
  function T(){ var n=I(); while(pk()&&(pk().k==='*'||pk().k==='/')){ var o=out[p++].k,r=I(); n=(function(l,r,o){return function(e){return o==='*'?l(e)*r(e):l(e)/r(e);};})(n,r,o);} return n; }
  function I(){ var n=U(); while(pk()&&pk().k==='&'){ p++; var r=P(); n=(function(l,r){return function(e){return l(e)*r(e);};})(n,r);} return n; }
  function U(){ if(pk()&&pk().k==='-'){ p++; var u=U(); return function(e){return -u(e);}; } if(pk()&&pk().k==='+'){ p++; return U(); } return P(); }
  function P(){ var b=Aa(); if(pk()&&pk().k==='^'){ p++; var x=U(); return function(e){return Math.pow(b(e),x(e));}; } return b; }
  function Aa(){ var t=out[p++]; if(!t) throw 0;
    if(t.k==='n') return function(){return t.v;};
    if(t.k==='v'){ if(t.v==='#') return function(){return Math.PI;}; if(t.v==='e') return function(){return Math.E;}; return function(e){return e[t.v];}; }
    if(t.k==='('){ var n=E(); if(!pk()||pk().k!==')') throw 0; p++; return n; }
    if(t.k==='f'){ var fn=F[t.v]; var ex=null;
      if(pk()&&pk().k==='^'){ p++; ex=Aa(); if(pk()&&pk().k==='&') p++; }            // sin^2(x)
      var arg; if(pk()&&pk().k==='('){ p++; arg=E(); if(!pk()||pk().k!==')') throw 0; p++; } else arg=P();
      return ex? function(e){ return Math.pow(fn(arg(e)),ex(e)); } : function(e){ return fn(arg(e)); }; }
    throw 0; }
  try{ var f=E(); if(p!==out.length) return null; return f; }catch(e){ return null; }
}
function calcEqual(input,answer){
  var f=calcCompile(input), g=calcCompile(answer); if(!f||!g) return false;
  var hits=0;
  for(var trial=0;trial<14;trial++){
    var env={}; 'abcdfghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ'.split('').forEach(function(c){ env[c]=0.35+Math.random()*2.3; });
    var x=f(env), y=g(env); if(!isFinite(x)||!isFinite(y)) continue;
    if(Math.abs(x-y)>1e-6*Math.max(1,Math.abs(x),Math.abs(y))) return false; hits++;
  }
  return hits>=4;
}
(function(){
  var _am=answerMatches;
  answerMatches=function(input,answer,accept,expr){
    if(expr==='calc'){ if(input===undefined||input===null||String(input).trim()==='') return false;
      if(calcEqual(input,answer)) return true; return (accept||[]).some(function(a){ return calcEqual(input,a); }); }
    return _am.apply(this,arguments); };
  var _kl=kbLayoutFor;
  kbLayoutFor=function(inp){ try{ var ts=state.tabs[activeTab], sl=SLIDES[activeTab][ts.idx], stp=sl.flat[parseInt(inp.dataset.step,10)]; if(stp.expr==='calc') return 'calc'; }catch(e){} return _kl(inp); };
  var _kp=kbPress;
  kbPress=function(k){ var m={'eˣ':'e^(','√':'√(','ln':'ln(','sin':'sin(','cos':'cos(','tan':'tan('}; if(KB.page==='calc'&&m[k]){ kbInsert(m[k]); return; } return _kp(k); };
})();

renderLogin();
})();
</script>
</body>
</html>
