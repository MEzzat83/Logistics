```mermaid
graph TD
    subgraph الموردين (Suppliers)
        S1[Suppliers]
    end

    subgraph المستودع الرئيسي (WH)
        WH_Food_Frozen(Food Items - Frozen)
        WH_Food_Ambient(Food Items - Ambient)
        WH_Food_Chilled(Food Items - Chilled)
        WH_Packaging(Packaging Items)
    end

    subgraph المطابخ المركزية (CPKs)
        CPK1
        CPK2
        CPK1_Semi_Finished(Semi-Finished Products - Stores)
        CPK2_Semi_Finished(Semi-Finished Products - Stores)
    end

    subgraph المتاجر (Stores)
        Stores
    end

    S1 -- Store Item (Food - Frozen) --> WH_Food_Frozen
    S1 -- Store Item (Food - Ambient) --> WH_Food_Ambient
    S1 -- Store Item (Food - Chilled) --> WH_Food_Chilled
    S1 -- Store Item (Packaging) --> WH_Packaging

    S1 -- DSD Items (Food - Frozen) --> CPK1
    S1 -- DSD Items (Food - Ambient) --> CPK1
    S1 -- DSD Items (Food - Chilled) --> CPK1

    S1 -- DSD Items (Food - Frozen) --> CPK2
    S1 -- DSD Items (Food - Ambient) --> CPK2
    S1 -- DSD Items (Food - Chilled) --> CPK2

    WH_Food_Frozen -- احتياجات CPKs & Stores --> CPK1
    WH_Food_Ambient -- احتياجات CPKs & Stores --> CPK1
    WH_Food_Chilled -- احتياجات CPKs & Stores --> CPK1
    WH_Packaging -- احتياجات CPKs --> CPK1

    WH_Food_Frozen -- احتياجات CPKs & Stores --> CPK2
    WH_Food_Ambient -- احتياجات CPKs & Stores --> CPK2
    WH_Food_Chilled -- احتياجات CPKs & Stores --> CPK2
    WH_Packaging -- احتياجات CPKs --> CPK2

    WH_Food_Frozen -- احتياجات CPKs & Stores --> Stores
    WH_Food_Ambient -- احتياجات CPKs & Stores --> Stores
    WH_Food_Chilled -- احتياجات CPKs & Stores --> Stores
    WH_Packaging -- احتياجات Stores --> Stores

    CPK1 -- المواد الأولية المتبقية (للفروع) --> Stores
    CPK1 -- Semi-Finished Products (للفروع) --> Stores

    CPK2 -- المواد الأولية المتبقية (للفروع) --> Stores
    CPK2 -- Semi-Finished Products (للفروع) --> Stores

    CPK1 -- استهلاك لإنتاج --> CPK1_Semi_Finished
    CPK2 -- استهلاك لإنتاج --> CPK2_Semi_Finished

```
