```mermaid
erDiagram
    CUSTOMER {
        int customer_id PK "Primary Key"
        string name
        string email
        string phone_number
    }

    PRODUCT {
        int product_id PK "Primary Key"
        string model_name
        string size
        decimal price
    }

    SALES {
        int sale_id PK "Primary Key"
        int customer_id FK "Foreign Key"
        int product_id FK "Foreign Key"
        date sale_date
        int quantity
    }

    INVENTORY {
        int inventory_id PK "Primary Key"
        int product_id FK "Foreign Key"
        int stock_level
    }

    CUSTOMER ||--o{ SALES : "makes"
    PRODUCT ||--o{ SALES : "is sold in"
    PRODUCT ||--|| INVENTORY : "has"



