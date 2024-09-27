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
