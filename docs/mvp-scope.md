# MVP scope (MarketingPlanner)

## Goals
Deliver a functional MVP that covers the core workflow: plan, create, approve, schedule, and publish content, while tracking campaigns and tasks with minimal setup.

## Screens (MVP in 10)
1. **Login/Team**: authenticate and select workspace/team.
2. **Dashboard**: today/this week view for upcoming milestones, blocked items, reviews, and quick KPIs (if available).
3. **Editorial Calendar**: month/week views, drag-and-drop scheduling, filter by channel and collection/theme.
4. **Create/Edit Content Piece**: form to define channel, format, objective, schedule, owner, approver, status, assets, and UTM link.
5. **Content Kanban**: board by status with quick updates and assignments.
6. **Campaigns**: list + detail with dates, checklist, budget (optional), and outcomes.
7. **Ideas Backlog**: capture and prioritize ideas with references.
8. **Tasks**: tasks by assignee with due dates and dependencies.
9. **Assets Library**: browse assets with tags and usage rights.
10. **Settings**: manage channels, statuses, roles, and templates.

## Core entities and minimum fields
### Content Piece
- Title
- Channel
- Format
- Objective
- Scheduled date/time
- Owner
- Approver
- Status (Idea → Draft → Production → Review → Approved → Scheduled → Published → Analyzed → Archived)
- Assets (references)
- UTM link

### Campaign
- Name
- Start/end dates
- Checklist
- Budget (optional)
- Status
- Outcome (notes/metrics)

### Task
- Title
- Related content/campaign
- Assignee
- Due date
- Status
- Dependency (optional)

### Asset
- File
- Tags
- Rights (organic/ads)
- Format variants

### User/Role
- Name
- Role (Admin, Marketing Lead, Creator, Operations, Viewer)

### Channel
- Name
- Default format(s)

### Status
- Name
- Order
- Type (content/campaign/task)

## Critical MVP flows
1. **Create content → review → approve → schedule → publish**
2. **Create campaign → checklist → track progress → close out**
3. **Assign tasks → track by assignee → mark done**

## Out of scope (for MVP)
- Full analytics integrations beyond manual KPI entry.
- Advanced automation rules beyond basic notifications.
- Multi-tenant billing and subscription management.
- Complex asset editing or in-app media processing.
