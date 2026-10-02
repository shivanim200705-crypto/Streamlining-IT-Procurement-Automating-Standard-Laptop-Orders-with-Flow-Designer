# Flow Design Notes – Standard laptop task

## Flow Metadata

| Property | Value |
|----------|-------|
| Name | Standard laptop task |
| Application | Global |
| Status | Active |
| Trigger | Service Catalog |
| Run as | System |

## Trigger Configuration

- **Type:** Service Catalog
- **Catalog Item:** Standard Laptop
- **Available Data Pills:**
  - Requested Item Record
  - Run Start Time UTC
  - Table Name
  - Run Start Date/Time

## Action: Create Catalog Task

| Input | Value |
|-------|-------|
| Table Name | Catalog Task [sc_task] |
| Requested Item | Trigger → Requested Item Record |
| Short Description | Laptop need to Configured |
| Description | Laptop need to Configured |

## Observed Runtime Behaviour

| Record | Number | Key Fields |
|--------|--------|------------|
| Requested Item | RITM0010004 | Item = Standard Laptop, Stage = Request Approved, State = Open |
| Catalog Task | SCTASK0010002 | Short description = Laptop need to Configured, Assignment group = Hardware, State = Open, Active = true |

## Related List Verification

On RITM0010004 → Related Links → Catalog Tasks (1):

- Number: SCTASK0010002
- Assignment group: Hardware
- Assigned to: (empty)
- Short description: Laptop need to Configured
- Actual start: populated
- Actual end: empty

## Screenshots Reference

| File | Description |
|------|-------------|
| `evidence/01-flow-designer-standard-laptop-task.png` | Flow Designer UI showing trigger and Create Catalog Task action |
| `evidence/02-catalog-task-sctask0010002.png` | SCTASK form view |
| `evidence/03-requested-item-ritm0010004.png` | RITM form view with variables |
| `evidence/04-ritm-related-catalog-tasks.png` | Related list of Catalog Tasks under the RITM |
