---
title: Trentino Urban Transportation
---

**Authors:** Diego Barquero Morera ([email](mailto:diego.barqueromorera@studenti.unitn.it)) and Vahan Petrosyan ([email](mailto:vahan.petrosyan@studenti.unitn.it))

## Introduction
This project discusses the development of a Knowledge Graph which aim is to provide an easy and convenient access to the information about bus stops, train stations and timetables of the trips inside the urban area of Trentino region. The project development phases followed the iTelos methodology due to the fact that it ensures the reusability of the resources handled and produced during each stage. 

The final solution has been obtained by the integration of static transportation data from different sources and producing a reusable ontology which are discussed in the following sections. 

## Purpose
The developed Knowledge Graph satisfies the following purpose:

&emsp; *"A person currently in an urban area of Trentino region wants to easily move from one place to another by means of public transportation."*

For this reason, the public transportation of urban areas of the region of Trentino (Italy) over a period of time of 10 months (between September 2022 and June 2023) has been considered.

## Knowledge Resources

Due to the fact that schemas play a crucial role in the knowledge and data integration, they were taken as the initial knowledge resources. For this purpose, [schema.org](https://schema.org/) has been considered for the extraction of entity types:

* [Organization](https://schema.org/Organization)
* [TrainStation](https://schema.org/TrainStation)
* [BusStop](https://schema.org/BusStop)
* [Trip](https://schema.org/Trip)
* [TravelAction](https://schema.org/TravelAction)
* [TrainTrip](https://schema.org/TrainTrip)
* [BusTrip](https://schema.org/BusTrip)
* [Schedule](https://schema.org/Schedule)
* [Event](https://schema.org/Event)
* [Place](https://schema.org/Place)

Besides, the [GTFS documentation](https://developers.google.com/transit/gtfs/reference) has been used along with the above-mentioned schemas as they were not covering the specific properties available in the data.

## Data Resources

The data of urban transportation for the Trentino region has been taken from [Trentino Transporti website](https://www.trentinotrasporti.it). In details, the information about the bus stops and timetables of bus routes were found in the [Open Data section](https://www.trentinotrasporti.it/open-data) which follows the guidelines of the GTFS specifications mentioned before. 

For the urban routes regarding the train service, the information has been extracted from unstructured data sources (i.e. timetables in PDF format) available at [Ferrovia section](https://www.trentinotrasporti.it/viaggia-con-noi/ferrovia). 

In order to describe the bus stops and train stations, additional information, namely seats and covering availability, was simulated following a normal random distribution by means of a Python script.

Finally, the collected data was merged into JSON and CSV format files.

## ER Model

The collected knowledge and data resources have been exploited for the development of Entity Relationships model. This diagram summarized the main aspects that should be covered by the knowledge layer of the final Knowledge Graph and has been used for the next stages.

<img src="./ermodel.png" width="600px" alt="ER model"/>

## ETG

The generation of entity type graph (ETG) has been done by the combination of the teleontology and intermediate ontology which were obtained during the previous phases by Protégé development tool. Some modifications were made, such as reorganization of the e-types, and as a result of these steps, a new schema was obtained, namely a formalized ETG.

The finalization of the ETG considered the sanitization of the entity under non ambiguous identifiers, which will aid in the future reusability of the schema. The KOS tool was used to achieve the language alignment by assigning unique global identifiers (GIDs) to each entity type, following the Universal Knowledge Core (UKC) standard. 

## KG

The final stage includes the development of EG from ETG and the adujusted data by Karmalinker. As a result, the obtained Knowledge Graph includes 6 etypes, 21 data properties and 5 object properties, namely, *has_calendar, has_lines, has_schedule, has_stops and has_trips*.

The final KG has been used for the development of SPARQL queries to answer the Competency Queries. 

## Resources

### Report
<>

### GitHub
<https://github.com/vahanpetrosian/TrentinoUrbanTransportation>

### Google Drive
<>



