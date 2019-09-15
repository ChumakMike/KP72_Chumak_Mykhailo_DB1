# KP72_Chumak_Mykhailo_DB1

Лабораторна робота № 1.

Ознайомлення з базовими операціями СУБД PostgreSQL

КП-72 Чумак Михайло Сергійович

Варіант 21 - Інтернет Магазин

Сутності:

1. Поставник товарів (Provider)

CREATE TABLE public."Provider"
(
    "ProviderID" integer NOT NULL DEFAULT nextval('"Provider_ProviderID_seq"'::regclass),
    "Name" text COLLATE pg_catalog."default" NOT NULL,
    "Adress" text COLLATE pg_catalog."default" NOT NULL,
    "Phone" text COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT "ProviderID_PK" PRIMARY KEY ("ProviderID")
)

2. Товар (Product)

CREATE TABLE public."Product"
(
    "ProductID" integer NOT NULL DEFAULT nextval('"Product_ProductID_seq"'::regclass),
    "Name" text COLLATE pg_catalog."default" NOT NULL,
    "Category" text COLLATE pg_catalog."default" NOT NULL,
    "Prod_Provider" integer NOT NULL,
    CONSTRAINT "ProductID_PK" PRIMARY KEY ("ProductID"),
    CONSTRAINT "Prod_Provider_FK" FOREIGN KEY ("Prod_Provider")
        REFERENCES public."Provider" ("ProviderID") MATCH FULL
        ON UPDATE CASCADE
        ON DELETE CASCADE
)

3. Покупець (Buyer)

CREATE TABLE public."Buyer"
(
    "BuyerID" integer NOT NULL DEFAULT nextval('"Buyer_BuyerID_seq"'::regclass),
    "Name" text COLLATE pg_catalog."default" NOT NULL,
    "Surname" text COLLATE pg_catalog."default" NOT NULL,
    "Login" text COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT "BuyerID_PK" PRIMARY KEY ("BuyerID")
)
