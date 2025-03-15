# CROSS Portfolio – Product Requirements Document (PRD)

## 1. Übersicht
• **Kurze Zusammenfassung der Idee**: Eine moderne, minimalistische Portfolio-Website für den Underground Techno-Produzenten CROSS aus Köln, die sein musikalisches Werk präsentiert und seine Ästhetik widerspiegelt.
• **Ziele und gewünschte Ergebnisse**: Präsentation von Musik-Releases, Veranstaltungsterminen und Blogartikeln in einem einheitlichen, hochwertigen Design; Förderung der künstlerischen Identität; Verbesserung der Online-Präsenz.
• **Zielgruppe / Nutzerprofil**: Elektronische Musikfans, insbesondere Techno-Enthusiasten; Club-Besucher in Köln und Umgebung; andere DJs und Produzenten; Label-Vertreter.

## 2. Detaillierte Funktionsbeschreibung

1. **Hero-Bereich mit SoundCloud-Player**
   - **Beschreibung**: Großflächiger Bereich mit prominentem SoundCloud-Player zur Wiedergabe der neuesten Tracks/Playlists
   - **User Story**: "Als Fan möchte ich sofort Cross' Musik hören können, ohne die Seite verlassen zu müssen."
   - **Eingaben/Ausgaben**: Automatisches Laden des Players mit vorausgewählter Playlist; Play/Pause/Skip-Funktionalität
   - **Sonderfälle**: Fallback-Anzeige, falls SoundCloud nicht geladen werden kann

2. **Release-Showcase**
   - **Beschreibung**: Grid-Layout mit 8 großen Karten, die jeweils ein Album/Release-Cover darstellen
   - **User Story**: "Als Musik-Enthusiast möchte ich einen visuellen Überblick über Cross' Veröffentlichungen haben."
   - **Eingaben/Ausgaben**: Klick auf Karte führt zu Detailansicht oder Streaming-Links
   - **Sonderfälle**: Hover-Effekte zeigen zusätzliche Informationen wie Titel und Release-Jahr

3. **Animierte Event-Ankündigungen**
   - **Beschreibung**: Bei Scroll-Down erscheint eine animierte "Timetable" mit kommenden Auftritten
   - **User Story**: "Als lokaler Fan möchte ich wissen, wann und wo ich Cross live erleben kann."
   - **Eingaben/Ausgaben**: Anklickbare Events führen zu Event-Details oder Ticket-Links
   - **Sonderfälle**: Visuelle Hervorhebung besonderer Events; Anzeige "Keine aktuellen Events" falls nötig

4. **Blog-System mit CMS**
   - **Beschreibung**: Einfach zu pflegendes CMS für Club-Erfahrungsberichte und andere Inhalte
   - **User Story**: "Als Besucher möchte ich authentische Einblicke in die Kölner Clubszene erhalten."
   - **Eingaben/Ausgaben**: Kategorisierte Beiträge mit Bildern, Tags und Kommentarfunktion
   - **Sonderfälle**: Möglichkeit, Beiträge zu pinnen oder als Feature hervorzuheben

5. **Scroll-Animationen**
   - **Beschreibung**: Subtile aber impaktvolle Animationen beim Scrollen, die den Underground-Charakter vermitteln
   - **User Story**: "Als Besucher möchte ich eine visuell ansprechende und immersive Erfahrung haben."
   - **Eingaben/Ausgaben**: Reaktion auf Scrollgeschwindigkeit und -richtung
   - **Sonderfälle**: Deaktivierungsoption für Nutzer mit Präferenz für reduzierte Bewegung

## 3. Technischer Überblick
• **Technologie-Stack & Programmiersprache(n)**: JavaScript/TypeScript
• **Architektur**: Astro als Framework mit React-Komponenten; Headless CMS für Blog-Inhalte
• **Frontend-Framework / UI-Library**: Astro mit React-Komponenten, GSAP für Animationen, TailwindCSS für Styling
• **Backend-System / Datenbanksystem**: Sanity.io als Headless CMS für Blog-Inhalte und Event-Daten

## 4. Dateistruktur & Modulare Aufteilung
```
cross-portfolio/
├── public/
│   ├── fonts/
│   ├── images/
│   └── favicon.ico
├── src/
│   ├── components/
│   │   ├── common/
│   │   ├── layout/
│   │   ├── releases/
│   │   ├── events/
│   │   └── blog/
│   ├── layouts/
│   ├── pages/
│   │   ├── index.astro
│   │   ├── about.astro
│   │   ├── releases.astro
│   │   ├── blog.astro
│   │   └── art.astro
│   ├── styles/
│   ├── utils/
│   └── sanity/
├── astro.config.mjs
├── tailwind.config.cjs
├── package.json
└── README.md
```

• **public/**: Statische Assets wie Bilder, Fonts und Favicon
• **src/components/**: Wiederverwendbare UI-Komponenten, nach Funktionalität gruppiert
• **src/pages/**: Hauptseiten der Website im Astro-Format
• **src/sanity/**: Konfiguration und Schemas für das Sanity CMS

## 5. Abhängigkeiten & Bibliotheken
• **Astro**: Framework für schnelle Websites und optimiertes Content-Rendering (https://astro.build/)
• **React**: Für interaktive Komponenten (https://reactjs.org/)
• **TailwindCSS**: Utility-First CSS-Framework für konsistentes Styling (https://tailwindcss.com/)
• **GSAP**: Animation-Library für hochwertige Scroll-Animationen (https://greensock.com/gsap/)
• **Sanity.io**: Headless CMS für Blog und dynamische Inhalte (https://www.sanity.io/)
• **SoundCloud API**: Einbindung des SoundCloud-Players und Zugriff auf Tracks (https://developers.soundcloud.com/)
• **Framer Motion**: Für reaktive und flüssige UI-Animationen (https://www.framer.com/motion/)

## 6. Mögliche APIs & Integrationen
• **SoundCloud API**: Einbindung von Playlists und Tracks
• **Spotify API**: Alternative Musikwiedergabe und Cross-Linking
• **Beatport API**: Integration von Release-Daten und Verlinkung zum Kauf
• **Instagram API**: Einbindung des Instagram-Feeds für aktuelle Updates
• **Resident Advisor API**: Eventdaten und Ticket-Links

## 7. Backend-Logik (falls vorhanden)
• **Endpoints**: 
  - `/api/blog`: CRUD für Blog-Artikel
  - `/api/events`: Verwaltung von Event-Terminen
  - `/api/releases`: Release-Daten und Metainformationen

• **Datenbank-Schema**:
  - **Blog-Post**: Titel, Inhalt, Autor, Datum, Kategorie, Tags, Bilder
  - **Event**: Datum, Ort, Name, Beschreibung, Flyer, Ticket-Link
  - **Release**: Titel, Cover, Release-Datum, Label, Tracks, Streaming-Links

• **Authentifizierung / Autorisierung**: Admin-Login für CMS über Sanity mit OAuth

## 8. Ablauf / Entwicklungs-Workflow
• **Setup**: 
  ```
  git clone [repository]
  npm install
  cp .env.example .env # Konfiguration der Umgebungsvariablen
  ```

• **Dev-Server starten**: 
  ```
  npm run dev
  ```

• **Deployment-Prozess**: 
  - CI/CD-Pipeline über GitHub Actions
  - Automatisches Deployment auf Vercel bei Push auf main/master Branch
  - Vorschau-Deployments für Pull Requests

## 9. Risiken & Offene Punkte
• **Potenzielle Engpässe**: Performance der animierten Elemente auf älteren mobilen Geräten
• **Noch nicht geklärte technische Fragen**: 
  - Optimale Integration von SoundCloud für minimale Ladezeiten
  - Skalierung der Bilddateien für unterschiedliche Geräte
• **Zukünftige Features/Erweiterungen**:
  - Merchandise-Shop-Integration
  - Direkter Download von Promo-Material für DJs
  - Newsletter-Funktion

## 10. Anhang
• **Code-Beispiele / Snippets**:
  ```jsx
  // Beispiel für eine Release-Karte mit Animation
  const ReleaseCard = ({ cover, title, label, year }) => {
    return (
      <motion.div 
        className="release-card bg-[#3a3f43] rounded-lg overflow-hidden"
        whileHover={{ 
          scale: 1.03,
          boxShadow: "0px 10px 30px rgba(0, 0, 0, 0.5)"
        }}
        transition={{ duration: 0.3 }}
      >
        <img src={cover} alt={title} className="w-full" />
        <div className="p-4">
          <h3 className="text-[#e5e1ea] text-xl font-bold">{title}</h3>
          <p className="text-[#62717b]">{label} · {year}</p>
        </div>
      </motion.div>
    );
  };
  ```

• **Projekt-Roadmap / Meilensteine**:
  1. Design-Phase: Mockups und Prototypen (1 Woche)
  2. Core Framework Setup und Basis-Layout (1 Woche)
  3. Komponenten-Entwicklung (Hero, Player, Cards) (2 Wochen)
  4. Animationen und Interaktionen (1 Woche)
  5. CMS-Integration und Blog-Funktionen (1 Woche)
  6. Content-Erstellung und Einfügung (1 Woche)
  7. Testing und Optimierung (1 Woche)
  8. Launch (1 Tag)

• **Ansprechpartner / Verantwortliche**:
  - Projektleitung: [Ihr Name]
  - Design: [Designer]
  - Entwicklung: [Entwickler]
  - Content: Cross (Musik/Bilder) und [Content-Creator] (Blog-Artikel)
