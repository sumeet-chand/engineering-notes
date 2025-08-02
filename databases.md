



Troubleshooting DB

1. Check logs → 2. Kill blockers → 3. Restart services → 4. Verify consistency → 5. Inspect OS resources (storage usage/process)


1. For Microsoft SQL Server (MS SQL)
✅ Your steps apply perfectly:

Kill blocking processes → sp_who2, KILL [SPID], or SSMS Activity Monitor.

Check SQL error logs → sp_readerrorlog or SSMS Log Viewer.

Restart services → SQL Server, SQL Agent, VSS Writer, etc.

Check DB consistency → DBCC CHECKDB.