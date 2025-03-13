erDiagram
    USER ||--|| PATIENT : Uses
    CUSTOMER ||--o{ ORDER : places
    CUSTOMER ||--o{ INVOICE : "liable for"
    DELIVERY_ADDRESS ||--o{ ORDER : receives
    INVOICE ||--|{ ORDER : covers
    ORDER ||--|{ ORDER_ITEM : includes
    PRODUCT_CATEGORY ||--|{ PRODUCT : contains
    PRODUCT ||--o{ ORDER_ITEM : "ordered in"