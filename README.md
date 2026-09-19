# Giaco&Dario™ – Sala giochi

I giochi del sito Giaco&Dario™, ospitati su GitHub Pages invece che incollati come codice dentro Google Sites.

## Struttura

```
index.html                 pagina della sala giochi (elenco di tutti i giochi)
giochi/<nome>/index.html   un gioco per cartella, file unico e autonomo
```

Giochi: `runner-ultimate` (Stickman Runner 2), `runner-deluxe`, `polpetta-letale`, `polpetta-2`, `ged-3d`, `balloon-blast`, `settore-9`, `street-brawler`, `test-reattivita`, `quanto-sei-unico`, `stimulation-clicker`, più `orologio` (il widget con ora e data dell'intestazione).
I due quiz restano su Wordwall.

## Pubblicare su GitHub Pages (una volta sola)

1. Accedi a github.com e crea un repository **pubblico** chiamato `giochi`.
2. Nella pagina del repository: *Add file → Upload files*, trascina **il contenuto** di questa cartella (non la cartella stessa) e conferma con *Commit changes*.
3. *Settings → Pages*: in *Source* scegli *Deploy from a branch*, branch `main`, cartella `/ (root)`, *Save*.
4. Dopo 1–2 minuti il sito è su `https://TUONOME.github.io/giochi/`.

Per aggiornare un gioco: apri il file su GitHub, matita, incolla il nuovo codice, *Commit changes*. La cronologia (*History*) permette di tornare a qualsiasi versione precedente.

## Collegarli a Google Sites

Per ogni gioco nella pagina Giochi:
1. *Inserisci → Incorpora → scheda "Tramite URL"* e incolla `https://TUONOME.github.io/giochi/giochi/<nome>/`.
2. Il link "schermo più grande" punta allo stesso indirizzo.

In alternativa si può mettere in Sites un solo link alla sala giochi (`https://TUONOME.github.io/giochi/`), che è la soluzione più leggera.

## Cosa è stato cambiato rispetto al codice originale

- **Velocità (Runner Deluxe, Runner Ultimate, Street Brawler, Balloon Blast, Stimulation Clicker):** questi giochi spostano tutto "a ogni frame", quindi su schermi a 120/144 Hz andavano 2–2,6 volte più veloci (misurato). Ora gli aggiornamenti hanno un ritmo fisso di 60 al secondo su qualsiasi schermo. Limite noto: su schermi sotto i 60 Hz il gioco rallenta, come prima.
- **Salvataggio (Runner Deluxe, Runner Ultimate, Giaco&Dario 3D):** usavano Firebase, che funziona solo dentro Gemini. Fuori da Gemini i Runner non salvavano niente e il 3D andava in errore all'avvio e non partiva proprio. Ora i progressi si salvano nel browser (`localStorage`), sul dispositivo di chi gioca. I pulsanti "Reset cloud" sono diventati "Reset progressi".
- **Tailwind:** prima ogni gioco scaricava Tailwind e lo compilava nel browser a ogni apertura. Ora il CSS è già compilato dentro il file.
- **Test dei riflessi:** la libreria di icone Lucide era `@latest` (poteva cambiare da sola e rompere il gioco); ora la versione è fissata.

Il resto del codice dei giochi è invariato.

## Limiti da conoscere

- I salvataggi sono per dispositivo e per browser: non si trasferiscono tra PC e telefono. In modalità anonima o con i cookie di terze parti bloccati, dentro Google Sites il salvataggio può non funzionare; il gioco va lo stesso, solo senza memoria.
- Il salvataggio fatto giocando dentro Google Sites e quello fatto aprendo il gioco a schermo intero possono risultare separati (Chrome isola i dati dei siti incorporati).
