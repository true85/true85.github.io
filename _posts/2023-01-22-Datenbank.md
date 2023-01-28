---
title:  "IT 시험 정리 DB"
layout: single
categories: klausure
tag: IT Test
toc: true
use_math: true #수학식 적용여부
author_profile: false #내 프로파일 안보이기
sidebar:
    nav: "docs" 
# search: false #검색불가
---

# Abschlussprüfung Teil 1

## WBL
[WBL](https://true85.github.io/klausure/WBL/)
## Gesellschaftslehre
[Gesellschaftslehre](https://true85.github.io/klausure/Gesellschaftslehre/)
## IT
[IT-E](https://true85.github.io/klausure/IT-E/)
[IT-P](https://true85.github.io/klausure/IT-P/)
[Datenbank](https://true85.github.io/klausure/Datenbank/)
## etc.
[etc](https://true85.github.io/klausure/etc/)


## a
### Redundanz, Primär-/Fremdschlüssel, Datensatz
Redundanz
: Zeichen für schlechtes Datenbankdesign  
Sind doppelte Informationen in einer Datenbank bzw. Datenbank-Tabelle. 

Primär-/Fremdschlüssel 
: Eine Spalte oder Spaltengruppe mit Werten in einer Tabelle, deren Werte eine Zeile in der Tabelle eindeutig kennzeichnen.  
: Eine Spalte oder eine Spaltengruppe in einer Tabelle, deren Werte den Werten des Primärschlüssels in einer anderen Tabelle entsprechen.  

Datensatz
: Ein Datensatz besteht aus einer Sammlung von miteinander verknüpften, aber eigenständigen Daten, die entweder einzeln oder auch gemeinsam aufgerufen und weiterverarbeitet werden können. Jeder Datensatz ist in einer bestimmten Datenstruktur organisiert.  

### referentielle Integrität
- Maßnahmen bei Löschoperationen (Constraints): CASCADE, DENY/RESTRICT, SET NULL
: Referentielle Integrität ist ein Konzept in relationalen Datenbanken, das sicherstellt, dass Datensätze in verschiedenen Tabellen miteinander verknüpft sind und dass keine ungültigen Verknüpfungen bestehen. Dies wird durch die Verwendung von Fremdschlüsseln erreicht. Ein Fremdschlüssel ist ein Schlüssel, der in einer Tabelle verwendet wird, um einen Bezug zu einem Primärschlüssel in einer anderen Tabelle herzustellen.  

Es gibt drei Arten von Regeln für referentielle Integrität:

CASCADE : Wenn ein Primärschlüssel geändert oder gelöscht wird, werden die zugehörigen Fremdschlüssel automatisch geändert oder gelöscht.  
SET NULL : Wenn ein Primärschlüssel gelöscht wird, werden die zugehörigen Fremdschlüssel auf NULL gesetzt.  
RESTRICT : Wenn ein Primärschlüssel gelöscht oder geändert wird, werden die zugehörigen Fremdschlüssel nicht geändert oder gelöscht und es wird ein Fehler ausgelöst.    

Referentielle Integrität sorgt dafür, dass die Daten in Ihrer Datenbank konsistent und vor Inkonsistenzen geschützt sind, und dass die Beziehungen zwischen den Tabellen immer korrekt sind.  

### Replikation erläutern
Replikation ist ein Verfahren, bei dem Daten von einer Datenbank auf eine oder mehrere andere Datenbanken repliziert werden, um sicherzustellen, dass die Daten auf allen Datenbanken identisch sind. Es gibt verschiedene Arten von Replikation wie Einfache Replikation, Mehrfach-Master-Replikation, Transaktionsreplikation und Merge-Replikation, je nach Anwendungsfall und Anforderungen können sie verwendet werden. Replikation wird in vielen Anwendungen verwendet, insbesondere in Umgebungen mit hohen Anforderungen an die Verfügbarkeit und Skalierbarkeit, es ermöglicht die Verteilung der Last auf mehrere Server, die Verwendung von Backup-Datenbanken für den Notfall und die Verbesserung der Leistung.  

### Trigger erklären
: Auslöser, bsp.: Bestand kleiner als X, dann Meldung an Benutzer  

### SQL-Befehle:
- CREATE, ALTER TABLE  
<!-- 왜 검정 바탕화면이 안나오는거지? -->
```sql
CREATE TABLE Tabellenname
( Datenfeld1 Datentyp [Attribut1 Attribut2],
 Datenfeld2 Datentyp [Attribut1 Attribut2],
 PRIMARY KEY (Datenfeld),
 FOREIGN KEY (Datenfeld)
 REFFERENCES Datenbankname.Tabellenname (Datenfeld)
 [ON DELETE {RESTRICT | CASCADE | SET NULL | NO ACTION}]
 [ON UPDATE {RESTRICT | CASCADE | SET NULL | NO ACTION}]
)
ENGINE = INNODB;
CREATE TABLE Persons (
    PersonID int,
    LastName varchar(255),
    FirstName varchar(255),
    Address varchar(255),
    City varchar(255)
);
```
```SQL
ALTER TABLE table_name
ADD column_name datatype;

ALTER TABLE table_name
DROP COLUMN column_name;

ALTER TABLE table_name
RENAME COLUMN old_name to new_name;

ALTER TABLE table_name
ALTER COLUMN column_name datatype;
```
- INSERT, UPDATE, DELETE

```SQL
INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);
```
```SQL
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```
```SQL
DELETE FROM table_name WHERE condition;
```
### SQL-Abfrage
- DDL, DML, DQL, DCL
![Abfrage](/assets/images/sql-commands.jpg)  
- SELECT-Aufbau rauf und runter: FROM, WHERE, JOIN, GROUP BY, HAVING, ORDER BY  

```SQL
---GROUP BY
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
ORDER BY column_name(s);
```
```SQL
---HAVING
SELECT column_name(s)
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s);
```
```SQL
---ORDER BY
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;
```
- Aggregatfunktionen COUNT, SUM, AVG etc
  
```SQL
SELECT COUNT(column_name), AVG(column_name), SUM(column_name)
FROM table_name
WHERE condition;
```

### 
Kardinalitäten: 
Die Kardinalität von Beziehungen definiert, wie viele Entitäten eines Entitätstyps mit genau einer Entität des anderen am Beziehungstyp beteiligten Entitätstyps (und umgekehrt) in Relation (Beziehung) stehen können oder müssen. Die Kardinalität von Beziehungen ist in relationalen Datenbanken in folgenden Formen vorhanden: 1:1 Beziehung, 1:n Beziehung und m:n Beziehung.

```
```

 