# Git Workflow Directive

Questa direttiva definisce la struttura dei repository e il workflow Git per questo progetto.

## Configurazione Repository

L'architettura del repository segue il modello Fork-and-Pull:

- **Fork Personale (Origin)**: `origin/main`
  - URL: `git@github.com:ToRvaLDz/dots-hyprland.git`
  - Utilizzato per lo sviluppo, il backup dei rami e le Pull Request.
- **Repository Originale (Upstream)**: `upstream/main`
  - URL: `https://github.com/end-4/dots-hyprland.git`
  - Utilizzato come sorgente della verità per il codice originale e per mantenere il fork aggiornato.

## Workflow Operativo

### 1. Sincronizzazione con Upstream
Prima di iniziare un nuovo task, assicurati che il ramo `main` sia aggiornato:
```bash
git checkout main
git pull upstream main
git push origin main
```

### 2. Creazione Feature Branch
Lavora sempre su rami dedicati partendo da `main` aggiornato:
```bash
git checkout -b feature/nome-task
```

### 3. Commit e Push
- Effettua commit atomici e descrittivi.
- Fai il push sul tuo fork (`origin`):
```bash
git push origin feature/nome-task
```

## Regole d'Oro
- **MAI** pushare direttamente su `upstream` (se avessi i permessi).
- **SEMPRE** verificare su quale branch ti trovi prima di eseguire operazioni distruttive.
- Quando l'utente chiede di "aggiornare dal repository originale", si riferisce a `upstream/main`.
- Quando l'utente chiede di "salvare i cambiamenti sul mio fork", si riferisce a `origin/main`.
