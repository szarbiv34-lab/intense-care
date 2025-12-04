<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>NeuroICU Sequential Rounds</title>
  <style>
    :root{--primary:#1e40af;--primary-light:#3b82f6;--success:#059669;--warning:#d97706;--danger:#dc2626;--surface:#fff;--surface-alt:#f8fafc;--text:#0f172a;--text-muted:#64748b;--border:#e2e8f0;--sah:#7c3aed;--ich:#dc2626;--stroke:#2563eb;--tbi:#f59e0b;--cardiac:#ec4899}
    *{box-sizing:border-box;margin:0;padding:0}
    body{font-family:system-ui,-apple-system,sans-serif;background:#0f172a;color:var(--text);font-size:14px;line-height:1.5}
    
    .app{display:flex;height:100vh;overflow:hidden}
    .sidebar{width:280px;background:#1e293b;color:#fff;display:flex;flex-direction:column;flex-shrink:0}
    .sidebar-header{padding:1rem;border-bottom:1px solid #334155}
    .sidebar-header h1{font-size:1rem;margin-bottom:.25rem}
    .sidebar-header p{font-size:.7rem;opacity:.7}
    
    .team-section{padding:.75rem;border-bottom:1px solid #334155}
    .team-title{font-size:.65rem;text-transform:uppercase;color:#94a3b8;margin-bottom:.5rem;font-weight:600}
    .team-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:.25rem}
    .team-btn{padding:.3rem;border:1px solid #475569;border-radius:4px;background:transparent;color:#94a3b8;font-size:.6rem;cursor:pointer;text-align:center}
    .team-btn.present{background:#059669;border-color:#059669;color:#fff}
    .team-btn:hover{border-color:#3b82f6}
    
    .census-section{flex:1;overflow-y:auto;padding:.5rem}
    .census-item{padding:.6rem;border-radius:6px;margin-bottom:.4rem;cursor:pointer;background:#334155;border:2px solid transparent}
    .census-item:hover{background:#3f4f6b}
    .census-item.active{border-color:var(--primary-light);background:#1e3a5f}
    .census-item.completed{opacity:.6}
    .census-item.completed::after{content:'✓';float:right;color:var(--success)}
    .census-name{font-weight:600;font-size:.85rem}
    .census-meta{font-size:.65rem;color:#94a3b8;display:flex;gap:.4rem;flex-wrap:wrap;margin-top:.2rem}
    .dx-tag{padding:.1rem .3rem;border-radius:3px;font-size:.55rem;font-weight:600;color:#fff}
    .dx-sah{background:var(--sah)}.dx-ich{background:var(--ich)}.dx-stroke{background:var(--stroke)}.dx-tbi{background:var(--tbi)}.dx-other{background:#6b7280}
    
    .add-pt-btn{width:100%;padding:.6rem;background:var(--primary);border:none;color:#fff;border-radius:6px;cursor:pointer;font-size:.8rem;margin-top:.5rem}
    
    .main{flex:1;display:flex;flex-direction:column;overflow:hidden}
    .main-header{background:var(--surface);border-bottom:1px solid var(--border);padding:.75rem 1.5rem;display:flex;justify-content:space-between;align-items:center}
    .patient-title{font-size:1.1rem;font-weight:600}
    .patient-subtitle{font-size:.75rem;color:var(--text-muted)}
    .header-actions{display:flex;gap:.5rem}
    
    .progress-bar{background:var(--surface);border-bottom:1px solid var(--border);padding:.5rem 1.5rem;display:flex;align-items:center;gap:.5rem}
    .progress-track{flex:1;height:8px;background:var(--border);border-radius:4px;overflow:hidden}
    .progress-fill{height:100%;background:linear-gradient(90deg,var(--primary),var(--success));transition:width .3s}
    .progress-text{font-size:.7rem;color:var(--text-muted);min-width:60px;text-align:right}
    
    .step-nav{background:var(--surface);border-bottom:1px solid var(--border);padding:.5rem 1rem;display:flex;gap:.25rem;overflow-x:auto}
    .step-dot{width:28px;height:28px;border-radius:50%;border:2px solid var(--border);display:flex;align-items:center;justify-content:center;font-size:.65rem;font-weight:600;cursor:pointer;flex-shrink:0;background:var(--surface);color:var(--text-muted)}
    .step-dot.active{border-color:var(--primary);background:var(--primary);color:#fff}
    .step-dot.done{border-color:var(--success);background:#ecfdf5;color:var(--success)}
    .step-dot.alert{border-color:var(--danger);background:#fef2f2;color:var(--danger)}
    
    .content{flex:1;overflow-y:auto;background:var(--surface-alt);padding:1.5rem}
    .step-section{display:none;max-width:900px;margin:0 auto}
    .step-section.active{display:block}
    
    .section-header{display:flex;align-items:center;gap:.75rem;margin-bottom:1rem}
    .section-icon{width:40px;height:40px;border-radius:10px;display:flex;align-items:center;justify-content:center;font-size:1.2rem}
    .section-icon.neuro{background:#ede9fe;color:var(--sah)}
    .section-icon.resp{background:#dbeafe;color:var(--stroke)}
    .section-icon.cardiac{background:#fce7f3;color:var(--cardiac)}
    .section-icon.general{background:#f1f5f9;color:#475569}
    .section-icon.family{background:#fef3c7;color:var(--warning)}
    .section-icon.plan{background:#d1fae5;color:var(--success)}
    .section-title{font-size:1.1rem;font-weight:600}
    .section-subtitle{font-size:.75rem;color:var(--text-muted)}
    .presenter-badge{margin-left:auto;padding:.25rem .75rem;border-radius:20px;font-size:.7rem;font-weight:600;color:#fff}
    .presenter-rn{background:#7c3aed}.presenter-md{background:#1e40af}.presenter-rt{background:#059669}.presenter-app{background:#0891b2}
    
    .card{background:var(--surface);border:1px solid var(--border);border-radius:10px;padding:1rem;margin-bottom:1rem}
    .card-title{font-weight:600;font-size:.85rem;margin-bottom:.75rem;display:flex;align-items:center;gap:.5rem}
    .card-title .badge{padding:.15rem .4rem;border-radius:4px;font-size:.6rem;font-weight:600}
    
    .alert-banner{padding:.75rem 1rem;border-radius:8px;margin-bottom:1rem;display:flex;align-items:center;gap:.75rem;font-size:.85rem}
    .alert-banner.danger{background:#fef2f2;border:1px solid var(--danger);color:#991b1b}
    .alert-banner.warning{background:#fffbeb;border:1px solid var(--warning);color:#92400e}
    .alert-banner.info{background:#eff6ff;border:1px solid var(--primary-light);color:#1e40af}
    .alert-banner.cardiac{background:#fdf2f8;border:1px solid var(--cardiac);color:#9d174d}
    
    .check-item{display:flex;align-items:flex-start;gap:.75rem;padding:.6rem 0;border-bottom:1px solid #f1f5f9}
    .check-item:last-child{border-bottom:none}
    .check-item input[type="checkbox"]{width:20px;height:20px;accent-color:var(--success);cursor:pointer;flex-shrink:0;margin-top:2px}
    .check-item label{flex:1;cursor:pointer;font-size:.85rem}
    .check-item.done label{color:var(--text-muted);text-decoration:line-through}
    .check-item select,.check-item input[type="number"],.check-item input[type="text"]{padding:.3rem .5rem;border:1px solid var(--border);border-radius:4px;font-size:.8rem}
    .check-item select.alert{border-color:var(--danger);background:#fef2f2}
    .role-tag{padding:.15rem .4rem;border-radius:3px;font-size:.55rem;font-weight:600;color:#fff;margin-left:auto;flex-shrink:0}
    .role-rn{background:#7c3aed}.role-md{background:#1e40af}.role-rt{background:#059669}.role-app{background:#0891b2}.role-pt{background:#ea580c}.role-rd{background:#65a30d}.role-sw{background:#db2777}
    
    .score-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(120px,1fr));gap:.75rem;margin-bottom:.75rem}
    .score-item label{display:block;font-size:.65rem;font-weight:600;text-transform:uppercase;color:var(--text-muted);margin-bottom:.25rem}
    .score-item select,.score-item input{width:100%;padding:.4rem;border:1px solid var(--border);border-radius:6px;font-size:.85rem}
    
    .gcs-display{display:flex;align-items:center;gap:1rem;padding:.75rem;background:var(--surface-alt);border-radius:8px;margin-bottom:.75rem}
    .gcs-inputs{display:flex;gap:.5rem;align-items:center;font-size:.85rem}
    .gcs-inputs input{width:40px;padding:.3rem;text-align:center;border:1px solid var(--border);border-radius:4px}
    .gcs-total{font-size:1.5rem;font-weight:700;padding:.25rem .75rem;border-radius:6px;margin-left:auto}
    .gcs-total.severe{background:#fef2f2;color:var(--danger)}
    .gcs-total.moderate{background:#fffbeb;color:var(--warning)}
    .gcs-total.mild{background:#ecfdf5;color:var(--success)}
    
    .vitals-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(100px,1fr));gap:.5rem;margin-bottom:.75rem}
    .vital-box{padding:.5rem;background:var(--surface-alt);border-radius:6px;text-align:center}
    .vital-box label{display:block;font-size:.6rem;text-transform:uppercase;color:var(--text-muted);margin-bottom:.2rem}
    .vital-box .value{font-size:1.1rem;font-weight:600}
    .vital-box.alert{background:#fef2f2}.vital-box.alert .value{color:var(--danger)}
    
    .order-verify{display:flex;gap:.5rem;align-items:center;margin-left:auto}
    .order-verify select{padding:.2rem .4rem;border:1px solid var(--border);border-radius:4px;font-size:.7rem}
    .order-verify select.mismatch{border-color:var(--danger);background:#fef2f2}
    .verify-icon{font-size:.9rem}
    .verify-icon.match{color:var(--success)}
    .verify-icon.mismatch{color:var(--danger)}
    
    .gap-section{margin-top:1rem}
    .gap-item{display:flex;align-items:center;gap:.5rem;padding:.5rem;background:#fef2f2;border:1px solid #fecaca;border-radius:6px;margin-bottom:.5rem;font-size:.8rem}
    .gap-item.resolved{background:#ecfdf5;border-color:#a7f3d0}
    .gap-item input[type="checkbox"]{width:16px;height:16px}
    .gap-item select{padding:.2rem;border:1px solid var(--border);border-radius:4px;font-size:.7rem}
    .add-gap-btn{padding:.4rem .75rem;background:var(--surface);border:1px dashed var(--border);border-radius:6px;cursor:pointer;font-size:.75rem;color:var(--text-muted)}
    
    .metrics-bar{display:grid;grid-template-columns:repeat(4,1fr);gap:.5rem;margin-bottom:1rem}
    .metric-box{padding:.5rem;background:var(--surface);border:1px solid var(--border);border-radius:6px;text-align:center}
    .metric-box .value{font-size:1.25rem;font-weight:700;color:var(--primary)}
    .metric-box .label{font-size:.6rem;text-transform:uppercase;color:var(--text-muted)}
    
    .visage-calc{background:#eff6ff;border:1px solid var(--primary-light);border-radius:8px;padding:1rem;margin-bottom:1rem}
    .visage-title{font-weight:600;font-size:.85rem;color:var(--primary);margin-bottom:.75rem;display:flex;align-items:center;gap:.5rem}
    .visage-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:.5rem}
    .visage-item{display:flex;justify-content:space-between;align-items:center;font-size:.8rem;padding:.3rem 0}
    .visage-item select{padding:.2rem .4rem;border:1px solid var(--border);border-radius:4px;font-size:.75rem}
    .visage-result{margin-top:.75rem;padding:.5rem;background:var(--primary);color:#fff;border-radius:6px;text-align:center;font-weight:600}
    .visage-result.candidate{background:var(--success)}
    .visage-result.not-candidate{background:#6b7280}
    
    .family-log{max-height:150px;overflow-y:auto;border:1px solid var(--border);border-radius:6px;margin-bottom:.75rem}
    .family-log-item{padding:.5rem .75rem;border-bottom:1px solid var(--border);font-size:.8rem}
    .family-log-item:last-child{border-bottom:none}
    .family-log-item .date{font-size:.65rem;color:var(--text-muted)}
    
    .btn{padding:.5rem 1rem;border:none;border-radius:6px;font-size:.85rem;font-weight:500;cursor:pointer}
    .btn-primary{background:var(--primary);color:#fff}
    .btn-success{background:var(--success);color:#fff}
    .btn-secondary{background:var(--surface);color:var(--text);border:1px solid var(--border)}
    .btn-lg{padding:.75rem 1.5rem;font-size:1rem}
    
    .nav-footer{padding:1rem 1.5rem;background:var(--surface);border-top:1px solid var(--border);display:flex;justify-content:space-between;align-items:center}
    .nav-footer .step-info{font-size:.8rem;color:var(--text-muted)}
    
    .notes-area{width:100%;padding:.5rem;border:1px solid var(--border);border-radius:6px;font-size:.85rem;font-family:inherit;resize:none}
    
    .empty-state{text-align:center;padding:3rem;color:var(--text-muted)}
    .empty-state h3{margin-bottom:.5rem}
    
    .modal{position:fixed;inset:0;background:rgba(0,0,0,.5);display:none;align-items:center;justify-content:center;z-index:1000}
    .modal.show{display:flex}
    .modal-content{background:var(--surface);border-radius:12px;padding:1.5rem;width:90%;max-width:500px;max-height:90vh;overflow-y:auto}
    .modal-title{font-size:1.1rem;font-weight:600;margin-bottom:1rem}
    .form-group{margin-bottom:1rem}
    .form-group label{display:block;font-size:.75rem;font-weight:600;margin-bottom:.25rem;color:var(--text-muted)}
    .form-group input,.form-group select{width:100%;padding:.5rem;border:1px solid var(--border);border-radius:6px}
    .form-row{display:grid;grid-template-columns:1fr 1fr;gap:.75rem}
    
    @media(max-width:768px){.sidebar{width:100%;position:fixed;bottom:0;height:auto;max-height:40vh;z-index:100;border-top:1px solid #334155}.app{flex-direction:column}.main{height:60vh}.team-section{display:none}}
  </style>
</head>
<body>

<div class="app">
  <aside class="sidebar">
    <div class="sidebar-header">
      <h1>🧠 NeuroICU Rounds</h1>
      <p>AtlantiCare • Sequential Flow</p>
    </div>
    
    <div class="team-section">
      <div class="team-title">Team Present</div>
      <div class="team-grid" id="teamGrid">
        <button class="team-btn" data-role="Attending" onclick="toggleTeam(this)">MD</button>
        <button class="team-btn" data-role="APP" onclick="toggleTeam(this)">APP</button>
        <button class="team-btn present" data-role="RN" onclick="toggleTeam(this)">RN</button>
        <button class="team-btn" data-role="RT" onclick="toggleTeam(this)">RT</button>
        <button class="team-btn" data-role="Pharm" onclick="toggleTeam(this)">PharmD</button>
        <button class="team-btn" data-role="PT" onclick="toggleTeam(this)">PT</button>
        <button class="team-btn" data-role="RD" onclick="toggleTeam(this)">RD</button>
        <button class="team-btn" data-role="SW" onclick="toggleTeam(this)">SW</button>
      </div>
    </div>
    
    <div class="census-section">
      <div class="team-title">Census</div>
      <div id="censusList"></div>
      <button class="add-pt-btn" onclick="openAddModal()">+ Add Patient</button>
    </div>
  </aside>
  
  <main class="main" id="mainArea">
    <div class="empty-state" id="emptyState">
      <h3>Select a Patient</h3>
      <p>Choose a patient from the census to begin rounds</p>
    </div>
    
    <div id="patientArea" style="display:none;flex-direction:column;height:100%">
      <header class="main-header">
        <div>
          <div class="patient-title" id="ptTitle">--</div>
          <div class="patient-subtitle" id="ptSubtitle">--</div>
        </div>
        <div class="header-actions">
          <button class="btn btn-secondary" onclick="exportHandoff()">📋 Handoff</button>
          <button class="btn btn-secondary" onclick="exportExcel()">📊 Excel</button>
          <button class="btn btn-secondary" onclick="completePatient()">✓ Complete</button>
        </div>
      </header>
      
      <div class="progress-bar">
        <div class="progress-track"><div class="progress-fill" id="progressFill" style="width:0%"></div></div>
        <div class="progress-text" id="progressText">0 / 14</div>
      </div>
      
      <nav class="step-nav" id="stepNav"></nav>
      
      <div class="content" id="contentArea">
        
        <!-- STEP 1: Patient Identity -->
        <section class="step-section" data-step="1">
          <div class="section-header">
            <div class="section-icon general">📋</div>
            <div><div class="section-title">Patient Identity & Status</div><div class="section-subtitle">Confirm patient, diagnosis, code status</div></div>
            <span class="presenter-badge presenter-rn">RN Leads</span>
          </div>
          
          <div class="card">
            <div class="check-item"><input type="checkbox" id="s1_identity" onchange="updateProgress()"><label for="s1_identity"><strong>Patient identity confirmed</strong> — Name, DOB, diagnosis</label><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s1_icuday" onchange="updateProgress()"><label for="s1_icuday">ICU Day</label><input type="number" id="icuDay" min="1" value="1" style="width:60px" onchange="save()"><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s1_dx" onchange="updateProgress()"><label for="s1_dx">Primary neuro pathology</label><select id="primaryDx" onchange="save()"><option value="">--</option><option value="sah">aSAH</option><option value="ich">ICH</option><option value="stroke">Large Stroke</option><option value="tbi">TBI</option><option value="seizure">Status Epilepticus</option><option value="other">Other</option></select></div>
            <div class="check-item"><input type="checkbox" id="s1_code" onchange="updateProgress()"><label for="s1_code"><strong>Code status verified</strong></label><select id="codeStatus" onchange="save()"><option value="full">Full Code</option><option value="dnr">DNR</option><option value="dni">DNI</option><option value="cmo">CMO</option></select><span class="role-tag role-md">MD</span></div>
          </div>
        </section>
        
        <!-- STEP 2: Overnight Events -->
        <section class="step-section" data-step="2">
          <div class="section-header">
            <div class="section-icon general">🌙</div>
            <div><div class="section-title">Overnight Events</div><div class="section-subtitle">Key events, vital trends, neuro changes</div></div>
            <span class="presenter-badge presenter-rn">RN Leads</span>
          </div>
          
          <div class="card">
            <div class="check-item"><input type="checkbox" id="s2_events" onchange="updateProgress()"><label for="s2_events"><strong>Significant events reviewed</strong></label><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s2_vitals" onchange="updateProgress()"><label for="s2_vitals">Vital sign trends</label><select id="vitalTrend" onchange="save()"><option value="stable">Stable</option><option value="improved">Improved</option><option value="concerning">Concerning</option></select><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s2_neuro" onchange="updateProgress()"><label for="s2_neuro">Neuro status change overnight?</label><select id="neuroChangeON" onchange="checkAlerts();save()"><option value="none">None</option><option value="improved">Improved</option><option value="declined">DECLINED ⚠️</option></select><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s2_new" onchange="updateProgress()"><label for="s2_new">New imaging/labs/consults communicated</label><span class="role-tag role-rn">RN</span></div>
          </div>
          
          <div class="card">
            <div class="card-title">Overnight Notes</div>
            <textarea class="notes-area" id="overnightNotes" rows="3" placeholder="Key overnight events..." onchange="save()"></textarea>
          </div>
        </section>
        
        <!-- STEP 3: Neurologic Status -->
        <section class="step-section" data-step="3">
          <div class="section-header">
            <div class="section-icon neuro">🧠</div>
            <div><div class="section-title">Neurologic Status</div><div class="section-subtitle">Exam, GCS, pupils, focal deficits</div></div>
            <span class="presenter-badge presenter-md">MD Leads</span>
          </div>
          
          <div id="neuroAlerts"></div>
          
          <div class="card">
            <div class="card-title">GCS Assessment</div>
            <div class="gcs-display">
              <div class="gcs-inputs">
                E <input type="number" id="gcsE" min="1" max="4" onchange="calcGCS();save()">
                V <input type="text" id="gcsV" placeholder="1-5/T" onchange="calcGCS();save()">
                M <input type="number" id="gcsM" min="1" max="6" onchange="calcGCS();save()">
              </div>
              <div class="gcs-total" id="gcsTotal">--</div>
            </div>
            <div class="check-item"><input type="checkbox" id="s3_exam" onchange="updateProgress()"><label for="s3_exam">Neuro exam documented</label><select id="examChange" onchange="save()"><option value="unchanged">Unchanged</option><option value="improved">Improved</option><option value="worse">WORSE ⚠️</option></select><span class="role-tag role-md">MD</span></div>
          </div>
          
          <div class="card">
            <div class="card-title">Pupils & Motor</div>
            <div class="score-grid">
              <div class="score-item"><label>Left Pupil</label><select id="pupilL" onchange="save()"><option value="">--</option><option>2mm</option><option>3mm</option><option>4mm</option><option>5mm</option><option>6mm</option><option>Fixed</option></select></div>
              <div class="score-item"><label>Right Pupil</label><select id="pupilR" onchange="save()"><option value="">--</option><option>2mm</option><option>3mm</option><option>4mm</option><option>5mm</option><option>6mm</option><option>Fixed</option></select></div>
              <div class="score-item"><label>Reactivity</label><select id="pupilReact" onchange="save()"><option value="">--</option><option value="brisk">Brisk</option><option value="sluggish">Sluggish</option><option value="fixed">Fixed</option></select></div>
              <div class="score-item"><label>Focal Deficits</label><select id="focalDef" onchange="save()"><option value="">--</option><option value="none">None</option><option value="stable">Stable</option><option value="new">NEW ⚠️</option><option value="improving">Improving</option></select></div>
            </div>
          </div>
          
          <!-- Disease-specific modules inserted here dynamically -->
          <div id="diseaseModules"></div>
        </section>
        
        <!-- STEP 4: ICP/Monitoring -->
        <section class="step-section" data-step="4">
          <div class="section-header">
            <div class="section-icon neuro">📊</div>
            <div><div class="section-title">Multimodal Monitoring</div><div class="section-subtitle">ICP, EVD, cEEG</div></div>
            <span class="presenter-badge presenter-md">MD Leads</span>
          </div>
          
          <div id="icpSection" class="card" style="display:none">
            <div class="card-title">ICP Monitoring <span class="badge" style="background:#fef2f2;color:var(--danger)">Active</span></div>
            <div class="vitals-grid">
              <div class="vital-box" id="icpBox"><label>ICP</label><div class="value" id="icpValue">--</div></div>
              <div class="vital-box"><label>MAP</label><div class="value" id="mapValue">--</div></div>
              <div class="vital-box" id="cppBox"><label>CPP</label><div class="value" id="cppValue">--</div></div>
            </div>
            <div class="score-grid">
              <div class="score-item"><label>Current ICP</label><input type="number" id="icpCurrent" min="0" onchange="updateICP();save()"></div>
              <div class="score-item"><label>Current MAP</label><input type="number" id="mapCurrent" min="0" onchange="updateICP();save()"></div>
              <div class="score-item"><label>ICP Trend</label><select id="icpTrend" onchange="save()"><option value="">--</option><option value="stable">Stable</option><option value="improving">Improving</option><option value="worsening">WORSENING</option></select></div>
            </div>
            <div class="check-item"><input type="checkbox" id="s4_icp" onchange="updateProgress()"><label for="s4_icp">ICP trends reviewed (24h)</label><span class="role-tag role-md">MD</span></div>
            <div class="check-item"><input type="checkbox" id="s4_cpp" onchange="updateProgress()"><label for="s4_cpp">CPP at target (≥60 mmHg)</label><select id="cppGoal" onchange="save()"><option value="">--</option><option value="yes">Yes</option><option value="no">No ⚠️</option></select></div>
          </div>
          
          <div id="evdSection" class="card" style="display:none">
            <div class="card-title">EVD Management <span class="badge" style="background:#e0f2fe;color:#0369a1">Day <span id="evdDayDisplay">1</span></span></div>
            <div id="evdAlert" class="alert-banner warning" style="display:none">⚠️ EVD Day 10+ — Increased infection risk. Review necessity.</div>
            <div class="score-grid">
              <div class="score-item"><label>EVD Day</label><input type="number" id="evdDay" min="1" value="1" onchange="checkEVDDay();save()"></div>
              <div class="score-item"><label>Height (cm H₂O)</label><input type="number" id="evdHeight" onchange="save()"></div>
              <div class="score-item"><label>Output (mL/24h)</label><input type="number" id="evdOutput" onchange="save()"></div>
              <div class="score-item"><label>CSF Appearance</label><select id="csfAppear" onchange="save()"><option value="">--</option><option value="clear">Clear</option><option value="xan">Xanthochromic</option><option value="bloody">Bloody</option><option value="cloudy">CLOUDY ⚠️</option></select></div>
            </div>
            <div class="check-item"><input type="checkbox" id="s4_evdHeight" onchange="updateProgress()"><label for="s4_evdHeight">EVD height matches order</label>
              <div class="order-verify"><select id="evdHeightOrder" onchange="verifyOrder('evdHeight');save()"><option value="">Order...</option><option>5 cm</option><option>10 cm</option><option>15 cm</option><option>20 cm</option></select><select id="evdHeightActual" onchange="verifyOrder('evdHeight');save()"><option value="">Actual...</option><option value="match">Match</option><option value="mismatch">MISMATCH</option></select><span class="verify-icon" id="evdHeightIcon"></span></div>
            </div>
            <div class="check-item"><input type="checkbox" id="s4_evdDrain" onchange="updateProgress()"><label for="s4_evdDrain">Drain status matches order</label>
              <div class="order-verify"><select id="drainOrder" onchange="verifyOrder('drain');save()"><option value="">Order...</option><option value="drain">Drain</option><option value="clamp">Clamp</option><option value="wean">Wean trial</option></select><select id="drainActual" onchange="verifyOrder('drain');save()"><option value="">Actual...</option><option value="match">Match</option><option value="mismatch">MISMATCH</option></select><span class="verify-icon" id="drainIcon"></span></div>
            </div>
            <div class="check-item"><input type="checkbox" id="s4_csf" onchange="updateProgress()"><label for="s4_csf">CSF sampled per protocol</label><select id="csfSample" onchange="save()"><option value="">--</option><option value="today">Today</option><option value="2d">2 days ago</option><option value="due">DUE (3+ days)</option></select></div>
          </div>
          
          <div id="eegSection" class="card" style="display:none">
            <div class="card-title">cEEG Monitoring <span class="badge" style="background:#f3e8ff;color:#7c3aed">Active</span></div>
            <div id="seizureAlert" class="alert-banner danger" style="display:none">🚨 Seizure activity detected — Review AEDs</div>
            <div class="score-grid">
              <div class="score-item"><label>EEG Status</label><select id="eegStatus" onchange="checkEEG();save()"><option value="">--</option><option value="normal">Normal</option><option value="slow">Diffuse slowing</option><option value="epileptiform">Epileptiform</option><option value="seizures">SEIZURES</option><option value="ncse">NCSE</option></select></div>
              <div class="score-item"><label>Background</label><select id="eegBg" onchange="save()"><option value="">--</option><option value="normal">Normal</option><option value="mild">Mild slowing</option><option value="mod">Mod slowing</option><option value="severe">Severe slowing</option></select></div>
            </div>
            <div class="check-item"><input type="checkbox" id="s4_eegReview" onchange="updateProgress()"><label for="s4_eegReview">EEG reviewed (formal read)</label><span class="role-tag role-md">MD</span></div>
            <div class="check-item"><input type="checkbox" id="s4_aed" onchange="updateProgress()"><label for="s4_aed">AED levels/dosing reviewed</label><select id="aedStatus" onchange="save()"><option value="">--</option><option value="adequate">Adequate</option><option value="adjust">Needs adjustment</option><option value="none">Not on AEDs</option></select><span class="role-tag role-app">APP</span></div>
          </div>
          
          <div class="card" id="noMonitoring">
            <p style="color:var(--text-muted);text-align:center;padding:1rem">No active ICP/EVD/EEG monitoring for this patient</p>
          </div>
        </section>
        
        <!-- STEP 5: Pain/Sedation/Delirium -->
        <section class="step-section" data-step="5">
          <div class="section-header">
            <div class="section-icon general">💊</div>
            <div><div class="section-title">Pain, Sedation & Delirium</div><div class="section-subtitle">ABCDEF Bundle: A, C, D</div></div>
            <span class="presenter-badge presenter-rn">RN Leads</span>
          </div>
          
          <div class="card">
            <div class="card-title">A — Pain Management</div>
            <div class="check-item"><input type="checkbox" id="s5_painAssess" onchange="updateProgress()"><label for="s5_painAssess">Pain assessed (numeric/behavioral)</label><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s5_painCtrl" onchange="updateProgress()"><label for="s5_painCtrl">Pain controlled</label><select id="painStatus" onchange="save()"><option value="yes">Yes - adequate</option><option value="no">No - needs adjustment</option></select></div>
            <div class="check-item"><input type="checkbox" id="s5_painICP" onchange="updateProgress()"><label for="s5_painICP">Pain/agitation impact on ICP considered</label><span class="role-tag role-md">MD</span></div>
          </div>
          
          <div class="card">
            <div class="card-title">C — Sedation</div>
            <div class="score-grid">
              <div class="score-item"><label>Current RASS</label><select id="rass" onchange="save()"><option>+4</option><option>+3</option><option>+2</option><option>+1</option><option selected>0</option><option>-1</option><option>-2</option><option>-3</option><option>-4</option><option>-5</option></select></div>
              <div class="score-item"><label>RASS Goal</label><select id="rassGoal" onchange="save()"><option>0</option><option selected>-1</option><option>-2</option><option>-3</option><option>-4</option><option>-5</option></select></div>
            </div>
            <div class="check-item"><input type="checkbox" id="s5_sedGoal" onchange="updateProgress()"><label for="s5_sedGoal">Sedation at goal</label><select id="sedAtGoal" onchange="save()"><option value="yes">Yes</option><option value="over">Over-sedated</option><option value="under">Under-sedated</option></select></div>
            <div class="check-item"><input type="checkbox" id="s5_sat" onchange="updateProgress()"><label for="s5_sat">SAT (Spontaneous Awakening Trial)</label><select id="satStatus" onchange="save()"><option value="">--</option><option value="passed">Passed</option><option value="failed">Failed</option><option value="contraindicated">Contraindicated</option><option value="na">N/A</option></select><span class="role-tag role-md">MD</span></div>
          </div>
          
          <div class="card">
            <div class="card-title">D — Delirium</div>
            <div class="check-item"><input type="checkbox" id="s5_cam" onchange="updateProgress()"><label for="s5_cam">CAM-ICU assessed</label><select id="camResult" onchange="save()"><option value="neg">Negative</option><option value="pos">POSITIVE</option><option value="uta">Unable to assess</option></select><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s5_delPrev" onchange="updateProgress()"><label for="s5_delPrev">Delirium prevention measures in place</label><select id="delPrev" onchange="save()"><option value="">--</option><option value="inplace">In place</option><option value="needed">Needs attention</option></select></div>
          </div>
        </section>
        
        <!-- STEP 6: Respiratory -->
        <section class="step-section" data-step="6">
          <div class="section-header">
            <div class="section-icon resp">🫁</div>
            <div><div class="section-title">Respiratory</div><div class="section-subtitle">ABCDEF Bundle: B — Breathing/SBT</div></div>
            <span class="presenter-badge presenter-rt">RT Leads</span>
          </div>
          
          <div class="card">
            <div class="card-title">Airway & Ventilation</div>
            <div class="check-item"><input type="checkbox" id="s6_airway" onchange="updateProgress()"><label for="s6_airway">Airway status</label><select id="airway" onchange="checkTrach();save()"><option value="native">Native</option><option value="ett">ETT</option><option value="trach">Trach</option></select><span class="role-tag role-rt">RT</span></div>
            <div class="check-item"><input type="checkbox" id="s6_vent" onchange="updateProgress()"><label for="s6_vent">Ventilation mode</label><select id="ventMode" onchange="save()"><option value="">--</option><option value="ra">Room Air</option><option value="nc">Nasal Cannula</option><option value="hfnc">HFNC</option><option value="nippv">NIPPV</option><option value="acvc">AC/VC</option><option value="psv">PSV</option></select><span class="role-tag role-rt">RT</span></div>
            <div class="check-item"><input type="checkbox" id="s6_sbt" onchange="updateProgress()"><label for="s6_sbt">SBT (Spontaneous Breathing Trial)</label><select id="sbtStatus" onchange="save()"><option value="na">N/A</option><option value="notcandidate">Not candidate</option><option value="candidate">Candidate today</option><option value="passed">Passed</option><option value="failed">Failed</option></select><span class="role-tag role-rt">RT</span></div>
          </div>
          
          <div id="visageSection" class="visage-calc" style="display:none">
            <div class="visage-title">🎯 VISAGE Score — Early Trach Assessment (Days 1-3)</div>
            <div class="visage-grid">
              <div class="visage-item"><span>Age ≥40</span><select id="visAge" onchange="calcVISAGE();save()"><option value="0">No (0)</option><option value="2">Yes (+2)</option></select></div>
              <div class="visage-item"><span>GCS Motor ≤4</span><select id="visGCS" onchange="calcVISAGE();save()"><option value="0">No (0)</option><option value="4">Yes (+4)</option></select></div>
              <div class="visage-item"><span>ISS ≥25</span><select id="visISS" onchange="calcVISAGE();save()"><option value="0">No (0)</option><option value="3">Yes (+3)</option></select></div>
              <div class="visage-item"><span>Thoracic AIS ≥3</span><select id="visThor" onchange="calcVISAGE();save()"><option value="0">No (0)</option><option value="3">Yes (+3)</option></select></div>
            </div>
            <div class="visage-result" id="visageResult">Score: 0 — Not candidate for early trach</div>
          </div>
        </section>
        
        <!-- STEP 7: Cardiovascular -->
        <section class="step-section" data-step="7">
          <div class="section-header">
            <div class="section-icon cardiac">❤️</div>
            <div><div class="section-title">Cardiovascular & Hemodynamics</div><div class="section-subtitle">Neurocardiovascular integration</div></div>
            <span class="presenter-badge presenter-md">MD Leads</span>
          </div>
          
          <div id="cardiacAlerts"></div>
          
          <div class="card">
            <div class="card-title">Hemodynamics</div>
            <div class="check-item"><input type="checkbox" id="s7_map" onchange="updateProgress()"><label for="s7_map">MAP at target</label><select id="mapTarget" onchange="save()"><option value="">--</option><option value="goal">At goal</option><option value="low">Below target</option><option value="high">Above target</option></select><span class="role-tag role-md">MD</span></div>
            <div class="check-item"><input type="checkbox" id="s7_pressors" onchange="updateProgress()"><label for="s7_pressors">Vasopressors</label><select id="pressorStatus" onchange="save()"><option value="none">None</option><option value="weaning">Weaning</option><option value="stable">Stable dose</option><option value="increasing">Increasing</option></select></div>
            <div class="check-item"><input type="checkbox" id="s7_fluid" onchange="updateProgress()"><label for="s7_fluid">Fluid balance reviewed</label><select id="fluidStatus" onchange="save()"><option value="">--</option><option value="even">Even</option><option value="positive">Positive</option><option value="negative">Negative</option></select><span class="role-tag role-rn">RN</span></div>
            <div class="check-item"><input type="checkbox" id="s7_glucose" onchange="updateProgress()"><label for="s7_glucose">Glucose control (140-180)</label><select id="glucoseStatus" onchange="save()"><option value="">--</option><option value="goal">At goal</option><option value="high">High</option><option value="low">Low</option></select></div>
          </div>
          
          <div class="card">
            <div class="card-title">Neuro-Cardiac Crosstalk <span class="badge" style="background:#fdf2f8;color:var(--cardiac)">Monitor</span></div>
            <div class="score-grid">
              <div class="score-item"><label>Troponin</label><select id="tropStatus" onchange="checkCardiac();save()"><option value="">--</option><option value="normal">Normal</option><option value="elevated">Elevated</option><option value="trending">Trending up</option></select></div>
              <div class="score-item"><label>BNP</label><select id="bnpStatus" onchange="save()"><option value="">--</option><option value="normal">Normal</option><option value="elevated">Elevated</option></select></div>
              <div class="score-item"><label>ECG</label><select id="ecgStatus" onchange="checkCardiac();save()"><option value="">--</option><option value="normal">Normal</option><option value="sttw">ST/TW changes</option><option value="qtc">QTc prolonged</option><option value="arrhythmia">Arrhythmia</option></select></div>
              <div class="score-item"><label>Echo</label><select id="echoStatus" onchange="checkCardiac();save()"><option value="">--</option><option value="normal">Normal</option><option value="rwma">RWMA</option><option value="takotsubo">Takotsubo ⚠️</option><option value="pending">Pending</option></select></div>
            </div>
            <div class="check-item"><input type="checkbox" id="s7_cardio" onchange="updateProgress()"><label for="s7_cardio">Cardiac status reviewed (SAH/TBI patients)</label><span class="role-tag role-md">MD</span></div>
          </div>
        </section>
        
        <!-- STEP 8: Labs & Infection -->
        <section class="step-section" data-step="8">
          <div class="section-header">
            <div class="section-icon general">🔬</div>
            <div><div class="section-title">Labs & Infection</div><div class="section-subtitle">Lab review, antibiotic stewardship</div></div>
            <span class="presenter-badge presenter-app">APP Leads</span>
          </div>
          
          <div class="card">
            <div class="card-title">Labs</div>
            <div class="check-item"><input type="checkbox" id="s8_labs" onchange="updateProgress()"><label for="s8_labs">Labs reviewed — action needed?</label><select id="labAction" onchange="save()"><option value="none">No action</option><option value="action">Action needed</option></select><span class="role-tag role-app">APP</span></div>
            <div class="check-item"><input type="checkbox" id="s8_lytes" onchange="updateProgress()"><label for="s8_lytes">Electrolytes at goal</label><select id="lyteStatus" onchange="save()"><option value="">--</option><option value="goal">At goal</option><option value="repleting">Repleting</option><option value="abnormal">Abnormal</option></select></div>
            <div class="check-item"><input type="checkbox" id="s8_na" onchange="updateProgress()"><label for="s8_na">Sodium target (disease-specific)</label><select id="naTarget" onchange="save()"><option value="">--</option><option value="goal">At goal</option><option value="low">Low</option><option value="high">High</option></select></div>
          </div>
          
          <div class="card">
            <div class="card-title">Infection & Antibiotics</div>
            <div class="check-item"><input type="checkbox" id="s8_abx" onchange="updateProgress()"><label for="s8_abx">Antibiotic stewardship</label><select id="abxStatus" onchange="save()"><option value="">--</option><option value="none">Not on antibiotics</option><option value="appropriate">Appropriate</option><option value="deescalate">De-escalate</option><option value="broaden">Broaden</option><option value="stop">Stop</option></select><span class="role-tag role-app">APP</span></div>
            <div class="check-item"><input type="checkbox" id="s8_fever" onchange="updateProgress()"><label for="s8_fever">Fever workup (if T &gt;38.3°C)</label><select id="feverWorkup" onchange="save()"><option value="">--</option><option value="afebrile">Afebrile</option><option value="done">Done</option><option value="pending">Pending</option></select></div>
          </div>
        </section>
        
        <!-- STEP 9: Lines/DVT/Skin -->
        <section class="step-section" data-step="9">
          <div class="section-header">
            <div class="section-icon general">🩺</div>
            <div><div class="section-title">Lines, DVT & Skin</div><div class="section-subtitle">CLABSI/CAUTI prevention, DVT prophylaxis</div></div>
            <span class="presenter-badge presenter-rn">RN Leads</span>
          </div>
          
          <div class="card">
            <div class="card-title">Line Necessity</div>
            <div class="check-item"><input type="checkbox" id="s9_central" onchange="updateProgress()"><label for="s9_central">Central line necessity (CLABSI)</label><select id="centralLine" onchange="save()"><option value="">--</option><option value="none">None</option><option value="needed">Needed</option><option value="remove">Can remove</option></select><span class="role-tag role-md">MD</span></div>
            <div class="check-item"><input type="checkbox" id="s9_foley" onchange="updateProgress()"><label for="s9_foley">Foley necessity (CAUTI)</label><select id="foleyStatus" onchange="save()"><option value="">--</option><option value="none">None</option><option value="needed">Needed</option><option value="remove">Can remove</option></select><span class="role-tag role-rn">RN</span></div>
          </div>
          
          <div class="card">
            <div class="card-title">DVT Prophylaxis — Order to Bedside Verification</div>
            <div class="check-item"><input type="checkbox" id="s9_dvtMech" onchange="updateProgress()"><label for="s9_dvtMech">Mechanical prophylaxis</label>
              <div class="order-verify"><select id="scdOrder" onchange="verifyOrder('scd');save()"><option value="">Order...</option><option value="scds">SCDs</option><option value="none">None</option></select><select id="scdActual" onchange="verifyOrder('scd');save()"><option value="">Actual...</option><option value="on">On patient</option><option value="off">NOT on</option></select><span class="verify-icon" id="scdIcon"></span></div>
              <span class="role-tag role-rn">RN</span>
            </div>
            <div class="check-item"><input type="checkbox" id="s9_dvtPharm" onchange="updateProgress()"><label for="s9_dvtPharm">Pharmacologic prophylaxis</label><select id="dvtPharm" onchange="save()"><option value="">--</option><option value="heparin">Heparin SQ</option><option value="lovenox">Enoxaparin</option><option value="hold">Holding (bleeding)</option><option value="needs">NEEDS ORDER ⚠️</option></select><span class="role-tag role-app">APP</span></div>
          </div>
          
          <div class="card">
            <div class="card-title">Skin</div>
            <div class="check-item"><input type="checkbox" id="s9_skin" onchange="updateProgress()"><label for="s9_skin">Skin integrity checked</label><select id="skinStatus" onchange="save()"><option value="">--</option><option value="intact">Intact</option><option value="concern">Concern/wound</option></select><span class="role-tag role-rn">RN</span></div>
          </div>
        </section>
        
        <!-- STEP 10: Mobility -->
        <section class="step-section" data-step="10">
          <div class="section-header">
            <div class="section-icon general">🚶</div>
            <div><div class="section-title">Mobility & Rehab</div><div class="section-subtitle">ABCDEF Bundle: E — Early Mobility</div></div>
            <span class="presenter-badge presenter-pt">PT Leads</span>
          </div>
          
          <div class="card">
            <div class="check-item"><input type="checkbox" id="s10_level" onchange="updateProgress()"><label for="s10_level">Mobility level</label><select id="mobLevel" onchange="save()"><option value="bedrest">Bedrest</option><option value="passive">Passive ROM</option><option value="active">Active ROM</option><option value="dangle">Dangle/sit EOB</option><option value="stand">Stand</option><option value="chair">Chair</option><option value="ambulate">Ambulate</option></select><span class="role-tag role-pt">PT</span></div>
            <div class="check-item"><input type="checkbox" id="s10_pt" onchange="updateProgress()"><label for="s10_pt">PT/OT following</label><select id="ptStatus" onchange="save()"><option value="">--</option><option value="following">Following</option><option value="consult">Needs consult</option><option value="hold">On hold</option></select></div>
            <div class="check-item"><input type="checkbox" id="s10_slp" onchange="updateProgress()"><label for="s10_slp">SLP/Swallow eval</label><select id="slpStatus" onchange="save()"><option value="">--</option><option value="passed">Passed - diet</option><option value="failed">Failed - NPO</option><option value="pending">Pending</option><option value="na">N/A (intubated)</option></select></div>
          </div>
        </section>
        
        <!-- STEP 11: Nutrition -->
        <section class="step-section" data-step="11">
          <div class="section-header">
            <div class="section-icon general">🍽️</div>
            <div><div class="section-title">Nutrition & GI</div><div class="section-subtitle">Feeding route, goal rate, prophylaxis</div></div>
            <span class="presenter-badge presenter-rd">RD Leads</span>
          </div>
          
          <div class="card">
            <div class="check-item"><input type="checkbox" id="s11_route" onchange="updateProgress()"><label for="s11_route">Nutrition route</label><select id="nutrRoute" onchange="save()"><option value="">--</option><option value="npo">NPO</option><option value="po">PO diet</option><option value="tube">Tube feeds</option><option value="tpn">TPN</option></select><span class="role-tag role-rd">RD</span></div>
            <div class="check-item"><input type="checkbox" id="s11_goal" onchange="updateProgress()"><label for="s11_goal">At goal rate/calories</label><select id="nutrGoal" onchange="save()"><option value="">--</option><option value="goal">At goal</option><option value="advancing">Advancing</option><option value="held">Held</option></select></div>
            <div class="check-item"><input type="checkbox" id="s11_ppi" onchange="updateProgress()"><label for="s11_ppi">Stress ulcer prophylaxis</label><select id="ppiStatus" onchange="save()"><option value="">--</option><option value="ppi">PPI</option><option value="h2">H2 blocker</option><option value="none">None needed</option><option value="needs">NEEDS ORDER</option></select><span class="role-tag role-app">APP</span></div>
            <div class="check-item"><input type="checkbox" id="s11_bowel" onchange="updateProgress()"><label for="s11_bowel">Bowel regimen</label><select id="bowelStatus" onchange="save()"><option value="">--</option><option value="regular">Regular BMs</option><option value="constipated">Constipated</option><option value="diarrhea">Diarrhea</option></select><span class="role-tag role-rn">RN</span></div>
          </div>
        </section>
        
        <!-- STEP 12: Family & GOC -->
        <section class="step-section" data-step="12">
          <div class="section-header">
            <div class="section-icon family">👨‍👩‍👧</div>
            <div><div class="section-title">Family & Goals of Care</div><div class="section-subtitle">ABCDEF Bundle: F — Family Engagement</div></div>
            <span class="presenter-badge presenter-md">MD/SW Leads</span>
          </div>
          
          <div class="card">
            <div class="card-title">Communication Log</div>
            <div class="family-log" id="familyLog">
              <div class="family-log-item" style="color:var(--text-muted);text-align:center">No entries yet</div>
            </div>
            <div style="display:flex;gap:.5rem;margin-top:.5rem">
              <input type="text" id="newFamilyNote" placeholder="Add communication note..." style="flex:1;padding:.4rem;border:1px solid var(--border);border-radius:4px;font-size:.8rem">
              <button class="btn btn-secondary" onclick="addFamilyLog()" style="padding:.4rem .75rem">Add</button>
            </div>
          </div>
          
          <div class="card">
            <div class="check-item"><input type="checkbox" id="s12_updated" onchange="updateProgress()"><label for="s12_updated">Family updated today</label><select id="famUpdate" onchange="save()"><option value="yes">Yes</option><option value="no">Needs update</option><option value="meeting">Meeting scheduled</option></select><span class="role-tag role-md">MD</span></div>
            <div class="check-item"><input type="checkbox" id="s12_goc" onchange="updateProgress()"><label for="s12_goc">Goals of care confirmed</label><select id="gocStatus" onchange="save()"><option value="confirmed">Confirmed</option><option value="discuss">Needs discussion</option><option value="pending">Pending family</option></select><span class="role-tag role-md">MD</span></div>
            <div class="check-item"><input type="checkbox" id="s12_understand" onchange="updateProgress()"><label for="s12_understand">Family understanding assessed</label><select id="famUnderstand" onchange="save()"><option value="">--</option><option value="good">Good understanding</option><option value="partial">Partial - needs reinforcement</option><option value="poor">Poor - needs meeting</option></select></div>
            <div class="check-item"><input type="checkbox" id="s12_sw" onchange="updateProgress()"><label for="s12_sw">Social work/case management</label><select id="swStatus" onchange="save()"><option value="">--</option><option value="following">Following</option><option value="consult">Needs consult</option></select><span class="role-tag role-sw">SW</span></div>
            <div class="check-item"><input type="checkbox" id="s12_dispo" onchange="updateProgress()"><label for="s12_dispo">Disposition planning</label><select id="dispoStatus" onchange="save()"><option value="">--</option><option value="icu">Remains ICU</option><option value="stepdown">Stepdown candidate</option><option value="rehab">Rehab screen</option><option value="ltac">LTAC screen</option></select></div>
          </div>
        </section>
        
        <!-- STEP 13: Care Gaps -->
        <section class="step-section" data-step="13">
          <div class="section-header">
            <div class="section-icon" style="background:#fef2f2;color:var(--danger)">⚠️</div>
            <div><div class="section-title">Care Gaps & Barriers</div><div class="section-subtitle">Identify and resolve gaps proactively</div></div>
            <span class="presenter-badge presenter-rn">Team</span>
          </div>
          
          <div class="card">
            <div class="card-title">Active Gaps</div>
            <div id="gapsList"></div>
            <div style="display:flex;gap:.5rem;margin-top:.75rem;flex-wrap:wrap">
              <select id="newGapType" style="padding:.4rem;border:1px solid var(--border);border-radius:4px;font-size:.8rem">
                <option value="order">Missing Order</option>
                <option value="consult">Consult Needed</option>
                <option value="communication">Communication Gap</option>
                <option value="equipment">Equipment Issue</option>
                <option value="other">Other</option>
              </select>
              <input type="text" id="newGapText" placeholder="Describe gap..." style="flex:1;min-width:150px;padding:.4rem;border:1px solid var(--border);border-radius:4px;font-size:.8rem">
              <button class="btn btn-secondary" onclick="addGap()">+ Add Gap</button>
            </div>
          </div>
        </section>
        
        <!-- STEP 14: Plan & Summary -->
        <section class="step-section" data-step="14">
          <div class="section-header">
            <div class="section-icon plan">📝</div>
            <div><div class="section-title">Plan & Summary</div><div class="section-subtitle">Priorities, tasks, metrics</div></div>
            <span class="presenter-badge presenter-md">MD Leads</span>
          </div>
          
          <div class="metrics-bar">
            <div class="metric-box"><div class="value" id="metricAdherence">--%</div><div class="label">Protocol Adherence</div></div>
            <div class="metric-box"><div class="value" id="metricLOS">--</div><div class="label">ICU Days</div></div>
            <div class="metric-box"><div class="value" id="metricGaps">--</div><div class="label">Open Gaps</div></div>
            <div class="metric-box"><div class="value" id="metricChecks">--</div><div class="label">Items Done</div></div>
          </div>
          
          <div class="card">
            <div class="card-title">Top 3 Priorities Today</div>
            <textarea class="notes-area" id="priorities" rows="4" placeholder="1. &#10;2. &#10;3." onchange="save()"></textarea>
          </div>
          
          <div class="card">
            <div class="card-title">Tasks (Owner — Due)</div>
            <textarea class="notes-area" id="tasks" rows="4" placeholder="Task — Owner — Time" onchange="save()"></textarea>
          </div>
          
          <div style="text-align:center;margin-top:1rem">
            <button class="btn btn-success btn-lg" onclick="completePatient()">✓ Complete Rounds for This Patient</button>
          </div>
        </section>
        
      </div>
      
      <footer class="nav-footer">
        <div class="step-info">Step <span id="currentStepNum">1</span> of 14</div>
        <div style="display:flex;gap:.5rem">
          <button class="btn btn-secondary" id="prevBtn" onclick="prevStep()">← Previous</button>
          <button class="btn btn-primary" id="nextBtn" onclick="nextStep()">Next →</button>
        </div>
      </footer>
    </div>
  </main>
</div>

<!-- Add Patient Modal -->
<div class="modal" id="addModal">
  <div class="modal-content">
    <div class="modal-title">Add Patient</div>
    <div class="form-group"><label>Name</label><input type="text" id="newName" placeholder="Last, First"></div>
    <div class="form-row">
      <div class="form-group"><label>Room</label><input type="text" id="newRoom" placeholder="ICU-1"></div>
      <div class="form-group"><label>ICU Day</label><input type="number" id="newICUDay" value="1" min="1"></div>
    </div>
    <div class="form-group"><label>Primary Diagnosis</label>
      <select id="newDx">
        <option value="sah">aSAH</option>
        <option value="ich">ICH</option>
        <option value="stroke">Large Stroke</option>
        <option value="tbi">TBI</option>
        <option value="seizure">Status Epilepticus</option>
        <option value="other">Other</option>
      </select>
    </div>
    <div class="form-row">
      <div class="form-group"><label>EVD?</label><select id="newEVD"><option value="no">No</option><option value="yes">Yes</option></select></div>
      <div class="form-group"><label>ICP Monitor?</label><select id="newICP"><option value="no">No</option><option value="yes">Yes</option></select></div>
    </div>
    <div class="form-row">
      <div class="form-group"><label>cEEG?</label><select id="newEEG"><option value="no">No</option><option value="yes">Yes</option></select></div>
      <div class="form-group"><label>Code Status</label><select id="newCode"><option value="full">Full Code</option><option value="dnr">DNR</option><option value="dni">DNI</option><option value="cmo">CMO</option></select></div>
    </div>
    <div style="display:flex;gap:.5rem;margin-top:1rem">
      <button class="btn btn-success" onclick="addPatient()">Add Patient</button>
      <button class="btn btn-secondary" onclick="closeAddModal()">Cancel</button>
    </div>
  </div>
</div>

<script>
let patients = JSON.parse(localStorage.getItem('neuroicu_v2') || '[]');
let activeId = null;
let currentStep = 1;
const totalSteps = 14;

const stepLabels = ['ID','ON','Neuro','Mon','PSD','Resp','CV','Lab','Line','Mob','Nutr','Fam','Gap','Plan'];

document.addEventListener('DOMContentLoaded', () => {
  renderCensus();
  renderStepNav();
});

function toggleTeam(btn) { btn.classList.toggle('present'); }

function renderCensus() {
  const list = document.getElementById('censusList');
  if (!patients.length) { list.innerHTML = '<p style="color:#94a3b8;font-size:.75rem;text-align:center;padding:1rem">No patients</p>'; return; }
  list.innerHTML = patients.map(p => `
    <div class="census-item ${p.id === activeId ? 'active' : ''} ${p.completed ? 'completed' : ''}" onclick="selectPatient('${p.id}')">
      <div class="census-name">${p.name || 'Unknown'}</div>
      <div class="census-meta">
        <span>${p.room || '--'}</span>
        <span class="dx-tag dx-${p.dx}">${p.dx?.toUpperCase() || '--'}</span>
        ${p.evd === 'yes' ? '<span class="dx-tag" style="background:#0891b2">EVD</span>' : ''}
      </div>
    </div>
  `).join('');
}

function renderStepNav() {
  document.getElementById('stepNav').innerHTML = stepLabels.map((l, i) => `<div class="step-dot" data-step="${i+1}" onclick="goToStep(${i+1})">${i+1}</div>`).join('');
}

function openAddModal() { document.getElementById('addModal').classList.add('show'); }
function closeAddModal() { document.getElementById('addModal').classList.remove('show'); }

function addPatient() {
  const name = document.getElementById('newName').value.trim();
  if (!name) { alert('Enter patient name'); return; }
  const p = {
    id: 'pt_' + Date.now(),
    name,
    room: document.getElementById('newRoom').value.trim(),
    dx: document.getElementById('newDx').value,
    icuDay: document.getElementById('newICUDay').value,
    evd: document.getElementById('newEVD').value,
    icp: document.getElementById('newICP').value,
    eeg: document.getElementById('newEEG').value,
    code: document.getElementById('newCode').value,
    data: {},
    gaps: [],
    familyLog: [],
    completed: false
  };
  patients.push(p);
  saveAll();
  closeAddModal();
  renderCensus();
  selectPatient(p.id);
  document.getElementById('newName').value = '';
  document.getElementById('newRoom').value = '';
}

function selectPatient(id) {
  activeId = id;
  currentStep = 1;
  const p = patients.find(x => x.id === id);
  if (!p) return;
  
  document.getElementById('emptyState').style.display = 'none';
  document.getElementById('patientArea').style.display = 'flex';
  
  document.getElementById('ptTitle').textContent = `${p.name} — ${p.room || 'No Room'}`;
  document.getElementById('ptSubtitle').textContent = `${p.dx?.toUpperCase() || '--'} | ICU Day ${p.icuDay || '?'} | ${(p.code || 'Full').toUpperCase()} CODE`;
  
  // Show/hide monitoring sections
  document.getElementById('icpSection').style.display = p.icp === 'yes' ? '' : 'none';
  document.getElementById('evdSection').style.display = p.evd === 'yes' ? '' : 'none';
  document.getElementById('eegSection').style.display = p.eeg === 'yes' ? '' : 'none';
  document.getElementById('noMonitoring').style.display = (p.icp === 'yes' || p.evd === 'yes' || p.eeg === 'yes') ? 'none' : '';
  
  // Show VISAGE for TBI
  document.getElementById('visageSection').style.display = p.dx === 'tbi' ? '' : 'none';
  
  loadData(p);
  renderCensus();
  goToStep(1);
}

function loadData(p) {
  const d = p.data || {};
  document.querySelectorAll('input[type="checkbox"]').forEach(cb => { cb.checked = d[cb.id] || false; updateCheckStyle(cb); });
  document.querySelectorAll('select, input[type="text"], input[type="number"], textarea').forEach(el => { if (el.id && d[el.id] !== undefined) el.value = d[el.id]; });
  
  // ICU day
  if (p.icuDay) document.getElementById('icuDay').value = p.icuDay;
  if (p.code) document.getElementById('codeStatus').value = p.code;
  if (p.dx) document.getElementById('primaryDx').value = p.dx;
  
  // Render gaps
  renderGaps(p.gaps || []);
  
  // Render family log
  renderFamilyLog(p.familyLog || []);
  
  calcGCS();
  updateICP();
  updateProgress();
  checkAlerts();
}

function save() {
  if (!activeId) return;
  const p = patients.find(x => x.id === activeId);
  if (!p) return;
  p.data = {};
  document.querySelectorAll('input[type="checkbox"]').forEach(cb => { p.data[cb.id] = cb.checked; });
  document.querySelectorAll('select, input[type="text"], input[type="number"], textarea').forEach(el => { if (el.id) p.data[el.id] = el.value; });
  p.icuDay = document.getElementById('icuDay').value;
  p.code = document.getElementById('codeStatus').value;
  saveAll();
}

function saveAll() {
  localStorage.setItem('neuroicu_v2', JSON.stringify(patients));
}

function updateCheckStyle(cb) {
  cb.closest('.check-item')?.classList.toggle('done', cb.checked);
}

function updateProgress() {
  if (!activeId) return;
  const p = patients.find(x => x.id === activeId);
  
  const checks = document.querySelectorAll('.step-section input[type="checkbox"]');
  const done = [...checks].filter(c => c.checked).length;
  const total = checks.length;
  const pct = Math.round((done / total) * 100);
  
  document.getElementById('progressFill').style.width = pct + '%';
  document.getElementById('progressText').textContent = `${done} / ${total}`;
  
  // Update step dots
  for (let s = 1; s <= totalSteps; s++) {
    const section = document.querySelector(`.step-section[data-step="${s}"]`);
    const sectionChecks = section?.querySelectorAll('input[type="checkbox"]') || [];
    const sectionDone = [...sectionChecks].filter(c => c.checked).length;
    const dot = document.querySelector(`.step-dot[data-step="${s}"]`);
    if (dot) {
      dot.classList.remove('done', 'active', 'alert');
      if (s === currentStep) dot.classList.add('active');
      else if (sectionChecks.length > 0 && sectionDone === sectionChecks.length) dot.classList.add('done');
    }
  }
  
  // Update metrics
  document.getElementById('metricAdherence').textContent = pct + '%';
  document.getElementById('metricLOS').textContent = p?.icuDay || '--';
  document.getElementById('metricGaps').textContent = (p?.gaps?.filter(g => !g.resolved).length) || 0;
  document.getElementById('metricChecks').textContent = done;
  
  save();
}

function goToStep(n) {
  currentStep = n;
  document.querySelectorAll('.step-section').forEach(s => s.classList.remove('active'));
  document.querySelector(`.step-section[data-step="${n}"]`)?.classList.add('active');
  
  document.querySelectorAll('.step-dot').forEach(d => d.classList.remove('active'));
  document.querySelector(`.step-dot[data-step="${n}"]`)?.classList.add('active');
  
  document.getElementById('currentStepNum').textContent = n;
  document.getElementById('prevBtn').disabled = n === 1;
  document.getElementById('nextBtn').textContent = n === totalSteps ? 'Finish' : 'Next →';
  
  document.getElementById('contentArea').scrollTop = 0;
  updateProgress();
}

function nextStep() { if (currentStep < totalSteps) goToStep(currentStep + 1); else completePatient(); }
function prevStep() { if (currentStep > 1) goToStep(currentStep - 1); }

function calcGCS() {
  const e = parseInt(document.getElementById('gcsE').value) || 0;
  const vRaw = document.getElementById('gcsV').value || '';
  const v = vRaw.toUpperCase() === 'T' ? 1 : (parseInt(vRaw) || 0);
  const m = parseInt(document.getElementById('gcsM').value) || 0;
  const total = e + v + m;
  const el = document.getElementById('gcsTotal');
  if (total > 0) {
    el.textContent = total + (vRaw.toUpperCase() === 'T' ? 'T' : '');
    el.className = 'gcs-total ' + (total <= 8 ? 'severe' : total <= 12 ? 'moderate' : 'mild');
  } else {
    el.textContent = '--';
    el.className = 'gcs-total';
  }
}

function updateICP() {
  const icp = parseInt(document.getElementById('icpCurrent').value) || 0;
  const map = parseInt(document.getElementById('mapCurrent').value) || 0;
  document.getElementById('icpValue').textContent = icp || '--';
  document.getElementById('mapValue').textContent = map || '--';
  const icpBox = document.getElementById('icpBox');
  icpBox.classList.toggle('alert', icp > 22);
  
  if (icp > 0 && map > 0) {
    const cpp = map - icp;
    document.getElementById('cppValue').textContent = cpp;
    document.getElementById('cppBox').classList.toggle('alert', cpp < 60);
  } else {
    document.getElementById('cppValue').textContent = '--';
  }
}

function checkAlerts() {
  // Check neuro decline
  const neuroChange = document.getElementById('neuroChangeON').value;
  let alerts = '';
  if (neuroChange === 'declined') {
    alerts += '<div class="alert-banner danger">🚨 Neuro Status DECLINED overnight — Immediate evaluation required</div>';
  }
  document.getElementById('neuroAlerts').innerHTML = alerts;
  
  // Cardiac alerts
  checkCardiac();
  
  // EEG alerts
  checkEEG();
  
  // EVD day alert
  checkEVDDay();
}

function checkCardiac() {
  const p = patients.find(x => x.id === activeId);
  if (!p || (p.dx !== 'sah' && p.dx !== 'tbi')) return;
  
  let alerts = '';
  const trop = document.getElementById('tropStatus').value;
  const echo = document.getElementById('echoStatus').value;
  const ecg = document.getElementById('ecgStatus').value;
  
  if (trop === 'elevated' || trop === 'trending') {
    alerts += '<div class="alert-banner cardiac">❤️ Elevated troponin — Consider neuro-cardiac syndrome (SAH/TBI)</div>';
  }
  if (echo === 'takotsubo') {
    alerts += '<div class="alert-banner cardiac">❤️ Takotsubo/Stress cardiomyopathy — Monitor for heart failure</div>';
  }
  if (ecg === 'arrhythmia') {
    alerts += '<div class="alert-banner cardiac">❤️ Arrhythmia detected — Review telemetry, consider cardiology</div>';
  }
  
  document.getElementById('cardiacAlerts').innerHTML = alerts;
}

function checkEEG() {
  const status = document.getElementById('eegStatus').value;
  document.getElementById('seizureAlert').style.display = (status === 'seizures' || status === 'ncse') ? '' : 'none';
}

function checkEVDDay() {
  const day = parseInt(document.getElementById('evdDay').value) || 0;
  document.getElementById('evdDayDisplay').textContent = day;
  document.getElementById('evdAlert').style.display = day >= 10 ? '' : 'none';
}

function checkTrach() {
  const p = patients.find(x => x.id === activeId);
  // Show VISAGE for intubated TBI patients in early days
  const airway = document.getElementById('airway').value;
  const icuDay = parseInt(document.getElementById('icuDay').value) || 1;
  document.getElementById('visageSection').style.display = (p?.dx === 'tbi' && airway === 'ett' && icuDay <= 5) ? '' : 'none';
}

function calcVISAGE() {
  const age = parseInt(document.getElementById('visAge').value) || 0;
  const gcs = parseInt(document.getElementById('visGCS').value) || 0;
  const iss = parseInt(document.getElementById('visISS').value) || 0;
  const thor = parseInt(document.getElementById('visThor').value) || 0;
  const total = age + gcs + iss + thor;
  
  const result = document.getElementById('visageResult');
  if (total >= 6) {
    result.textContent = `Score: ${total} — ✓ CANDIDATE for early trach (Days 1-3)`;
    result.className = 'visage-result candidate';
  } else {
    result.textContent = `Score: ${total} — Not candidate for early trach`;
    result.className = 'visage-result not-candidate';
  }
}

function verifyOrder(type) {
  const orderEl = document.getElementById(type === 'evdHeight' ? 'evdHeightOrder' : type === 'drain' ? 'drainOrder' : 'scdOrder');
  const actualEl = document.getElementById(type === 'evdHeight' ? 'evdHeightActual' : type === 'drain' ? 'drainActual' : 'scdActual');
  const iconEl = document.getElementById(type === 'evdHeight' ? 'evdHeightIcon' : type === 'drain' ? 'drainIcon' : 'scdIcon');
  
  const isMismatch = actualEl.value === 'mismatch' || actualEl.value === 'off';
  orderEl.classList.toggle('mismatch', isMismatch);
  actualEl.classList.toggle('mismatch', isMismatch);
  
  if (actualEl.value === 'match' || actualEl.value === 'on') {
    iconEl.textContent = '✓';
    iconEl.className = 'verify-icon match';
  } else if (isMismatch) {
    iconEl.textContent = '✗';
    iconEl.className = 'verify-icon mismatch';
  } else {
    iconEl.textContent = '';
  }
}

// Gaps management
function renderGaps(gaps) {
  const list = document.getElementById('gapsList');
  if (!gaps.length) { list.innerHTML = '<p style="color:var(--text-muted);font-size:.8rem">No active gaps — great!</p>'; return; }
  list.innerHTML = gaps.map((g, i) => `
    <div class="gap-item ${g.resolved ? 'resolved' : ''}">
      <input type="checkbox" ${g.resolved ? 'checked' : ''} onchange="toggleGap(${i})">
      <span style="flex:1"><strong>${g.type}:</strong> ${g.text}</span>
      <button onclick="removeGap(${i})" style="background:none;border:none;cursor:pointer;color:var(--text-muted)">✕</button>
    </div>
  `).join('');
}

function addGap() {
  const p = patients.find(x => x.id === activeId);
  if (!p) return;
  const type = document.getElementById('newGapType').value;
  const text = document.getElementById('newGapText').value.trim();
  if (!text) return;
  if (!p.gaps) p.gaps = [];
  p.gaps.push({ type, text, resolved: false });
  document.getElementById('newGapText').value = '';
  renderGaps(p.gaps);
  saveAll();
  updateProgress();
}

function toggleGap(i) {
  const p = patients.find(x => x.id === activeId);
  if (!p || !p.gaps[i]) return;
  p.gaps[i].resolved = !p.gaps[i].resolved;
  renderGaps(p.gaps);
  saveAll();
  updateProgress();
}

function removeGap(i) {
  const p = patients.find(x => x.id === activeId);
  if (!p) return;
  p.gaps.splice(i, 1);
  renderGaps(p.gaps);
  saveAll();
  updateProgress();
}

// Family log
function renderFamilyLog(log) {
  const el = document.getElementById('familyLog');
  if (!log.length) { el.innerHTML = '<div class="family-log-item" style="color:var(--text-muted);text-align:center">No entries yet</div>'; return; }
  el.innerHTML = log.map(l => `<div class="family-log-item"><div class="date">${l.date}</div>${l.note}</div>`).join('');
}

function addFamilyLog() {
  const p = patients.find(x => x.id === activeId);
  if (!p) return;
  const note = document.getElementById('newFamilyNote').value.trim();
  if (!note) return;
  if (!p.familyLog) p.familyLog = [];
  p.familyLog.unshift({ date: new Date().toLocaleString(), note });
  document.getElementById('newFamilyNote').value = '';
  renderFamilyLog(p.familyLog);
  saveAll();
}

function completePatient() {
  const p = patients.find(x => x.id === activeId);
  if (!p) return;
  p.completed = true;
  saveAll();
  renderCensus();
  alert(`Rounds completed for ${p.name}`);
}

function exportHandoff() {
  const p = patients.find(x => x.id === activeId);
  if (!p) { alert('Select a patient first'); return; }
  const d = p.data || {};
  
  // Calculate GCS
  const e = parseInt(d.gcsE) || 0;
  const vRaw = d.gcsV || '';
  const v = vRaw.toString().toUpperCase() === 'T' ? 1 : (parseInt(vRaw) || 0);
  const m = parseInt(d.gcsM) || 0;
  const gcsTotal = (e + v + m) > 0 ? (e + v + m) + (vRaw.toString().toUpperCase() === 'T' ? 'T' : '') : '--';
  
  let txt = 'NEUROICU HANDOFF\n' + '='.repeat(50) + '\n';
  txt += p.name + ' | Room: ' + (p.room || '--') + ' | ICU Day: ' + (p.icuDay || '--') + '\n';
  txt += 'Dx: ' + (p.dx || '--').toUpperCase() + ' | Code: ' + (p.code || '--').toUpperCase() + '\n';
  txt += 'GCS: ' + gcsTotal + '\n\n';
  
  if (d.priorities) txt += 'PRIORITIES:\n' + d.priorities + '\n\n';
  if (d.tasks) txt += 'TASKS:\n' + d.tasks + '\n\n';
  
  if (p.gaps && p.gaps.filter(g => !g.resolved).length > 0) {
    txt += 'OPEN GAPS:\n' + p.gaps.filter(g => !g.resolved).map(g => '- ' + g.type + ': ' + g.text).join('\n') + '\n\n';
  }
  
  txt += 'Generated: ' + new Date().toLocaleString();
  
  // Download as text file
  const blob = new Blob([txt], { type: 'text/plain;charset=utf-8;' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'Handoff_' + (p.name || 'Patient').replace(/[^a-z0-9]/gi, '_') + '_' + new Date().toISOString().slice(0,10) + '.txt';
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
  URL.revokeObjectURL(url);
}

function exportExcel() {
  // Export all patients or single patient
  const exportAll = patients.length > 1 ? confirm('Export all patients? (Cancel for current patient only)') : false;
  const patientsToExport = exportAll ? patients : [patients.find(x => x.id === activeId)].filter(Boolean);
  
  if (!patientsToExport.length) { alert('No patients to export. Add a patient first.'); return; }
  
  // Build CSV headers
  const headers = [
    'Name','Room','ICU_Day','Diagnosis','Code_Status','EVD','ICP_Monitor','EEG',
    'GCS_E','GCS_V','GCS_M','GCS_Total','Pupil_L','Pupil_R','Pupil_React','Focal_Deficits',
    'ICP_Current','MAP_Current','CPP','ICP_Trend',
    'EVD_Day','EVD_Height','EVD_Output','CSF_Appearance',
    'EEG_Status','EEG_Background','AED_Status',
    'RASS','RASS_Goal','CAM_ICU','Pain_Status',
    'Airway','Vent_Mode','SBT_Status',
    'MAP_Target','Pressor_Status','Fluid_Status','Glucose_Status',
    'Troponin','BNP','ECG','Echo',
    'Sodium_Status','Lyte_Status','Abx_Status',
    'Central_Line','Foley','DVT_Pharm','Skin_Status',
    'Mobility_Level','PT_Status','SLP_Status',
    'Nutrition_Route','Nutrition_Goal','PPI_Status','Bowel_Status',
    'Family_Updated','GOC_Status','Dispo_Status',
    'Protocol_Adherence','Open_Gaps','Priorities','Tasks',
    'Rounds_Completed','Export_Date'
  ];
  
  // Build rows
  const rows = patientsToExport.map(p => {
    const d = p.data || {};
    const totalChecks = 50; // approximate
    let doneCount = 0;
    for (let key in d) { if (d[key] === true) doneCount++; }
    const adherence = Math.round((doneCount/totalChecks)*100) + '%';
    const openGaps = (p.gaps?.filter(g => !g.resolved).length) || 0;
    
    // Calculate GCS
    const e = parseInt(d.gcsE) || 0;
    const vRaw = d.gcsV || '';
    const v = vRaw.toString().toUpperCase() === 'T' ? 1 : (parseInt(vRaw) || 0);
    const m = parseInt(d.gcsM) || 0;
    const gcsTotal = (e + v + m) > 0 ? (e + v + m) + (vRaw.toString().toUpperCase() === 'T' ? 'T' : '') : '';
    
    // Calculate CPP
    const icp = parseInt(d.icpCurrent) || 0;
    const map = parseInt(d.mapCurrent) || 0;
    const cpp = (icp > 0 && map > 0) ? (map - icp) : '';
    
    return [
      p.name || '', p.room || '', p.icuDay || '', (p.dx || '').toUpperCase(), p.code || '', p.evd || '', p.icp || '', p.eeg || '',
      d.gcsE || '', d.gcsV || '', d.gcsM || '', gcsTotal, d.pupilL || '', d.pupilR || '', d.pupilReact || '', d.focalDef || '',
      d.icpCurrent || '', d.mapCurrent || '', cpp, d.icpTrend || '',
      d.evdDay || '', d.evdHeight || '', d.evdOutput || '', d.csfAppear || '',
      d.eegStatus || '', d.eegBg || '', d.aedStatus || '',
      d.rass || '', d.rassGoal || '', d.camResult || '', d.painStatus || '',
      d.airway || '', d.ventMode || '', d.sbtStatus || '',
      d.mapTarget || '', d.pressorStatus || '', d.fluidStatus || '', d.glucoseStatus || '',
      d.tropStatus || '', d.bnpStatus || '', d.ecgStatus || '', d.echoStatus || '',
      d.naTarget || '', d.lyteStatus || '', d.abxStatus || '',
      d.centralLine || '', d.foleyStatus || '', d.dvtPharm || '', d.skinStatus || '',
      d.mobLevel || '', d.ptStatus || '', d.slpStatus || '',
      d.nutrRoute || '', d.nutrGoal || '', d.ppiStatus || '', d.bowelStatus || '',
      d.famUpdate || '', d.gocStatus || '', d.dispoStatus || '',
      adherence, openGaps, (d.priorities || '').replace(/\n/g, ' | '), (d.tasks || '').replace(/\n/g, ' | '),
      p.completed ? 'Yes' : 'No', new Date().toLocaleString()
    ];
  });
  
  // Convert to CSV
  const csvContent = [headers, ...rows].map(row => 
    row.map(cell => {
      const str = String(cell ?? '');
      return str.includes(',') || str.includes('"') || str.includes('\n') 
        ? '"' + str.replace(/"/g, '""') + '"' 
        : str;
    }).join(',')
  ).join('\n');
  
  // Download
  const blob = new Blob(['\ufeff' + csvContent], { type: 'text/csv;charset=utf-8;' });
  const url = URL.createObjectURL(blob);
  const a = document.createElement('a');
  a.href = url;
  a.download = 'NeuroICU_Rounds_' + new Date().toISOString().slice(0,10) + '.csv';
  document.body.appendChild(a);
  a.click();
  document.body.removeChild(a);
  URL.revokeObjectURL(url);
}
</script>
</body>
</html>
