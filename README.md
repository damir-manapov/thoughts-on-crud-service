# thoughts-on-crud-service

Круд сервис к движку хранения

* Методы
* RLS
* API
* Audit
* Schema with validation
* Statistics
* Impersonation
* Users, roles (ro, rw, access to entities)
* Pass errors of underlaying storage engine
* Handles schema versions (stores for validation, updates if mismatched, retries if schema changed one time)
* Publishes events on changes so one could store them somewhere
* Option to track previous data for audit. Note possible race conditions explicitly
* Do we want to add filters on updates to implement cas on app side?
* Automatic schema reload on given period
* Request id passed downstream
* Schema version in meta
* Non blocking schema update on read operstions

Out of scope
* No migrations
* No schema change

Postpones:
* Tuples

Subprojects:
* Interface
* Integration tests to run against storage engine
