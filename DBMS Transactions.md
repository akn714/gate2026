
## **Transactions in DBMS – Short Summary**

A **transaction** is a sequence of database operations (read/write) treated as a single logical unit of work. It must follow the **ACID properties**:
- **Atomicity** – All operations execute completely or none at all.
- **Consistency** – Database remains in a valid state before and after the transaction.
- **Isolation** – Concurrent transactions do not interfere improperly.
- **Durability** – Once committed, changes are permanent.

---
## **Transaction States**
Active → Partially Committed → Committed  
Active → Failed → Aborted

---
## **Schedules**
A **schedule** is the order in which operations of multiple transactions are executed.
- **Serial Schedule** – Transactions execute one after another.
- **Non-serial Schedule** – Operations of transactions are interleaved.
---
## **Serializability**
Ensures that a non-serial schedule produces the same result as some serial schedule.
### Types:
1. **Conflict Serializability**
    - Based on conflicting operations (R/W on same data item).
    - Checked using a **Precedence Graph (Serialization Graph)**:
        - Nodes = Transactions
        - Edge Ti → Tj if Ti’s operation conflicts and occurs before Tj’s.
        - **If graph has no cycle → schedule is conflict-serializable**
        -  If there is loop or cycle in graph then it is conflict serializable
	- **conflict**:
		- r-w
		- w-r
		- w-w
	<img src="./BIN/Pasted image 20260207230941.png">
2. **View Serializability**
    - Based on read-from and final write relationships.
    - More general but harder to test.
---
## **Recoverability**
Ensures safe recovery from failures.
### Types:
1. **Recoverable Schedule**
    - If Tj reads data written by Ti, then **Ti must commit before Tj commits**.
2. **Cascadeless Schedule**
    - Transactions read only committed data.
    - Avoids cascading rollbacks.
3. **Strict Schedule**
    - No transaction can read or write a data item until the last transaction that wrote it commits.
    - Prevents dirty reads and dirty writes.
    - Strict ⊂ Cascadeless ⊂ Recoverable
---
## **Concurrency Control**
Ensures isolation and serializability.
### Common Techniques:
- **Two-Phase Locking (2PL)**
    - Growing Phase: Acquire locks.
    - Shrinking Phase: Release locks.
    - Guarantees conflict serializability.
    - Strict 2PL ensures strict schedules.
- **Timestamp Ordering**
    - Transactions ordered by timestamps.
    - Ensures serializability without locks.
- **Validation-based (Optimistic) Protocol**
    - Read → Validate → Write phases.
---
## **Making Transactions**
Basic operations:
- `BEGIN TRANSACTION`
- `READ(X)`
- `WRITE(X)`
- `COMMIT`
- `ROLLBACK`
---
## **Checking for Serializability (Steps)**
1. Identify conflicting operations.
2. Draw Precedence Graph.
3. Check for cycles:
    - No cycle → Serializable
    - Cycle present → Not serializable
