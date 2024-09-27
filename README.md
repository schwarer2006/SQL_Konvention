### **Regelwerk für Datenbankobjekte**

#### **1\. Allgemeine Grundsätze**

*   **Konsistenz**: Halte dich immer an einheitliche Benennungs- und Formatierungsregeln.
    
*   **Lesbarkeit**: Alle Datenbankobjekte sollten klar benannt und strukturiert sein, um die Lesbarkeit und Wartbarkeit zu erhöhen.
    
*   **Vermeidung von Abkürzungen**: Abkürzungen sollten nur verwendet werden, wenn sie allgemein verständlich sind.
    
*   **Dokumentation**: Jede Änderung an Datenbankobjekten sollte dokumentiert werden.
    

#### **2\. Namenskonventionen**

##### **Tabellen**

*   **Staging-Tabellen**: stg\_\_
    
    *   Beispiel: stg\_salesforce\_customers
        
*   **DWH-Tabellen**:
    
    *   Dimensionstabellen: dwh\_dim\_
        
        *   Beispiel: dwh\_dim\_customer
            
    *   Faktentabellen: dwh\_fact\_
        
        *   Beispiel: dwh\_fact\_sales
            
*   **Data Mart Tabellen**:
    
    *   Dimensionstabellen: dm\_\_dim\_
        
        *   Beispiel: dm\_sales\_dim\_customer
            
    *   Faktentabellen: dm\_\_fact\_
        
        *   Beispiel: dm\_sales\_fact\_orders
            

##### **Views**

*   **Staging Views**: stg\_vw\_\_
    
*   **DWH Views**: dwh\_vw\_
    
*   **Data Mart Views**: dm\_\_vw\_
    
*   Beispiel: dm\_sales\_vw\_monthly\_revenue
    

##### **Stored Procedures**

*   **Staging**: stg\_sp\_
    
*   **DWH**: dwh\_sp\_
    
*   **Data Mart**: dm\_\_sp\_
    
*   Beispiel: dwh\_sp\_load\_fact\_sales
    

##### **Functions**

*   **Staging**: stg\_fn\_
    
*   **DWH**: dwh\_fn\_
    
*   **Data Mart**: dm\_\_fn\_
    
*   Beispiel: dm\_sales\_fn\_calculate\_discount
    

##### **Trigger**

*   Benennung: \_trg\_\_
    
*   Beispiel: dwh\_trg\_fact\_sales\_update
    

##### **Indizes**

*   **Syntax**: idx\_\_
    
*   Beispiel: idx\_customers\_lastname
    

#### **3\. SQL Schreibweisen und Formatierung**

*   **Schlüsselwörter** in Großbuchstaben (SELECT, FROM, WHERE).
    
*   **Tabellen- und Spaltennamen** in Kleinbuchstaben (customer\_id).
    
*   **Einrückung**: Verwende Einrückungen und Zeilenumbrüche, um Abfragen strukturiert darzustellen.
    
*   **Aliases**: Aliasse immer kurz, eindeutig und sinnvoll halten, z.B., c für customers.
    

#### **4\. Kommentare**

*   **Einzeilige Kommentare**: -- Beschreibung
    
    *   Beispiel: -- Berechnet die Gesamtumsätze pro Kunde
        
*   sqlCode kopieren/\* Beschreibung: Berechnung der monatlichen Umsätze Autor: Erik Datum: 27.09.2024\*/
    

#### **5\. Datenbank-Design-Prinzipien**

*   \*\*Vermeide SELECT \***:** Wähle nur die benötigten Spalten aus.
    
*   **Normalisierung**: Halte die Tabellen möglichst normalisiert (mindestens 3. Normalform).
    
*   **Primärschlüssel**: Jeder Tabelle sollte ein Primärschlüssel zugeordnet sein.
    
*   **Fremdschlüssel**: Verwende Fremdschlüssel, um Beziehungen zwischen Tabellen zu definieren und Datenintegrität zu gewährleisten.
    
*   **Indexes**: Lege Indizes auf häufig verwendete Spalten an, um Abfragen zu optimieren, aber setze sie gezielt ein.
    

#### **6\. Stored Procedures und Funktionen**

*   **Parameterbenennung**: Verwende p\_ als Präfix für Parameter, z.B., @p\_customer\_id.
    
*   **Dokumentation**: Jede Prozedur oder Funktion sollte am Anfang eine Beschreibung enthalten, die Zweck, Autor, Datum und Parameter erläutert.
    
*   **Transaktionen**: Nutze Transaktionen (BEGIN TRANSACTION, COMMIT, ROLLBACK) bei Prozeduren, die mehrere Schritte umfassen.
    

#### **7\. Triggers**

*   **Verwendung**: Trigger sollten sparsam und nur dann eingesetzt werden, wenn eine automatisierte Reaktion auf Datenänderungen notwendig ist.
    
*   **Dokumentation**: Beschreibe den Zweck und die Bedingungen des Triggers in Kommentaren am Anfang des Codes.
    

#### **8\. Fehlerbehandlung**

*   **Stored Procedures** sollten Fehlerbehandlungen (TRY...CATCH) enthalten.
    
*   **Logging**: Nutze Logging-Tabellen, um Fehler und Laufzeitinformationen festzuhalten.
    

#### **9\. Sicherheit**

*   **Berechtigungen**: Vergib nur die notwendigen Berechtigungen für Datenbankobjekte.
    
*   **Rollenbasierte Zugriffssteuerung**: Verwende Rollen, um Berechtigungen zentral zu steuern.
    

#### **10\. Versionierung und Änderungen**

*   **Versionshinweise**: Bei Änderungen an Objekten sollten Versionshinweise (Datum, Autor, Beschreibung der Änderung) hinzugefügt werden.
    
*   **Versionsverwaltung**: Verwende ein Versionskontrollsystem (z.B., Git), um Änderungen am Datenbankschema zu verfolgen.
    

### Zusammenfassung

Dieses Regelwerk hilft dabei, eine konsistente, strukturierte und wartbare Datenbankumgebung zu schaffen. Es verbessert die Zusammenarbeit im Team, vereinfacht die Fehlersuche und sorgt für eine bessere Dokumentation und Wartbarkeit der Datenbankobjekte.
