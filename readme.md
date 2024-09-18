# Lucrare de laborator nr. 1

# TEMA: *"BAZELE HTTP"*
<br>
<br>


# SARCINA 1. *Analiza cererilor HTTP*
<br>

## *~~GRESIT~~*

## 1. Ce metodă HTTP a fost utilizată pentru a trimite cererea?
#### *Request Method:POST*

## 2. Ce anteturi au fost trimise în cerere?
#### *POST /login/process.php HTTP/1.1*
#### accept: \*/\* 
### *accept-encoding: gzip, deflate*
### *accept-language: en-US,en;q=0.9,ro;q=0.8*
### *connection: keep-alive*
### *content-length: 37*
### *content-type:application/x-www-form-urlencoded; charset=UTF-8*
### *host: sandbox.usm.md*
### *origin: http://sandbox.usm.md*
### *referer: http://sandbox.usm.md/login/*
### *user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36*
### *x-requested-with: XMLHttpRequest*

## 3. Ce parametri au fost trimiși în cerere?
#### *username: student*
#### *password: studentpass*


## 4. Ce cod de stare a fost returnat de server?
#### *Status Code: 401 Unauthorized*

## 5. Ce anteturi au fost trimise în răspuns?
#### *HTTP/1.1 401 Unauthorized*
#### *connection: keep-alive*
#### *content-type: text/plain;charset=UTF-8*
#### *date: Wed, 18 Sep 2024 20:08:51 GMT*
#### *server: nginx/1.24.0 (Ubuntu)*
#### *transfer-encoding: chunked*

<br>
<br>

## ~~CORECT~~

## 1. Ce metodă HTTP a fost utilizată pentru a trimite cererea?
#### *Request Method:POST*

## 2. Ce anteturi au fost trimise în cerere?
#### *POST /login/process.php HTTP/1.1*
#### accept: \*/\* 
#### *accept-encoding: gzip, deflate*
#### *accept-language: en-US,en;q=0.9,ro;q=0.8*
#### *connection: keep-alive*
#### *content-length: 32*
#### *content-type: application/x-www-form-urlencoded; charset=UTF-8*
#### *host: sandbox.usm.md*
#### *origin: http://sandbox.usm.md*
#### *referer: http://sandbox.usm.md/login/*
#### *user-agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/128.0.0.0 Safari/537.36*
#### *x-requested-with: XMLHttpRequest*

## 3. Ce parametri au fost trimiși în cerere?
#### *username: admin*
#### *password: password*

## 4. Ce cod de stare a fost returnat de server?
#### *Status Code: 200 OK*
## 5. Ce anteturi au fost trimise în răspuns?
#### *HTTP/1.1 200 OK*
#### *connection: keep-alive*
#### *content-type: text/plain;charset=UTF-8*
#### *date: Wed, 18 Sep 2024 20:20:43 GMT*
#### *server: nginx/1.24.0 (Ubuntu)*
#### *transfer-encoding: chunked*

<br>
<br>

# SARCINA 2. *"Crearea cererilor HTTP"*
## 1. Scrieți o cerere de tip GET către server la adresa http://sandbox.com, indicând în antetul User-Agent numele și prenumele dvs.
#### *GET / HTTP/1.1*
#### *Host: sandbox.com*
#### *User-Agent: [Caisin][Valeria]*

<br>

## 2. Scrieți o cerere de tip POST către server la adresa http://sandbox.com/cars, indicând în corpul cererii următorii parametri: make: Toyota; model: Corolla; year: 2020
#### *POST /cars HTTP/1.1*
#### *Host: sandbox.com*
#### *Content-Type: application/x-www-form-urlencoded*
#### *Content-Length: 34*
#### *make=Toyota&model=Corolla&year=2020*

<br>

## 3. Scrieți o cerere de tip PUT către server la adresa http://sandbox.com/cars/1, indicând în antetul User-Agent numele și prenumele dvs., în antetul Content-Type valoarea application/json, iar în corpul cererii următorii parametri: json { "make": "Toyota", "model": "Corolla", "year": 2021 }
#### *PUT /cars/1 HTTP/1.1*
#### *Host: sandbox.com*
#### *User-Agent: [Caisin][Valeria]*
#### *Content-Type: application/json*
#### *Content-Length: 40*

<br>

## 4.Scrieți unul dintre posibilele răspunsuri ale serverului la cererea anterioară. http POST /cars HTTP/1.1 Host: sandbox.com Content-Type: application/json User-Agent: John Doe model=Corolla&make=Toyota&year=2020 Presupuneți situațiile în care serverul poate returna codurile de stare HTTP 200, 201, 400, 401, 403, 404, 500.

#### **HTTP 200 OK:** 
##### *Indică faptul că cererea a fost procesată cu succes. De obicei, acesta este folosit când serverul a primit cererea și a procesat-o, dar nu a creat o resursă nouă.*
#### **HTTP 201 Created:** 
##### *Indică faptul că resursa a fost creată cu succes. Acesta este codul de stare corespunzător pentru o cerere POST care creează o resursă nouă.*
#### **HTTP 400 Bad Request:**
##### *Indică faptul că cererea este invalidă din punct de vedere sintactic. De exemplu, dacă datele JSON sunt incomplete sau incorecte.*
#### **HTTP 401 Unauthorized:**
##### *Indică faptul că cererea necesită autentificare și utilizatorul nu este autentificat sau a furnizat credențiale invalide.*
#### **HTTP 403 Forbidden:**
##### *Indică faptul că utilizatorul nu are permisiunea necesară pentru a accesa resursa solicitată.*
#### **HTTP 404 Not Found:**
##### *Indică faptul că resursa solicitată nu a fost găsită pe server. Acest cod poate fi rar pentru cererile POST, dar ar putea fi utilizat dacă endpoint-ul /cars nu există.*
#### **HTTP 500 Internal Server Error:**
##### *Indică faptul că a avut loc o eroare pe server în timp ce se procesa cererea. Acest cod este utilizat atunci când serverul întâlnește o problemă neașteptată.*

<br>

## 5.Scrieți o cerere de tip DELETE la alegerea dvs. și să explicați de ce, în acest caz, este potrivit să utilizați metoda DELETE.

#### *DELETE /cars/12345 HTTP/1.1*
#### *Host: sandbox.com*
#### *User-Agent: Michael Durdoul*
#### *Authorization: Bearer <your_access_token>*

### EXPLICATIE: 
#### *Metoda DELETE este utilizată pentru a șterge o resursă specifică de pe server. În acest caz, cererea DELETE /cars/12345 este utilizată pentru a șterge resursa identificată prin ID-ul 12345 din colecția de mașini (/cars).*
#### *Metoda DELETE este potrivită aici deoarece:*
#### *- cererea vizează eliminarea unei resurse specificate prin ID-ul 12345.*
#### *-  stergerea aceleași resurse de mai multe ori are același efect, fără efecte secundare suplimentare.*
#### *- indică în mod clar intenția de a elimina resursa, nu de a modifica sau vizualiza datele.*
