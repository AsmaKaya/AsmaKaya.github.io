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


#Description of the diagram:

A Customer can make multiple Sales
A Product can be part of multiple Sales
A Product has one corresponding Inventory 
This ERD serves as an efficient model for the shoe store's database structure, facilitating management of customers, sales transactions, and inventory levels.
