<!DOCTYPE html>
<html lang="cs">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Moje Uhlíková Stopa - Semafor</title>
    <style>
        :root {
            --green: #4CAF50;
            --yellow: #FFC107;
            --red: #F44336;
            --light-blue: #f0f7ff;
        }

        * { box-sizing: border-box; font-family: 'Segoe UI', sans-serif; }
        body { background-color: var(--light-blue); padding: 20px; }
        .container { max-width: 800px; margin: 0 auto; }
        
        .header { text-align: center; margin-bottom: 30px; background: white; padding: 20px; border-radius: 15px; box-shadow: 0 4px 15px rgba(0,0,0,0.1); }
        .total-score { font-size: 24px; font-weight: bold; color: #2c3e50; }

        .day-card { background: white; border-radius: 15px; padding: 20px; margin-bottom: 20px; box-shadow: 0 4px 10px rgba(0,0,0,0.05); }
        .day-title { font-size: 20px; font-weight: bold; margin-bottom: 15px; border-bottom: 2px solid #eee; padding-bottom: 5px; }

        .category-row { display: flex; align-items: center; justify-content: space-between; margin-bottom: 15px; flex-wrap: wrap; }
        .category-label { font-weight: bold; width: 100px; }

        .traffic-light { display: flex; gap: 10px; }
        .light { width: 40px; height: 40px; border-radius: 50%; cursor: pointer; border: 3px solid transparent; opacity: 0.3; transition: 0.3s; display: flex; align-items: center; justify-content: center; color: white; font-weight: bold; }
        .light.active { opacity: 1; border-color: #333; transform: scale(1.1); }
        .green { background-color: var(--green); }
        .yellow { background-color: var(--yellow); }
        .red { background-color: var(--red); }

        .input-area { display: flex; align-items: center; gap: 10px; }
        input[type="number"] { width: 60px; padding: 5px; border: 1px solid #ccc; border-radius: 5px; }

        .day-result { background: #f9f9f9; padding: 10px; border-radius: 8px; margin-top: 10px; text-align: right; font-weight: bold; }
        .btn-reset { background: #2c3e50; color: white; border: none; padding: 10px 20px; border-radius: 5px; cursor: pointer; display: block; margin: 20px auto; }
    </style>
</head>
<body>

<div class="container">
    <div class="header">
        <h1>🌱 Moje Uhlíková Stopa</h1>
        <div class="total-score">Celý týden: <span id="total-week-carbon">0</span> kg CO2</div>
    </div>

    <div id="days-container"></div>

    <button class="btn-reset" onclick="resetData()">Smazat všechna data</button>
</div>

<script>
    const days = ['Pondělí', 'Úterý', 'Středa', 'Čtvrtek', 'Pátek', 'Sobota', 'Neděle'];
    const categories = [
        { id: 'pohyb', label: 'Pohyb', units: 'km', factors: { green: 0, yellow: 0.05, red: 0.15 } },
        { id: 'jidlo', label: 'Jídlo', units: 'porce', factors: { green: 0.5, yellow: 1.2, red: 3.5 } },
        { id: 'aktivita', label: 'Aktivita', units: 'ks', factors: { green: 0.05, yellow: 0.3, red: 2.0 } }
    ];

    let state = JSON.parse(localStorage.getItem('carbonData')) || {};

    function init() {
        const container = document.getElementById('days-container');
        container.innerHTML = '';

        days.forEach(day => {
            if (!state[day]) state[day] = { pohyb: { color: '', val: 0 }, jidlo: { color: '', val: 0 }, aktivita: { color: '', val: 0 } };

            const card = document.createElement('div');
            card.className = 'day-card';
            
            let html = `<div class="day-title">${day}</div>`;
            
            categories.forEach(cat => {
                const currentData = state[day][cat.id];
                html += `
                    <div class="category-row">
                        <div class="category-label">${cat.label}</div>
                        <div class="traffic-light">
                            <div class="light green ${currentData.color === 'green' ? 'active' : ''}" onclick="update('${day}', '${cat.id}', 'green')">Z</div>
                            <div class="light yellow ${currentData.color === 'yellow' ? 'active' : ''}" onclick="update('${day}', '${cat.id}', 'yellow')">Ž</div>
                            <div class="light red ${currentData.color === 'red' ? 'active' : ''}" onclick="update('${day}', '${cat.id}', 'red')">Č</div>
                        </div>
                        <div class="input-area">
                            <input type="number" value="${currentData.val}" onchange="updateVal('${day}', '${cat.id}', this.value)">
                            <span>${cat.units}</span>
                        </div>
                    </div>
                `;
            });

            html += `<div class="day-result">Denní stopa: <span id="res-${day}">0</span> kg CO2</div>`;
            card.innerHTML = html;
            container.appendChild(card);
            calculateDay(day);
        });
        calculateTotal();
    }

    function update(day, catId, color) {
        state[day][catId].color = color;
        save();
        init();
    }

    function updateVal(day, catId, val) {
        state[day][catId].val = parseFloat(val) || 0;
        save();
        calculateDay(day);
        calculateTotal();
    }

    function calculateDay(day) {
        let total = 0;
        categories.forEach(cat => {
            const data = state[day][cat.id];
            if (data.color) {
                total += data.val * cat.factors[data.color];
            }
        });
        document.getElementById(`res-${day}`).textContent = total.toFixed(2);
        return total;
    }

    function calculateTotal() {
        let totalWeek = 0;
        days.forEach(day => {
            totalWeek += calculateDay(day);
        });
        document.getElementById('total-week-carbon').textContent = totalWeek.toFixed(2);
    }

    function save() {
        localStorage.setItem('carbonData', JSON.stringify(state));
    }

    function resetData() {
        if(confirm('Opravdu smazat?')) {
            state = {};
            save();
            init();
        }
    }

    init();
</script>

</body>
</html>
