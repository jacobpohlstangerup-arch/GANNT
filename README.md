<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700&family=DM+Sans:wght@300;400;500&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#f0ece4;--sur:#fff;--brd:#ddd8ce;--txt:#1a1714;--mut:#7a736c;
  --acc:#0d3d5c;--acc2:#155e86;--abg:#e8f2f9;
  --red:#a91c1c;--redbg:#fdf2f2;
  --r:8px;--sh:0 1px 4px rgba(0,0,0,.07),0 6px 20px rgba(0,0,0,.05);
}
body{font-family:'DM Sans',sans-serif;background:var(--bg);color:var(--txt);min-height:100vh;font-size:13.5px;line-height:1.5}
header{background:var(--acc);color:#fff;padding:0 28px;height:54px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:200;box-shadow:0 2px 8px rgba(0,0,0,.18)}
.logo{font-family:'Syne',sans-serif;font-size:15px;font-weight:700;letter-spacing:.04em}
.logo span{opacity:.45;font-weight:400;font-size:13px;margin-left:6px}
.langbtn{background:rgba(255,255,255,.13);border:1px solid rgba(255,255,255,.28);color:#fff;padding:5px 14px;border-radius:4px;font-family:'Syne',sans-serif;font-size:11px;font-weight:700;letter-spacing:.1em;cursor:pointer;transition:background .15s}
.langbtn:hover{background:rgba(255,255,255,.24)}
.wrap{max-width:1140px;margin:0 auto;padding:24px 20px}
.panel{background:var(--sur);border:1px solid var(--brd);border-radius:var(--r);margin-bottom:18px;box-shadow:var(--sh);overflow:hidden}
.ph{padding:12px 18px;border-bottom:1px solid var(--brd);background:#f9f8f5;display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap}
.ph-t{font-family:'Syne',sans-serif;font-size:10.5px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--mut)}
.pb{padding:18px}
.g3{display:grid;grid-template-columns:2fr 1fr 1fr;gap:14px}
.fg{display:flex;flex-direction:column;gap:4px}
.fg label{font-family:'Syne',sans-serif;font-size:10px;font-weight:700;letter-spacing:.09em;text-transform:uppercase;color:var(--mut)}
input,select{padding:8px 10px;border:1px solid var(--brd);border-radius:5px;font-family:'DM Sans',sans-serif;font-size:13.5px;background:#fff;color:var(--txt);transition:border-color .15s;width:100%}
input:focus,select:focus{outline:none;border-color:var(--acc);box-shadow:0 0 0 3px rgba(13,61,92,.09)}
.btn{display:inline-flex;align-items:center;gap:5px;padding:8px 14px;border-radius:5px;border:1px solid transparent;font-family:'DM Sans',sans-serif;font-size:13px;font-weight:500;cursor:pointer;transition:all .15s;white-space:nowrap;line-height:1}
.bp{background:var(--acc);color:#fff;border-color:var(--acc)}.bp:hover{background:var(--acc2)}
.bo{background:#fff;color:var(--txt);border-color:var(--brd)}.bo:hover{background:var(--bg)}
.bd{background:#fff;color:var(--red);border-color:#e0aaaa;padding:5px 9px;font-size:12px}.bd:hover{background:var(--redbg)}
.bsm{padding:5px 10px;font-size:12px}
.tbar{display:flex;gap:7px;flex-wrap:wrap;align-items:center}
.alert{padding:9px 13px;border-radius:5px;font-size:13px;margin-bottom:14px;border:1px solid;display:none}
.as{background:var(--abg);border-color:#9ec8e8;color:var(--acc)}
.ae{background:var(--redbg);border-color:#e8aaaa;color:var(--red)}

/* Project cards */
.proj-area{display:flex;flex-direction:column;gap:12px;margin-bottom:0}
.proj-card{background:var(--sur);border:1px solid var(--brd);border-radius:var(--r);box-shadow:var(--sh);overflow:hidden}
.proj-head{padding:10px 16px;display:flex;align-items:center;gap:10px;background:#f9f8f5;border-bottom:1px solid var(--brd)}
.proj-bar{width:5px;height:30px;border-radius:3px;flex-shrink:0}
.proj-name-inp{flex:1;border:1px solid transparent;background:transparent;padding:4px 6px;font-family:'Syne',sans-serif;font-size:13px;font-weight:600;border-radius:4px;transition:border-color .15s,background .15s}
.proj-name-inp:hover{background:#f0ede8;border-color:var(--brd)}
.proj-name-inp:focus{background:#fff;border-color:var(--acc);outline:none}
.proj-badge{font-family:'Syne',sans-serif;font-size:10px;font-weight:600;letter-spacing:.06em;padding:2px 8px;border-radius:3px;color:#fff}
.proj-body{padding:16px}
.add-g{display:grid;grid-template-columns:2fr 1fr 1fr auto;gap:9px;align-items:end;margin-bottom:14px}
.empty{text-align:center;padding:24px;color:var(--mut);font-size:13px}

/* Drag-and-drop task list */
.dnd-list{list-style:none;display:flex;flex-direction:column;gap:0}
.dnd-item{display:grid;grid-template-columns:28px 2fr 1fr 1fr auto;gap:8px;align-items:center;padding:8px 0;border-bottom:1px solid #f0ece5;cursor:default;transition:background .12s,box-shadow .12s;border-radius:4px;user-select:none}
.dnd-item:last-child{border-bottom:none}
.dnd-item.dragging{opacity:.4;background:var(--abg)}
.dnd-item.drag-over{box-shadow:0 -2px 0 0 var(--acc)}
.dnd-item.ed{background:var(--abg);margin:0 -16px;padding:8px 16px;grid-template-columns:28px 2fr 1fr 1fr auto}
.drag-handle{display:flex;flex-direction:column;gap:3px;align-items:center;justify-content:center;cursor:grab;padding:4px 2px;opacity:.35;transition:opacity .15s}
.drag-handle:hover{opacity:.7}
.drag-handle span{display:block;width:14px;height:1.5px;background:var(--mut);border-radius:2px}
.drag-handle:active{cursor:grabbing}
.tcat{font-weight:500;display:flex;align-items:center;gap:8px;font-size:13px}
.dot{width:8px;height:8px;border-radius:50%;flex-shrink:0}
.tdates{font-size:12px;color:var(--mut);font-variant-numeric:tabular-nums}
.tacts{display:flex;gap:5px;justify-content:flex-end}

.gantt-scroll{overflow-x:auto;padding:20px}
canvas{display:block;border-radius:4px}
</style>
</head>
<body>
<header>
  <div class="logo">GANTT <span data-k="subtitle">Fondsansøgning</span></div>
  <button class="langbtn" id="langBtn" onclick="toggleLang()">EN</button>
</header>

<div class="wrap">
  <div id="alertBox" class="alert"></div>

  <!-- Global settings -->
  <div class="panel">
    <div class="ph"><span class="ph-t" data-k="lSettings">Indstillinger</span></div>
    <div class="pb">
      <div class="g3">
        <div class="fg"><label data-k="lChartTitle">Charttitel</label>
          <input id="chartTitle" value="Forskningsprogram" oninput="scheduleRender()">
        </div>
        <div class="fg"><label data-k="lStartYear">Startår</label>
          <input id="startYear" type="number" value="2026" min="2000" max="2050" onchange="scheduleRender()">
        </div>
        <div class="fg"><label data-k="lDuration">Varighed (år)</label>
          <select id="duration" onchange="scheduleRender()">
            <option>1</option><option>2</option><option>3</option><option>4</option><option>5</option>
          </select>
        </div>
      </div>
    </div>
  </div>

  <!-- Projects -->
  <div class="panel">
    <div class="ph">
      <span class="ph-t" data-k="lProjects">Projekter</span>
      <button class="btn bp bsm" onclick="addProject()">
        <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
        <span data-k="btnAddProject">Tilføj projekt</span>
      </button>
    </div>
    <div class="pb" style="padding-top:14px">
      <div class="proj-area" id="projArea"></div>
    </div>
  </div>

  <!-- Gantt -->
  <div class="panel">
    <div class="ph">
      <span class="ph-t" data-k="lGantt">Gantt Chart</span>
      <div class="tbar">
        <button class="btn bo bsm" onclick="exportImg('png')"><span data-k="btnPNG">Eksportér PNG</span></button>
        <button class="btn bo bsm" onclick="exportImg('jpeg')"><span data-k="btnJPEG">Eksportér JPEG</span></button>
        <button class="btn bo bsm" onclick="exportPDF()"><span data-k="btnPDF">Eksportér PDF</span></button>
        <button class="btn bo bsm" onclick="exportExcelFile()"><span data-k="btnExcel">Eksportér Excel</span></button>
      </div>
    </div>
    <div class="gantt-scroll"><canvas id="ganttCanvas"></canvas></div>
  </div>
</div>

<script>
// ── i18n ──────────────────────────────────────────────────────────────────
// Category translation map (key = canonical English name)
const CAT_MAP = {
  'Planning & Preparation':  {da:'Planlægning & Forberedelse', en:'Planning & Preparation'},
  'Literature Review':       {da:'Litteraturgennemgang',        en:'Literature Review'},
  'Methodology Design':      {da:'Metodedesign',                en:'Methodology Design'},
  'Ethical Approval':        {da:'Etisk godkendelse',           en:'Ethical Approval'},
  'Data Collection':         {da:'Dataindsamling',              en:'Data Collection'},
  'Data Analysis':           {da:'Dataanalyse',                 en:'Data Analysis'},
  'Writing & Revision':      {da:'Skrivning & Redigering',      en:'Writing & Revision'},
  'Final Submission':        {da:'Endelig indlevering',         en:'Final Submission'},
};
// Build reverse lookup (any lang → canonical key)
const CAT_REVERSE = {};
Object.entries(CAT_MAP).forEach(([key,v])=>{ CAT_REVERSE[key]=key; CAT_REVERSE[v.da]=key; CAT_REVERSE[v.en]=key; });

function translateCat(name, toLang) {
  const key = CAT_REVERSE[name];
  return key ? CAT_MAP[key][toLang] : name; // unknown = keep as-is
}

const L = {
  da:{
    subtitle:'Fondsansøgning', lSettings:'Indstillinger',
    lChartTitle:'Charttitel', lStartYear:'Startår', lDuration:'Varighed (år)',
    lProjects:'Projekter', btnAddProject:'Tilføj projekt', lGantt:'Gantt Chart',
    btnPNG:'Eksportér PNG', btnJPEG:'Eksportér JPEG', btnPDF:'Eksportér PDF', btnExcel:'Eksportér Excel',
    edit:'Rediger', save:'Gem', cancel:'Annuller', delete:'Slet',
    lCat:'Kategori', lStart:'Startdato (DD-MM-ÅÅÅÅ)', lEnd:'Slutdato (DD-MM-ÅÅÅÅ)',
    btnAdd:'Tilføj', noTasks:'Ingen opgaver – tilføj en ovenfor.',
    noProjects:'Ingen projekter. Tilføj et projekt ovenfor.',
    errF:'Udfyld alle felter.', errFmt:'Ugyldig dato – brug DD-MM-ÅÅÅÅ.',
    errOrd:'Startdato skal være før slutdato.',
    tasks:'opgaver', projects:'projekter', taskLabel:'Opgave',
    months:['Januar','Februar','Marts','April','Maj','Juni','Juli','August','September','Oktober','November','December'],
    msS:['Jan','Feb','Mar','Apr','Maj','Jun','Jul','Aug','Sep','Okt','Nov','Dec'],
    qF:['1. kvartal','2. kvartal','3. kvartal','4. kvartal'],
    qS:['K1','K2','K3','K4'], projName:'Projekt',
  },
  en:{
    subtitle:'Grant Application', lSettings:'Settings',
    lChartTitle:'Chart Title', lStartYear:'Start Year', lDuration:'Duration (years)',
    lProjects:'Projects', btnAddProject:'Add Project', lGantt:'Gantt Chart',
    btnPNG:'Export PNG', btnJPEG:'Export JPEG', btnPDF:'Export PDF', btnExcel:'Export Excel',
    edit:'Edit', save:'Save', cancel:'Cancel', delete:'Delete',
    lCat:'Category', lStart:'Start Date (DD-MM-YYYY)', lEnd:'End Date (DD-MM-YYYY)',
    btnAdd:'Add', noTasks:'No tasks yet – add one above.',
    noProjects:'No projects. Add one above.',
    errF:'Please fill in all fields.', errFmt:'Invalid date – use DD-MM-YYYY.',
    errOrd:'Start date must be before end date.',
    tasks:'tasks', projects:'projects', taskLabel:'Task',
    months:['January','February','March','April','May','June','July','August','September','October','November','December'],
    msS:['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'],
    qF:['1st Quarter','2nd Quarter','3rd Quarter','4th Quarter'],
    qS:['Q1','Q2','Q3','Q4'], projName:'Project',
  }
};
let lang = 'da';
const t = k => L[lang][k] ?? k;

function toggleLang() {
  const prev = lang;
  lang = lang === 'da' ? 'en' : 'da';
  document.getElementById('langBtn').textContent = lang === 'da' ? 'EN' : 'DA';
  // Translate all standard category names in tasks
  projects.forEach(p => p.tasks.forEach(task => {
    task.category = translateCat(task.category, lang);
  }));
  // Update static labels
  document.querySelectorAll('[data-k]').forEach(el => { const v = t(el.dataset.k); if(v) el.textContent = v; });
  renderAllProjects();
  scheduleRender();
}

// ── Palettes ──────────────────────────────────────────────────────────────
const PALETTES = [
  {h:'#0d3d5c', bars:['#0d3d5c','#155e86','#1a7aad','#2292cc','#4aabda','#6bbfe3','#94d2eb','#b8e2f2']},
  {h:'#1a4d2e', bars:['#1a4d2e','#236b3e','#2e8a52','#3aaa67','#52c27e','#74d49a','#98e3b6','#bdeece']},
  {h:'#5c1a1a', bars:['#5c1a1a','#842424','#a93030','#c94040','#d96060','#e48888','#edaaaa','#f5cccc']},
  {h:'#3d2e0d', bars:['#3d2e0d','#6b5014','#936e1c','#b88822','#d4a62e','#e8c05a','#f0d388','#f7e6b5']},
  {h:'#2e0d5c', bars:['#2e0d5c','#451a86','#5e2aad','#7a3fd4','#9660e0','#ae84e8','#c8a8f0','#e0ccf8']},
];
const pal = i => PALETTES[i % PALETTES.length];

// ── State ─────────────────────────────────────────────────────────────────
let projects = [], nextPid = 1, nextTid = 1, editKey = null;
let renderTimer = null;

const DEF_CATS = [
  {en:'Planning & Preparation',   sm:1,sd:1, em:2, ed:28},
  {en:'Literature Review',        sm:1,sd:15,em:5, ed:31},
  {en:'Methodology Design',       sm:3,sd:1, em:6, ed:30},
  {en:'Ethical Approval',         sm:4,sd:1, em:6, ed:30},
  {en:'Data Collection',          sm:5,sd:1, em:9, ed:30},
  {en:'Data Analysis',            sm:8,sd:1, em:11,ed:30},
  {en:'Writing & Revision',       sm:9,sd:1, em:12,ed:15},
  {en:'Final Submission',         sm:11,sd:15,em:12,ed:31},
];

// ── Date helpers ──────────────────────────────────────────────────────────
function iso(y,m,d){return`${y}-${String(m).padStart(2,'0')}-${String(d).padStart(2,'0')}`}
function parseEU(s){
  const m=String(s).trim().match(/^(\d{1,2})[.\-\/](\d{1,2})[.\-\/](\d{4})$/);
  if(!m)return null;
  const d=new Date(`${m[3]}-${m[2].padStart(2,'0')}-${m[1].padStart(2,'0')}T00:00:00`);
  return isNaN(d)?null:d;
}
function toISO(s){
  if(s instanceof Date)return iso(s.getFullYear(),s.getMonth()+1,s.getDate());
  const d=parseEU(String(s)); if(d)return iso(d.getFullYear(),d.getMonth()+1,d.getDate());
  if(/^\d{4}-\d{2}-\d{2}$/.test(String(s).trim()))return String(s).trim();
  return'';
}
function toEU(i){const m=String(i).match(/^(\d{4})-(\d{2})-(\d{2})$/);return m?`${m[3]}-${m[2]}-${m[1]}`:i;}

function makeDefTasks(y){
  return DEF_CATS.map(d=>({
    id:nextTid++, category:translateCat(d.en,lang),
    start:iso(y,d.sm,d.sd), end:iso(y,d.em,d.ed)
  }));
}

// ── Projects CRUD ─────────────────────────────────────────────────────────
function addProject(){
  const y=parseInt(document.getElementById('startYear').value)||2026;
  const idx=projects.length;
  projects.push({id:nextPid++, name:`${t('projName')} ${idx+1}`, tasks:makeDefTasks(y), pal:idx});
  renderAllProjects(); scheduleRender();
}
function deleteProjPrompt(pid){
  if(!confirm(lang==='da'?'Slet dette projekt?':'Delete this project?'))return;
  projects=projects.filter(p=>p.id!==pid);
  renderAllProjects(); scheduleRender();
}
function updateProjName(pid,v){const p=projects.find(x=>x.id===pid);if(p){p.name=v;scheduleRender();}}

// ── Tasks CRUD ────────────────────────────────────────────────────────────
function addTask(pid){
  const p=projects.find(x=>x.id===pid); if(!p)return;
  const cat=document.getElementById(`nc${pid}`).value.trim();
  const sr=document.getElementById(`ns${pid}`).value.trim();
  const er=document.getElementById(`ne${pid}`).value.trim();
  if(!cat||!sr||!er){showAlert(t('errF'),'e');return}
  if(!parseEU(sr)||!parseEU(er)){showAlert(t('errFmt'),'e');return}
  const s=toISO(sr),e=toISO(er);
  if(s>=e){showAlert(t('errOrd'),'e');return}
  p.tasks.push({id:nextTid++,category:cat,start:s,end:e});
  document.getElementById(`nc${pid}`).value='';
  document.getElementById(`ns${pid}`).value='';
  document.getElementById(`ne${pid}`).value='';
  renderAllProjects(); scheduleRender();
}
function deleteTask(pid,tid){
  const p=projects.find(x=>x.id===pid); if(!p)return;
  p.tasks=p.tasks.filter(x=>x.id!==tid);
  renderAllProjects(); scheduleRender();
}
function startEdit(pid,tid){editKey=`${pid}-${tid}`;renderAllProjects();}
function cancelEdit(){editKey=null;renderAllProjects();}
function saveEdit(pid,tid){
  const p=projects.find(x=>x.id===pid); if(!p)return;
  const cat=document.getElementById(`ec${pid}_${tid}`).value.trim();
  const sr=document.getElementById(`es${pid}_${tid}`).value.trim();
  const er=document.getElementById(`ee${pid}_${tid}`).value.trim();
  if(!cat||!sr||!er){showAlert(t('errF'),'e');return}
  if(!parseEU(sr)||!parseEU(er)){showAlert(t('errFmt'),'e');return}
  const s=toISO(sr),e=toISO(er);
  if(s>=e){showAlert(t('errOrd'),'e');return}
  const task=p.tasks.find(x=>x.id===tid);
  if(task){task.category=cat;task.start=s;task.end=e;}
  editKey=null; renderAllProjects(); scheduleRender();
}

// ── Drag-and-drop ─────────────────────────────────────────────────────────
let dragPid=null, dragTid=null, dragOverTid=null;

function onDragStart(e, pid, tid){
  dragPid=pid; dragTid=tid;
  e.dataTransfer.effectAllowed='move';
  setTimeout(()=>{ const el=document.querySelector(`.dnd-item[data-tid="${tid}"]`); if(el)el.classList.add('dragging'); },0);
}
function onDragOver(e, pid, tid){
  e.preventDefault(); e.dataTransfer.dropEffect='move';
  if(dragOverTid===tid)return;
  document.querySelectorAll('.dnd-item.drag-over').forEach(el=>el.classList.remove('drag-over'));
  dragOverTid=tid;
  const el=document.querySelector(`.dnd-item[data-tid="${tid}"]`); if(el)el.classList.add('drag-over');
}
function onDrop(e, pid, tid){
  e.preventDefault();
  if(dragPid!==pid||dragTid===tid){cleanup();return;}
  const p=projects.find(x=>x.id===pid); if(!p){cleanup();return;}
  const fromIdx=p.tasks.findIndex(x=>x.id===dragTid);
  const toIdx=p.tasks.findIndex(x=>x.id===tid);
  if(fromIdx<0||toIdx<0){cleanup();return;}
  const [moved]=p.tasks.splice(fromIdx,1);
  p.tasks.splice(toIdx,0,moved);
  cleanup(); renderAllProjects(); scheduleRender();
}
function onDragEnd(){cleanup();}
function cleanup(){
  document.querySelectorAll('.dnd-item.dragging,.dnd-item.drag-over').forEach(el=>{el.classList.remove('dragging','drag-over');});
  dragPid=null; dragTid=null; dragOverTid=null;
}

// ── Render all project cards ──────────────────────────────────────────────
function renderAllProjects(){
  const area=document.getElementById('projArea');
  if(!projects.length){area.innerHTML=`<div class="empty">${t('noProjects')}</div>`;return;}
  area.innerHTML=projects.map((p,pi)=>{
    const pl=pal(p.pal??pi);
    const taskRows=p.tasks.map((task,ti)=>{
      const key=`${p.id}-${task.id}`;
      const bc=pl.bars[ti%pl.bars.length];
      if(editKey===key) return `
        <li class="dnd-item ed" data-tid="${task.id}">
          <span></span>
          <input id="ec${p.id}_${task.id}" value="${esc(task.category)}">
          <input id="es${p.id}_${task.id}" value="${toEU(task.start)}" placeholder="DD-MM-YYYY">
          <input id="ee${p.id}_${task.id}" value="${toEU(task.end)}" placeholder="DD-MM-YYYY">
          <div class="tacts">
            <button class="btn bp bsm" onclick="saveEdit(${p.id},${task.id})">${t('save')}</button>
            <button class="btn bo bsm" onclick="cancelEdit()">${t('cancel')}</button>
          </div>
        </li>`;
      return `
        <li class="dnd-item" data-tid="${task.id}" draggable="true"
          ondragstart="onDragStart(event,${p.id},${task.id})"
          ondragover="onDragOver(event,${p.id},${task.id})"
          ondrop="onDrop(event,${p.id},${task.id})"
          ondragend="onDragEnd()">
          <div class="drag-handle" title="${lang==='da'?'Træk for at flytte':'Drag to reorder'}">
            <span></span><span></span><span></span>
          </div>
          <div class="tcat"><span class="dot" style="background:${bc}"></span>${esc(task.category)}</div>
          <div class="tdates">${toEU(task.start)}</div>
          <div class="tdates">${toEU(task.end)}</div>
          <div class="tacts">
            <button class="btn bo bsm" onclick="startEdit(${p.id},${task.id})">${t('edit')}</button>
            <button class="btn bd" onclick="deleteTask(${p.id},${task.id})">${t('delete')}</button>
          </div>
        </li>`;
    }).join('');

    return `
    <div class="proj-card">
      <div class="proj-head">
        <div class="proj-bar" style="background:${pl.h}"></div>
        <input class="proj-name-inp" value="${esc(p.name)}" oninput="updateProjName(${p.id},this.value)">
        <span class="proj-badge" style="background:${pl.h}">${p.tasks.length} ${t('tasks')}</span>
        <button class="btn bd bsm" onclick="deleteProjPrompt(${p.id})">✕</button>
      </div>
      <div class="proj-body">
        <div class="add-g">
          <div class="fg"><label>${t('lCat')}</label>
            <input id="nc${p.id}" type="text" list="catHints" placeholder="${Object.values(CAT_MAP)[0][lang]}...">
          </div>
          <div class="fg"><label>${t('lStart')}</label><input id="ns${p.id}" type="text" placeholder="DD-MM-YYYY"></div>
          <div class="fg"><label>${t('lEnd')}</label><input id="ne${p.id}" type="text" placeholder="DD-MM-YYYY"></div>
          <div class="fg"><label>&nbsp;</label>
            <button class="btn bp" onclick="addTask(${p.id})">
              <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
              ${t('btnAdd')}
            </button>
          </div>
        </div>
        <ul class="dnd-list">${taskRows||`<div class="empty">${t('noTasks')}</div>`}</ul>
      </div>
    </div>`;
  }).join('');
}

// ── Gantt Canvas ──────────────────────────────────────────────────────────
function scheduleRender(){clearTimeout(renderTimer);renderTimer=setTimeout(()=>renderGantt(),80);}

function renderGantt(sc=null){
  const canvas=document.getElementById('ganttCanvas');
  if(!canvas)return;
  const scale=sc||(window.devicePixelRatio||1);
  drawGantt(canvas,{
    title:document.getElementById('chartTitle').value.trim()||'Gantt Chart',
    startYear:parseInt(document.getElementById('startYear').value)||2026,
    dur:parseInt(document.getElementById('duration').value)||1,
    projects, lang, scale
  });
}

function drawGantt(canvas,{title,startYear,dur,projects,lang,scale}){
  const endYear=startYear+dur-1;
  const LW=210,PR=20,TH=44,HY=26,HQ=22,HM=18,HDR=HY+HQ+HM;
  const TR=34,PH=28,PG=10,FH=26;
  const totalMon=dur*12;
  const availW=Math.max(700,Math.min(1060,window.innerWidth-80));
  const MW=Math.max(42,Math.floor((availW-LW-PR)/totalMon));
  const CW=MW*totalMon;
  const totalW=LW+CW+PR;

  let cH=0;
  projects.forEach((p,i)=>{if(i>0)cH+=PG; cH+=PH+p.tasks.length*TR;});
  if(!projects.length)cH=TR*2;
  const totalH=TH+HDR+cH+FH+4;

  canvas.width=totalW*scale; canvas.height=totalH*scale;
  canvas.style.width=totalW+'px'; canvas.style.height=totalH+'px';
  const ctx=canvas.getContext('2d');
  ctx.scale(scale,scale);

  const C={bg:'#fff',sur:'#f8f7f4',rowA:'#f3f1ed',brd:'#c8c2b8',brdL:'#e2ddd5',txt:'#1a1714',mut:'#7a736c',wh:'#fff'};
  const msS=L[lang].msS, qS=L[lang].qS, qF=L[lang].qF;

  ctx.fillStyle=C.bg; ctx.fillRect(0,0,totalW,totalH);

  // Title
  ctx.fillStyle='#0d3d5c'; ctx.fillRect(0,0,totalW,TH);
  ctx.fillStyle=C.wh; ctx.textBaseline='middle'; ctx.textAlign='left';
  ctx.font=`700 14px 'Syne',sans-serif`; ctx.fillText(title,16,TH/2);
  const period=startYear===endYear?`${startYear}`:`${startYear} – ${endYear}`;
  ctx.fillStyle='rgba(255,255,255,.5)'; ctx.textAlign='right';
  ctx.font=`400 11.5px 'DM Sans',sans-serif`; ctx.fillText(period,totalW-PR,TH/2);

  // Year header
  ctx.fillStyle='#0d3d5c'; ctx.fillRect(0,TH,totalW,HY);
  ctx.fillStyle='rgba(255,255,255,.65)'; ctx.textAlign='left'; ctx.textBaseline='middle';
  ctx.font=`600 9.5px 'Syne',sans-serif`;
  ctx.fillText(lang==='da'?'OPGAVE':'TASK',14,TH+HY/2);
  for(let yi=0;yi<dur;yi++){
    const xL=LW+yi*12*MW, xR=xL+12*MW;
    ctx.fillStyle=C.wh; ctx.textAlign='center'; ctx.font=`600 12px 'Syne',sans-serif`;
    ctx.fillText(String(startYear+yi),(xL+xR)/2,TH+HY/2);
    if(yi>0){ctx.strokeStyle='rgba(255,255,255,.2)';ctx.lineWidth=1;ctx.beginPath();ctx.moveTo(xL,TH);ctx.lineTo(xL,TH+HY);ctx.stroke();}
  }

  // Quarter header
  const qTop=TH+HY;
  ctx.fillStyle='#155e86'; ctx.fillRect(0,qTop,totalW,HQ);
  ctx.fillStyle=C.mut; ctx.fillRect(0,qTop,LW,HQ);
  for(let yi=0;yi<dur;yi++){for(let qi=0;qi<4;qi++){
    const lx=LW+(yi*12+qi*3)*MW, midx=lx+1.5*MW;
    ctx.strokeStyle='rgba(255,255,255,.15)';ctx.lineWidth=1;ctx.beginPath();ctx.moveTo(lx,qTop);ctx.lineTo(lx,qTop+HQ);ctx.stroke();
    ctx.fillStyle=C.wh; ctx.textAlign='center'; ctx.textBaseline='middle'; ctx.font=`600 10px 'Syne',sans-serif`;
    ctx.fillText(3*MW>80?qF[qi]:qS[qi],midx,qTop+HQ/2);
  }}

  // Month header
  const mTop=qTop+HQ;
  ctx.fillStyle='#e8f2f9'; ctx.fillRect(0,mTop,totalW,HM);
  ctx.fillStyle=C.sur; ctx.fillRect(0,mTop,LW,HM);
  for(let yi=0;yi<dur;yi++){for(let mi=0;mi<12;mi++){
    const mx=LW+(yi*12+mi)*MW;
    ctx.strokeStyle=C.brdL;ctx.lineWidth=0.5;ctx.beginPath();ctx.moveTo(mx,mTop);ctx.lineTo(mx,mTop+HM);ctx.stroke();
    if(MW>=24){ctx.fillStyle=C.mut;ctx.textAlign='center';ctx.textBaseline='middle';ctx.font=`400 9.5px 'DM Sans',sans-serif`;
      ctx.fillText(MW>=36?msS[mi]:msS[mi][0],mx+MW/2,mTop+HM/2);}
  }}

  // Divider
  ctx.strokeStyle=C.brd;ctx.lineWidth=1.5;ctx.beginPath();ctx.moveTo(0,TH+HDR);ctx.lineTo(totalW,TH+HDR);ctx.stroke();

  // Period math
  const pS=new Date(startYear,0,1).getTime(), pE=new Date(endYear,11,31,23,59,59).getTime(), pL=pE-pS;
  const xOf=iso=>{const d=new Date(iso+'T00:00:00').getTime();return LW+Math.max(0,Math.min(1,(d-pS)/pL))*CW;};

  let curY=TH+HDR;

  if(!projects.length){
    ctx.fillStyle=C.mut; ctx.textAlign='center'; ctx.textBaseline='middle'; ctx.font=`400 13px 'DM Sans',sans-serif`;
    ctx.fillText(lang==='da'?'Ingen projekter.':'No projects.',totalW/2,curY+TR);
  }

  projects.forEach((proj,pi)=>{
    if(pi>0)curY+=PG;
    const pl=pal(proj.pal??pi);
    const projH=PH+proj.tasks.length*TR;

    // Project header
    ctx.fillStyle=pl.h; ctx.fillRect(0,curY,totalW,PH);
    ctx.fillStyle=C.wh; ctx.textAlign='left'; ctx.textBaseline='middle'; ctx.font=`600 12px 'Syne',sans-serif`;
    ctx.fillText(proj.name||`${t('projName')} ${pi+1}`,14,curY+PH/2);
    ctx.fillStyle='rgba(255,255,255,.25)'; ctx.textAlign='right'; ctx.font=`400 10px 'DM Sans',sans-serif`;
    ctx.fillText(`${proj.tasks.length} ${t('tasks')}`,totalW-PR,curY+PH/2);

    // Grid lines
    for(let c=0;c<totalMon;c++){
      const gx=LW+c*MW, isQ=c%3===0;
      ctx.strokeStyle=isQ?C.brdL:'rgba(0,0,0,.03)'; ctx.lineWidth=isQ?.8:.5;
      ctx.beginPath();ctx.moveTo(gx,curY+PH);ctx.lineTo(gx,curY+projH);ctx.stroke();
    }

    // Task rows
    proj.tasks.forEach((task,ti)=>{
      const ry=curY+PH+ti*TR, bc=pl.bars[ti%pl.bars.length];
      ctx.fillStyle=ti%2===0?C.bg:C.rowA; ctx.fillRect(0,ry,totalW,TR);
      ctx.strokeStyle=C.brdL;ctx.lineWidth=0.5;ctx.beginPath();ctx.moveTo(0,ry+TR);ctx.lineTo(totalW,ry+TR);ctx.stroke();

      ctx.fillStyle=bc; ctx.beginPath();ctx.arc(13,ry+TR/2,4.5,0,Math.PI*2);ctx.fill();
      ctx.fillStyle=C.txt; ctx.textAlign='left'; ctx.textBaseline='middle'; ctx.font=`400 12px 'DM Sans',sans-serif`;
      let lbl=task.category;
      while(ctx.measureText(lbl).width>LW-30&&lbl.length>3)lbl=lbl.slice(0,-1);
      if(lbl!==task.category)lbl=lbl.slice(0,-1)+'…';
      ctx.fillText(lbl,25,ry+TR/2);

      const bx=xOf(task.start), bxE=xOf(task.end), bw=Math.max(3,bxE-bx);
      const bh=18, by=ry+(TR-bh)/2, br=3.5;
      ctx.shadowColor='rgba(0,0,0,.13)';ctx.shadowBlur=3;ctx.shadowOffsetY=1.5;
      ctx.fillStyle=bc; rr(ctx,bx,by,bw,bh,br); ctx.fill();
      ctx.shadowColor='transparent';ctx.shadowBlur=0;ctx.shadowOffsetY=0;
      const g=ctx.createLinearGradient(bx,by,bx,by+bh);
      g.addColorStop(0,'rgba(255,255,255,.2)');g.addColorStop(1,'rgba(255,255,255,0)');
      ctx.fillStyle=g; rr(ctx,bx,by,bw,bh,br); ctx.fill();
      if(bw>110){
        const dl=`${toEU(task.start)} → ${toEU(task.end)}`;
        ctx.font=`400 9px 'DM Sans',sans-serif`;
        if(ctx.measureText(dl).width<bw-10){ctx.fillStyle='rgba(255,255,255,.9)';ctx.textAlign='center';ctx.textBaseline='middle';ctx.fillText(dl,bx+bw/2,by+bh/2);}
      }
    });

    // Project bottom border
    ctx.globalAlpha=.3; ctx.strokeStyle=pl.h; ctx.lineWidth=1.5;
    ctx.beginPath();ctx.moveTo(0,curY+projH);ctx.lineTo(totalW,curY+projH);ctx.stroke();
    ctx.globalAlpha=1;
    curY+=projH;
  });

  // Column separator
  ctx.strokeStyle=C.brd;ctx.lineWidth=1.5;ctx.beginPath();ctx.moveTo(LW,TH);ctx.lineTo(LW,curY);ctx.stroke();

  // Footer
  const fy=curY+4;
  ctx.fillStyle=C.sur; ctx.fillRect(0,fy,totalW,FH);
  ctx.strokeStyle=C.brdL;ctx.lineWidth=1;ctx.beginPath();ctx.moveTo(0,fy);ctx.lineTo(totalW,fy);ctx.stroke();
  ctx.fillStyle=C.mut; ctx.font=`400 9.5px 'DM Sans',sans-serif`; ctx.textAlign='left'; ctx.textBaseline='middle';
  ctx.fillText(`${title} · ${period} · ${projects.length} ${t('projects')} · ${projects.reduce((s,p)=>s+p.tasks.length,0)} ${t('tasks')}`,14,fy+FH/2);
  ctx.textAlign='right'; ctx.fillText(new Date().toLocaleDateString(lang==='da'?'da-DK':'en-GB'),totalW-PR,fy+FH/2);
  ctx.strokeStyle=C.brd;ctx.lineWidth=1;ctx.strokeRect(.5,.5,totalW-1,totalH-1);
}

function rr(ctx,x,y,w,h,r){
  ctx.beginPath();ctx.moveTo(x+r,y);ctx.lineTo(x+w-r,y);ctx.quadraticCurveTo(x+w,y,x+w,y+r);
  ctx.lineTo(x+w,y+h-r);ctx.quadraticCurveTo(x+w,y+h,x+w-r,y+h);ctx.lineTo(x+r,y+h);
  ctx.quadraticCurveTo(x,y+h,x,y+h-r);ctx.lineTo(x,y+r);ctx.quadraticCurveTo(x,y,x+r,y);ctx.closePath();
}

// ── Export image ──────────────────────────────────────────────────────────
function exportImg(fmt){
  const tmp=document.createElement('canvas');
  drawGantt(tmp,{
    title:document.getElementById('chartTitle').value.trim()||'Gantt Chart',
    startYear:parseInt(document.getElementById('startYear').value)||2026,
    dur:parseInt(document.getElementById('duration').value)||1,
    projects, lang, scale:3
  });
  const mime=fmt==='jpeg'?'image/jpeg':'image/png', ext=fmt==='jpeg'?'jpg':'png';
  const a=document.createElement('a');
  a.download=(getFilename()||'gantt')+'.'+ext;
  a.href=tmp.toDataURL(mime,.96);
  document.body.appendChild(a);a.click();document.body.removeChild(a);
}

// ── Export PDF (via canvas → data URL embedded in HTML print) ─────────────
function exportPDF(){
  const tmp=document.createElement('canvas');
  drawGantt(tmp,{
    title:document.getElementById('chartTitle').value.trim()||'Gantt Chart',
    startYear:parseInt(document.getElementById('startYear').value)||2026,
    dur:parseInt(document.getElementById('duration').value)||1,
    projects, lang, scale:3
  });
  const imgData=tmp.toDataURL('image/png',.98);
  const w=tmp.width/3, h=tmp.height/3; // logical px

  // Open a print window with the image
  const win=window.open('','_blank','width=1200,height=900');
  if(!win){showAlert(lang==='da'?'Tillad popups for at eksportere PDF.':'Allow popups to export PDF.','e');return;}

  const title=document.getElementById('chartTitle').value.trim()||'Gantt Chart';
  // Scale to A4 landscape (297×210mm ≈ 1122×794 at 96dpi)
  const A4w=1058, A4h=748;
  const scale=Math.min(A4w/w, A4h/h, 1);
  const sw=Math.round(w*scale), sh=Math.round(h*scale);

  win.document.write(`<!DOCTYPE html><html><head>
    <meta charset="UTF-8"><title>${title}</title>
    <style>
      *{margin:0;padding:0;box-sizing:border-box}
      html,body{width:${sw+40}px;background:#fff;font-family:'DM Sans',Helvetica,sans-serif}
      .page{padding:20px;display:flex;flex-direction:column;align-items:flex-start}
      img{width:${sw}px;height:${sh}px;display:block;border:1px solid #ddd}
      .meta{margin-top:10px;font-size:10px;color:#888}
      @media print{
        @page{size:A4 landscape;margin:10mm}
        html,body{width:auto}
        img{width:100%;height:auto;max-width:277mm;border:none}
        .meta{font-size:8pt}
      }
    </style>
  </head><body>
    <div class="page">
      <img src="${imgData}" alt="${title}">
      <div class="meta">${title} · ${new Date().toLocaleDateString(lang==='da'?'da-DK':'en-GB')}</div>
    </div>
    <script>window.onload=function(){window.print();}<\/script>
  </body></html>`);
  win.document.close();
}

// ── Export Excel ──────────────────────────────────────────────────────────
function exportExcelFile(){
  const title=document.getElementById('chartTitle').value.trim()||'Gantt';
  const wb=XLSX.utils.book_new();
  const all=[['Projekt','Kategori','Startdato','Slutdato']];
  projects.forEach(p=>p.tasks.forEach(x=>all.push([p.name,x.category,toEU(x.start),toEU(x.end)])));
  const ws=XLSX.utils.aoa_to_sheet(all);
  ws['!cols']=[{wch:26},{wch:30},{wch:14},{wch:14}];
  XLSX.utils.book_append_sheet(wb,ws,'Gantt Data');
  projects.forEach(p=>{
    const pr=[['Kategori','Startdato','Slutdato'],...p.tasks.map(x=>[x.category,toEU(x.start),toEU(x.end)])];
    const pws=XLSX.utils.aoa_to_sheet(pr);
    pws['!cols']=[{wch:30},{wch:14},{wch:14}];
    XLSX.utils.book_append_sheet(wb,pws,(p.name||'Projekt').substring(0,31));
  });
  XLSX.writeFile(wb,getFilename()+'.xlsx');
}

function getFilename(){return(document.getElementById('chartTitle').value.trim()||'gantt').replace(/[^\w\-æøåÆØÅ ]/g,'_');}

// ── Utilities ─────────────────────────────────────────────────────────────
function showAlert(msg,type){
  const b=document.getElementById('alertBox');
  b.className=`alert a${type}`; b.textContent=msg; b.style.display='block';
  clearTimeout(b._t); b._t=setTimeout(()=>b.style.display='none',4500);
}
function esc(s){return String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');}

// ── Init ──────────────────────────────────────────────────────────────────
projects.push({id:nextPid++,name:'Projekt 1',tasks:makeDefTasks(2026),pal:0});
renderAllProjects();
renderGantt();
document.getElementById('startYear').addEventListener('change',scheduleRender);
document.getElementById('duration').addEventListener('change',scheduleRender);
</script>
<datalist id="catHints">
  <option value="Planning & Preparation"><option value="Literature Review"><option value="Methodology Design">
  <option value="Ethical Approval"><option value="Data Collection"><option value="Data Analysis">
  <option value="Writing & Revision"><option value="Final Submission">
  <option value="Planlægning & Forberedelse"><option value="Litteraturgennemgang"><option value="Metodedesign">
  <option value="Etisk godkendelse"><option value="Dataindsamling"><option value="Dataanalyse">
  <option value="Skrivning & Redigering"><option value="Endelig indlevering">
</datalist>
</body>
</html>
