# orai_sqlo
SELECT "Hello world!";
.open orszagok.db
--Mi MADAGASZKÁR fővárosa?
--SELECT Fovaros FROM orszagok WHERE Orszag == "MADAGASZKÁR"; Antananarivo

--Melyik ország fővárosa OUAGADOUGOU?
--SELECT Orszag FROM orszagok WHERE Fovaros == "OUAGADOUGOU"; Burkina Faso

--Melyik ország autójele a TT?
--Select Orszag From orszagok WHERE Autojel == "TT"; Trinidad es tobago

--Melyik ország pénzének jele az SGD?
--Select Orszag From orszagok WHERE Penzjel == "SGD"; Szingapur

--Melyik ország nemzetközi telefon-hívószáma a 61?
--Select Orszag From orszagok WHERE Telefon == 61; AUSZTRÁLIA

--Mekkora területű Monaco?
 --SELECT Terulet FROM orszagok WHERE Orszag == "MONACO" 1.95

--Hányan laknak Máltán?
--SELECT Nepesseg From orszagok WHERE orszag == "MÁLTA"   392

--Mennyi Japán népsűrűsége?
--SELECT Nepesseg From orszagok WHERE Orszag == "JAPÁN" 127600

--Hány lakosa van a Földnek?
--SELECT SUM(nepesseg) From orszagok 7076338

--Mennyi az országok területe összesen?
--SELECT SUM(Terulet) FROM Orszagok  133598224.66

--Mennyi az országok átlagos népessége?  
--SELECT AVG(Nepesseg) from orszagok 36475.9690721649

--Mennyi az országok átlagos területe?
--SELECT AVG(Terulet) from orszagok 688650.64257732

--Mennyi a Föld népsűrűsége?
--SELECT SUM(Nepesseg) / SUM(Terulet) * 1000 from orszagok 53

--Hány 1.000.000 km2-nél nagyobb területű ország van?
--SELECT Count(*) from orszagok where Terulet > 1000000         29

--Hány 100 km2-nél kisebb területű ország van?
--SELECT Count(*) from orszagok where Terulet < 100        5

--Hány 20.000 főnél kevesebb lakosú ország van?
--SELECT Count(*) FROM orszagok WHERE Nepesseg <= 20000 143

--Hány országra igaz, hogy területe kisebb 100 km2-nél,
--vagy pedig a lakossága kevesebb 20.000 főnél?
--SELECT Count(*) FROM orszagok WHERE Terulet < 100 OR Nepesseg <20000     143

--Hány ország területe 50.000 és 150.000 km2 közötti? 
--SELECT count(*) FROM orszagok where Terulet BETWEEN 50000 AND 150000         35

--Hány ország lakossága 8 és 12 millió közötti?
--SELECT count(*) FROM orszagok WHERE Nepesseg BETWEEN 8000 AND 12000      23

--Mely fővárosok népesebbek 20 millió főnél?
--SELECT Fovaros FROM orszagok WHERE NEP_fovaros > 20000   TOKIO MEXIKOVAROS

--Mely országok népsűrűsége nagyobb 500 fő/km2-nél?
--SELECT Orszag FROM orszagok WHERE Nepesseg / Terulet * 1000 > 500 MÁLTAMONACO VATIKÁN  BANGLADES NAURU SZINGAPÚR MALDIV-SZIGETEK

--Hány ország államformája köztársaság?
--SELECT Count(*) FROM orszagok WHERE Allamforma == "köztársaság"    76

--Mely országok pénzneme a kelet-karib dollár?
--SELECT Orszag FROM orszagok WHERE Penznem = "kelet-karib dollár" SAINT LUCIA
--SAINT VINCENT ÉS GRENADINE GRENADA ANTIGUA ÉS BARBUDA DOMINIKAI KÖZÖSSÉG SAINT KITTS ÉS NEVIS

--Hány ország nevében van benne az "ORSZÁG" szó? 
--SELECT Count(0) FROM orszagok WHERE orszag LIKE '%ORSZÁG'    17

--Mely országokban korona a hivatalos fizetőeszköz?
--SELECT Orszag FROM orszagok WHERE Penznem  LIKE "%korona" NORVÉGIA SVÉDORSZÁG CSEHORSZÁG DÁNIA IZLAND

--Mennyi Európa területe?
SELECT Terulet from orszagok WHERE Foldr_hely = "EURÓPA"
