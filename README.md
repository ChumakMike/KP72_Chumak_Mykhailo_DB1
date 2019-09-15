# KP72_Chumak_Mykhailo_DB1

Лабораторна робота № 1.

Ознайомлення з базовими операціями СУБД PostgreSQL

КП-72 Чумак Михайло Сергійович

Варіант 21 - Інтернет Магазин

Сутності:

1. Поставник товарів (Provider)

CREATE TABLE public."Provider"
(
    "ProviderID" integer NOT NULL,
    "Name" text COLLATE pg_catalog."default" NOT NULL,
    "Adress" text COLLATE pg_catalog."default" NOT NULL,
    "Phone" text COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT "ProviderID" PRIMARY KEY ("ProviderID")
)

2. Товар (Product)

CREATE TABLE public."Product"
(
    "ProductID" integer NOT NULL,
    "Name" text COLLATE pg_catalog."default" NOT NULL,
    "Category" text COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT "ProductID" PRIMARY KEY ("ProductID"),
    CONSTRAINT "Prod_Provider" FOREIGN KEY ("ProductID")
        REFERENCES public."Provider" ("ProviderID") MATCH SIMPLE
        ON UPDATE NO ACTION
        ON DELETE NO ACTION
)

3. Покупець (Buyer)

CREATE TABLE public."Buyer"
(
    "BuyerID" integer NOT NULL,
    "Name" text COLLATE pg_catalog."default" NOT NULL,
    "Surname" text COLLATE pg_catalog."default" NOT NULL,
    "Login" text COLLATE pg_catalog."default" NOT NULL,
    CONSTRAINT "BuyerID" PRIMARY KEY ("BuyerID")
)
