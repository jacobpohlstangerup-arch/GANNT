<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700&family=DM+Sans:wght@300;400;500&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#f7f5f0;--surface:#fff;--border:#e2ddd6;--text:#1c1917;--muted:#78716c;
  --accent:#0f4c75;--accent2:#1b6ca8;--accentbg:#eef4fa;
  --danger:#b91c1c;--dangerbg:#fef2f2;
  --shadow:0 1px 3px rgba(0,0,0,.07),0 4px 16px rgba(0,0,0,.05);
  --radius:7px;
}
body{font-family:'DM Sans',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;font-size:13.5px}

/* HEADER */
header{background:var(--accent);color:#fff;padding:0 24px;height:52px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:200}
.logo{font-family:'Syne',sans-serif;font-size:16px;font-weight:700;letter-spacing:.03em}
.logo span{opacity:.5;font-weight:400}
.hbtns{display:flex;gap:8px;align-items:center}
.langbtn{background:rgba(255,255,255,.12);border:1px solid rgba(255,255,255,.25);color:#fff;padding:4px 12px;border-radius:4px;font-family:'Syne',sans-serif;font-size:11px;font-weight:600;letter-spacing:.08em;cursor:pointer;transition:background .15s}
.langbtn:hover{background:rgba(255,255,255,.22)}

/* LAYOUT */
.app{display:grid;grid-template-columns:260px 1fr;min-height:calc(100vh - 52px)}

/* SIDEBAR */
.sidebar{background:#fff;border-right:1px solid var(--border);display:flex;flex-direction:column;overflow:hidden}
.sidebar-head{padding:16px;border-bottom:1px solid var(--border);display:flex;flex-direction:column;gap:10px}
.sidebar-title{font-family:'Syne',sans-serif;font-size:11px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--muted)}
.btn-new{width:100%;padding:9px;background:var(--accent);color:#fff;border:none;border-radius:var(--radius);font-family:'DM Sans',sans-serif;font-size:13px;font-weight:500;cursor:pointer;transition:background .15s;display:flex;align-items:center;justify-content:center;gap:6px}
.btn-new:hover{background:var(--accent2)}
.project-list{flex:1;overflow-y:auto;padding:8px}
.proj-item{display:flex;align-items:center;gap:8px;padding:9px 10px;border-radius:6px;cursor:pointer;transition:background .12s;border:1px solid transparent;margin-bottom:3px}
.proj-item:hover{background:var(--accentbg)}
.proj-item.active{background:var(--accentbg);border-color:#c5d9ed}
.proj-name{flex:1;font-weight:500;font-size:13px;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.proj-delete{opacity:0;transition:opacity .15s;background:none;border:none;color:var(--danger);cursor:pointer;padding:2px 5px;border-radius:3px;font-size:14px;line-height:1}
.proj-item:hover .proj-delete{opacity:1}
.proj-dot{width:9px;height:9px;border-radius:50%;flex-shrink:0}

/* MAIN */
.main{flex:1;overflow:auto;display:flex;flex-direction:column}
.main-inner{padding:24px;flex:1}

/* PANEL */
.panel{background:var(--surface);border:1px solid var(--border);border-radius:10px;margin-bottom:18px;box-shadow:var(--shadow);overflow:hidden}
.ph{padding:13px 18px;border-bottom:1px solid var(--border);background:#faf9f7;display:flex;align-items:center;justify-content:space-between;gap:10px}
.ph-title{font-family:'Syne',sans-serif;font-size:11px;font-weight:600;letter-spacing:.1em;text-transform:uppercase;color:var(--muted)}
.pb{padding:18px}

/* FORM */
.settings-grid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:14px;margin-bottom:0}
.fg{display:flex;flex-direction:column;gap:5px}
.fg label{font-family:'Syne',sans-serif;font-size:10px;font-weight:600;letter-spacing:.08em;text-transform:uppercase;color:var(--muted)}
input[type=text],input[type=number],input[type=date],select{
  padding:8px 10px;border:1px solid var(--border);border-radius:5px;
  font-family:'DM Sans',sans-serif;font-size:13px;background:#fff;color:var(--text);
  transition:border-color .15s;width:100%
}
input:focus,select:focus{outline:none;border-color:var(--accent);box-shadow:0 0 0 3px rgba(15,76,117,.09)}

.task-form-grid{display:grid;grid-template-columns:2fr 1fr 1fr auto auto;gap:10px;align-items:end;margin-bottom:16px}
.task-list{list-style:none}
.task-row{display:grid;grid-template-columns:2fr 1fr 1fr auto;gap:10px;align-items:center;padding:9px 0;border-bottom:1px solid #f0ede8}
.task-row:last-child{border-bottom:none}
.task-row.editing{background:var(--accentbg);margin:0 -18px;padding:9px 18px}
.task-cat{font-weight:500;display:flex;align-items:center;gap:8px}
.dot{width:9px;height:9px;border-radius:50%;flex-shrink:0}
.task-dates{font-family:'Syne',sans-serif;font-size:12px;color:var(--muted)}
.task-acts{display:flex;gap:5px}

/* BUTTONS */
.btn{display:inline-flex;align-items:center;gap:5px;padding:7px 13px;border-radius:5px;border:1px solid transparent;font-family:'DM Sans',sans-serif;font-size:13px;font-weight:500;cursor:pointer;transition:all .15s;white-space:nowrap}
.btn-primary{background:var(--accent);color:#fff;border-color:var(--accent)}
.btn-primary:hover{background:var(--accent2)}
.btn-secondary{background:#fff;color:var(--text);border-color:var(--border)}
.btn-secondary:hover{background:var(--bg);border-color:#b5b0a8}
.btn-danger{background:#fff;color:var(--danger);border-color:#f0a0a0;padding:5px 9px;font-size:12px}
.btn-danger:hover{background:var(--dangerbg)}
.btn-sm{padding:5px 10px;font-size:12px}

/* ALERT */
.alert{padding:9px 13px;border-radius:5px;font-size:13px;margin-bottom:12px;border:1px solid}
.alert-success{background:var(--accentbg);border-color:#a0c4e0;color:var(--accent)}
.alert-error{background:var(--dangerbg);border-color:#f0a0a0;color:var(--danger)}

/* GANTT */
.gantt-wrap{overflow-x:auto;padding:0}
.gantt-canvas-wrap{padding:16px}
#ganttCanvas{max-width:100%;display:block;border-radius:6px}

/* EMPTY */
.empty{text-align:center;padding:36px 20px;color:var(--muted)}
.empty p{font-size:14px}

.filewrap{position:relative;display:inline-flex}
.filewrap input[type=file]{position:absolute;opacity:0;width:100%;height:100%;cursor:pointer}

.toolbar{display:flex;gap:8px;flex-wrap:wrap}
</style>
</head>
<body>

<header>
  <div class="logo">GANTT <span>/ Research Planner</span></div>
  <div class="hbtns">
    <button class="langbtn" id="langBtn" onclick="toggleLang()">EN</button>
  </div>
</header>

<div class="app">
  <!-- SIDEBAR -->
  <div class="sidebar">
    <div class="sidebar-head">
      <div class="sidebar-title" data-k="projects">Projekter</div>
      <button class="btn-new" onclick="newProject()">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
        <span data-k="newProject">Nyt projekt</span>
      </button>
    </div>
    <div class="project-list" id="projectList"></div>
  </div>

  <!-- MAIN -->
  <div class="main">
    <div class="main-inner" id="mainContent">
      <div class="empty"><p data-k="selectOrCreate">Vælg et projekt fra listen, eller opret et nyt.</p></div>
    </div>
  </div>
</div>

<script>
// ─── TRANSLATIONS ──────────────────────────────────────────────────────────
const L = {
  da:{
    projects:'Projekter', newProject:'Nyt projekt', selectOrCreate:'Vælg et projekt, eller opret et nyt.',
    settings:'Indstillinger', projectName:'Projektnavn', startYear:'Startår', duration:'Varighed (år)',
    tasks:'Opgaver', importExcel:'Importer Excel',
    category:'Kategori', startDate:'Startdato (DD-MM-ÅÅÅÅ)', endDate:'Slutdato (DD-MM-ÅÅÅÅ)',
    add:'Tilføj', save:'Gem', cancel:'Annuller', edit:'Rediger', delete:'Slet',
    ganttChart:'Gantt Chart', exportPNG:'Eksportér PNG', exportJPEG:'Eksportér JPEG', exportExcel:'Eksportér Excel',
    noTasks:'Ingen opgaver endnu.',
    errorFields:'Udfyld alle felter.', errorDates:'Startdato skal være før slutdato.',
    errorDateFmt:'Ugyldigt datoformat. Brug DD-MM-ÅÅÅÅ.',
    imported:'opgaver importeret.', task:'Opgave',
    quarters:['1. kvartal','2. kvartal','3. kvartal','4. kvartal'],
    months:['Jan','Feb','Mar','Apr','Maj','Jun','Jul','Aug','Sep','Okt','Nov','Dec'],
    untitledProject:'Nyt projekt',
    confirmDelete:'Slet dette projekt?',
    year:'År',
  },
  en:{
    projects:'Projects', newProject:'New Project', selectOrCreate:'Select a project or create a new one.',
    settings:'Settings', projectName:'Project Name', startYear:'Start Year', duration:'Duration (years)',
    tasks:'Tasks', importExcel:'Import Excel',
    category:'Category', startDate:'Start Date (DD-MM-YYYY)', endDate:'End Date (DD-MM-YYYY)',
    add:'Add', save:'Save', cancel:'Cancel', edit:'Edit', delete:'Delete',
    ganttChart:'Gantt Chart', exportPNG:'Export PNG', exportJPEG:'Export JPEG', exportExcel:'Export Excel',
    noTasks:'No tasks yet.',
    errorFields:'Please fill in all fields.', errorDates:'Start date must be before end date.',
    errorDateFmt:'Invalid date format. Use DD-MM-YYYY.',
    imported:'tasks imported.',task:'Task',
    quarters:['1st Quarter','2nd Quarter','3rd Quarter','4th Quarter'],
    months:['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'],
    untitledProject:'New Project',
    confirmDelete:'Delete this project?',
    year:'Year',
  }
};
let lang='da';
const t=k=>L[lang][k]||k;

// ─── STATE ─────────────────────────────────────────────────────────────────
const DEFAULT_CATS=[
  'Planning & Preparation','Literature Review','Methodology Design',
  'Ethical Approval','Data Collection','Data Analysis','Writing & Revision','Final Submission'
];
const BAR_COLORS=['#0f4c75','#1b6ca8','#2e86de','#48bfe3','#006d77','#52b788','#e76f51','#f4a261','#457b9d','#a8dadc','#8338ec','#bc6c25'];
let projects=[];
let activeId=null;
let nextPid=1,nextTid=1;

function proj(){return projects.find(p=>p.id===activeId)}

// ─── DATE UTILS ────────────────────────────────────────────────────────────
// EU display: DD-MM-YYYY ↔ internal: YYYY-MM-DD
function toISO(d){
  if(!d)return'';
  if(d instanceof Date){
    const y=d.getFullYear(),m=String(d.getMonth()+1).padStart(2,'0'),dd=String(d.getDate()).padStart(2,'0');
    return`${y}-${m}-${dd}`;
  }
  d=String(d).trim();
  // already ISO
  if(/^\d{4}-\d{2}-\d{2}$/.test(d))return d;
  // DD-MM-YYYY
  const m=d.match(/^(\d{1,2})[.\-\/](\d{1,2})[.\-\/](\d{4})$/);
  if(m)return`${m[3]}-${m[2].padStart(2,'0')}-${m[1].padStart(2,'0')}`;
  return'';
}
function toEU(iso){
  if(!iso)return'';
  const m=iso.match(/^(\d{4})-(\d{2})-(\d{2})$/);
  if(!m)return iso;
  return`${m[3]}-${m[2]}-${m[1]}`;
}
function parseEU(s){
  // Accepts DD-MM-YYYY or DD/MM/YYYY or DD.MM.YYYY
  const m=String(s).trim().match(/^(\d{1,2})[.\-\/](\d{1,2})[.\-\/](\d{4})$/);
  if(!m)return null;
  const d=new Date(`${m[3]}-${m[2].padStart(2,'0')}-${m[1].padStart(2,'0')}`);
  return isNaN(d)?null:d;
}
function isValidEU(s){return parseEU(s)!==null}

// ─── PROJECT MANAGEMENT ────────────────────────────────────────────────────
function makeDefaultTasks(){
  const year=new Date().getFullYear();
  const spans=[
    [1,1,3,31],[2,1,5,30],[3,1,6,30],[4,1,5,31],
    [5,1,8,31],[6,1,10,31],[8,1,11,30],[10,1,12,31]
  ];
  return DEFAULT_CATS.map((cat,i)=>{
    const [sm,sd,em,ed]=spans[i]||[1,1,12,31];
    return{
      id:nextTid++,category:cat,
      start:toISO(new Date(year,sm-1,sd)),
      end:toISO(new Date(year,em-1,ed)),
      color:BAR_COLORS[i%BAR_COLORS.length]
    };
  });
}

function newProject(){
  const p={
    id:nextPid++,
    name:t('untitledProject')+' '+(projects.length+1),
    startYear:new Date().getFullYear(),
    duration:1,
    tasks:makeDefaultTasks()
  };
  projects.push(p);
  setActive(p.id);
  renderSidebar();
  // focus name input
  setTimeout(()=>{const el=document.getElementById('projNameInput');if(el)el.focus();},80);
}

function deleteProject(id,e){
  e.stopPropagation();
  if(!confirm(t('confirmDelete')))return;
  projects=projects.filter(p=>p.id!==id);
  if(activeId===id){activeId=projects.length?projects[0].id:null}
  renderSidebar();
  renderMain();
}

function setActive(id){
  activeId=id;
  renderSidebar();
  renderMain();
}

// ─── SIDEBAR ───────────────────────────────────────────────────────────────
function renderSidebar(){
  const el=document.getElementById('projectList');
  if(!projects.length){el.innerHTML=`<div style="padding:16px;color:var(--muted);font-size:12px">${t('noTasks')}</div>`;return}
  el.innerHTML=projects.map((p,i)=>`
    <div class="proj-item${p.id===activeId?' active':''}" onclick="setActive(${p.id})">
      <div class="proj-dot" style="background:${BAR_COLORS[i%BAR_COLORS.length]}"></div>
      <div class="proj-name">${esc(p.name)}</div>
      <button class="proj-delete" onclick="deleteProject(${p.id},event)" title="Slet">✕</button>
    </div>`).join('');
}

// ─── MAIN CONTENT ──────────────────────────────────────────────────────────
function renderMain(){
  const mc=document.getElementById('mainContent');
  const p=proj();
  if(!p){mc.innerHTML=`<div class="empty"><p data-k="selectOrCreate">${t('selectOrCreate')}</p></div>`;return}

  mc.innerHTML=`
  <div id="alertBox" style="display:none"></div>

  <!-- Settings -->
  <div class="panel">
    <div class="ph"><span class="ph-title" data-k="settings">${t('settings')}</span></div>
    <div class="pb">
      <div class="settings-grid">
        <div class="fg">
          <label data-k="projectName">${t('projectName')}</label>
          <input type="text" id="projNameInput" value="${esc(p.name)}" oninput="updateProjectName(this.value)">
        </div>
        <div class="fg">
          <label data-k="startYear">${t('startYear')}</label>
          <input type="number" id="startYearInput" value="${p.startYear}" min="2000" max="2050" onchange="updateProjectYear()">
        </div>
        <div class="fg">
          <label data-k="duration">${t('duration')}</label>
          <select id="durationInput" onchange="updateProjectDuration()">
            ${[1,2,3,4,5].map(n=>`<option value="${n}"${p.duration===n?' selected':''}>${n}</option>`).join('')}
          </select>
        </div>
      </div>
    </div>
  </div>

  <!-- Tasks -->
  <div class="panel">
    <div class="ph">
      <span class="ph-title" data-k="tasks">${t('tasks')}</span>
      <div class="toolbar">
        <div class="filewrap">
          <button class="btn btn-secondary btn-sm">
            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M21 15v4a2 2 0 01-2 2H5a2 2 0 01-2-2v-4"/><polyline points="17 8 12 3 7 8"/><line x1="12" y1="3" x2="12" y2="15"/></svg>
            ${t('importExcel')}
          </button>
          <input type="file" accept=".xlsx,.xls" onchange="importExcel(event)">
        </div>
      </div>
    </div>
    <div class="pb">
      <div class="task-form-grid">
        <div class="fg">
          <label>${t('category')}</label>
          <input type="text" id="newCat" list="catSuggestions" placeholder="f.eks. Data Collection...">
          <datalist id="catSuggestions">${DEFAULT_CATS.map(c=>`<option value="${c}">`).join('')}</datalist>
        </div>
        <div class="fg">
          <label>${t('startDate')}</label>
          <input type="text" id="newStart" placeholder="01-01-${p.startYear}">
        </div>
        <div class="fg">
          <label>${t('endDate')}</label>
          <input type="text" id="newEnd" placeholder="31-12-${p.startYear}">
        </div>
        <div class="fg"><label>&nbsp;</label>
          <button class="btn btn-primary" onclick="addTask()">
            <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
            ${t('add')}
          </button>
        </div>
      </div>
      <ul class="task-list" id="taskList"></ul>
    </div>
  </div>

  <!-- Gantt -->
  <div class="panel">
    <div class="ph">
      <span class="ph-title">${t('ganttChart')}</span>
      <div class="toolbar">
        <button class="btn btn-secondary btn-sm" onclick="exportImage('png')">${t('exportPNG')}</button>
        <button class="btn btn-secondary btn-sm" onclick="exportImage('jpeg')">${t('exportJPEG')}</button>
        <button class="btn btn-secondary btn-sm" onclick="exportExcel()">${t('exportExcel')}</button>
      </div>
    </div>
    <div class="gantt-canvas-wrap">
      <canvas id="ganttCanvas"></canvas>
    </div>
  </div>`;

  renderTaskList();
  renderGantt();
}

function updateProjectName(v){const p=proj();if(p){p.name=v;renderSidebar()}}
function updateProjectYear(){const p=proj();if(p){p.startYear=parseInt(document.getElementById('startYearInput').value)||2025;renderGantt()}}
function updateProjectDuration(){const p=proj();if(p){p.duration=parseInt(document.getElementById('durationInput').value)||1;renderGantt()}}

// ─── TASKS ─────────────────────────────────────────────────────────────────
let editingId=null;

function addTask(){
  const p=proj();if(!p)return;
  const cat=document.getElementById('newCat').value.trim();
  const startRaw=document.getElementById('newStart').value.trim();
  const endRaw=document.getElementById('newEnd').value.trim();
  if(!cat||!startRaw||!endRaw){showAlert(t('errorFields'),'error');return}
  if(!isValidEU(startRaw)||!isValidEU(endRaw)){showAlert(t('errorDateFmt'),'error');return}
  const start=toISO(startRaw),end=toISO(endRaw);
  if(start>=end){showAlert(t('errorDates'),'error');return}
  p.tasks.push({id:nextTid++,category:cat,start,end,color:BAR_COLORS[p.tasks.length%BAR_COLORS.length]});
  document.getElementById('newCat').value='';
  document.getElementById('newStart').value='';
  document.getElementById('newEnd').value='';
  renderTaskList();renderGantt();
}

function deleteTask(id){
  const p=proj();if(!p)return;
  p.tasks=p.tasks.filter(t=>t.id!==id);
  renderTaskList();renderGantt();
}

function startEdit(id){editingId=id;renderTaskList()}
function cancelEdit(){editingId=null;renderTaskList()}

function saveEdit(id){
  const p=proj();if(!p)return;
  const cat=document.getElementById('ec_'+id).value.trim();
  const startRaw=document.getElementById('es_'+id).value.trim();
  const endRaw=document.getElementById('ee_'+id).value.trim();
  if(!cat||!startRaw||!endRaw){showAlert(t('errorFields'),'error');return}
  if(!isValidEU(startRaw)||!isValidEU(endRaw)){showAlert(t('errorDateFmt'),'error');return}
  const start=toISO(startRaw),end=toISO(endRaw);
  if(start>=end){showAlert(t('errorDates'),'error');return}
  const task=p.tasks.find(t=>t.id===id);
  if(task){task.category=cat;task.start=start;task.end=end}
  editingId=null;renderTaskList();renderGantt();
}

function renderTaskList(){
  const p=proj();
  const ul=document.getElementById('taskList');
  if(!ul)return;
  if(!p||!p.tasks.length){ul.innerHTML=`<div class="empty"><p>${t('noTasks')}</p></div>`;return}
  ul.innerHTML=p.tasks.map(task=>{
    if(editingId===task.id){
      return`<li class="task-row editing">
        <input id="ec_${task.id}" type="text" value="${esc(task.category)}">
        <input id="es_${task.id}" type="text" value="${toEU(task.start)}" placeholder="DD-MM-YYYY">
        <input id="ee_${task.id}" type="text" value="${toEU(task.end)}" placeholder="DD-MM-YYYY">
        <div class="task-acts">
          <button class="btn btn-primary btn-sm" onclick="saveEdit(${task.id})">${t('save')}</button>
          <button class="btn btn-secondary btn-sm" onclick="cancelEdit()">${t('cancel')}</button>
        </div>
      </li>`;
    }
    return`<li class="task-row">
      <div class="task-cat"><div class="dot" style="background:${task.color}"></div>${esc(task.category)}</div>
      <div class="task-dates">${toEU(task.start)}</div>
      <div class="task-dates">${toEU(task.end)}</div>
      <div class="task-acts">
        <button class="btn btn-secondary btn-sm" onclick="startEdit(${task.id})">${t('edit')}</button>
        <button class="btn btn-danger" onclick="deleteTask(${task.id})">${t('delete')}</button>
      </div>
    </li>`;
  }).join('');
}

// ─── GANTT CANVAS ──────────────────────────────────────────────────────────
function renderGantt(){
  const p=proj();
  const canvas=document.getElementById('ganttCanvas');
  if(!canvas||!p)return;

  const tasks=p.tasks;
  const startYear=p.startYear;
  const dur=p.duration; // 1–5 years
  const endYear=startYear+dur-1;
  const totalMonths=dur*12;

  // Dimensions
  const LABEL_W=200;
  const DATE_COL_W=100; // start date col
  const RIGHT_PAD=20;
  const ROW_H=38;
  const HEADER_H=52; // quarter row + month row
  const BAR_H=20;
  const DPR=window.devicePixelRatio||1;

  const allMonths=[];
  for(let y=startYear;y<=endYear;y++){
    for(let m=0;m<12;m++) allMonths.push({year:y,month:m});
  }

  const MONTH_W=Math.max(38, Math.floor((900-LABEL_W-DATE_COL_W-RIGHT_PAD)/totalMonths));
  const CHART_W=MONTH_W*totalMonths;
  const totalW=LABEL_W+DATE_COL_W+CHART_W+RIGHT_PAD;
  const totalH=HEADER_H+Math.max(tasks.length,1)*ROW_H+24;

  canvas.width=totalW*DPR;
  canvas.height=totalH*DPR;
  canvas.style.width=totalW+'px';
  canvas.style.height=totalH+'px';
  const ctx=canvas.getContext('2d');
  ctx.scale(DPR,DPR);

  // Colors
  const C={
    bg:'#ffffff', headerBg:'#f0f4f8', headerBg2:'#f7f9fb',
    border:'#d8d3cc', borderLight:'#ece8e2',
    text:'#1c1917', muted:'#78716c', white:'#fff',
    accent:'#0f4c75', accentLight:'#eef4fa',
    rowAlt:'#faf9f8'
  };

  // BG
  ctx.fillStyle=C.bg;
  ctx.fillRect(0,0,totalW,totalH);

  // ── Draw quarter headers ──
  const quarters=t('quarters');
  const months=t('months');

  // Quarter header row
  ctx.fillStyle=C.headerBg;
  ctx.fillRect(0,0,totalW,26);
  ctx.strokeStyle=C.border;
  ctx.lineWidth=1;
  ctx.beginPath();ctx.moveTo(0,26);ctx.lineTo(totalW,26);ctx.stroke();

  // Quarter labels
  for(let yi=0;yi<dur;yi++){
    for(let qi=0;qi<4;qi++){
      const startMonth=yi*12+qi*3;
      const qX=LABEL_W+DATE_COL_W+startMonth*MONTH_W;
      const qW=3*MONTH_W;
      // vertical line
      ctx.strokeStyle=C.border;
      ctx.lineWidth=1;
      ctx.beginPath();ctx.moveTo(qX,0);ctx.lineTo(qX,HEADER_H);ctx.stroke();
      // label
      ctx.fillStyle=C.accent;
      ctx.font=`600 10px 'Syne',sans-serif`;
      ctx.textAlign='center';
      const label=dur>1?`${startYear+yi} ${quarters[qi]}`:quarters[qi];
      ctx.fillText(label,qX+qW/2,17);
    }
  }

  // Month header row
  ctx.fillStyle=C.headerBg2;
  ctx.fillRect(0,26,totalW,26);
  ctx.strokeStyle=C.border;
  ctx.lineWidth=1;
  ctx.beginPath();ctx.moveTo(0,52);ctx.lineTo(totalW,52);ctx.stroke();

  allMonths.forEach(({year,month},i)=>{
    const mx=LABEL_W+DATE_COL_W+i*MONTH_W;
    ctx.strokeStyle=C.borderLight;
    ctx.lineWidth=.5;
    ctx.beginPath();ctx.moveTo(mx,26);ctx.lineTo(mx,HEADER_H);ctx.stroke();
    ctx.fillStyle=C.muted;
    ctx.font=`400 10px 'DM Sans',sans-serif`;
    ctx.textAlign='center';
    if(MONTH_W>=32) ctx.fillText(months[month],mx+MONTH_W/2,42);
    else if(MONTH_W>=22) ctx.fillText(months[month].charAt(0),mx+MONTH_W/2,42);
  });

  // Column header: Task / Start date
  ctx.fillStyle=C.headerBg;
  ctx.fillRect(0,0,LABEL_W,HEADER_H);
  ctx.fillRect(LABEL_W,0,DATE_COL_W,HEADER_H);
  ctx.fillStyle=C.accent;
  ctx.font=`600 10.5px 'Syne',sans-serif`;
  ctx.textAlign='left';
  ctx.fillText(lang==='da'?'Opgave':'Task',12,17);
  ctx.fillText(lang==='da'?'Periode':'Period',LABEL_W+8,17);

  // Vertical separator LABEL | DATE | CHART
  ctx.strokeStyle=C.border;ctx.lineWidth=1;
  ctx.beginPath();ctx.moveTo(LABEL_W,0);ctx.lineTo(LABEL_W,totalH);ctx.stroke();
  ctx.beginPath();ctx.moveTo(LABEL_W+DATE_COL_W,0);ctx.lineTo(LABEL_W+DATE_COL_W,totalH);ctx.stroke();

  // ── Rows ──
  const periodStart=new Date(startYear,0,1);
  const periodEnd=new Date(endYear,11,31);
  const totalDays=(periodEnd-periodStart)/86400000+1;

  function dayPct(dateStr){
    const d=new Date(dateStr);
    return Math.max(0,Math.min(1,(d-periodStart)/((periodEnd-periodStart)+86400000)));
  }

  if(!tasks.length){
    ctx.fillStyle=C.muted;
    ctx.font=`400 13px 'DM Sans',sans-serif`;
    ctx.textAlign='center';
    ctx.fillText(t('noTasks'),totalW/2,HEADER_H+ROW_H/2+6);
  }

  tasks.forEach((task,i)=>{
    const y=HEADER_H+i*ROW_H;
    // Row bg
    ctx.fillStyle=i%2===0?C.bg:C.rowAlt;
    ctx.fillRect(0,y,totalW,ROW_H);
    // Row border
    ctx.strokeStyle=C.borderLight;ctx.lineWidth=.5;
    ctx.beginPath();ctx.moveTo(0,y+ROW_H);ctx.lineTo(totalW,y+ROW_H);ctx.stroke();

    // Color dot + label
    ctx.fillStyle=task.color;
    ctx.beginPath();ctx.arc(14,y+ROW_H/2,5,0,Math.PI*2);ctx.fill();
    ctx.fillStyle=C.text;
    ctx.font=`500 12.5px 'DM Sans',sans-serif`;
    ctx.textAlign='left';
    const maxLabelW=LABEL_W-30;
    let label=task.category;
    while(ctx.measureText(label).width>maxLabelW&&label.length>3) label=label.slice(0,-1);
    if(label!==task.category) label=label.slice(0,-1)+'…';
    ctx.fillText(label,26,y+ROW_H/2+5);

    // Date cell
    ctx.fillStyle=C.muted;
    ctx.font=`400 11px 'DM Sans',sans-serif`;
    const dateStr=`${toEU(task.start)}`;
    ctx.fillText(dateStr,LABEL_W+6,y+ROW_H/2+5);

    // Bar
    const left=dayPct(task.start);
    const right=dayPct(task.end);
    const bx=LABEL_W+DATE_COL_W+left*CHART_W;
    const bw=Math.max(3,(right-left)*CHART_W);
    const by=y+(ROW_H-BAR_H)/2;

    ctx.fillStyle=task.color;
    ctx.beginPath();
    const r=3;
    ctx.moveTo(bx+r,by);ctx.lineTo(bx+bw-r,by);ctx.quadraticCurveTo(bx+bw,by,bx+bw,by+r);
    ctx.lineTo(bx+bw,by+BAR_H-r);ctx.quadraticCurveTo(bx+bw,by+BAR_H,bx+bw-r,by+BAR_H);
    ctx.lineTo(bx+r,by+BAR_H);ctx.quadraticCurveTo(bx,by+BAR_H,bx,by+BAR_H-r);
    ctx.lineTo(bx,by+r);ctx.quadraticCurveTo(bx,by,bx+r,by);
    ctx.closePath();ctx.fill();

    // Bar end date label (if space)
    if(bw>80){
      ctx.fillStyle='rgba(255,255,255,0.92)';
      ctx.font=`500 10px 'DM Sans',sans-serif`;
      ctx.textAlign='center';
      const endLabel=toEU(task.end);
      ctx.fillText(endLabel,bx+bw/2,by+BAR_H/2+4);
    }
  });

  // Title footer
  ctx.fillStyle=C.muted;
  ctx.font=`400 11px 'DM Sans',sans-serif`;
  ctx.textAlign='left';
  const footerY=HEADER_H+Math.max(tasks.length,1)*ROW_H+16;
  ctx.fillText(p.name+` · ${startYear}${dur>1?'–'+(startYear+dur-1):''}`,12,footerY);

  // Right border
  ctx.strokeStyle=C.border;ctx.lineWidth=1;
  ctx.beginPath();ctx.moveTo(totalW-1,0);ctx.lineTo(totalW-1,totalH);ctx.stroke();
  // Bottom border
  ctx.beginPath();ctx.moveTo(0,totalH-1);ctx.lineTo(totalW,totalH-1);ctx.stroke();
  // Top border
  ctx.beginPath();ctx.moveTo(0,0);ctx.lineTo(totalW,0);ctx.stroke();
}

// ─── EXPORT IMAGE ─────────────────────────────────────────────────────────
function exportImage(fmt){
  const p=proj();if(!p)return;
  const canvas=document.getElementById('ganttCanvas');
  if(!canvas)return;
  const mime=fmt==='jpeg'?'image/jpeg':'image/png';
  const ext=fmt==='jpeg'?'jpg':'png';
  const url=canvas.toDataURL(mime,0.95);
  const a=document.createElement('a');
  a.download=`${(p.name||'gantt').replace(/[^a-zA-Z0-9-_]/g,'_')}.${ext}`;
  a.href=url;
  document.body.appendChild(a);a.click();document.body.removeChild(a);
}

// ─── EXPORT EXCEL ─────────────────────────────────────────────────────────
function exportExcel(){
  const p=proj();if(!p)return;
  const rows=[['Kategori','Startdato','Slutdato'],...p.tasks.map(t=>[t.category,toEU(t.start),toEU(t.end)])];
  const ws=XLSX.utils.aoa_to_sheet(rows);
  ws['!cols']=[{wch:32},{wch:16},{wch:16}];
  const wb=XLSX.utils.book_new();
  XLSX.utils.book_append_sheet(wb,ws,'Gantt');
  XLSX.writeFile(wb,`${(p.name||'gantt').replace(/[^a-zA-Z0-9-_]/g,'_')}.xlsx`);
}

// ─── IMPORT EXCEL ─────────────────────────────────────────────────────────
function importExcel(e){
  const file=e.target.files[0];if(!file)return;
  const p=proj();if(!p)return;
  const reader=new FileReader();
  reader.onload=function(ev){
    try{
      const wb=XLSX.read(ev.target.result,{type:'binary',cellDates:true});
      const ws=wb.Sheets[wb.SheetNames[0]];
      const rows=XLSX.utils.sheet_to_json(ws);
      let cnt=0;
      rows.forEach(row=>{
        const cat=row['Kategori']||row['Category']||row['kategori']||row['category'];
        let start=row['Startdato']||row['Start Date']||row['startdato']||row['start_date'];
        let end=row['Slutdato']||row['End Date']||row['slutdato']||row['end_date'];
        if(!cat||!start||!end)return;
        if(start instanceof Date)start=toISO(start);else start=toISO(String(start));
        if(end instanceof Date)end=toISO(end);else end=toISO(String(end));
        if(!start||!end||start>=end)return;
        p.tasks.push({id:nextTid++,category:String(cat),start,end,color:BAR_COLORS[p.tasks.length%BAR_COLORS.length]});
        cnt++;
      });
      showAlert(`${cnt} ${t('imported')}`,'success');
      renderTaskList();renderGantt();
    }catch(err){showAlert('Import fejl: '+err.message,'error')}
  };
  reader.readAsBinaryString(file);
  e.target.value='';
}

// ─── UTILITIES ────────────────────────────────────────────────────────────
function showAlert(msg,type){
  const box=document.getElementById('alertBox');if(!box)return;
  box.className=`alert alert-${type}`;box.textContent=msg;box.style.display='block';
  setTimeout(()=>{if(box)box.style.display='none'},4000);
}
function esc(s){return String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;')}

function toggleLang(){
  lang=lang==='da'?'en':'da';
  document.getElementById('langBtn').textContent=lang==='da'?'EN':'DA';
  updateStaticLabels();
  renderSidebar();
  renderMain();
}
function updateStaticLabels(){
  document.querySelectorAll('[data-k]').forEach(el=>{ const k=el.dataset.k; if(L[lang][k]) el.textContent=t(k); });
}

// ─── INIT ────────────────────────────────────────────────────────────────
newProject();
</script>
</body>
</html>
