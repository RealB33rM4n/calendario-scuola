# 🧪 GUIDA TEST - Sistema Calendarizzazione v3.0.3

## Test di Verifica Bug Fix

---

## ✅ TEST 1: VERIFICA FIX DOPPIA CALENDARIZZAZIONE

### Obiettivo
Verificare che nessun corso possa essere calendarizzato contemporaneamente in due aule diverse nella stessa fascia oraria.

### Prerequisiti
- Sistema v3.0.3 attivo
- Almeno 2 aule disponibili con capienza adeguata
- Database pulito o calendario azzerato

### Procedura

#### STEP 1: Configurazione Ambiente
```
1. Accedere alla sezione "Aule"
2. Verificare almeno 2 aule attive:
   - Aula 1: capienza ≥ 25 posti
   - Aula 2: capienza ≥ 25 posti

3. Accedere alla sezione "Docenti"  
4. Verificare almeno 2 docenti disponibili

5. Accedere alla sezione "Corsi"
6. Se presenti lezioni precedenti, azzerare calendario
```

#### STEP 2: Creazione Corso Test
```
Nome: TEST_DOPPIA_CAL
Totale Ore: 16h
Numero Studenti: 25
Max Ore Giornaliere: 8h
Max Ore Consecutive: 4h
Data Inizio: [domani]
Data Fine: [tra 7 giorni]
Aula Assegnata: [LASCIARE VUOTO - usa qualsiasi aula]

Docenti:
- Docente 1: 8h
- Docente 2: 8h

Materie: [opzionale]
```

#### STEP 3: Calendarizzazione
```
1. Salvare il corso "TEST_DOPPIA_CAL"
2. Cliccare "Auto-Calendarizza TUTTI"
3. Attendere completamento
4. Verificare messaggio successo
```

#### STEP 4: Verifica Risultati
```
1. Aprire vista "Settimana"
2. Navigare alla settimana del corso
3. Per ogni fascia oraria (9:00, 10:00, 11:00, 14:00, ecc.):
   
   ✅ PASS: Il corso appare SOLO in 1 aula
   ❌ FAIL: Il corso appare in 2+ aule contemporaneamente
```

### Risultato Atteso
- Il corso "TEST_DOPPIA_CAL" deve apparire **massimo 1 volta** per ogni fascia oraria
- Non devono esistere sovrapposizioni in aule diverse

### In Caso di FAIL
Se il test fallisce:
1. Screenshot della doppia calendarizzazione
2. Verificare versione (deve essere v3.0.3)
3. Controllare console browser per errori JavaScript
4. Segnalare il problema con screenshot

---

## 🔍 TEST 2: VERIFICA CALENDARIZZAZIONE COMPLETA

### Obiettivo
Verificare che i corsi vengano calendarizzati per tutte le ore disponibili nel pomeriggio.

### Prerequisiti
- Sistema v3.0.3 attivo
- Test 1 completato con successo

### Procedura

#### STEP 1: Creazione Corso Pomeridiano
```
Nome: TEST_POMERIGGIO
Totale Ore: 4h
Numero Studenti: 25
Max Ore Giornaliere: 4h
Max Ore Consecutive: 4h
Data Inizio: [domani]
Data Fine: [tra 2 giorni]
Aula Assegnata: Aula 1 [SELEZIONARE UN'AULA SPECIFICA]

Docenti:
- Docente 1: 4h (verificare disponibilità 14:00-18:00)

Materie:
- Materia Test: 4h
```

#### STEP 2: Verifica Disponibilità Docente
```
1. Andare in sezione "Insegnanti"
2. Selezionare Docente 1
3. Gestione Indisponibilità → Verificare che 14:00-18:00 sia LIBERO
4. Se bloccato, rimuovere indisponibilità
```

#### STEP 3: Calendarizzazione
```
1. Salvare corso "TEST_POMERIGGIO"
2. Cliccare "Auto-Calendarizza TUTTI"
3. Attendere completamento
```

#### STEP 4: Verifica Risultati
```
1. Vista Settimana → giorno del corso
2. Verificare fascia pomeridiana:

   ✅ PASS: Corso calendarizzato 14:00-18:00 (4 ore consecutive)
   ⚠️  WARNING: Corso calendarizzato solo 14:00-15:00 (1 ora)
   ❌ FAIL: Corso non calendarizzato
```

### Diagnosi se Non Completo

**Se il corso è solo 1 ora invece di 4:**

```
CHECKLIST DIAGNOSTICA:

□ maxConsecutiveHours = 4? 
  → Se < 4, aumentare a 4

□ Docente disponibile 14:00-18:00?
  → Controllare sezione Indisponibilità

□ Aula libera 14:00-18:00?
  → Verificare che nessun altro corso occupi l'aula

□ Altri corsi nello stesso giorno?
  → Se sì, potrebbero aver occupato docente/aula

□ Ore rimanenti materia?
  → Verificare che "Materia Test" abbia 4h
```

### Risultato Atteso
Il corso deve essere calendarizzato per **tutte le 4 ore consecutive** se:
- Docente disponibile
- Aula libera
- Configurazione corretta (maxConsecutiveHours ≥ 4)

---

## 🔧 TEST 3: STRESS TEST MULTI-CORSO

### Obiettivo
Verificare robustezza sistema con multipli corsi simultanei.

### Procedura

#### STEP 1: Creazione Scenario Complesso
```
Creare 4 corsi:

1. CORSO_A
   - 20h totali, maxDaily: 4h, Aula: A1
   
2. CORSO_B
   - 20h totali, maxDaily: 4h, Aula: A2
   
3. CORSO_C
   - 16h totali, maxDaily: 4h, Aula: [nessuna]
   
4. CORSO_D
   - 12h totali, maxDaily: 3h, Aula: [nessuna]

Date: Tutte sovrapposte (stessa settimana)
Docenti: 3 docenti condivisi
```

#### STEP 2: Calendarizzazione Globale
```
1. Auto-Calendarizza TUTTI
2. Attendere completamento (potrebbe richiedere 10-30 secondi)
3. Verificare messaggio di completamento
```

#### STEP 3: Verifiche
```
Per ogni giorno della settimana:

✅ Nessun corso appare 2 volte nella stessa ora
✅ Nessun docente ha 2 lezioni contemporanee
✅ Nessuna aula ha 2 lezioni contemporanee
✅ Rispettati limiti orari giornalieri
✅ Pausa pranzo 13:00-14:00 rispettata
```

### Risultato Atteso
- Sistema gestisce correttamente conflitti
- Tutti i corsi vengono calendarizzati (almeno parzialmente)
- Nessuna violazione delle regole di business

---

## 📊 TEST 4: VERIFICA RETROCOMPATIBILITÀ

### Obiettivo
Assicurare che corsi creati con v3.0.2 funzionino con v3.0.3.

### Procedura
```
1. Se disponibile backup v3.0.2:
   - Importare dati corsi precedenti
   - Verificare che calendario esistente sia preservato

2. Eseguire nuova calendarizzazione
3. Verificare che:
   ✅ Corsi esistenti non vengano duplicati
   ✅ Nuove lezioni rispettino il fix bug #1
   ✅ Nessun dato corrotto o perso
```

---

## 📋 REPORT TEST

### Template Report
```
TEST ESEGUITO: [Nome Test]
DATA: [gg/mm/aaaa]
VERSIONE: v3.0.3
RISULTATO: [PASS / FAIL / WARNING]

DETTAGLI:
- Configurazione usata: [...]
- Comportamento osservato: [...]
- Screenshot: [link/allegato]
- Note: [...]

ANOMALIE:
- [Elenco eventuali problemi]

CONCLUSIONI:
- [Sintesi risultati]
```

---

## ✅ CRITERI DI ACCETTAZIONE

Il sistema v3.0.3 è considerato **STABILE** se:

1. ✅ Test 1: PASS al 100%
   - Nessuna doppia calendarizzazione mai rilevata

2. ✅ Test 2: PASS oppure causa identificata
   - Se FAIL, deve essere per limiti configurazione (non bug)

3. ✅ Test 3: PASS con 0 violazioni regole

4. ✅ Test 4: PASS (se applicabile)

---

## 🚨 AZIONI IN CASO DI TEST FALLITI

### Test 1 FAIL (Doppia Calendarizzazione)
```
PRIORITÀ: CRITICA 🔴
AZIONE:
1. NON deployare in produzione
2. Verificare versione file (deve essere v3.0.3)
3. Controllare che fix sia presente nel codice
4. Ripetere test con browser diverso
5. Se persiste, rollback a v3.0.2 e analisi approfondita
```

### Test 2 FAIL (Calendarizzazione Incompleta)
```
PRIORITÀ: MEDIA 🟡
AZIONE:
1. Verificare configurazione corso (checklist diagnostica)
2. Controllare disponibilità risorse
3. Se configurazione corretta ma risultato errato → bug da analizzare
4. Deploy può procedere se Test 1 è PASS
```

### Test 3 FAIL (Violazioni Regole)
```
PRIORITÀ: ALTA 🟠
AZIONE:
1. Identificare tipo violazione specifica
2. Se violazione = doppia calendarizzazione → vedi Test 1
3. Se violazione = altro → analizzare caso specifico
4. Valutare se bloccare deploy
```

---

## 📞 SUPPORTO

In caso di problemi durante i test:
1. Raccogliere screenshot calendario
2. Esportare configurazione corsi
3. Salvare console browser (F12 → Console)
4. Documentare procedura esatta che causa il problema
5. Inviare materiale per analisi

---

*Guida Test generata per v3.0.3*
*Ultima revisione: 27 Ottobre 2025*
