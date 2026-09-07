# Wildlife-Buch-Test

index.html

<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="theme-color" content="#183b2b">

<title>Wildlife Buch</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
  background: #f4f3ed;
  color: #17231d;
}

header {
  background: linear-gradient(145deg, #183b2b, #4b795d);
  color: white;
  padding: 25px 20px 20px;
}

header h1 {
  margin: 0;
  font-size: 29px;
}

header p {
  margin: 5px 0 0;
  opacity: 0.8;
}

main {
  max-width: 700px;
  margin: auto;
  padding: 16px 16px 100px;
}

.page {
  display: none;
}

.page.active {
  display: block;
}

.card {
  background: white;
  border-radius: 19px;
  padding: 17px;
  margin-bottom: 13px;
  box-shadow: 0 4px 18px rgba(0,0,0,0.05);
}

.hero {
  background: linear-gradient(135deg, #dcebdc, #fbfaf3);
}

h2 {
  margin-top: 4px;
}

h3 {
  margin-bottom: 8px;
}

.muted {
  color: #718078;
}

button {
  font: inherit;
}

.primary {
  border: 0;
  background: #183b2b;
  color: white;
  border-radius: 13px;
  padding: 13px 17px;
  font-weight: 700;
}

.secondary {
  border: 0;
  background: #eaf0eb;
  color: #183b2b;
  border-radius: 12px;
  padding: 10px 13px;
  font-weight: 650;
}

.search {
  width: 100%;
  padding: 14px;
  border: 1px solid #dce2dc;
  border-radius: 14px;
  font-size: 16px;
  background: white;
}

.grid {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 10px;
}

.stat {
  background: white;
  border: 1px solid #e0e4df;
  border-radius: 16px;
  padding: 14px;
}

.stat strong {
  display: block;
  font-size: 25px;
  color: #183b2b;
}

.animal {
  width: 60px;
  height: 60px;
  border-radius: 16px;
  background: #e2ece2;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 31px;
  flex-shrink: 0;
}

.species {
  display: flex;
  align-items: center;
  gap: 13px;
}

.badge {
  display: inline-block;
  background: #e8f0e9;
  color: #183b2b;
  padding: 5px 8px;
  border-radius: 50px;
  font-size: 11px;
  margin: 2px;
}

.row {
  display: flex;
  gap: 7px;
  flex-wrap: wrap;
}

input,
select,
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #dce2dc;
  border-radius: 11px;
  background: white;
  font: inherit;
}

label {
  display: block;
  font-weight: 700;
  margin: 12px 0 5px;
}

textarea {
  min-height: 90px;
}

.photo {
  width: 100%;
  max-height: 400px;
  object-fit: cover;
  border-radius: 14px;
  margin-top: 10px;
}

.empty {
  text-align: center;
  color: #718078;
  padding: 30px 10px;
}

.map {
  height: 170px;
  border-radius: 16px;
  background: #e4e8dc;
  position: relative;
  overflow: hidden;
}

.map-land {
  position: absolute;
  width: 70%;
  height: 70%;
  left: 15%;
  top: 15%;
  background: #c9d2c0;
  border-radius: 50%;
  transform: rotate(-8deg);
}

.map-text {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  color: #536259;
}

nav {
  position: fixed;
  bottom: 0;
  left: 0;
  right: 0;
  background: white;
  border-top: 1px solid #dde2dc;
  display: flex;
  z-index: 20;
  padding-bottom: env(safe-area-inset-bottom);
}

nav button {
  flex: 1;
  border: 0;
  background: white;
  color: #718078;
  padding: 9px 2px;
  font-size: 11px;
}

nav button.active {
  color: #183b2b;
  font-weight: 800;
}

.icon {
  display: block;
  font-size: 22px;
  margin-bottom: 2px;
}

.observation {
  border-bottom: 1px solid #e1e5e0;
  padding: 12px 0;
}

.observation:last-child {
  border-bottom: 0;
}

hr {
  border: 0;
  border-top: 1px solid #e1e5e0;
  margin: 18px 0;
}
</style>
</head>

<body>

<header>
  <h1>Wildlife Buch 🐾</h1>
  <p>Dein persönliches Buch der Tierbeobachtungen</p>
</header>

<main>

<!-- START -->

<section id="start" class="page active">

  <div class="card hero">

    <span class="badge">🌿 Naturbeobachtung</span>

    <h2>Welche Tiere hast du gesehen?</h2>

    <p class="muted">
      Halte deine echten Tierbeobachtungen in freier Natur fest.
    </p>

    <button class="primary" onclick="openPage('tiere')">
      🐾 Tier auswählen
    </button>

  </div>

  <div class="grid">

    <div class="stat">
      <strong id="statSpecies">0</strong>
      Arten gesehen
    </div>

    <div class="stat">
      <strong id="statObservations">0</strong>
      Beobachtungen
    </div>

    <div class="stat">
      <strong id="statCountries">0</strong>
      Länder
    </div>

    <div class="stat">
      <strong id="statContinents">0</strong>
      Kontinente
    </div>

  </div>

  <div class="card">

    <h3>Zuletzt gesehen</h3>

    <div id="recent">
      <div class="empty">
        Noch keine Beobachtungen.
      </div>
    </div>

  </div>

</section>


<!-- TIERE -->

<section id="tiere" class="page">

  <h2>🐾 Tiere</h2>

  <input
    id="search"
    class="search"
    placeholder="🔎 Tier suchen..."
    oninput="renderAnimals()"
  >

  <div class="row" style="margin:10px 0">

    <button class="secondary" onclick="setFilter('Alle')">
      Alle
    </button>

    <button class="secondary" onclick="setFilter('Europa')">
      Europa
    </button>

    <button class="secondary" onclick="setFilter('Afrika')">
      Afrika
    </button>

    <button class="secondary" onclick="setFilter('Asien')">
      Asien
    </button>

    <button class="secondary" onclick="setFilter('Australien')">
      Australien
    </button>

  </div>

  <div id="animalList"></div>

</section>


<!-- BEOBACHTUNGEN -->

<section id="beobachtungen" class="page">

  <h2>📖 Meine Beobachtungen</h2>

  <div id="observationList"></div>

</section>


<!-- PROFIL -->

<section id="profil" class="page">

  <h2>👤 Mein Profil</h2>

  <div class="card hero">

    <h2>Dein Wildlife-Buch</h2>

    <p class="muted">
      Deine persönliche Statistik wächst mit jeder Beobachtung.
    </p>

  </div>

  <div class="grid">

    <div class="stat">
      <strong id="profileSpecies">0</strong>
      Arten
    </div>

    <div class="stat">
      <strong id="profileObservations">0</strong>
      Beobachtungen
    </div>

    <div class="stat">
      <strong id="profileCountries">0</strong>
      Länder
    </div>

    <div class="stat">
      <strong id="profileHabitats">0</strong>
      Lebensräume
    </div>

  </div>

</section>

</main>


<!-- NAVIGATION -->

<nav>

  <button class="active" data-page="start">
    <span class="icon">🏠</span>
    Start
  </button>

  <button data-page="tiere">
    <span class="icon">🐾</span>
    Tiere
  </button>

  <button data-page="beobachtungen">
    <span class="icon">📖</span>
    Beobachtungen
  </button>

  <button data-page="profil">
    <span class="icon">👤</span>
    Profil
  </button>

</nav>


<script>

const animals = [

  {
    id: "alpenschneehuhn",
    name: "Alpenschneehuhn",
    latin: "Lagopus muta",
    emoji: "🐦",
    continent: "Europa",
    family: "Fasanenartige",
    habitat: "Alpine Tundra & Felsregionen",
    rarity: "Selten",
    risk: "Nicht gefährdet"
  },

  {
    id: "elefant",
    name: "Afrikanischer Savannenelefant",
    latin: "Loxodonta africana",
    emoji: "🐘",
    continent: "Afrika",
    family: "Elefanten",
    habitat: "Savanne & Buschland",
    rarity: "Gelegentlich",
    risk: "Gefährdet"
  },

  {
    id: "giraffe",
    name: "Giraffe",
    latin: "Giraffa camelopardalis",
    emoji: "🦒",
    continent: "Afrika",
    family: "Giraffenartige",
    habitat: "Savanne & offene Wälder",
    rarity: "Gelegentlich",
    risk: "Gefährdet"
  },

  {
    id: "kaenguru",
    name: "Rotes Riesenkänguru",
    latin: "Osphranter rufus",
    emoji: "🦘",
    continent: "Australien",
    family: "Kängurus",
    habitat: "Trockene Ebenen & Buschland",
    rarity: "Häufig",
    risk: "Nicht gefährdet"
  },

  {
    id: "eisbaer",
    name: "Eisbär",
    latin: "Ursus maritimus",
    emoji: "🐻‍❄️",
    continent: "Arktis",
    family: "Bären",
    habitat: "Meereis & Küsten",
    rarity: "Sehr selten",
    risk: "Gefährdet"
  },

  {
    id: "rothirsch",
    name: "Rothirsch",
    latin: "Cervus elaphus",
    emoji: "🦌",
    continent: "Europa",
    family: "Hirsche",
    habitat: "Wälder, Wiesen & Berge",
    rarity: "Häufig",
    risk: "Nicht gefährdet"
  },

  {
    id: "seeadler",
    name: "Seeadler",
    latin: "Haliaeetus albicilla",
    emoji: "🦅",
    continent: "Europa",
    family: "Habichtartige",
    habitat: "Küsten, Seen & Flüsse",
    rarity: "Gelegentlich",
    risk: "Nicht gefährdet"
  },

  {
    id: "komodowaran",
    name: "Komodowaran",
    latin: "Varanus komodoensis",
    emoji: "🦎",
    continent: "Asien",
    family: "Warane",
    habitat: "Trockene Wälder & Savannen",
    rarity: "Sehr selten",
    risk: "Gefährdet"
  }

];


let observations =
  JSON.parse(
    localStorage.getItem("wildlifeObservations") || "[]"
  );

let currentFilter = "Alle";

let currentPhoto = "";


/* NAVIGATION */

function openPage(page) {

  document
    .querySelectorAll(".page")
    .forEach(p => p.classList.remove("active"));

  document
    .getElementById(page)
    .classList.add("active");

  document
    .querySelectorAll("nav button")
    .forEach(button => {

      button.classList.toggle(
        "active",
        button.dataset.page === page
      );

    });

  if (page === "tiere") {
    renderAnimals();
  }

  if (page === "beobachtungen") {
    renderObservations();
  }

  updateStats();

  window.scrollTo(0, 0);
}


/* NAV BUTTONS */

document
  .querySelectorAll("nav button")
  .forEach(button => {

    button.addEventListener(
      "click",
      () => openPage(button.dataset.page)
    );

  });


/* FILTER */

function setFilter(filter) {

  currentFilter = filter;

  renderAnimals();

}


/* TIERLISTE */

function renderAnimals() {

  const search =
    document
      .getElementById("search")
      .value
      .toLowerCase();

  const list =
    animals.filter(animal => {

      const matchesFilter =
        currentFilter === "Alle" ||
        animal.continent === currentFilter;

      const text =
        (
          animal.name +
          " " +
          animal.latin +
          " " +
          animal.family +
          " " +
          animal.habitat
        ).toLowerCase();

      return matchesFilter && text.includes(search);

    });


  document.getElementById("animalList").innerHTML =
    list.map(animal => `

      <div
        class="card species"
        onclick="showAnimal('${animal.id}')"
      >

        <div class="animal">
          ${animal.emoji}
        </div>

        <div>

          <strong>${animal.name}</strong>

          <div class="muted">
            <i>${animal.latin}</i>
          </div>

          <span class="badge">
            ${animal.continent}
          </span>

          <span class="badge">
            ${animal.habitat}
          </span>

        </div>

      </div>

    `).join("");


  if (list.length === 0) {

    document.getElementById("animalList").innerHTML =
      `
      <div class="empty">
        Keine passende Tierart gefunden.
      </div>
      `;

  }

}


/* TIERDETAIL */

function showAnimal(id) {

  const animal =
    animals.find(a => a.id === id);

  const ownObservations =
    observations.filter(o => o.animalId === id);


  document.getElementById("animalList").innerHTML = `

    <div class="card">

      <button
        class="secondary"
        onclick="renderAnimals()"
      >
        ← Zurück
      </button>


      <div
        class="species"
        style="margin-top:15px"
      >

        <div class="animal">
          ${animal.emoji}
        </div>

        <div>

          <h2>${animal.name}</h2>

          <div class="muted">
            <i>${animal.latin}</i>
          </div>

        </div>

      </div>


      <p>
        Steckbrief dieser Tierart mit Informationen
        zu Familie, Lebensraum und Gefährdungsstatus.
      </p>


      <div class="row">

        <span class="badge">
          Familie: ${animal.family}
        </span>

        <span class="badge">
          ${animal.risk}
        </span>

        <span class="badge">
          ${animal.rarity}
        </span>

      </div>


      <h3>🌍 Lebensraum</h3>

      <div class="map">

        <div class="map-land"></div>

        <div class="map-text">
          🗺️ ${animal.continent}
        </div>

      </div>


      <p class="muted">
        Lebensraum: ${animal.habitat}
      </p>


      <hr>


      <h3>
        ➕ Beobachtung eintragen
      </h3>


      <form
        onsubmit="saveObservation(event, '${animal.id}')"
      >

        <label>
          Datum & Uhrzeit
        </label>

        <input
          name="date"
          type="datetime-local"
          required
        >


        <label>
          Ort / Land
        </label>

        <input
          name="place"
          placeholder="z. B. Berchtesgaden, Deutschland"
        >


        <label>
          Genauer Standort
        </label>

        <input
          name="location"
          placeholder="GPS oder Beschreibung"
        >


        <label>
          Anzahl der Tiere
        </label>

        <input
          name="count"
          type="number"
          min="1"
          value="1"
        >


        <label>
          Wetter
        </label>

        <select name="weather">

          <option>Sonnig</option>
          <option>Bewölkt</option>
          <option>Regen</option>
          <option>Schnee</option>
          <option>Nebel</option>
          <option>Unbekannt</option>

        </select>


        <label>
          Tageszeit
        </label>

        <select name="time">

          <option>Morgen</option>
          <option>Vormittag</option>
          <option>Mittag</option>
          <option>Nachmittag</option>
          <option>Abend</option>
          <option>Nacht</option>

        </select>


        <label>
          Persönliche Bewertung
        </label>

        <input
          name="rating"
          type="range"
          min="1"
          max="5"
          value="5"
        >


        <label>
          Notizen
        </label>

        <textarea
          name="notes"
          placeholder="Verhalten, Situation, Besonderheiten..."
        ></textarea>


        <label>
          Foto
        </label>

        <input
          type="file"
          accept="image/*"
          capture="environment"
          onchange="readPhoto(this)"
        >


        <div id="photoPreview"></div>


        <button
          class="primary"
          style="margin-top:14px"
        >
          💾 Beobachtung speichern
        </button>

      </form>


      ${
        ownObservations.length
        ?
        `
        <hr>

        <h3>
          Deine bisherigen Sichtungen
        </h3>

        ${
          ownObservations
            .slice()
            .reverse()
            .map(o => `

              <div class="observation">

                <strong>
                  ${new Date(o.date).toLocaleString("de-DE")}
                </strong>

                <br>

                ${o.place || "Ort unbekannt"}

                · ${o.count} Tier(e)

                <br>

                <span class="muted">
                  ${o.notes || ""}
                </span>

              </div>

            `)
            .join("")
        }

        `
        :
        ""
      }

    </div>

  `;

}


/* FOTO */

function readPhoto(input) {

  if (!input.files[0]) return;

  const reader =
    new FileReader();

  reader.onload =
    function(event) {

      currentPhoto =
        event.target.result;

      document.getElementById(
        "photoPreview"
      ).innerHTML =
        `
        <img
          class="photo"
          src="${currentPhoto}"
        >
        `;

    };

  reader.readAsDataURL(input.files[0]);

}


/* BEOBACHTUNG SPEICHERN */

function saveObservation(event, animalId) {

  event.preventDefault();

  const form =
    new FormData(event.target);

  const observation =
    Object.fromEntries(form.entries());

  observation.animalId =
    animalId;

  observation.count =
    Number(observation.count || 1);

  observation.photo =
    currentPhoto;


  observations.push(
    observation
  );


  localStorage.setItem(
    "wildlifeObservations",
    JSON.stringify(observations)
  );


  currentPhoto = "";


  alert(
    "Beobachtung gespeichert! 🐾"
  );


  openPage(
    "beobachtungen"
  );

}


/* BEOBACHTUNGEN */

function renderObservations() {

  const container =
    document.getElementById(
      "observationList"
    );


  if (observations.length === 0) {

    container.innerHTML = `

      <div class="card empty">

        Noch keine Beobachtungen.

        <br><br>

        <button
          class="primary"
          onclick="openPage('tiere')"
        >
          Erste Beobachtung eintragen
        </button>

      </div>

    `;

    return;

  }


  container.innerHTML =
    observations
      .slice()
      .reverse()
      .map((observation, reverseIndex) => {

        const animal =
          animals.find(
            a =>
              a.id ===
              observation.animalId
          );


        return `

          <div class="card">

            <div class="species">

              <div class="animal">
                ${animal.emoji}
              </div>

              <div>

                <strong>
                  ${animal.name}
                </strong>

                <div class="muted">

                  ${new Date(
                    observation.date
                  ).toLocaleString("de-DE")}

                </div>

                <div>

                  ${
                    observation.place ||
                    "Ort unbekannt"
                  }

                  ·

                  ${observation.count}
                  Tier(e)

                </div>

              </div>

            </div>


            ${
              observation.photo
              ?
              `
              <img
                class="photo"
                src="${observation.photo}"
              >
              `
              :
              ""
            }


            <p class="muted">

              ${
                observation.notes ||
                "Keine Notizen"
              }

            </p>

          </div>

        `;

      })
      .join("");

}


/* STATISTIK */

function updateStats() {

  const uniqueSpecies =
    new Set(
      observations.map(
        o => o.animalId
      )
    );


  const countries =
    new Set(
      observations
        .map(
          o =>
            (o.place || "")
              .split(",")
              .pop()
              .trim()
        )
        .filter(Boolean)
    );


  const continents =
    new Set(
      [...uniqueSpecies]
        .map(
          id =>
            animals.find(
              a => a.id === id
            )?.continent
        )
        .filter(Boolean)
    );


  document.getElementById(
    "statSpecies"
  ).textContent =
    uniqueSpecies.size;


  document.getElementById(
    "statObservations"
  ).textContent =
    observations.length;


  document.getElementById(
    "statCountries"
  ).textContent =
    countries.size;


  document.getElementById(
    "statContinents"
  ).textContent =
    continents.size;


  document.getElementById(
    "profileSpecies"
  ).textContent =
    uniqueSpecies.size;


  document.getElementById(
    "profileObservations"
  ).textContent =
    observations.length;


  document.getElementById(
    "profileCountries"
  ).textContent =
    countries.size;


  const habitats =
    new Set(
      [...uniqueSpecies]
        .map(
          id =>
            animals.find(
              a => a.id === id
            )?.habitat
        )
        .filter(Boolean)
    );


  document.getElementById(
    "profileHabitats"
  ).textContent =
    habitats.size;


  const recent =
    document.getElementById(
      "recent"
    );


  if (observations.length === 0) {

    recent.innerHTML =
      `
      <div class="empty">
        Noch keine Beobachtungen.
      </div>
      `;

    return;

  }


  recent.innerHTML =
    observations
      .slice(-4)
      .reverse()
      .map(o => {

        const animal =
          animals.find(
            a =>
              a.id ===
              o.animalId
          );


        return `

          <div class="observation">

            <strong>
              ${animal.emoji}
              ${animal.name}
            </strong>

            <br>

            <span class="muted">

              ${
                o.place ||
                "Ort unbekannt"
              }

              ·

              ${new Date(
                o.date
              ).toLocaleDateString("de-DE")}

            </span>

          </div>

        `;

      })
      .join("");

}


/* START */

renderAnimals();

updateStats();

</script>

</body>
</html>