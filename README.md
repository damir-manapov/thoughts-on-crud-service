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
* Whether to return processed entity
* Ignore duplicates on create many, update many option

Out of scope
* No migrations
* No schema change
* We don't want return resulted entiti on update/create, it affects performance. Or maybe we should give ability to user set such parameter still?
* Replace for full rewrite entry by provided values, update to merge provided values to previous ones
* Expressions in update (+1 for example). Can't be performed due to uniqueness by in different database

Postpones:
* Tuples

Subprojects:
* Interface
* Integration tests to run against storage engine

Mass operations similar to Etl load are expected to be handled by different mechanism, that should respect all storage constraints on its own
