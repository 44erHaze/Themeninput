# FETCH-API

Die Fetch-API ist eine Schnittstelle in JavaScript, die es ermöglicht, HTTP-Anfragen durchzuführen, um Daten von einem Server abzurufen oder an einen Server zu senden.

## Code Beispiele

### GET-Anfrage

```javascript
fetch('https://api.example.com/data')
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```




### POST-Anfragen

```javascript
fetch('https://api.example.com/create', {
  method: 'POST',
  body: JSON.stringify({ key: 'value' }),
  headers: { 'Content-Type': 'application/json' }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```




### PUT-Anfragen

```javascript
fetch('https://api.example.com/update', {
  method: 'PUT',
  body: JSON.stringify({ key: 'new-value' }),
  headers: { 'Content-Type': 'application/json' }
})
  .then(response => response.json())
  .then(data => console.log(data))
  .catch(error => console.error('Error:', error));
```





# Swagger / OpenAPI

Swagger, jetzt als OpenAPI bekannt, ist ein Framework zur Erstellung und Dokumentation von RESTful APIs.

## Nutzen:

- Erleichtert das Entwerfen, Dokumentieren und Testen von APIs.
- Bietet eine einheitliche Methode, um APIs zu beschreiben und zu dokumentieren.
- Generiert automatisch API-Dokumentation, die für Entwickler leicht verständlich ist.
- Unterstützt das Testen von APIs direkt von der Dokumentation aus.

### Code Beispiel

```yaml
openapi: 3.0.0
info:
  title: ToDo List API
  version: 1.0.0
paths:
  /tasks:
    get:
      summary: Ruft alle Aufgaben ab
      responses:
        '200':
          description: Erfolgreiche Antwort
          content:
            application/json:
              example:
                - id: 1
                  title: Einkaufen
                - id: 2
                  title: Meeting
    post:
      summary: Erstellt eine neue Aufgabe
      requestBody:
        required: true
        content:
          application/json:
            example:
              title: Hausaufgaben
      responses:
        '201':
          description: Aufgabe erfolgreich erstellt
  /tasks/{id}:
    get:
      summary: Ruft eine Aufgabe ab
      parameters:
        - name: id
          in: path
          required: true
          schema:
            type: integer
      responses:
        '200':
          description: Erfolgreiche Antwort
          content:
            application/json:
              example:
                id: 1
                title: Einkaufen
    put:
      summary: Aktualisiert eine Aufgabe
      parameters:
        - name: id
          in: path
          required: true
          schema:
            type: integer
      requestBody:
        required: true
        content:
          application/json:
            example:
              title: Neuer Titel
      responses:
        '204':
          description: Aufgabe erfolgreich aktualisiert
```

# JavaScript Frameworks: React, Angular, Vue.js

## React (Facebook)


### Nutzen:

- Bibliothek zur Entwicklung von Benutzeroberflächen, die auf wiederverwendbaren Komponenten basieren.
- Unterstützt das Erstellen von komplexen UIs durch effiziente Aktualisierung von Komponenten.
- Verwendung von JSX (einer Mischung aus JavaScript und HTML), um UI-Komponenten zu erstellen.
- Ermöglicht die Verwendung von State und Props zur Verwaltung von Datenflüssen.


### Code Beispiel

```javascript
import React, { useState } from 'react';

function Counter() {
  const [count, setCount] = useState(0);

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```


## Angular (Google)


### Nutzen:

- Umfassendes Framework zur Entwicklung von Webanwendungen.
- Verwendet TypeScript, um statisches Typing in JavaScript einzuführen.
- Bietet eine umfangreiche Sammlung von Bibliotheken und Werkzeugen für verschiedene Aspekte der Entwicklung.
- Unterstützt die Erstellung von Komponenten-basierten Anwendungen.


### Code Beispiel:

```javascript
import { Component } from '@angular/core';

@Component({
  selector: 'app-root',
  template: `
    <h1>Hello Angular!</h1>
  `,
})
export class AppComponent {}
```



## Vue.js


### Nutzen:

- Progressives Framework zur Entwicklung von Benutzeroberflächen.
- Einfach einzubinden und zu erlernen, auch für Entwickler mit begrenzten Vorkenntnissen.
- Bietet reaktive Datenbindung und Komponenten-basierte Entwicklung.
- Gut geeignet für schnelle Prototypen sowie für die Entwicklung komplexer Anwendungen.


### Code Beispiel:

```html
<template>
  <div>
    <p>Message: {{ message }}</p>
    <button @click="changeMessage">Change Message</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      message: 'Hello Vue!',
    };
  },
  methods: {
    changeMessage() {
      this.message = 'New message!';
    },
  },
};
</script>
```