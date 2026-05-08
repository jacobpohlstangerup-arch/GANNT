<!DOCTYPE html>
<html lang="da">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<script src="https://cdnjs.cloudflare.com/ajax/libs/xlsx/0.18.5/xlsx.full.min.js"></script>
<style>
@import url('https://fonts.googleapis.com/css2?family=Syne:wght@400;600;700&family=DM+Sans:wght@300;400;500&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#f0ece4;--surface:#fff;--border:#ddd8ce;--text:#1a1714;--muted:#7a736c;
  --accent:#0d3d5c;--accent2:#155e86;--accentbg:#e8f2f9;
  --danger:#a91c1c;--dangerbg:#fdf2f2;
  --r:8px;--shadow:0 1px 4px rgba(0,0,0,.07),0 6px 20px rgba(0,0,0,.05);
}
body{font-family:'DM Sans',sans-serif;background:var(--bg);color:var(--text);min-height:100vh;font-size:13.5px;line-height:1.5}
header{background:var(--accent);color:#fff;padding:0 28px;height:54px;display:flex;align-items:center;justify-content:space-between;position:sticky;top:0;z-index:100;box-shadow:0 2px 8px rgba(0,0,0,.18)}
.logo{font-family:'Syne',sans-serif;font-size:15px;font-weight:700;letter-spacing:.04em}
.logo span{opacity:.45;font-weight:400;font-size:13px;margin-left:6px}
.langbtn{background:rgba(255,255,255,.13);border:1px solid rgba(255,255,255,.28);color:#fff;padding:5px 14px;border-radius:4px;font-family:'Syne',sans-serif;font-size:11px;font-weight:700;letter-spacing:.1em;cursor:pointer;transition:background .15s}
.langbtn:hover{background:rgba(255,255,255,.24)}
.wrap{max-width:1140px;margin:0 auto;padding:24px 20px}
.panel{background:var(--surface);border:1px solid var(--border);border-radius:var(--r);margin-bottom:18px;box-shadow:var(--shadow);overflow:hidden}
.ph{padding:12px 18px;border-bottom:1px solid var(--border);background:#f9f8f5;display:flex;align-items:center;justify-content:space-between;gap:10px;flex-wrap:wrap}
.ph-title{font-family:'Syne',sans-serif;font-size:10.5px;font-weight:700;letter-spacing:.12em;text-transform:uppercase;color:var(--muted)}
.pb{padding:18px}
.row3{display:grid;grid-template-columns:2fr 1fr 1fr;gap:14px}
.fg{display:flex;flex-direction:column;gap:4px}
.fg label{font-family:'Syne',sans-serif;font-size:10px;font-weight:700;letter-spacing:.09em;text-transform:uppercase;color:var(--muted)}
input,select{padding:8px 10px;border:1px solid var(--border);border-radius:5px;font-family:'DM Sans',sans-serif;font-size:13.5px;background:#fff;color:var(--text);transition:border-color .15s;width:100%}
input:focus,select:focus{outline:none;border-color:var(--accent);box-shadow:0 0 0 3px rgba(13,61,92,.09)}
.btn{display:inline-flex;align-items:center;gap:5px;padding:8px 14px;border-radius:5px;border:1px solid transparent;font-family:'DM Sans',sans-serif;font-size:13px;font-weight:500;cursor:pointer;transition:all .15s;white-space:nowrap;line-height:1}
.btn-primary{background:var(--accent);color:#fff;border-color:var(--accent)}
.btn-primary:hover{background:var(--accent2)}
.btn-outline{background:#fff;color:var(--text);border-color:var(--border)}
.btn-outline:hover{background:var(--bg)}
.btn-danger{background:#fff;color:var(--danger);border-color:#e0aaaa;padding:5px 9px;font-size:12px}
.btn-danger:hover{background:var(--dangerbg)}
.btn-sm{padding:5px 10px;font-size:12px}
.btn-ghost{background:none;border:1px dashed var(--border);color:var(--muted)}
.btn-ghost:hover{background:var(--bg);color:var(--text)}
.tbar{display:flex;gap:7px;flex-wrap:wrap;align-items:center}
/* Projects accordion */
.projects-area{display:flex;flex-direction:column;gap:12px;margin-bottom:18px}
.proj-card{background:var(--surface);border:1px solid var(--border);border-radius:var(--r);box-shadow:var(--shadow);overflow:hidden}
.proj-card-head{padding:11px 16px;display:flex;align-items:center;gap:10px;background:#f9f8f5;border-bottom:1px solid var(--border)}
.proj-color-bar{width:5px;height:32px;border-radius:3px;flex-shrink:0}
.proj-name-input{flex:1;border:1px solid transparent;background:transparent;padding:4px 6px;font-family:'Syne',sans-serif;font-size:13px;font-weight:600;border-radius:4px;transition:border-color .15s,background .15s}
.proj-name-input:hover{background:#f0ede8;border-color:var(--border)}
.proj-name-input:focus{background:#fff;border-color:var(--accent);outline:none;box-shadow:0 0 0 2px rgba(13,61,92,.08)}
.proj-card-body{padding:16px}
.add-grid{display:grid;grid-template-columns:2fr 1fr 1fr auto;gap:9px;align-items:end;margin-bottom:14px}
.tlist{list-style:none}
.trow{display:grid;grid-template-columns:2fr 1fr 1fr auto;gap:9px;align-items:center;padding:8px 0;border-bottom:1px solid #f0ece5}
.trow:last-child{border-bottom:none}
.trow.ed{background:var(--accentbg);margin:0 -16px;padding:8px 16px;border-radius:4px}
.tcat{font-weight:500;display:flex;align-items:center;gap:8px;font-size:13px}
.dot{width:8px;height:8px;border-radius:50%;flex-shrink:0}
.tdates{font-size:12px;color:var(--muted);font-variant-numeric:tabular-nums}
.tacts{display:flex;gap:5px;justify-content:flex-end}
.alert{padding:9px 13px;border-radius:5px;font-size:13px;margin-bottom:14px;border:1px solid;display:none}
.alert-s{background:var(--accentbg);border-color:#9ec8e8;color:var(--accent)}
.alert-e{background:var(--dangerbg);border-color:#e8aaaa;color:var(--danger)}
.empty{text-align:center;padding:24px;color:var(--muted);font-size:13px}
.gantt-scroll{overflow-x:auto;padding:20px}
canvas{display:block;border-radius:4px}
.proj-badge{font-family:'Syne',sans-serif;font-size:10px;font-weight:600;letter-spacing:.06em;padding:2px 8px;border-radius:3px;color:#fff}
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
    <div class="ph"><span class="ph-title" data-k="lSettings">Indstillinger</span></div>
    <div class="pb">
      <div class="row3">
        <div class="fg">
          <label data-k="lChartTitle">Charttitel</label>
          <input id="chartTitle" type="text" value="Forskningsprogram" oninput="scheduleRender()">
        </div>
        <div class="fg">
          <label data-k="lStartYear">Startår</label>
          <input id="startYear" type="number" value="2026" min="2000" max="2050" onchange="scheduleRender()">
        </div>
        <div class="fg">
          <label data-k="lDuration">Varighed (år)</label>
          <select id="duration" onchange="scheduleRender()">
            <option value="1">1</option><option value="2">2</option>
            <option value="3">3</option><option value="4">4</option><option value="5">5</option>
          </select>
        </div>
      </div>
    </div>
  </div>

  <!-- Projects -->
  <div class="panel">
    <div class="ph">
      <span class="ph-title" data-k="lProjects">Projekter</span>
      <button class="btn btn-primary btn-sm" onclick="addProject()">
        <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
        <span data-k="btnAddProject">Tilføj projekt</span>
      </button>
    </div>
    <div class="pb" style="padding-top:14px">
      <div class="projects-area" id="projectsArea"></div>
    </div>
  </div>

  <!-- Gantt -->
  <div class="panel">
    <div class="ph">
      <span class="ph-title" data-k="lGantt">Gantt Chart</span>
      <div class="tbar">
        <button class="btn btn-outline btn-sm" onclick="exportImage('png')"><span data-k="btnPNG">Eksportér PNG</span></button>
        <button class="btn btn-outline btn-sm" onclick="exportImage('jpeg')"><span data-k="btnJPEG">Eksportér JPEG</span></button>
        <button class="btn btn-outline btn-sm" onclick="exportExcelFile()"><span data-k="btnExcel">Eksportér Excel</span></button>
      </div>
    </div>
    <div class="gantt-scroll">
      <canvas id="ganttCanvas"></canvas>
    </div>
  </div>
</div>

<script>
// ── i18n ──────────────────────────────────────────────────────────────────
const L = {
  da:{
    subtitle:'Fondsansøgning', lSettings:'Indstillinger', lChartTitle:'Charttitel',
    lStartYear:'Startår', lDuration:'Varighed (år)', lProjects:'Projekter',
    btnAddProject:'Tilføj projekt', lGantt:'Gantt Chart',
    btnPNG:'Eksportér PNG', btnJPEG:'Eksportér JPEG', btnExcel:'Eksportér Excel',
    edit:'Rediger', save:'Gem', cancel:'Annuller', delete:'Slet',
    lCategory:'Kategori', lStart:'Startdato (DD-MM-ÅÅÅÅ)', lEnd:'Slutdato (DD-MM-ÅÅÅÅ)',
    btnAdd:'Tilføj', noTasks:'Ingen opgaver – tilføj en ovenfor.',
    errFields:'Udfyld alle felter.', errFmt:'Ugyldigt datoformat – brug DD-MM-ÅÅÅÅ.',
    errOrder:'Startdato skal være før slutdato.',
    projName:'Projekt', tasks:'opgaver',
    months:['Januar','Februar','Marts','April','Maj','Juni','Juli','August','September','Oktober','November','December'],
    monthsS:['Jan','Feb','Mar','Apr','Maj','Jun','Jul','Aug','Sep','Okt','Nov','Dec'],
    quarters:['1. kvartal','2. kvartal','3. kvartal','4. kvartal'],
    quartersS:['K1','K2','K3','K4'], taskLabel:'Opgave',
  },
  en:{
    subtitle:'Grant Application', lSettings:'Settings', lChartTitle:'Chart Title',
    lStartYear:'Start Year', lDuration:'Duration (years)', lProjects:'Projects',
    btnAddProject:'Add Project', lGantt:'Gantt Chart',
    btnPNG:'Export PNG', btnJPEG:'Export JPEG', btnExcel:'Export Excel',
    edit:'Edit', save:'Save', cancel:'Cancel', delete:'Delete',
    lCategory:'Category', lStart:'Start Date (DD-MM-YYYY)', lEnd:'End Date (DD-MM-YYYY)',
    btnAdd:'Add', noTasks:'No tasks yet – add one above.',
    errFields:'Please fill in all fields.', errFmt:'Invalid date format – use DD-MM-YYYY.',
    errOrder:'Start date must be before end date.',
    projName:'Project', tasks:'tasks',
    months:['January','February','March','April','May','June','July','August','September','October','November','December'],
    monthsS:['Jan','Feb','Mar','Apr','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'],
    quarters:['1st Quarter','2nd Quarter','3rd Quarter','4th Quarter'],
    quartersS:['Q1','Q2','Q3','Q4'], taskLabel:'Task',
  }
};
let lang='da';
const t=k=>L[lang][k]??k;
function toggleLang(){
  lang=lang==='da'?'en':'da';
  document.getElementById('langBtn').textContent=lang==='da'?'EN':'DA';
  document.querySelectorAll('[data-k]').forEach(el=>{const v=t(el.dataset.k);if(v)el.textContent=v;});
  renderAllProjects(); scheduleRender();
}

// ── Palette ───────────────────────────────────────────────────────────────
const PROJECT_PALETTES = [
  // each project gets its own palette: [header, bar shades...]
  {h:'#0d3d5c', bars:['#0d3d5c','#155e86','#1a7aad','#2292cc','#4aabda','#6bbfe3','#94d2eb','#b8e2f2']},
  {h:'#1a4d2e', bars:['#1a4d2e','#236b3e','#2e8a52','#3aaa67','#52c27e','#74d49a','#98e3b6','#bdeece']},
  {h:'#5c1a1a', bars:['#5c1a1a','#842424','#a93030','#c94040','#d96060','#e48888','#edaaaa','#f5cccc']},
  {h:'#3d2e0d', bars:['#3d2e0d','#6b5014','#936e1c','#b88822','#d4a62e','#e8c05a','#f0d388','#f7e6b5']},
  {h:'#2e0d5c', bars:['#2e0d5c','#451a86','#5e2aad','#7a3fd4','#9660e0','#ae84e8','#c8a8f0','#e0ccf8']},
];

function getPalette(idx){ return PROJECT_PALETTES[idx % PROJECT_PALETTES.length]; }

// ── State ─────────────────────────────────────────────────────────────────
let projects=[];
let nextPid=1, nextTid=1;
let editKey=null; // "pid-tid"

const DEFAULT_CATS=[
  {cat:'Planning & Preparation',   sm:1,sd:1, em:2, ed:28},
  {cat:'Literature Review',        sm:1,sd:15,em:5, ed:31},
  {cat:'Methodology Design',       sm:3,sd:1, em:6, ed:30},
  {cat:'Ethical Approval',         sm:4,sd:1, em:6, ed:30},
  {cat:'Data Collection',          sm:5,sd:1, em:9, ed:30},
  {cat:'Data Analysis',            sm:8,sd:1, em:11,ed:30},
  {cat:'Writing & Revision',       sm:9,sd:1, em:12,ed:15},
  {cat:'Final Submission',         sm:11,sd:15,em:12,ed:31},
];

function isoDate(y,m,d){return`${y}-${String(m).padStart(2,'0')}-${String(d).padStart(2,'0')}`}
function parseEU(s){
  const m=String(s).trim().match(/^(\d{1,2})[.\-\/](\d{1,2})[.\-\/](\d{4})$/);
  if(!m)return null;
  const d=new Date(`${m[3]}-${m[2].padStart(2,'0')}-${m[1].padStart(2,'0')}T00:00:00`);
  return isNaN(d)?null:d;
}
function toISO(s){
  if(s instanceof Date)return isoDate(s.getFullYear(),s.getMonth()+1,s.getDate());
  const d=parseEU(String(s));
  if(d)return isoDate(d.getFullYear(),d.getMonth()+1,d.getDate());
  if(/^\d{4}-\d{2}-\d{2}$/.test(String(s).trim()))return String(s).trim();
  return'';
}
function toEU(iso){
  const m=String(iso).match(/^(\d{4})-(\d{2})-(\d{2})$/);
  return m?`${m[3]}-${m[2]}-${m[1]}`:iso;
}

function makeDefaultTasks(y){
  return DEFAULT_CATS.map((d,i)=>({
    id:nextTid++,category:d.cat,
    start:isoDate(y,d.sm,d.sd),end:isoDate(y,d.em,d.ed)
  }));
}

function addProject(){
  const y=parseInt(document.getElementById('startYear').value)||2026;
  const idx=projects.length;
  projects.push({
    id:nextPid++, name:`${t('projName')} ${idx+1}`,
    tasks:makeDefaultTasks(y), palette:idx
  });
  renderAllProjects(); scheduleRender();
}

function deleteProject(pid){
  if(!confirm(lang==='da'?'Slet dette projekt?':'Delete this project?'))return;
  projects=projects.filter(p=>p.id!==pid);
  renderAllProjects(); scheduleRender();
}

function addTask(pid){
  const p=projects.find(x=>x.id===pid); if(!p)return;
  const catEl=document.getElementById(`nc${pid}`);
  const sEl=document.getElementById(`ns${pid}`);
  const eEl=document.getElementById(`ne${pid}`);
  const cat=catEl.value.trim(), sr=sEl.value.trim(), er=eEl.value.trim();
  if(!cat||!sr||!er){showAlert(t('errFields'),'e');return}
  if(!parseEU(sr)||!parseEU(er)){showAlert(t('errFmt'),'e');return}
  const start=toISO(sr), end=toISO(er);
  if(start>=end){showAlert(t('errOrder'),'e');return}
  p.tasks.push({id:nextTid++,category:cat,start,end});
  catEl.value=''; sEl.value=''; eEl.value='';
  renderAllProjects(); scheduleRender();
}

function deleteTask(pid,tid){
  const p=projects.find(x=>x.id===pid); if(!p)return;
  p.tasks=p.tasks.filter(t=>t.id!==tid);
  renderAllProjects(); scheduleRender();
}
function startEdit(pid,tid){editKey=`${pid}-${tid}`;renderAllProjects();}
function cancelEdit(){editKey=null;renderAllProjects();}
function saveEdit(pid,tid){
  const p=projects.find(x=>x.id===pid); if(!p)return;
  const cat=document.getElementById(`ec${pid}_${tid}`).value.trim();
  const sr=document.getElementById(`es${pid}_${tid}`).value.trim();
  const er=document.getElementById(`ee${pid}_${tid}`).value.trim();
  if(!cat||!sr||!er){showAlert(t('errFields'),'e');return}
  if(!parseEU(sr)||!parseEU(er)){showAlert(t('errFmt'),'e');return}
  const start=toISO(sr), end=toISO(er);
  if(start>=end){showAlert(t('errOrder'),'e');return}
  const task=p.tasks.find(x=>x.id===tid);
  if(task){task.category=cat;task.start=start;task.end=end;}
  editKey=null; renderAllProjects(); scheduleRender();
}

// ── Render project cards ──────────────────────────────────────────────────
function renderAllProjects(){
  const area=document.getElementById('projectsArea');
  if(!projects.length){
    area.innerHTML=`<div class="empty" style="padding:20px 0">
      <p style="margin-bottom:10px">${lang==='da'?'Ingen projekter endnu.':'No projects yet.'}</p>
    </div>`;
    return;
  }
  area.innerHTML=projects.map((p,pi)=>{
    const pal=getPalette(p.palette??pi);
    const taskRows=p.tasks.map(task=>{
      const key=`${p.id}-${task.id}`;
      if(editKey===key) return `
        <li class="trow ed">
          <input id="ec${p.id}_${task.id}" value="${esc(task.category)}">
          <input id="es${p.id}_${task.id}" value="${toEU(task.start)}" placeholder="DD-MM-YYYY">
          <input id="ee${p.id}_${task.id}" value="${toEU(task.end)}" placeholder="DD-MM-YYYY">
          <div class="tacts">
            <button class="btn btn-primary btn-sm" onclick="saveEdit(${p.id},${task.id})">${t('save')}</button>
            <button class="btn btn-outline btn-sm" onclick="cancelEdit()">${t('cancel')}</button>
          </div>
        </li>`;
      const barColor=pal.bars[p.tasks.indexOf(task)%pal.bars.length];
      return `
        <li class="trow">
          <div class="tcat"><span class="dot" style="background:${barColor}"></span>${esc(task.category)}</div>
          <div class="tdates">${toEU(task.start)}</div>
          <div class="tdates">${toEU(task.end)}</div>
          <div class="tacts">
            <button class="btn btn-outline btn-sm" onclick="startEdit(${p.id},${task.id})">${t('edit')}</button>
            <button class="btn btn-danger" onclick="deleteTask(${p.id},${task.id})">${t('delete')}</button>
          </div>
        </li>`;
    }).join('');
    return `
    <div class="proj-card">
      <div class="proj-card-head">
        <div class="proj-color-bar" style="background:${pal.h}"></div>
        <input class="proj-name-input" value="${esc(p.name)}" oninput="updateProjName(${p.id},this.value)" placeholder="${t('projName')}...">
        <span class="proj-badge" style="background:${pal.h}">${p.tasks.length} ${t('tasks')}</span>
        <button class="btn btn-danger btn-sm" onclick="deleteProject(${p.id})" title="${t('delete')}">✕</button>
      </div>
      <div class="proj-card-body">
        <div class="add-grid">
          <div class="fg">
            <label>${t('lCategory')}</label>
            <input id="nc${p.id}" type="text" list="catHints" placeholder="f.eks. Data Collection...">
          </div>
          <div class="fg">
            <label>${t('lStart')}</label>
            <input id="ns${p.id}" type="text" placeholder="DD-MM-YYYY">
          </div>
          <div class="fg">
            <label>${t('lEnd')}</label>
            <input id="ne${p.id}" type="text" placeholder="DD-MM-YYYY">
          </div>
          <div class="fg"><label>&nbsp;</label>
            <button class="btn btn-primary" onclick="addTask(${p.id})">
              <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><line x1="12" y1="5" x2="12" y2="19"/><line x1="5" y1="12" x2="19" y2="12"/></svg>
              ${t('btnAdd')}
            </button>
          </div>
        </div>
        <ul class="tlist">${taskRows||`<div class="empty">${t('noTasks')}</div>`}</ul>
      </div>
    </div>`;
  }).join('');
}

function updateProjName(pid,v){
  const p=projects.find(x=>x.id===pid);
  if(p){p.name=v;scheduleRender();}
}

// ── Gantt Canvas ──────────────────────────────────────────────────────────
let renderTimer=null;
function scheduleRender(){clearTimeout(renderTimer);renderTimer=setTimeout(renderGantt,80);}

function renderGantt(exportScale=null){
  const canvas=document.getElementById('ganttCanvas');
  if(!canvas)return;
  const scale=exportScale||Math.min(window.devicePixelRatio||1,2);
  const title=document.getElementById('chartTitle').value.trim()||'Gantt Chart';
  const startYear=parseInt(document.getElementById('startYear').value)||2026;
  const dur=parseInt(document.getElementById('duration').value)||1;
  drawGantt(canvas,{title,startYear,dur,projects,lang,scale});
}

function drawGantt(canvas, opts){
  const {title,startYear,dur,projects,lang,scale}=opts;
  const endYear=startYear+dur-1;

  // ── Constants ──
  const LABEL_W=210, PAD_R=20;
  const TITLE_H=44, HDR_YEAR=26, HDR_QTR=22, HDR_MON=18;
  const HDR_H=HDR_YEAR+HDR_QTR+HDR_MON;
  const TASK_ROW=34, PROJ_HEADER=30, PROJ_GAP=10, FOOTER_H=26;

  const totalMonths=dur*12;
  const availW=Math.max(700,Math.min(1060,window.innerWidth-80));
  const MON_W=Math.max(42,Math.floor((availW-LABEL_W-PAD_R)/totalMonths));
  const CHART_W=MON_W*totalMonths;
  const totalW=LABEL_W+CHART_W+PAD_R;

  // compute total height
  let contentH=0;
  projects.forEach((p,i)=>{
    if(i>0)contentH+=PROJ_GAP;
    contentH+=PROJ_HEADER+p.tasks.length*TASK_ROW;
  });
  if(!projects.length)contentH=TASK_ROW*2;
  const totalH=TITLE_H+HDR_H+contentH+FOOTER_H+4;

  canvas.width=totalW*scale; canvas.height=totalH*scale;
  canvas.style.width=totalW+'px'; canvas.style.height=totalH+'px';
  const ctx=canvas.getContext('2d');
  ctx.scale(scale,scale);

  const P={
    bg:'#ffffff',surface:'#f8f7f4',rowAlt:'#f3f1ed',
    border:'#c8c2b8',borderLt:'#e2ddd5',
    text:'#1a1714',muted:'#7a736c',white:'#ffffff',
  };

  const msS=L[lang].monthsS, qS=L[lang].quartersS, qF=L[lang].quarters;

  // bg
  ctx.fillStyle=P.bg; ctx.fillRect(0,0,totalW,totalH);

  // ── Title bar ──
  ctx.fillStyle='#0d3d5c'; ctx.fillRect(0,0,totalW,TITLE_H);
  ctx.fillStyle=P.white; ctx.textBaseline='middle'; ctx.textAlign='left';
  ctx.font=`700 14px 'Syne',sans-serif`; ctx.fillText(title,16,TITLE_H/2);
  const period=startYear===endYear?`${startYear}`:`${startYear} – ${endYear}`;
  ctx.fillStyle='rgba(255,255,255,.5)'; ctx.textAlign='right';
  ctx.font=`400 11.5px 'DM Sans',sans-serif`; ctx.fillText(period,totalW-PAD_R,TITLE_H/2);

  const hTop=TITLE_H;

  // ── Year header ──
  ctx.fillStyle='#0d3d5c'; ctx.fillRect(0,hTop,totalW,HDR_YEAR);
  // task col label
  ctx.fillStyle='rgba(255,255,255,.65)'; ctx.textAlign='left'; ctx.textBaseline='middle';
  ctx.font=`600 9.5px 'Syne',sans-serif`;
  ctx.fillText(lang==='da'?'OPGAVE':'TASK',14,hTop+HDR_YEAR/2);
  for(let yi=0;yi<dur;yi++){
    const xL=LABEL_W+yi*12*MON_W, xR=xL+12*MON_W;
    ctx.fillStyle=P.white; ctx.textAlign='center'; ctx.textBaseline='middle';
    ctx.font=`600 12px 'Syne',sans-serif`;
    ctx.fillText(String(startYear+yi),(xL+xR)/2,hTop+HDR_YEAR/2);
    if(yi>0){
      ctx.strokeStyle='rgba(255,255,255,.2)'; ctx.lineWidth=1;
      ctx.beginPath(); ctx.moveTo(xL,hTop); ctx.lineTo(xL,hTop+HDR_YEAR); ctx.stroke();
    }
  }

  // ── Quarter header ──
  const qTop=hTop+HDR_YEAR;
  ctx.fillStyle='#155e86'; ctx.fillRect(0,qTop,totalW,HDR_QTR);
  ctx.fillStyle=P.muted; ctx.fillRect(0,qTop,LABEL_W,HDR_QTR);
  for(let yi=0;yi<dur;yi++){
    for(let qi=0;qi<4;qi++){
      const lx=LABEL_W+(yi*12+qi*3)*MON_W;
      const midx=lx+1.5*MON_W;
      ctx.strokeStyle='rgba(255,255,255,.15)'; ctx.lineWidth=1;
      ctx.beginPath(); ctx.moveTo(lx,qTop); ctx.lineTo(lx,qTop+HDR_QTR); ctx.stroke();
      ctx.fillStyle=P.white; ctx.textAlign='center'; ctx.textBaseline='middle';
      ctx.font=`600 10px 'Syne',sans-serif`;
      const ql=3*MON_W>80?qF[qi]:qS[qi];
      ctx.fillText(ql,midx,qTop+HDR_QTR/2);
    }
  }

  // ── Month header ──
  const mTop=qTop+HDR_QTR;
  ctx.fillStyle='#e8f2f9'; ctx.fillRect(0,mTop,totalW,HDR_MON);
  ctx.fillStyle=P.surface; ctx.fillRect(0,mTop,LABEL_W,HDR_MON);
  for(let yi=0;yi<dur;yi++){
    for(let mi=0;mi<12;mi++){
      const mx=LABEL_W+(yi*12+mi)*MON_W;
      ctx.strokeStyle=P.borderLt; ctx.lineWidth=0.5;
      ctx.beginPath(); ctx.moveTo(mx,mTop); ctx.lineTo(mx,mTop+HDR_MON); ctx.stroke();
      if(MON_W>=28){
        ctx.fillStyle=P.muted; ctx.textAlign='center'; ctx.textBaseline='middle';
        ctx.font=`400 9.5px 'DM Sans',sans-serif`;
        ctx.fillText(MON_W>=36?msS[mi]:msS[mi][0],mx+MON_W/2,mTop+HDR_MON/2);
      }
    }
  }

  // Divider below header
  ctx.strokeStyle=P.border; ctx.lineWidth=1.5;
  ctx.beginPath(); ctx.moveTo(0,hTop+HDR_H); ctx.lineTo(totalW,hTop+HDR_H); ctx.stroke();

  // ── Period math ──
  const periodStart=new Date(startYear,0,1).getTime();
  const periodEnd=new Date(endYear,11,31,23,59,59).getTime();
  const periodLen=periodEnd-periodStart;
  function xOf(iso){
    const d=new Date(iso+'T00:00:00').getTime();
    return LABEL_W+Math.max(0,Math.min(1,(d-periodStart)/periodLen))*CHART_W;
  }

  // ── Draw projects ──
  let curY=TITLE_H+HDR_H;

  if(!projects.length){
    ctx.fillStyle=P.muted; ctx.textAlign='center'; ctx.textBaseline='middle';
    ctx.font=`400 13px 'DM Sans',sans-serif`;
    ctx.fillText(lang==='da'?'Ingen projekter.':'No projects.',totalW/2,curY+TASK_ROW);
  }

  projects.forEach((proj,pi)=>{
    if(pi>0)curY+=PROJ_GAP;
    const pal=getPalette(proj.palette??pi);
    const projH=PROJ_HEADER+proj.tasks.length*TASK_ROW;

    // project header band
    ctx.fillStyle=pal.h;
    ctx.fillRect(0,curY,totalW,PROJ_HEADER);
    ctx.fillStyle=P.white; ctx.textAlign='left'; ctx.textBaseline='middle';
    ctx.font=`600 12px 'Syne',sans-serif`;
    ctx.fillText(proj.name||`${t('projName')} ${pi+1}`,14,curY+PROJ_HEADER/2);
    // task count badge
    ctx.fillStyle='rgba(255,255,255,.25)';
    const badge=`${proj.tasks.length} ${t('tasks')}`;
    ctx.font=`400 10px 'DM Sans',sans-serif`;
    ctx.textAlign='right';
    ctx.fillText(badge,totalW-PAD_R,curY+PROJ_HEADER/2);

    // vertical grid lines across project
    for(let col=0;col<totalMonths;col++){
      const gx=LABEL_W+col*MON_W;
      const isQ=col%3===0;
      ctx.strokeStyle=isQ?P.borderLt:'rgba(0,0,0,.03)';
      ctx.lineWidth=isQ?0.8:0.5;
      ctx.beginPath(); ctx.moveTo(gx,curY+PROJ_HEADER); ctx.lineTo(gx,curY+projH); ctx.stroke();
    }

    // task rows
    proj.tasks.forEach((task,ti)=>{
      const ry=curY+PROJ_HEADER+ti*TASK_ROW;
      const barColor=pal.bars[ti%pal.bars.length];

      ctx.fillStyle=ti%2===0?P.bg:P.rowAlt;
      ctx.fillRect(0,ry,totalW,TASK_ROW);

      ctx.strokeStyle=P.borderLt; ctx.lineWidth=0.5;
      ctx.beginPath(); ctx.moveTo(0,ry+TASK_ROW); ctx.lineTo(totalW,ry+TASK_ROW); ctx.stroke();

      // dot + label
      ctx.fillStyle=barColor;
      ctx.beginPath(); ctx.arc(13,ry+TASK_ROW/2,4.5,0,Math.PI*2); ctx.fill();
      ctx.fillStyle=P.text; ctx.textAlign='left'; ctx.textBaseline='middle';
      ctx.font=`400 12px 'DM Sans',sans-serif`;
      const maxLW=LABEL_W-30;
      let label=task.category;
      while(ctx.measureText(label).width>maxLW&&label.length>3)label=label.slice(0,-1);
      if(label!==task.category)label=label.slice(0,-1)+'…';
      ctx.fillText(label,25,ry+TASK_ROW/2);

      // bar
      const bx=xOf(task.start), bxE=xOf(task.end);
      const bw=Math.max(3,bxE-bx);
      const bh=18, by=ry+(TASK_ROW-bh)/2, br=3.5;

      ctx.shadowColor='rgba(0,0,0,.13)'; ctx.shadowBlur=3; ctx.shadowOffsetY=1.5;
      ctx.fillStyle=barColor;
      roundRect(ctx,bx,by,bw,bh,br); ctx.fill();
      ctx.shadowColor='transparent'; ctx.shadowBlur=0; ctx.shadowOffsetY=0;

      // gloss
      const g=ctx.createLinearGradient(bx,by,bx,by+bh);
      g.addColorStop(0,'rgba(255,255,255,.2)'); g.addColorStop(1,'rgba(255,255,255,0)');
      ctx.fillStyle=g; roundRect(ctx,bx,by,bw,bh,br); ctx.fill();

      // date label inside bar
      if(bw>110){
        const dl=`${toEU(task.start)} → ${toEU(task.end)}`;
        ctx.font=`400 9px 'DM Sans',sans-serif`;
        if(ctx.measureText(dl).width<bw-10){
          ctx.fillStyle='rgba(255,255,255,.9)'; ctx.textAlign='center'; ctx.textBaseline='middle';
          ctx.fillText(dl,bx+bw/2,by+bh/2);
        }
      }
    });

    // Bottom border of project
    ctx.strokeStyle=pal.h; ctx.lineWidth=1.5;
    ctx.globalAlpha=0.3;
    ctx.beginPath(); ctx.moveTo(0,curY+projH); ctx.lineTo(totalW,curY+projH); ctx.stroke();
    ctx.globalAlpha=1;

    curY+=projH;
  });

  // ── Column separator ──
  ctx.strokeStyle=P.border; ctx.lineWidth=1.5;
  ctx.beginPath(); ctx.moveTo(LABEL_W,TITLE_H); ctx.lineTo(LABEL_W,curY); ctx.stroke();

  // ── Footer ──
  const fy=curY+4;
  ctx.fillStyle=P.surface; ctx.fillRect(0,fy,totalW,FOOTER_H);
  ctx.strokeStyle=P.borderLt; ctx.lineWidth=1;
  ctx.beginPath(); ctx.moveTo(0,fy); ctx.lineTo(totalW,fy); ctx.stroke();
  ctx.fillStyle=P.muted; ctx.font=`400 9.5px 'DM Sans',sans-serif`;
  ctx.textAlign='left'; ctx.textBaseline='middle';
  ctx.fillText(`${title} · ${period} · ${projects.length} ${lang==='da'?'projekter':'projects'} · ${projects.reduce((s,p)=>s+p.tasks.length,0)} ${t('tasks')}`,14,fy+FOOTER_H/2);
  ctx.textAlign='right';
  ctx.fillText(new Date().toLocaleDateString(lang==='da'?'da-DK':'en-GB'),totalW-PAD_R,fy+FOOTER_H/2);

  // ── Outer border ──
  ctx.strokeStyle=P.border; ctx.lineWidth=1;
  ctx.strokeRect(0.5,0.5,totalW-1,totalH-1);
}

function roundRect(ctx,x,y,w,h,r){
  ctx.beginPath();
  ctx.moveTo(x+r,y); ctx.lineTo(x+w-r,y); ctx.quadraticCurveTo(x+w,y,x+w,y+r);
  ctx.lineTo(x+w,y+h-r); ctx.quadraticCurveTo(x+w,y+h,x+w-r,y+h);
  ctx.lineTo(x+r,y+h); ctx.quadraticCurveTo(x,y+h,x,y+h-r);
  ctx.lineTo(x,y+r); ctx.quadraticCurveTo(x,y,x+r,y);
  ctx.closePath();
}

// ── Export image ──────────────────────────────────────────────────────────
function exportImage(fmt){
  const tmp=document.createElement('canvas');
  const title=document.getElementById('chartTitle').value.trim()||'Gantt Chart';
  const startYear=parseInt(document.getElementById('startYear').value)||2026;
  const dur=parseInt(document.getElementById('duration').value)||1;
  drawGantt(tmp,{title,startYear,dur,projects,lang,scale:3});
  const mime=fmt==='jpeg'?'image/jpeg':'image/png';
  const ext=fmt==='jpeg'?'jpg':'png';
  const a=document.createElement('a');
  a.download=(title.replace(/[^\w\-æøåÆØÅ ]/g,'_')||'gantt')+'.'+ext;
  a.href=tmp.toDataURL(mime,0.96);
  document.body.appendChild(a); a.click(); document.body.removeChild(a);
}

// ── Export Excel ──────────────────────────────────────────────────────────
function exportExcelFile(){
  const title=document.getElementById('chartTitle').value.trim()||'Gantt';
  const wb=XLSX.utils.book_new();
  // Sheet 1: all data
  const rows=[['Projekt','Kategori','Startdato','Slutdato']];
  projects.forEach(p=>p.tasks.forEach(t=>rows.push([p.name,t.category,toEU(t.start),toEU(t.end)])));
  const ws=XLSX.utils.aoa_to_sheet(rows);
  ws['!cols']=[{wch:26},{wch:30},{wch:14},{wch:14}];
  XLSX.utils.book_append_sheet(wb,ws,'Gantt Data');
  // One sheet per project
  projects.forEach(p=>{
    const pr=[['Kategori','Startdato','Slutdato'],...p.tasks.map(t=>[t.category,toEU(t.start),toEU(t.end)])];
    const pws=XLSX.utils.aoa_to_sheet(pr);
    pws['!cols']=[{wch:30},{wch:14},{wch:14}];
    XLSX.utils.book_append_sheet(wb,pws,(p.name||'Projekt').substring(0,31));
  });
  XLSX.writeFile(wb,(title.replace(/[^\w\-æøåÆØÅ ]/g,'_')||'gantt')+'.xlsx');
}

// ── Utilities ─────────────────────────────────────────────────────────────
function showAlert(msg,type){
  const b=document.getElementById('alertBox');
  b.className=`alert alert-${type}`; b.textContent=msg; b.style.display='block';
  clearTimeout(b._t); b._t=setTimeout(()=>b.style.display='none',4500);
}
function esc(s){return String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;').replace(/"/g,'&quot;');}

// ── Init ──────────────────────────────────────────────────────────────────
// Create one default project
const y0=2026;
projects.push({id:nextPid++,name:lang==='da'?'Projekt 1':'Project 1',tasks:makeDefaultTasks(y0),palette:0});
renderAllProjects();
renderGantt();

document.getElementById('startYear').addEventListener('change',scheduleRender);
document.getElementById('duration').addEventListener('change',scheduleRender);
</script>
<datalist id="catHints">
  <option value="Planning &amp; Preparation">
  <option value="Literature Review">
  <option value="Methodology Design">
  <option value="Ethical Approval">
  <option value="Data Collection">
  <option value="Data Analysis">
  <option value="Writing &amp; Revision">
  <option value="Final Submission">
</datalist>
</body>
</html>
