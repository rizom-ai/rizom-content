filters:
  and:
    - file.inFolder("newsletter")
views:
  - name: All Newsletters
    order:
      - file.name
      - subject
      - status
      - entityIds
      - scheduledFor
      - sentAt
      - buttondownId
      - sourceEntityType
    type: table
  - groupBy:
      direction: ASC
      property: status
    name: By Status
    order:
      - file.name
      - subject
      - status
      - entityIds
      - scheduledFor
      - sentAt
      - buttondownId
      - sourceEntityType
    type: table
