# Project-Java-OOP-DB
CREATE TABLE Airlines (
    airline_id IDENTITY PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    country VARCHAR(100) NOT NULL
);
CREATE TABLE Aircrafts (
    aircraft_id IDENTITY PRIMARY KEY,
    model VARCHAR(100) NOT NULL,
    manufacturer VARCHAR(100) NOT NULL,
    capacity INT NOT NULL,
    airline_id INT NOT NULL,
    FOREIGN KEY (airline_id) REFERENCES Airlines(airline_id)
);
CREATE TABLE Flights (
    flight_id IDENTITY PRIMARY KEY,
    flight_number INT NOT NULL,
    airline_id INT NOT NULL,
    aircraft_id INT NOT NULL,
    departure_country VARCHAR(100) NOT NULL,
    arrival_country VARCHAR(100) NOT NULL,
    departure_time TIMESTAMP NOT NULL,
    arrival_time TIMESTAMP NOT NULL,
    FOREIGN KEY (aircraft_id) REFERENCES Aircrafts(aircraft_id),
    FOREIGN KEY (airline_id) REFERENCES Airlines(airline_id)
);
