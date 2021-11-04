# Introduction
BussinessIntelligenceInFootball is repository for final, thesis, project for faculty.  
It is based on data from [Kaggle European Soccer data set](https://www.kaggle.com/hugomathien/soccer).  
Full name of final work is "Business intelligence in football: Modelling, Analysis and Reporting "  
For now [work](Nerminko-Omanić-IB110010-Final-thesis.pdf) is written just in Bosnian language, but soon it will be translated into English

# Getting Started
European Soccer data set is in NoSql database, for the purpose of project it is extracted in excel, transformed and imported into [SQL relational database](SoccerDB_diagram.png).  
[Data warehouse](SoccerDW_diagramFinal.png) is designed to analyze success of teams based on result of matches in star schema with 5 dimensions and fact table Golovi.  
Integration of data from database to data warehouse using [Microsoft Integration Service](/SoccerDW_IntegrationServices).
For further analyze, based on data warehouse, [tabular model](/SoccerDW_Tabular2) is created with messures and KPI's.
Reporting is done in PowerBI

# Build and Test
1. Import database to your local SQL server using script.
2. Create data warehouse using script set up.
3. Open [Microsoft Integration Project](/SoccerDW_IntegrationServices) with Visual Studio and run packages for loading data.
4. Open [Tabular model](/SoccerDW_Tabular2) with Visual Studio and change source of data to connect to your local data warehouse
5. Open PowerBI project and preview reports.


# Screenshots

## Microsoft Integration Service

### Dimension Clubs (DimKlub)

Flow of data
Translation of sources:
* Klubovi_SaOcjenamaBezDuplih (clubs with tactical setup, which have unique names of clubs)
* SviKlubovi_BezOcjenaBezDuplih (all clubs without tactical setup, which have unique names)  
* Klubovi_SaOcjenamaSamoDuplaImenaKlubova (clubs with tactical setup, just ones which have clubs with same name)
* SviKlubovi_BezOcjenaSamoDupli (clubs without tactical setup, just clubs which names are repeating)  
**NOTE! In data set there are 3 pairs of clubs which have same long name of club, for purpose of analysis their long and short club name is connected into new club name to have all clubs with unique name**
![DimKlub](/IntegrationServicesScreenShoots/DimKlub_DataLoad.png)

Querries for sources
Translation:
* sa mjerenjima (wiht tactical setup)
* bez mjerenja (without tactical setup)
![DimKlubsQuerries](/IntegrationServicesScreenShoots/KlubLoad.png)

### Fact Goals (Fact Golovi)

Flow of data
Translation of sources: 
![FactGolovi](/IntegrationServicesScreenShoots/FactGolovi_DataLoad.png)

## PowerBI

Inside PowerBI project you can check several types of reports:
* League standings (every league has unique report with logo of the league)
* Scored and conceded goals over months
* Comparison of clubs on scored and conceded goals over months
* Map
* Comparison of clubs on tactial setup

### League standings

![England](/ReportsScreenShoots/LeagueStandingsEngland.png)

![Spain](/ReportsScreenShoots/LeagueStandingsSpain.png)

### Scored and conceded goals over months

![Goals](/ReportsScreenShoots/IndividualGoalsGraph.png)
![GoalsTooltip](/ReportsScreenShoots/IndividualGoalsTooltip.png)

### Comparison of clubs based on scored and conceded goals over months

![ComparisonGoals](/ReportsScreenShoots/ComparisonGoals.png)
![ComparisonGoalsToolTip](/ReportsScreenShoots/ComparisonTooltip.png)

### Map

![Map](/ReportsScreenShoots/Map.png)

### Comparison of clubs based on tactial setup

![TacticalComparison](/ReportsScreenShoots/TacticalComparison.png)
