# Useful KQL Queries

## PowerShell Activity

```kql
process.name:"powershell.exe"
```

## MSI Execution

```kql
process.command_line:*msi*
```

## cURL Activity

```kql
process.name:"curl.exe"
```

## Registry Activity

```kql
process.name:"reg.exe"
```

## Scheduled Tasks

```kql
process.command_line:*schtasks*
```

## Authentication Activity

```kql
event.category:"authentication"
```
