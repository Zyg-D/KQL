https://dataexplorer.azure.com/clusters/help/databases/Samples 

Cheat sheet: https://docs.microsoft.com/en-us/azure/data-explorer/kusto/query/sqlcheatsheet

Create table

```kql
let FactTable=datatable(name:string,timeprofile:string) [
  "Paul", "10:30",
  "Eric", "8:30",
  "Eric", "9:30",
  "Petra", "9:49"
];
```

Join

```
DimTable
| join FactTable on name
| project name, timeprofile, details
| where surname in ('Cena')
```

Group by, aggregate

```
| summarize AccountName=max(AccountName) by user
```
