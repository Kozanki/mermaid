# Entity Relationship Diagrams

erDiagram
    // Entities
    entity "Tablet Type" {
        "Tablet Type ID" as TTID
        "Name"
        "Storage Space"
        "Display Type"
        "Processor Type ID" as PTID
    }

    entity "Processor Type" {
        "Processor Type ID" as PTID
        "Manufacturer"
        "Manufacturer Code"
    }

    entity "Customer" {
        "Customer ID" as CID
        "Name"
        "Address"
        "Phone"
    }

    entity "Shipped Tablet" {
        "Tablet Serial Number" as SerialNumber
        "Tablet Type ID" as TTID
        "Shipping Date"
        "Customer ID" as CID
    }

    // Relationships
    TTID ||--|{ PTID : "Uses"
    "Tablet Type" ||--o{ "Shipped Tablet" : "Ships"
    "Shipped Tablet" }|--|| "Customer" : "Belongs to"
