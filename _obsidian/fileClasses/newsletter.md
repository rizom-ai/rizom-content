---
fields:
  - id: subject
    name: subject
    type: Input
  - id: status
    name: status
    options:
      '0': generating
      '1': draft
      '2': queued
      '3': published
      '4': failed
    type: Select
  - id: entityIds
    name: entityIds
    type: Multi
  - id: scheduledFor
    name: scheduledFor
    type: Input
  - id: sentAt
    name: sentAt
    type: Input
  - id: buttondownId
    name: buttondownId
    type: Input
  - id: sourceEntityType
    name: sourceEntityType
    type: Input
filesPaths: newsletter
---
