# Introduction
BussinessIntelligenceInFootball is final "thesis" project for faculty.  
Full business intelligence project based on data from [Kaggle European Soccer data set](https://www.kaggle.com/hugomathien/soccer).  
Full name of final work is "Business intelligence in football: Modelling, Analysis and Reporting "  
For now work is written just in Bosnian language, but soon it will be translated into English

# Getting Started
European Soccer data set is in NoSql database, for the purpose of project it is extracted in excel, transformed and imported into SQL relational database.  
Data warehouse is designed to analyze success of teams in star schema with 5 dimensions and fact table Golovi.  
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
Inside PowerBI project you can check several types of reports:
* League order (every league has unique report with logo of choosen league)
* Clubs scored and conceded goals over months
* Comparison of clubs on scored and conceded goals over months
* Map
* Comparison of clubs on tactial setup

## League oreder

## Clubs scored and conceded goals over months

## Comparison of clubs on scored and conceded goals over months

## Map

## Comparison of clubs on tactial setup
