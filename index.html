<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tablica Odjazdów MZK Gorzów - Stilon</title>
    <style>
        body {
            background-color: #111;
            color: #fff;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            display: flex;
            justify-content: center;
            padding: 20px;
        }
        .board {
            background: #000;
            border: 4px solid #333;
            border-radius: 8px;
            width: 100%;
            max-width: 500px;
            padding: 15px;
            box-shadow: 0 0 15px rgba(0,0,0,0.5);
        }
        .header {
            font-size: 1.2rem;
            font-weight: bold;
            text-align: center;
            border-bottom: 2px solid #ff9900;
            padding-bottom: 10px;
            margin-bottom: 15px;
            color: #ff9900;
        }
        .departure-row {
            display: flex;
            justify-content: space-between;
            padding: 8px 5px;
            border-bottom: 1px solid #222;
            font-size: 1.1rem;
        }
        .line {
            color: #ff9900;
            font-weight: bold;
            width: 40px;
        }
        .direction {
            flex-grow: 1;
            padding-left: 10px;
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
        }
        .time {
            color: #00ff00;
            font-weight: bold;
            text-align: right;
            min-width: 70px;
        }
        .loading, .error {
            text-align: center;
            color: #888;
            padding: 20px;
        }
        .error { color: #ff3333; }
    </style>
</head>
<body>

    <div class="board">
        <div id="stop-name" class="header">MZK Gorzów - Ładowanie...</div>
        <div id="departures-list">
            <div class="loading">Pobieranie oficjalnych danych live dla przystanku Stilon...</div>
        </div>
    </div>

    <script>
        // Identyfikator oficjalny dla przystanku Stilon
        const STOP_ID = "112"; 
        
        // Adres oficjalnego API Trapeze w Gorzowie
        const OFFICIAL_API_URL = `https://gorzow.pl{STOP_ID}`;
        
        // Wykorzystanie proxy do ominięcia ograniczeń CORS w przeglądarce
        const PROXY_URL = "https://allorigins.win" + encodeURIComponent(OFFICIAL_API_URL);

        async function fetchMzkData() {
            try {
                const response = await fetch(PROXY_URL);
                if (!response.ok) throw new Error("Błąd sieci");
                
                const wrapper = await response.json();
                const data = JSON.parse(wrapper.contents); 

                const listContainer = document.getElementById("departures-list");
                const stopHeader = document.getElementById("stop-name");

                if (data.stopName) {
                    stopHeader.innerText = data.stopName;
                }

                listContainer.innerHTML = "";

                if (!data.departures || data.departures.length === 0) {
                    listContainer.innerHTML = '<div class="loading">Brak zaplanowanych odjazdów w najbliższym czasie.</div>';
                    return;
                }

                data.departures.forEach(item => {
                    const row = document.createElement("div");
                    row.className = "departure-row";

                    // Wyświetlanie surowych, oficjalnych danych z Gorzowa: linia, kierunek, czas rzeczywisty
                    row.innerHTML = `
                        <span class="line">${item.line || ''}</span>
                        <span class="direction">${item.direction || ''}</span>
                        <span class="time">${item.time || ''}</span>
                    `;
                    listContainer.appendChild(row);
                });

            } catch (err) {
                console.error(err);
                document.getElementById("departures-list").innerHTML = 
                    `<div class="error">Nie udało się pobrać danych z oficjalnego serwera komunikacji.</div>`;
            }
        }

        // Pobranie danych na starcie
        fetchMzkData();

        // Automatyczne odświeżanie tablicy co 30 sekund
        setInterval(fetchMzkData, 30000);
    </script>

</body>
</html>
