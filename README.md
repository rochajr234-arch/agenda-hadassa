<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Agenda Mágica de Hadassa 💖✨</title>
<link rel="manifest" href="manifest.json">
<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
<style>
:root {
    --rosa-bebe: #FFC0CB;
    --lilas: #D8B4E2;
    --creme: #FFF0E6;
    --dourado: #F5C16C;
    --azul: #4FC3F7;
    --prova: #FFB6C1;
    --aula: #FFDAB9;
    --trabalho: #E6E6FA;
    --viagem: #87CEFA;
    --comemoracao: #F5C16C;
    --hover-shadow: rgba(0,0,0,0.15);
}

* { box-sizing: border-box; margin:0; padding:0; }

body {
    font-family: 'Quicksand', sans-serif;
    background: linear-gradient(135deg, #FFF0E6, #E8D0F5);
    color:#333;
    transition: background 1s;
    animation: bgFade 10s infinite alternate;
}

@keyframes bgFade {
    0% { background: linear-gradient(135deg, #FFF0E6, #E8D0F5);}
    50% { background: linear-gradient(135deg, #FFE6F0, #F5E8FF);}
    100% { background: linear-gradient(135deg, #FFF0E6, #E8D0F5);}
}

header {
    background: linear-gradient(45deg, #FFC0CB, #D8B4E2);
    color: #fff;
    text-align: center;
    padding: 25px;
    font-size: 2.2em;
    font-family: 'Pacifico', cursive;
    box-shadow: 0 4px 20px rgba(0,0,0,0.2);
    position: sticky;
    top:0;
    z-index: 100;
    border-bottom: 3px solid #F5C16C;
}

.container {
    max-width: 950px;
    margin: 20px auto;
    padding: 0 15px;
}

.add-event {
    background: #fff;
    padding: 20px;
    border-radius: 25px;
    box-shadow: 0 6px 20px rgba(0,0,0,0.2);
    display:flex;
    flex-wrap: wrap;
    gap:15px;
    align-items:center;
    margin-bottom:25px;
    transition: transform 0.3s;
}

.add-event:hover { transform: translateY(-4px); }

.add-event input, .add-event select {
    flex: 1;
    padding:12px;
    border-radius:15px;
    border:1px solid #ccc;
    font-size:1em;
}

.add-event button {
    background: linear-gradient(45deg, #FFC0CB, #D8B4E2);
    color:#fff;
    border:none;
    padding:12px 20px;
    border-radius:15px;
    cursor:pointer;
    font-weight:600;
    transition: transform 0.3s, box-shadow 0.3s;
}

.add-event button:hover { transform: scale(1.05); box-shadow: 0 0 15px #FFC0CB;}

.calendar-nav {
    display:flex;
    justify-content:space-between;
    align-items:center;
    margin-bottom:15px;
}

.calendar-nav button {
    background: linear-gradient(45deg, #FFC0CB, #D8B4E2);
    color:#fff;
    border:none;
    padding:8px 12px;
    border-radius:12px;
    cursor:pointer;
    font-weight:600;
    transition: transform 0.3s, box-shadow 0.3s;
}

.calendar-nav button:hover { transform: scale(1.1); box-shadow:0 0 15px #FFC0CB;}

.month-year {
    font-weight:bold;
    font-size:1.3em;
    color:#5C2E91;
    text-shadow: 1px 1px 3px #fff;
}

.calendar {
    display:grid;
    grid-template-columns: repeat(7,1fr);
    gap:10px;
}

.day {
    background:#fff;
    border-radius:25px;
    padding:12px;
    min-height:90px;
    position:relative;
    box-shadow:0 4px 15px rgba(0,0,0,0.15);
    display:flex;
    flex-direction:column;
    gap:5px;
    cursor:pointer;
    transition: transform 0.3s, box-shadow 0.3s, background 0.5s;
}

.day:hover {
    transform: translateY(-5px) scale(1.02);
    box-shadow:0 8px 25px rgba(0,0,0,0.2);
    background: #FFF5F8;
}

.day.today {
    border: 3px solid #F5C16C;
    box-shadow: 0 0 15px #F5C16C;
}

.day-header {
    font-weight:bold;
    text-align:right;
    font-size:0.9em;
}

.event-card {
    border-radius:15px;
    padding:5px 8px;
    font-size:0.85em;
    display:flex;
    justify-content:space-between;
    align-items:center;
    cursor:grab;
    margin-top:4px;
    position:relative;
    color:#333;
    transition: transform 0.3s, box-shadow 0.3s, background 0.5s;
}

.event-card:hover {
    transform: translateY(-2px) scale(1.02);
    box-shadow:0 6px 20px rgba(0,0,0,0.2);
}

.event-card.Aula { background: linear-gradient(45deg,#FFDAB9,#FFE4C4);}
.event-card.Prova { background: linear-gradient(45deg,#FFB6C1,#FF69B4);}
.event-card.Trabalho { background: linear-gradient(45deg,#E6E6FA,#D8B4E2);}
.event-card.Viagem { background: linear-gradient(45deg,#87CEFA,#00BFFF);}
.event-card.Comemoração { background: linear-gradient(45deg,#F5C16C,#FFD700);}

.delete-btn {
    background:none;
    border:none;
    cursor:pointer;
    font-size:0.9em;
    color:#888;
    transition: color 0.2s;
}

.delete-btn:hover { color:red; }

.note-icon {
    position:absolute;
    top:5px;
    left:5px;
    font-size:1.3em;
    color:#F5C16C;
    pointer-events:none;
    animation: pulse 1.5s infinite;
}

@keyframes pulse {
    0%,100% { transform: scale(1);}
    50% { transform: scale(1.2);}
}

.notes-popup {
    position:fixed;
    top:50%;
    left:50%;
    transform: translate(-50%,-50%) scale(0);
    background:#fff;
    padding:20px;
    border-radius:25px;
    box-shadow:0 8px 25px rgba(0,0,0,0.25);
    display:flex;
    flex-direction:column;
    gap:10px;
    z-index:1000;
    width:90%;
    max-width:400px;
    transition: transform 0.3s ease;
}

.notes-popup.show { transform: translate(-50%,-50%) scale(1); }

.notes-popup textarea {
    width:100%;
    height:120px;
    border-radius:15px;
    border:1px solid #ccc;
    padding:10px;
    resize:none;
}

.notes-popup button {
    background: linear-gradient(45deg,#FFC0CB,#D8B4E2);
    color:#fff;
    border:none;
    padding:12px 16px;
    border-radius:15px;
    cursor:pointer;
    font-weight:600;
    transition: transform 0.3s, box-shadow 0.3s;
}

.notes-popup button:hover { transform: scale(1.05); box-shadow:0 0 15px #FFC0CB;}

.overlay {
    position:fixed;
    top:0; left:0;
    width:100%; height:100%;
    background: rgba(0,0,0,0.3);
    display:none;
    z-index:900;
}

@media (max-width:700px){ .calendar{ grid-template-columns: repeat(3,1fr); gap:5px; } }
</style>
</head>
<body>

<header>Agenda Mágica de Hadassa 💖✨</header>

<div class="container">
    <div class="add-event">
        <input type="text" id="event-name" placeholder="Nome da atividade">
        <input type="date" id="event-date">
        <select id="event-type">
            <option value="">Tipo de evento</option>
            <option value="Aula">📚 Aula</option>
            <option value="Prova">📝 Prova</option>
            <option value="Trabalho">✏️ Trabalho</option>
            <option value="Viagem">✈️ Viagem</option>
            <option value="Comemoração">🎉 Comemoração</option>
        </select>
        <button onclick="addEvent()">Adicionar</button>
    </div>

    <div class="calendar-nav">
        <button onclick="prevMonth()">⏮️</button>
        <div class="month-year" id="month-year"></div>
        <button onclick="nextMonth()">⏭️</button>
    </div>

    <div class="calendar" id="calendar"></div>
</div>

<div class="overlay" id="overlay"></div>

<div class="notes-popup" id="notes-popup">
    <h3>Anotações ✨</h3>
    <textarea id="notes-text" placeholder="Escreva suas anotações mágicas..."></textarea>
    <button onclick="saveNotes()">Salvar</button>
</div>

<!-- Áudio suave -->
<audio id="ding" src="ding.mp3" preload="auto"></audio>

<script>
const calendarEl=document.getElementById('calendar');
const monthYearEl=document.getElementById('month-year');
const notesPopup=document.getElementById('notes-popup');
const overlay=document.getElementById('overlay');
const notesText=document.getElementById('notes-text');
const ding = document.getElementById('ding');

let today=new Date();
let currentMonth=today.getMonth();
let currentYear=today.getFullYear();
let selectedDay=null;

let eventsData=JSON.parse(localStorage.getItem('eventsData')||'{}');
let notesData=JSON.parse(localStorage.getItem('notesData')||'{}');

const weekColors = ['#FFEBEE','#FFF3E0','#E8F5E9','#E3F2FD','#F3E5F5','#FFFDE7','#FBE9E7'];

function renderCalendar(month=currentMonth, year=currentYear){
    calendarEl.innerHTML='';
    const firstDay=new Date(year,month,1).getDay();
    const daysInMonth=new Date(year,month+1,0).getDate();
    monthYearEl.textContent=`${new Date(year,month).toLocaleString('pt-BR',{month:'long'})} ${year}`;

    for(let i=0;i<firstDay;i++) calendarEl.appendChild(document.createElement('div'));

    for(let day=1;day<=daysInMonth;day++){
        const dayEl=document.createElement('div');
        dayEl.classList.add('day');
        const dateStr=`${year}-${(month+1).toString().padStart(2,'0')}-${day.toString().padStart(2,'0')}`;
        dayEl.dataset.date=dateStr;
        dayEl.style.background = weekColors[new Date(dateStr).getDay()];
        dayEl.innerHTML=`<div class="day-header">${day}</div>`;
        dayEl.addEventListener('click',()=>openNotes(dateStr));

        // Destacar o dia atual
        if(dateStr===`${today.getFullYear()}-${(today.getMonth()+1).toString().padStart(2,'0')}-${today.getDate().toString().padStart(2,'0')}`){
            dayEl.classList.add('today');
        }

        if(notesData[dateStr]&&notesData[dateStr].trim()!==''){
            const noteIcon=document.createElement('div');
            noteIcon.classList.add('note-icon');
            noteIcon.innerHTML='📝';
            noteIcon.title=notesData[dateStr].substring(0,50)+'...';
            dayEl.appendChild(noteIcon);
        }

        calendarEl.appendChild(dayEl);
    }

    Object.keys(eventsData).forEach(date=>{
        const dayEl=document.querySelector(`.day[data-date='${date}']`);
        if(dayEl){
            eventsData[date].forEach(ev=>{
                const card=document.createElement('div');
                card.classList.add('event-card',ev.type);
                card.setAttribute('draggable','true');
                card.innerHTML=`<span>${ev.name}</span> <button class="delete-btn" onclick="deleteEvent('${date}', this)">✖</button>`;
                dayEl.appendChild(card);
            });
        }
    });
}

function addEvent(){
    const name=document.getElementById('event-name').value.trim();
    const date=document.getElementById('event-date').value;
    const type=document.getElementById('event-type').value;
    if(!name||!date||!type){ alert('Preencha todos os campos!'); return; }
    if(!eventsData[date]) eventsData[date]=[];
    eventsData[date].push({name,type});
    localStorage.setItem('eventsData',JSON.stringify(eventsData));
    renderCalendar();
    document.getElementById('event-name').value='';
    document.getElementById('event-date').value='';
    document.getElementById('event-type').value='';
    ding.play(); // som ao adicionar
}

function deleteEvent(date, btn){
    const card=btn.parentElement;
    const name=card.querySelector('span').textContent;
    const idx=eventsData[date].findIndex(ev=>ev.name===name);
    if(idx>-1) eventsData[date].splice(idx,1);
    localStorage.setItem('eventsData',JSON.stringify(eventsData));
    renderCalendar();
}

function prevMonth(){ currentMonth--; if(currentMonth<0){ currentMonth=11; currentYear--; } renderCalendar();}
function nextMonth(){ currentMonth++; if(currentMonth>11){ currentMonth=0; currentYear++; } renderCalendar();}

function openNotes(date){
    selectedDay=date;
    notesText.value=notesData[date]||'';
    notesPopup.classList.add('show');
    overlay.style.display='block';
}

function saveNotes(){
    notesData[selectedDay]=notesText.value;
    localStorage.setItem('notesData',JSON.stringify(notesData));
    notesPopup.classList.remove('show');
    overlay.style.display='none';
    renderCalendar();
    ding.play(); // som ao salvar
}

overlay.addEventListener('click',()=>{ notesPopup.classList.remove('show'); overlay.style.display='none'; });

// Drag & Drop
document.addEventListener('dragstart',e=>{
    if(e.target.classList.contains('event-card')){
        e.dataTransfer.setData('text/plain',JSON.stringify({
            name:e.target.querySelector('span').textContent,
            type:Array.from(e.target.classList).find(c=>['Aula','Prova','Trabalho','Viagem','Comemoração'].includes(c)),
            fromDate:e.target.parentElement.dataset.date
        }));
    }
});

document.addEventListener('dragover',e=>e.preventDefault());
document.addEventListener('drop',e=>{
    e.preventDefault();
    const target=e.target.closest('.day');
    if(target){
        const data=JSON.parse(e.dataTransfer.getData('text/plain'));
        if(!eventsData[target.dataset.date]) eventsData[target.dataset.date]=[];
        eventsData[target.dataset.date].push({name:data.name,type:data.type});
        const idx=eventsData[data.fromDate].findIndex(ev=>ev.name===data.name);
        if(idx>-1) eventsData[data.fromDate].splice(idx,1);
        localStorage.setItem('eventsData',JSON.stringify(eventsData));
        renderCalendar();
    }
});

renderCalendar();

// Registrar Service Worker
if('serviceWorker' in navigator){
    navigator.serviceWorker.register('sw.js');
}
</script>

</body>
</html>