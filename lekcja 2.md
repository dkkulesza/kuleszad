delete from postac where wiek=72;

delete from postac where wiek=47;

alter table walizka drop foreign key walizka_ibfk_1;

alter table przetwory drop foreign key przetwory_ibfk_1;

alter table przetwory drop foreign key przetwory_ibfk_2;

alter table postac DROP  PRIMARY KEY;

ALTER TABLE postac ADD pesel CHAR(11) not null first;

UPDATE postac SET pesel='80031543936' WHERE id_postaci=1;

UPDATE postac SET pesel='20300199369' WHERE id_postaci=2;

UPDATE postac SET pesel='69033178768' WHERE id_postaci=3;

UPDATE postac SET pesel='44992046510' WHERE id_postaci=4;

UPDATE postac SET pesel='55939900234' WHERE id_postaci=5;

UPDATE postac SET pesel='77823443204' WHERE id_postaci=7;

ALTER TABLE postac ADD PRIMARY KEY (pesel);

ALTER TABLE postac MODIFY COLUMN rodzaj ENUM('wiking','ptak','kobieta','syrena');

INSERT INTO postac VALUES ('00240943725', 9, 'Gertruda Nieszczera', 'syrena', '2000-04
-09', 20, NULL, NULL);

UPDATE postac SET statek='knara' WHERE nazwa LIKE '%a%';

UPDATE statek SET max_ladownosc = (max_ladownosc*0.7) WHERE year(data_wodowania) BETWEEN 1900 AND 2000;

ALTER TABLE postac ADD CHECK (wiek<1000);

ALTER TABLE postac MODIFY COLUMN rodzaj ENUM('wiking','ptak','kobieta','syrena','waz');

INSERT INTO postac VALUES ('10261285256', 10, 'Loko', 'waz', '2010-06-12', 3, NULL, NULL);

CREATE TABLE marynarz LIKE postac;

INSERT INTO marynarz SELECT * FROM postac WHERE statek IS NOT NULL;
