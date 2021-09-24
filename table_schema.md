
CREATE TABLE county_pop (
    fips INT   NOT NULL,
    population FLOAT NOT NULL,
    density FLOAT NOT NULL,
    PRIMARY KEY (fips)
);

CREATE TABLE county_fips (
    county VARCHAR NOT NULL,
    fips INT   NOT NULL,
    PRIMARY KEY (County, fips),
    FOREIGN KEY (fips) REFERENCES county_pop(fips) 
);

CREATE TABLE county_tests_data (
    date DATE NOT NULL, 
    area VARCHAR NOT NULL,
    total_tests FLOAT  NOT NULL,
    positive_tests FLOAT NOT NULL,
    FOREIGN KEY (area) REFERENCES county_fips(county)
);

CREATE TABLE county_cases_data (
    date DATE   NOT NULL,
    area VARCHAR   NOT NULL,
    month VARCHAR   NOT NULL,
    cases FLOAT   NOT NULL,
    deaths FLOAT   NOT NULL,
    FOREIGN KEY (area) REFERENCES county_fips(county)
);

CREATE TABLE county_vac_data (
    county VARCHAR   NOT NULL,
    month VARCHAR   NOT NULL,
    administered_date DATE   NOT NULL,
    fully_vaccinated INT   NOT NULL,
    partially_vaccinated INT   NOT NULL,
    FOREIGN KEY (county) REFERENCES county_fips(county)
);
