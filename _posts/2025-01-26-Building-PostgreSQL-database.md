---
layout: post
title: How I have built a database in PostgreSQL
subtitle: example codes and output
categories: database
tags: [postgreSQL, database]
---
## How I have built my database

I have created 4 tables using CREATE TABLE function. Below are the SQL codes I used.  
CREATE TABLE Customers (
    CustomerID SERIAL PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    Email VARCHAR(100) UNIQUE NOT NULL,
    VehicleType VARCHAR(50),
    SubscriptionPlan VARCHAR(50),
    RegistrationDate TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    ContactNumber VARCHAR(15)
);
CREATE TABLE EnergyProviders (
    ProviderID SERIAL PRIMARY KEY,
    Name VARCHAR(100) NOT NULL,
    ContactInfo_Email VARCHAR(100),
    ContactInfo_Phone VARCHAR(15),
    EnergyRates DECIMAL(6, 2) NOT NULL,
    ContractStartDate TIMESTAMP NOT NULL
);

CREATE TABLE ChargingStations (
    StationID INTEGER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    Location_Address VARCHAR(255) NOT NULL,
    Location_City VARCHAR(100) NOT NULL,
    Location_Country VARCHAR(100) NOT NULL,
    Capacity DECIMAL(6, 2) NOT NULL, -- kW
    Status VARCHAR(10) DEFAULT 'Active', -- Active/Inactive
    InstallationDate TIMESTAMP NOT NULL,
    ProviderID INTEGER NOT NULL REFERENCES EnergyProviders(ProviderID) ON DELETE CASCADE
);
CREATE TABLE Transactions (
    TransactionID INTEGER GENERATED ALWAYS AS IDENTITY PRIMARY KEY,
    CustomerID INTEGER NOT NULL REFERENCES Customers(CustomerID) ON DELETE CASCADE,
    StationID INTEGER NOT NULL REFERENCES ChargingStations(StationID) ON DELETE CASCADE,
    Timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    EnergyConsumed DECIMAL(6, 2) NOT NULL, -- kWh
    Cost DECIMAL(10, 2) NOT NULL, -- €
    PaymentMethod VARCHAR(50) NOT NULL, -- e.g., Credit Card, PayPal
    ChargingDuration INTEGER NOT NULL -- Minutes
);
