**SMX2B** · Projecte Ion Ballester · Alex Luque

Empresa d'interiorisme

# Chatbot de gestió de *cites* per a una empresa d'interiorisme

Un xat integrat a la web que respon preguntes i, sobretot, deixa reservar en pocs missatges una primera consulta de 30 minuts per preparar un pressupost.

[El client](#client) [El servei](#servei) [Dades](#dades) [Reserves](#condicions) [La web](#web) [Arquitectura](#recorregut)

ServeiPrimera consulta

Durada30 min

**1** El client i el problema

## Concertar una primera cita no hauria de dependre d'una trucada

El negoci és una empresa de disseny i interiorisme que ofereix decoració, reforma i assessorament per a habitatges i locals.

Avui

### Trucades perdudes

Els clients contacten per telèfon, per correu electrònic o en persona per demanar informació i concertar una cita. Una trucada sense resposta és una sol·licitud perduda.

Avui

### Esperes

Aquest sistema fa esperar el client abans de saber si pot reservar i quan.

Avui

### Horaris que no coincideixen

Costa trobar una hora que encaixi alhora amb la disponibilitat del client i la del personal.

El producte

### Un chatbot que permet consultar informació i, principalment, concertar una cita amb un professional.

La cita serveix per parlar del projecte i preparar un pressupost.

- Facilita la gestió de les cites.
- Redueix la feina administrativa del personal.
- Deixa al client reservar una hora disponible de manera ràpida i senzilla.

**2** El servei reservable

## Una primera consulta d'interiorisme per preparar un pressupost

El client explica què necessita, indica quin espai vol reformar o decorar i rep una primera orientació sobre el projecte.

Durada

30 min

Per cita

Dies

Dl – Dv

Dilluns a divendres

Franges per dia

18

10 al matí i 8 a la tarda

Per franja

1 reserva

Mai dues cites alhora

Matí · 09:00 – 14:00

Sense cites

Tarda · 17:00 – 21:00

09:0014:0017:0021:00

Les cites es gestionen sempre amb l'hora local del negoci.

**3** Dades mínimes necessàries

## Cinc dades i res més

Per crear una reserva, el chatbot només demana el que necessita per gestionar la cita.

- **Nom**Nom i cognoms del client.
- **Contacte**Telèfon o correu electrònic.
- **Data**Dia de la cita.
- **Hora**Franja de 30 minuts dins l'horari del servei.
- **Motiu**Motiu general: reforma de cuina, reforma de bany, decoració d'un habitatge o reforma d'un local.

No es demanen dades personals que no siguin necessàries per gestionar la cita.

Reserva Exemple 1

Nom

Ion Ballester

Contacte

ionballester@gmail.com

Data

22/09/2026

Hora

10:30

Motiu

Reforma de cuina

Reserva Exemple 2

Nom

Alex Luque

Contacte

alexluque@gmail.com

Data

22/09/2026

Hora

11:00

Motiu

Decoració d'habitatge

**4** Condicions de les reserves

## La disponibilitat es comprova abans de confirmar

Una reserva s'accepta quan el client ha donat les dades mínimes i la franja triada és lliure.

1. **El client tria una hora** Un cop donades les dades mínimes.
2. **El sistema comprova la disponibilitat** Abans de confirmar res.

   **Lliure**La cita queda registrada a la base de dades i el client rep una confirmació.

   **Ocupada**El chatbot avisa que l'hora ja no està disponible i mostra altres franges perquè el client en triï una.

**Accés de gestió per al personal** Pot consultar les cites, modificar-les o cancel·lar-les. Quan una cita canvia, el sistema actualitza la informació corresponent.

**Dimarts 22/09/2026** Exemple interactiu

Matí

Tarda

LliureOcupadaTriada

**5** Esbós de la web

## Una estructura senzilla perquè el client trobi el servei i reservi

Cinc seccions. Quatre són públiques i l'accés de gestió és només per al personal.

Inici

### Inici

- Presentació de l'empresa
- Explicació breu dels serveis
- Botó per parlar amb el chatbot

Serveis

### Serveis

- Interiorisme
- Decoració
- Reformes
- Assessorament i pressupostos

Cita

### Concertar una cita

- Formulari de reserva
- Selecció de data
- Selecció d'hora disponible
- Dades de contacte
- Motiu de la consulta

Xat

### Chatbot

- Finestra de xat integrada a la web
- Guia el client durant tota la reserva
- Consulta de disponibilitat
- Confirmació de la cita

Restringit

### Accés de gestió

- Només per al personal
- Consulta de les cites
- Modificació de cites
- Cancel·lació de cites

**6** Recorregut de les dades

## Navegador, Nginx, backend i MariaDB

El chatbot també es connecta amb un servei d'IA que interpreta les preguntes i peticions dels clients.

Client

**Navegador**Entra a la pàgina web

Servidor web

**Nginx**Dirigeix les peticions

Backend

**Node**Lògica de l'aplicació i de les reserves

**Servei d'IA**Entén les peticions i guia la conversa

Base de dades

**MariaDB**Cites i franges

1. **El client entra a la web** mitjançant el navegador.
2. El navegador envia les peticions al servidor web **Nginx**.
3. Nginx dirigeix les peticions al **backend** de l'aplicació.
4. El backend consulta **MariaDB** per comprovar les cites existents i les franges disponibles.
5. El chatbot utilitza el **servei d'IA** per entendre les peticions del client i guiar-lo durant la conversa.
6. Quan el client escull una franja disponible, el backend **registra la reserva** a MariaDB.
7. El sistema retorna la **confirmació** al chatbot i es mostra al client.

Projecte**Chatbot de gestió de cites per a una empresa d'interiorisme**

Curs**SMX2B**

Autors**Ion Ballester\
Alex Luque**

Tecnologia**Nginx · Node · MariaDB · IA**