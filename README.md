https://dataexplorer.azure.com/clusters/help/databases/Samples 

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
```
