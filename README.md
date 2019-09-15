# KP72_Chumak_Mykhailo_DB1
Lab 1 for DB

CREATE TABLE public."Provider"
(
    "ProviderID" integer NOT NULL,
    "Name" text NOT NULL,
    "Adress" text NOT NULL,
    "Phone" text NOT NULL,
    CONSTRAINT "ProviderID" PRIMARY KEY ("ProviderID")
)
