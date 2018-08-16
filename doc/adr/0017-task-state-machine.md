# 17. Task state machine

Date: 2018-08-15

## Status

Proposed

## Context

As outlined in [ADR-0016][adr-0016], the Data Submission Service will use
"tasks" to describe something that a supplier must complete.

Tasks will exist in a state machine that outlines what is happening with them.

Currently, we expect there to be 3 states:

* **unstarted** - must be completed, but there has not been any interaction yet
* **in_progress** - there is something happening with this task at the moment
(eg a supplier has started a submission)
* **completed** - there is nothing further to do on this task

## Decision

The system will model the 3 tasks highlighted above.

Tasks will proceed through the states from `unstarted` to `in_progress` to
`completed`, as shown in the following diagram.

![Task state machine diagram](/doc/diagrams/0017-task-states.jpg)

## Consequences

We will need to model tasks to have this state machine.

This will impact exports to the Data Warehouse.

[adr-0016]: 0016-data-structure-tasks-submissions-entries-and-files.md