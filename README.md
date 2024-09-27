# SQL Programmierstil-Regelwerk

## 1. Allgemeine Richtlinien
- **Verwende immer aussagekräftige und lesbare Namen** für Tabellen, Spalten und Aliase.
- **Verwende durchgängig Englisch** als Sprache für Namen und Kommentare.
- **Einheitliche Groß-/Kleinschreibung**: Konventionen für SQL-Schlüsselwörter, Tabellennamen, Spaltennamen und Variablen sollten konsequent eingehalten werden.

## 2. Namenskonventionen
- **Tabellennamen**: Verwende `Singular` (z. B. `Customer`, `Order`), und beginne mit einem Großbuchstaben.
- **Spaltennamen**: Snake_case oder CamelCase (z. B. `customer_id` oder `CustomerID`) – konsistent innerhalb des Projekts bleiben.
- **Alias-Namen**: Kurz, eindeutig und beschreibend (z. B. `c` für `Customer`).
- **Variablennamen**: CamelCase (z. B. `TotalRevenue`).

## 3. Schlüsselwort-Schreibweisen
- **SQL-Schlüsselwörter in Großbuchstaben**: `SELECT`, `FROM`, `WHERE`, etc.
- **Datenbank-Objektnamen in Kleinbuchstaben** oder CamelCase.

**Beispiel**:
```sql
SELECT customer_id, first_name, last_name
FROM customer
WHERE is_active = 1;


Hier ist das Regelwerk komplett und korrekt im Markdown-Format:

markdown
Code kopieren
# SQL Programmierstil-Regelwerk

## 1. Allgemeine Richtlinien
- **Verwende immer aussagekräftige und lesbare Namen** für Tabellen, Spalten und Aliase.
- **Verwende durchgängig Englisch** als Sprache für Namen und Kommentare.
- **Einheitliche Groß-/Kleinschreibung**: Konventionen für SQL-Schlüsselwörter, Tabellennamen, Spaltennamen und Variablen sollten konsequent eingehalten werden.

## 2. Namenskonventionen
- **Tabellennamen**: Verwende `Singular` (z. B. `Customer`, `Order`), und beginne mit einem Großbuchstaben.
- **Spaltennamen**: Snake_case oder CamelCase (z. B. `customer_id` oder `CustomerID`) – konsistent innerhalb des Projekts bleiben.
- **Alias-Namen**: Kurz, eindeutig und beschreibend (z. B. `c` für `Customer`).
- **Variablennamen**: CamelCase (z. B. `TotalRevenue`).

## 3. Schlüsselwort-Schreibweisen
- **SQL-Schlüsselwörter in Großbuchstaben**: `SELECT`, `FROM`, `WHERE`, etc.
- **Datenbank-Objektnamen in Kleinbuchstaben** oder CamelCase.

**Beispiel**:
```sql
SELECT customer_id, first_name, last_name
FROM customer
WHERE is_active = 1;
4. Formatierung
Jeder SQL-Befehl sollte in einer neuen Zeile beginnen.
Einrückungen: Verwende vier Leerzeichen oder einen Tab zur Einrückung von Codeblöcken.
Verwende Leerzeichen um Operatoren (=, <, >, AND, OR) für bessere Lesbarkeit.
Beispiel:

sql
Code kopieren
SELECT 
    OrderID, 
    CustomerID, 
    OrderDate 
FROM 
    Orders 
WHERE 
    OrderStatus = 'Shipped'
    AND OrderDate >= '2023-01-01';
5. Joins
Schreibe Joins immer auf separate Zeilen, mit entsprechenden Einrückungen.
Verwende Aliase, um die Lesbarkeit von Joins zu erhöhen.
Beispiel:

sql
Code kopieren
SELECT 
    o.OrderID, 
    c.CustomerName 
FROM 
    Orders o
INNER JOIN 
    Customers c ON o.CustomerID = c.CustomerID;
6. Kommentare
Verwende Einzeilige Kommentare (--) für kurze Anmerkungen.
Mehrzeilige Kommentare (/* ... */) für ausführlichere Erklärungen oder Dokumentation.
Beispiele:

sql
Code kopieren
-- Dieser Kommentar beschreibt den Zweck der folgenden Abfrage
SELECT * FROM Orders; 

/* 
   Diese Abfrage ermittelt alle aktiven Kunden 
   mit mindestens einer Bestellung im Jahr 2023 
*/
SELECT * 
FROM Customers 
WHERE IsActive = 1;
7. Dokumentation
Schreibe eine kurze Beschreibung jeder SQL-Prozedur, Funktion oder View.
Verwende Markdown, um Code und Kommentare übersichtlich zu gestalten.
Dokumentiere Eingabe- und Ausgabeparameter sowie Rückgabewerte.
Beispiel in Markdown:

markdown
Code kopieren
### Prozedur: `GetCustomerOrders`
- **Beschreibung**: Diese Prozedur gibt alle Bestellungen eines Kunden zurück.
- **Parameter**:
  - `@CustomerID` (int): Die ID des Kunden
- **Rückgabewerte**: 
  - `OrderID`, `OrderDate`, `TotalAmount`
sql
Code kopieren
CREATE PROCEDURE GetCustomerOrders (@CustomerID INT)
AS
BEGIN
    SELECT OrderID, OrderDate, TotalAmount 
    FROM Orders 
    WHERE CustomerID = @CustomerID;
END;
8. Best Practices
Verwende JOIN-Bedingungen anstelle von Subselects, wenn möglich.
Nutze EXISTS anstelle von IN für bessere Leistung bei Abfragen mit großen Datenmengen.
**Vermeide SELECT ***: Gib explizit die benötigten Spalten an.
Code kopieren

Du kannst dieses Markdown-Dokument jet
