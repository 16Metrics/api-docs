Definitions and Terms
=====================

The following is a non exhaustive list of terms used throughout this documentation. Please read this before diving deeper into the docs.

Event
-----
An event is a JSON object containing the details of a state at aparticular point in time. Two major events in the system are **payment** and **refund**.

Event Store
-----------
This is the database that holds the collections of all the events.

Payment Event
-------------
A payment event is typically pushed on a successful charge created by the customer in your app. This can be pushed in realtime or batched for later ingestion. This contains all the data necessary to calculate the required KPIs/Metrics and the identity of the customer.

Refund Event
------------
A refund event is typically pushed on a successful return of the money to the customer. This is recommended to be pushed in realtime. This contains all the data required to complete the context for calculation of required KPIs/Metrics and the identity of the customer.