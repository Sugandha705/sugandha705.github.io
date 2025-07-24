# React + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend using TypeScript with type-aware lint rules enabled. Check out the [TS template](https://github.com/vitejs/vite/tree/main/packages/create-vite/template-react-ts) for information on how to integrate TypeScript and [`typescript-eslint`](https://typescript-eslint.io) in your project.


## GitHub Action

- In GitHub gibt es diese Dinge, die man GitHub Actions nennt
   - Das sind kleine Stücke von Automatisierung
   - Actions können etwas Code ausführen / eine Aktion für dich durchführen
   - Zum Beispiel jedes Mal, wenn du einen Push machst, wird es npm run build ausführen
   - Es kann sogar deinen Code an andere Orte kopieren

- Das ist die einfachste Form einer "CI/CD" Pipeline
   - Continuous Integration
   - Continuous Deployment

## Render.com

- Es gibt auch viele andere Möglichkeiten des Deployments
- Heute schauen wir uns an, wie man eine React App mit Render.com deployed

## Todo-App

1. Erstellt ein neues React-Projekt

2. Legt zwei neue Dateien im components-Ordner an: ToDoList.jsx und ToDoItem.jsx

3. In ToDoList.jsx:
- Die Komponente returned ein div mit folgendem Inhalt:
   - eine h1 mit dem Titel "Todo Liste"
   - darunter ein Formular mit einem Input und einem Button
   - darunter eine zunächst leere unordered list und einen p-Tag mit dem Text "Erledigte Todos:"

4. Formular konfigurieren:
- Über das Formular soll es möglich sein, ein neues Todo einzutragen
- Das Input-Feld soll von React kontrolliert werden
- Beim Absenden des Formulars soll eine Funktion mit dem Namen "handleSubmit" aufgerufen werden

5. useReducer vorbereiten:
- Die Todos sollen mit dem useReducer Hook verwaltet werden
- Initialisiert useReducer mit dem Startwert und erstellt eine zunächst leere reducer Funktion

6. In ToDoItem.jsx:
- Die Komponente returned ein li-Element mit folgendem Inhalt:
   - Ein div-Container und darunter ein button mit dem Text "Löschen"
   - In dem div befindet sich ein input-Feld vom Typ "checkbox" gefolgt von einem label
- Importiert den useId Hook (initialisiert in mit: const id = useId()) und wendet ihn an für:
   - die id vom input
   - die htmlFor prop vom label

   7. In ToDoList.jsx
- In der handleSubmit Funktion soll jetzt die Möglichkeit geschaffen werden, ein Todo hinzuzufügen
- Erstelle eine Logik, die die reducer-Funktion aufruft und dort dem State ein Item hinzufügt
- Um jedem Item eine Id zu geben, benutzt diese Funktion: crypto.randomUUID()


8. Todos auf der Seite anzeigen:
- Importiert die ToDoItem.jsx
- im reducer-state sind jetzt unsere Todos gespeichert, nutze diesen um die Todos dynamisch zu generieren
- Jede ToDoItem-Komponente soll den reducer-state erhalten und im label anzeigen

9. Todos toggeln:
- Erstelle die Logik um in der reducer-Funktion die Todos toggeln zu können, d.h.
   - Beim Klicken auf die Checkbox soll diese abwechselnd aus-/abgewählt werden
   - Bei ausgewählter Checkbox soll das Todo durchgestrichen werden
- Um das zu erreichen müssen Änderungen in ToDoList.jsx und ToDoItem.jsx gemacht werden


10. Todos löschen:
- Erstelle jetzt auch eine Logik um einzelne Todos löschen zu können
- Die reducer-Funktion sollte einen weiteren Eintrag hinzubekommen
- Es sind wieder Änderungen in ToDoList.jsx und ToDoItem.jsx nötig

11. Erledigte Todos zählen 
- Erstelle eine weitere Funktion, die zählt, wie viele Todos bereits erledigt sind
- Benutze für diese Funktion den useMemo-Hook
- Das Ergebnis soll im entsprechenden p-Tag auf der Seite angezeigt werden