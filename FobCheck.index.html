<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FobCheck</title>
<style>
:root { --bg:#101214; --card:#1b1f23; --card2:#252a2f; --text:#f4f6f8; --muted:#aab2bb; --line:#343a40; --accent:#5d9cff; }
*{box-sizing:border-box} body{margin:0;background:var(--bg);color:var(--text);font-family:Arial,sans-serif}
header{padding:24px 18px 18px;border-bottom:1px solid var(--line);position:sticky;top:0;background:#101214}
h1{margin:0;font-size:26px;letter-spacing:1px}.sub{color:var(--muted);font-size:13px;margin-top:5px}
main{max-width:600px;margin:auto;padding:16px}.screen{display:none}.screen.active{display:block}
.card,.item{background:var(--card);border:1px solid var(--line);border-radius:14px;padding:16px;margin-bottom:12px}
button{width:100%;border:0;border-radius:12px;padding:17px;margin:7px 0;background:var(--card2);color:var(--text);font-size:16px;text-align:left}
button.primary{background:var(--accent);color:white;text-align:center;font-weight:bold} button.small{width:auto;padding:10px 14px;margin:4px;text-align:center}
input,select,textarea{width:100%;padding:13px;margin:6px 0 14px;background:#111417;color:var(--text);border:1px solid var(--line);border-radius:9px;font-size:16px}
label{font-size:13px;color:var(--muted)} .back{background:transparent;color:var(--muted);padding:8px 0}
.status{font-weight:bold}.green{color:#57d68d}.yellow{color:#f1c85b}.red{color:#ff6b6b}
.meta{color:var(--muted);font-size:13px;line-height:1.5}.empty{text-align:center;color:var(--muted);padding:40px 10px}
footer{text-align:center;color:#6f7780;font-size:11px;padding:20px}
</style>
</head>
<body>
<header><h1>🔑 FOBCHECK</h1><div class="sub">Nissan & Universal Fob Identifier</div></header>
<main>
<section id="home" class="screen active">
  <div class="card"><div class="meta">Personal inventory and identification tool. Unknown items remain <b>Needs Verification</b>.</div></div>
  <button onclick="show('add')">➕ &nbsp; ADD FOB<br><span class="meta">Save FCC ID, part number and details</span></button>
  <button onclick="show('inventory')">📦 &nbsp; MY INVENTORY<br><span class="meta">View and search saved fobs</span></button>
  <button onclick="show('search')">🔎 &nbsp; SEARCH FOB<br><span class="meta">Search your inventory</span></button>
</section>

<section id="add" class="screen">
<button class="back" onclick="show('home')">← Back</button>
<div class="card"><h2>Add Fob</h2>
<label>Brand</label><select id="brand"><option>Nissan</option><option>Universal / Aftermarket</option></select>
<label>FCC ID</label><input id="fcc" placeholder="Example: KR5S180144106">
<label>Part Number</label><input id="part" placeholder="Enter part number">
<label>Frequency (optional)</label><input id="freq" placeholder="Example: 315 MHz">
<label>Buttons</label><input id="buttons" type="number" min="0" placeholder="Number of buttons">
<label>Condition</label><select id="condition"><option>Good</option><option>Used</option><option>Damaged</option><option>Unknown</option></select>
<label>Status</label><select id="status"><option>Needs Verification</option><option>Potentially Reusable</option><option>Do Not Reuse</option><option>Unknown</option></select>
<label>Notes</label><textarea id="notes" rows="3" placeholder="Optional notes"></textarea>
<button class="primary" onclick="saveFob()">SAVE FOB</button></div>
</section>

<section id="inventory" class="screen">
<button class="back" onclick="show('home')">← Back</button>
<h2>My Inventory</h2><input id="filter" placeholder="Search FCC ID or part number..." oninput="renderInventory()">
<div id="list"></div>
</section>

<section id="search" class="screen">
<button class="back" onclick="show('home')">← Back</button>
<h2>Search Fob</h2><input id="searchText" placeholder="FCC ID or part number">
<button class="primary" onclick="doSearch()">SEARCH</button><div id="searchResults"></div>
</section>
</main>
<footer>FobCheck v0.1 • Local data only • Identification & inventory aid</footer>
<script>
const KEY='fobcheck_inventory_v1';
function getFobs(){return JSON.parse(localStorage.getItem(KEY)||'[]')}
function setFobs(x){localStorage.setItem(KEY,JSON.stringify(x))}
function show(id){document.querySelectorAll('.screen').forEach(x=>x.classList.remove('active'));document.getElementById(id).classList.add('active');if(id==='inventory')renderInventory()}
function cls(s){return s==='Potentially Reusable'?'green':s==='Needs Verification'||s==='Unknown'?'yellow':'red'}
function saveFob(){
 const f={id:Date.now(),brand:brand.value,fcc:fcc.value.trim(),part:part.value.trim(),freq:freq.value.trim(),buttons:buttons.value,condition:condition.value,status:status.value,notes:notes.value.trim(),date:new Date().toLocaleDateString()};
 if(!f.fcc&&!f.part){alert('Enter at least an FCC ID or Part Number.');return}
 const a=getFobs();a.unshift(f);setFobs(a);['fcc','part','freq','buttons','notes'].forEach(id=>document.getElementById(id).value='');alert('Fob saved.');show('inventory');
}
function card(f){
 return `<div class="item"><b>🔑 ${escape(f.brand)}</b><br><span class="status ${cls(f.status)}">${escape(f.status)}</span>
 <div class="meta">FCC ID: ${escape(f.fcc||'—')}<br>Part #: ${escape(f.part||'—')}<br>Condition: ${escape(f.condition)}${f.freq?'<br>Frequency: '+escape(f.freq):''}${f.notes?'<br>Notes: '+escape(f.notes):''}</div>
 <button class="small" onclick="del(${f.id})">Delete</button></div>`;
}
function escape(s){return String(s).replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]))}
function renderInventory(){
 const q=(filter?.value||'').toLowerCase();const a=getFobs().filter(f=>Object.values(f).join(' ').toLowerCase().includes(q));
 list.innerHTML=a.length?a.map(card).join(''):'<div class="empty">No fobs saved yet.</div>';
}
function doSearch(){
 const q=searchText.value.toLowerCase().trim();const a=getFobs().filter(f=>Object.values(f).join(' ').toLowerCase().includes(q));
 searchResults.innerHTML=q?(a.length?a.map(card).join(''):'<div class="empty">No matching fob in your inventory.</div>'):'';
}
function del(id){if(confirm('Delete this fob?')){setFobs(getFobs().filter(f=>f.id!==id));renderInventory();}}
</script>
</body></html>
