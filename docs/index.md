# Projecte: Chatbot de gestió de cites per a una empresa d'interiorisme

## 1. El client i el problema

El negoci és una empresa dedicada al disseny i interiorisme, que ofereix serveis de decoració, reforma i assessorament per a habitatges i locals.

Actualment, els clients contacten amb l'empresa principalment per telèfon, correu electrònic o presencialment per sol·licitar informació i concertar una cita. Aquest sistema pot provocar esperes, trucades perdudes i dificultats per trobar un horari que coincideixi amb la disponibilitat del client i del personal.

El nostre producte serà un chatbot que permetrà als clients consultar informació i, principalment, concertar una cita per parlar amb un professional i preparar un pressupost.

## 2. El servei reservable

El servei que es podrà reservar serà una primera consulta d'interiorisme per preparar un pressupost. Cada cita tindrà una durada de 30 minuts.

- Dilluns a divendres
- De 09:00 a 14:00 i de 17:00 a 21:00
- Durada de cada cita: 30 minuts

Les cites es gestionaran sempre amb l'hora local del negoci. Només es permetrà una reserva per cada franja horària disponible.

## 3. Dades mínimes necessàries

- Nom i cognoms
- Telèfon o correu electrònic de contacte
- Data de la cita
- Hora de la cita
- Motiu general de la consulta

Exemple:

```text
Nom: Marc García
Contacte: marc.garcia@example.com
Data: 22/09/2026
Hora: 10:30
Motiu: Reforma de cuina
```

No es demanaran dades personals que no siguin necessàries per gestionar la cita.

## 4. Condicions de les reserves

Una reserva s'acceptarà quan el client hagi proporcionat les dades mínimes i la franja horària estigui disponible. El sistema comprovarà la disponibilitat abans de confirmar la reserva.

Si la franja està ocupada, el chatbot informarà el client i li mostrarà altres franges disponibles. Una vegada confirmada, la cita quedarà registrada a la base de dades i el client rebrà una confirmació.

El personal podrà consultar, modificar o cancel·lar les cites des de l'accés de gestió.

## 5. Esbós de la web

- **Inici:** presentació de l'empresa, explicació breu dels serveis i botó per parlar amb el chatbot.
- **Serveis:** interiorisme, decoració, reformes, assessorament i pressupostos.
- **Concertar una cita:** formulari de reserva, selecció de data i hora, dades de contacte i motiu de la consulta.
- **Chatbot:** finestra de xat integrada que guia el client durant la reserva.
- **Accés de gestió:** accés restringit al personal per consultar, modificar i cancel·lar cites.

## 6. Recorregut de les dades

Navegador → Nginx → Backend → MariaDB

El chatbot també estarà connectat amb el servei d'IA per interpretar les preguntes i peticions dels clients.

1. El client entra a la pàgina web mitjançant el navegador.
2. El navegador envia les peticions al servidor web Nginx.
3. Nginx dirigeix les peticions al backend de l'aplicació.
4. El backend consulta MariaDB per comprovar les cites existents i les franges disponibles.
5. El chatbot utilitza el servei d'IA per entendre les peticions del client i guiar-lo durant la conversa.
6. Quan el client escull una franja disponible, el backend registra la reserva a MariaDB.
7. El sistema retorna la confirmació al chatbot i aquesta es mostra al client.