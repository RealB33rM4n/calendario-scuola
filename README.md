[readme-school-system.md](https://github.com/user-attachments/files/22681814/readme-school-system.md)
# 📚 Sistema Gestione Aule e Calendari Scuola

Sistema completo per la gestione delle aule scolastiche e la creazione automatica dei calendari delle lezioni per gli insegnanti.

## 🎯 Caratteristiche Principali

- ✅ Gestione illimitata di insegnanti e aule
- ✅ Calendario sincronizzato con date reali
- ✅ 3 visualizzazioni temporali (Settimana, Mese, Anno)
- ✅ Calendario mensile completo in stile griglia
- ✅ Controllo automatico conflitti orari
- ✅ Colori distintivi per materia
- ✅ Export PDF e Excel per insegnante
- ✅ Modifica e eliminazione lezioni
- ✅ Gestione completa aule
- ✅ Statistiche utilizzo aule
- ✅ Interfaccia responsive

---

## 📋 Indice

1. [Gestione Insegnanti](#-gestione-insegnanti)
2. [Gestione Aule](#-gestione-aule)
3. [Gestione Lezioni](#-gestione-lezioni)
4. [Calendario](#-calendario)
5. [Visualizzazioni](#-visualizzazioni)
6. [Export Dati](#-export-dati)
7. [Installazione](#-installazione)
8. [Configurazione](#%EF%B8%8F-configurazione)

---

## 👨‍🏫 Gestione Insegnanti

### Aggiungi Insegnante
1. Vai alla tab **"Insegnanti"**
2. Clicca **"+ Aggiungi Insegnante"**
3. Compila i campi:
   - Nome completo
   - Email
   - Materia principale
4. Clicca **"Salva"**

### Elimina Insegnante
- Clicca l'icona del **cestino** 🗑️
- Conferma l'eliminazione
- ⚠️ **Attenzione**: Tutte le lezioni dell'insegnante verranno eliminate

### Visualizza Statistiche
Ogni insegnante mostra:
- Nome e materia
- Email di contatto
- Numero totale lezioni programmate

---

## 🏫 Gestione Aule

### Caratteristiche Aule
Ogni aula ha:
- **Nome** (es. "Informatica 20", "Lab Chimica")
- **Numero posti** (1-100 studenti)
- **Tipologia** (Informatica, Parrucchieri, Didattica, Laboratorio, Aula Magna)
- **Proiettore** (SI/NO)

### Aggiungi Aula
1. Vai alla tab **"Aule"**
2. Clicca **"+ Aggiungi Aula"**
3. Compila:
   - Nome aula
   - Numero posti (1-100)
   - Tipologia dal menu a tendina
   - ☑️ Spunta "Proiettore disponibile" se presente
4. Clicca **"Salva"**

### Modifica Aula
1. Clicca il pulsante **"Modifica"** (blu) sulla card dell'aula
2. Modifica i campi desiderati:
   - Nome
   - Capacità
   - Tipologia
   - Presenza proiettore
3. Clicca **"Aggiorna"**

### Elimina Aula
1. Clicca il pulsante **"Elimina"** (rosso)
2. Conferma l'eliminazione
3. ⚠️ **Protezione**: Non puoi eliminare aule con lezioni programmate

### Visualizzazione Aule
Ogni card mostra:
- Nome e tipologia dell'aula
- Badge verde "📽️ Proiettore" se disponibile
- Numero posti (in evidenza)
- **Statistiche utilizzo**:
  - Lezioni programmate
  - Ore totali occupate
  - Utilizzo medio per lezione

**Contatore totale**: Visualizza sempre il numero totale di aule disponibili.

---

## 📅 Gestione Lezioni

### Aggiungi Lezione
1. Vai alla tab **"Dashboard"**
2. Clicca **"+ Aggiungi Lezione"**
3. Seleziona:
   - **Insegnante** (menu a tendina)
   - **Aula** (menu a tendina con capacità)
   - **Data** (selettore calendario)
   - **Ora inizio** (8:00-18:00)
   - **Durata** (1-8 ore consecutive)
   - **Materia/Corso** (testo libero)
4. Clicca **"Salva"**

### Modifica Lezione
**Metodo 1 - Dalla lista:**
1. Scorri fino alla sezione "Gestione Lezioni"
2. Clicca l'icona **matita** 📝 (blu) sulla lezione
3. Modifica i campi desiderati
4. Clicca **"Aggiorna"**

**Metodo 2 - Dal calendario mensile:**
1. Seleziona vista "Mese"
2. Clicca direttamente sulla lezione nel calendario
3. Modifica e clicca **"Aggiorna"**

**Metodo 3 - Dalla vista anno:**
1. Seleziona vista "Anno"
2. Clicca l'icona matita sulla lezione
3. Modifica e salva

### Elimina Lezione
1. Clicca l'icona **cestino** 🗑️ (rosso)
2. Conferma l'eliminazione

### Controllo Conflitti
Il sistema verifica automaticamente:
- ✅ L'insegnante non sia già impegnato nello stesso orario
- ✅ L'aula non sia già occupata nello stesso orario
- ⚠️ In caso di conflitto, mostra un messaggio di avviso

---

## 🗓️ Calendario

### Sincronizzazione Date Reali
- Il calendario è sincronizzato con il **calendario solare**
- Mostra sempre la **data corrente** nell'intestazione
- Le lezioni sono associate a **date specifiche** (formato YYYY-MM-DD)

### Navigazione Temporale
- **← →** Frecce per navigare tra periodi
- **"Oggi"** Pulsante per tornare immediatamente alla data corrente
- Il sistema calcola automaticamente i giorni della settimana

### Legenda Materie
Colori distintivi per ogni materia:
- 🔵 **Programmazione** → Blu
- 🟣 **Database** → Viola
- 🩷 **Taglio Base** → Rosa
- 🌹 **Colorazione** → Rosa scuro
- 🔷 **Informatica** → Ciano
- 🟡 **Parrucchiere** → Ambra
- ⚪ **Altre materie** → Grigio (default)

---

## 👁️ Visualizzazioni

### Vista Settimana
**Caratteristiche:**
- Tabella oraria 8:00-18:00
- 6 giorni (Lunedì-Sabato)
- Ogni cella mostra: materia, insegnante, aula, durata
- Le lezioni occupano più righe in base alla durata
- Mostra le date esatte (es. "Lunedì 6/10")

**Ideale per:** Pianificazione settimanale dettagliata

### Vista Mese - Calendario Completo
**Caratteristiche:**
- Griglia 7x6 stile calendario tradizionale
- Giorni della settimana (Lun-Dom)
- Giorni del mese precedente/successivo in grigio
- **Giorno corrente evidenziato** con bordo blu
- Lezioni visualizzate direttamente nei giorni
- **Click sulle lezioni** per modificarle

**Layout esempio:**
```
Lun  Mar  Mer  Gio  Ven  Sab  Dom
[28] [29] [30] [1]  [2]  [3]  [4]
              09:00      11:00
              Prog       Taglio
[5]  [6]  [7]  [8]  [9]  [10] [11]
```

**Ideale per:** Visione d'insieme mensile, pianificazione a lungo termine

### Vista Anno
**Caratteristiche:**
- Lista cronologica di tutte le lezioni dell'anno
- Ordinate per data
- Ogni lezione mostra: data completa, insegnante, aula, orario
- Icone per modificare o eliminare
- Contatore totale lezioni

**Ideale per:** Analisi annuale, report completi

### Calendari Individuali Insegnanti
Ogni insegnante ha un calendario personale che mostra:
- Vista settimanale corrente
- Solo le proprie lezioni
- Colori per materia
- Pulsanti export PDF e Excel

---

## 📤 Export Dati

### Export PDF
1. Trova il calendario dell'insegnante
2. Clicca il pulsante **"PDF"** (rosso) 📄
3. Il file viene scaricato automaticamente

**Contenuto file PDF:**
```
CALENDARIO LEZIONI - Prof. Rossi Mario
Materia: Informatica
Email: rossi@scuola.it
========================================

LUNEDÌ
  09:00 - 11:00 | Programmazione
  Aula: Informatica 20 (20 posti)

MARTEDÌ
  14:00 - 16:00 | Database
  Aula: Informatica 28 (28 posti)
```

### Export Excel (CSV)
1. Trova il calendario dell'insegnante
2. Clicca il pulsante **"Excel"** (verde) 📊
3. Il file CSV viene scaricato

**Formato CSV:**
```csv
Data,Giorno,Ora Inizio,Ora Fine,Materia,Aula,Posti
2025-10-06,Lunedì,09:00,11:00,Programmazione,Informatica 20,20
2025-10-07,Martedì,14:00,16:00,Database,Informatica 28,28
```

**Apribile con:** Microsoft Excel, Google Sheets, LibreOffice Calc

---

## 🚀 Installazione

### Prerequisiti
- Nessuno! È un'applicazione web standalone
- Funziona su qualsiasi browser moderno (Chrome, Firefox, Safari, Edge)

### Opzione 1: Uso Locale
1. Scarica il file `index.html`
2. Aprilo con un browser web
3. Inizia a usare l'applicazione

⚠️ **Nota**: I dati non vengono salvati tra una sessione e l'altra

### Opzione 2: GitHub Pages (Consigliato)
1. Crea un repository su GitHub
2. Carica il file `index.html`
3. Vai su **Settings** → **Pages**
4. Seleziona **Source: main branch**
5. Clicca **Save**
6. Attendi 1-2 minuti
7. Visita: `https://tuonome.github.io/nome-repository`

### Opzione 3: Hosting Web
1. Acquista uno spazio web (5-10€/mese)
2. Carica il file `index.html` via FTP
3. Accedi tramite il tuo dominio

---

## ⚙️ Configurazione

### Aule Predefinite
Il sistema include 4 aule di esempio:
- Informatica 20 (20 posti, Informatica, con proiettore)
- Informatica 28 (28 posti, Informatica, con proiettore)
- Parrucchieri/Estetiste (25 posti, Parrucchieri, senza proiettore)
- Aula Piccola (8 posti, Didattica, senza proiettore)

**Puoi:**
- Modificare queste aule
- Eliminare quelle non necessarie
- Aggiungere nuove aule

### Insegnanti Predefiniti
Il sistema include 2 insegnanti di esempio:
- Prof. Rossi Mario (Informatica)
- Prof.ssa Bianchi Laura (Parrucchiere)

**Puoi:**
- Eliminare gli insegnanti di esempio
- Aggiungere i tuoi insegnanti
- Gestire fino a 10+ insegnanti (illimitato)

### Orari
**Orario standard:**
- Inizio: 8:00
- Fine: 18:00 (ultimo slot 18:00)
- Intervalli: 1 ora

**Durata lezioni:**
- Minimo: 1 ora
- Massimo: 8 ore consecutive

### Tipologie Aule Disponibili
- Informatica
- Parrucchieri
- Didattica
- Laboratorio
- Aula Magna

---

## 📱 Compatibilità

### Browser Supportati
- ✅ Google Chrome (consigliato)
- ✅ Mozilla Firefox
- ✅ Microsoft Edge
- ✅ Safari
- ✅ Opera

### Dispositivi
- 💻 Desktop/Laptop (esperienza ottimale)
- 📱 Tablet (responsive)
- 📱 Smartphone (responsive con limitazioni)

---

## 🎨 Interfaccia

### Layout Principale
```
┌─────────────────────────────────────┐
│  Sistema Gestione Aule e Calendari │
│  Data corrente: Venerdì, 3 Ottobre  │
└─────────────────────────────────────┘

┌───────────┬────────────┬──────────┐
│ Dashboard │ Insegnanti │   Aule   │
└───────────┴────────────┴──────────┘

┌─────────────────────────────────────┐
│      [Contenuto della sezione]      │
└─────────────────────────────────────┘
```

### Colori Interfaccia
- **Blu** (#2563EB): Azioni primarie, tab attive
- **Verde** (#16A34A): Salvataggio, conferma
- **Rosso** (#DC2626): Eliminazione, alert
- **Grigio**: Elementi secondari
- **Materie**: Colori distintivi per ogni materia

---

## 📊 Statistiche e Report

### Per Aula
- Numero totale lezioni programmate
- Ore totali di occupazione
- Utilizzo medio per lezione
- Tipologia e capacità
- Presenza proiettore

### Per Insegnante
- Numero totale lezioni
- Calendario settimanale
- Export personalizzati

### Generali
- Totale aule disponibili
- Totale insegnanti
- Totale lezioni programmate (per periodo)

---

## ⚠️ Limitazioni Attuali

### Salvataggio Dati
- **I dati NON vengono salvati** quando chiudi il browser
- Le modifiche sono temporanee (solo in memoria)
- Ad ogni refresh, i dati tornano ai valori predefiniti

### Soluzioni Future
Per salvare i dati permanentemente, sarà necessario:
1. Implementare un database (es. Firebase, MySQL)
2. Aggiungere un sistema di login utenti
3. Sviluppare un backend server-side

---

## 🔒 Sicurezza

### Controlli Implementati
- ✅ Validazione campi obbligatori
- ✅ Controllo conflitti orari
- ✅ Protezione eliminazione aule con lezioni
- ✅ Conferma prima di eliminare elementi
- ✅ Limiti su capacità aule (1-100)
- ✅ Limiti su durata lezioni (1-8 ore)

---

## 🐛 Risoluzione Problemi

### La pagina non si carica
- Controlla di avere una connessione internet (per caricare le librerie)
- Prova a ricaricare la pagina (Ctrl+F5 o Cmd+Shift+R)
- Prova un altro browser

### Non vedo le modifiche
- Ricorda che i dati non vengono salvati permanentemente
- Ad ogni refresh torni ai dati iniziali
- Per salvare, serve un database

### Il calendario non mostra la data corrente
- Controlla le impostazioni data/ora del tuo computer
- Il sistema usa la data di sistema

### Export non funziona
- Verifica che il browser permetta i download
- Controlla le impostazioni popup/blocco download
- Alcuni browser mobile hanno limitazioni

---

## 📝 Note Tecniche

### Tecnologie Utilizzate
- **React 18.2.0**: Framework JavaScript
- **Tailwind CSS**: Styling responsive
- **Babel**: Transpiler JavaScript
- **HTML5**: Struttura
- **JavaScript ES6+**: Logica applicazione

### Librerie Esterne
Tutte caricate da CDN:
- React & ReactDOM (CDN Cloudflare)
- Babel Standalone (CDN Cloudflare)
- Tailwind CSS (CDN ufficiale)

### Struttura File
```
index.html
├── <head>
│   ├── Meta tags
│   ├── Title
│   ├── Librerie CDN
│   └── Stili custom
├── <body>
│   ├── <div id="root">
│   └── <script type="text/babel">
│       ├── Componenti React
│       ├── State Management
│       ├── Funzioni logiche
│       └── Render App
└── </html>
```

---

## 📞 Supporto

Per domande, problemi o suggerimenti, puoi:
- Aprire una Issue su GitHub
- Contattare l'amministratore del sistema
- Consultare questo README

---

## 🎓 Casi d'Uso

### Scuola di Formazione Professionale
Gestisci corsi di:
- Informatica
- Parrucchiere ed Estetica
- Altre specializzazioni

### Istituto Tecnico
- Laboratori informatica
- Aule didattiche
- Laboratori tecnici

### Centro di Formazione
- Corsi brevi
- Workshop
- Lezioni intensive

---

## 🔮 Sviluppi Futuri (Roadmap)

### In Programma
- [ ] Salvataggio permanente dati (database)
- [ ] Sistema login utenti
- [ ] Permessi differenziati (admin/docente)
- [ ] Notifiche via email
- [ ] Calendario Google sincronizzato
- [ ] App mobile nativa
- [ ] Registro presenze studenti
- [ ] Gestione assenze docenti
- [ ] Backup automatico
- [ ] Temi colore personalizzabili

---

## 📜 Licenza

Questo software è fornito "così com'è", senza garanzie di alcun tipo.
Libero utilizzo per scopi educativi e formativi.

---

## 🙏 Crediti

Sviluppato con ❤️ per semplificare la gestione scolastica.

---

## 📚 Guida Rapida

### Setup in 3 Minuti
1. Scarica `index.html`
2. Apri con browser
3. Inizia ad aggiungere insegnanti e aule!

### Primo Utilizzo
1. **Elimina** gli insegnanti di esempio
2. **Aggiungi** i tuoi insegnanti
3. **Modifica** le aule esistenti o aggiungine di nuove
4. **Crea** le prime lezioni
5. **Visualizza** il calendario
6. **Esporta** i calendari individuali

---

## 📖 FAQ

**Q: I dati vengono salvati?**  
A: No, al momento i dati sono temporanei. Ad ogni refresh si resettano.

**Q: Posso usarlo offline?**  
A: No, richiede connessione internet per caricare le librerie.

**Q: Quanti insegnanti posso gestire?**  
A: Illimitati! Il sistema scala automaticamente.

**Q: Posso cambiare i colori delle materie?**  
A: Attualmente no, ma è previsto in futuri aggiornamenti.

**Q: Funziona su smartphone?**  
A: Sì, ma l'esperienza desktop è migliore per l'editing.

**Q: Posso stampare i calendari?**  
A: Sì, usa la funzione stampa del browser o esporta in PDF.

**Q: Come aggiungo più di 8 ore consecutive?**  
A: Attualmente il massimo è 8 ore. Per lezioni più lunghe, crea lezioni separate.

---

**Versione:** 1.0  
**Ultimo aggiornamento:** Ottobre 2025  
**Stato:** Stabile e pronto all'uso ✅
