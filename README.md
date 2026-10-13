# Oracle APEX Workflow Guide

A practical reference for building workflows and human tasks (approvals) in Oracle APEX 23.2–24.2, written from hands-on experience.

📄 **Guide:** [`apex_workflow_guide.pdf`](apex_workflow_guide.pdf)

## What it covers

- **Tasks:** approval vs. action tasks, task definition actions and events, the Task Details page, participants and roles
- **Life cycles:** task, workflow and activity states and their transitions (with diagram and tables)
- **APIs:** useful views (`APEX_WORKFLOWS`, `APEX_TASKS`, …) and `APEX_HUMAN_TASK` / `APEX_WORKFLOW` examples
- **Patterns:** passing data between tasks, completing tasks from code, workflow parameters vs. variables, development vs. active versions
- **Troubleshooting:** ORA-20987 on task creation, rolling back after termination, automations that don't fire, tasks that users can't see

## Example

Reading a parameter set in one task from a later activity:

```sql
:TASK1_USER := apex_human_task.get_task_parameter_value (
                 p_task_id         => :TASK1_ID,
                 p_param_static_id => 'USER_NAME' );
```

> `APEX_APPROVAL` is deprecated; all examples use `APEX_HUMAN_TASK`.

## Disclaimer

This is a personal, simplified reference, not official documentation. Behaviour can vary between APEX versions and configurations, so always check the [official Oracle documentation](https://docs.oracle.com/en/database/oracle/apex/24.1/htmdb/managing-workflows-and-tasks.html) and test before using anything in production.

## Repository contents

```
├── apex_workflow_guide.pdf   # the guide
└── README.md
```
