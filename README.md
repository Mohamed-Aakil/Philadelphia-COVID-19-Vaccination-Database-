# Philadelphia-COVID-19-Vaccination-Database
<b> (1) Project Summary </b>

The Philadelphia Covid Vaccination Database tracks vaccination rates in the city of Philadelphia.  With our database we can assist the Philadelphia Department of Public Health (PDPH) in tracking COVID-19 vaccine administration data in the city of Philadelphia. Patient demographic information, the pre-existing conditions of different patient populations, insurance information, vaccine adverse reactions, and other information related to vaccination sites and vaccine administration is captured in our database.  

Specific demographic and area information can be produced from our database for all residents of the city of Philadelphia. Consequently, these reports can be utilized by the Philadelphia Department of Public Health for targeted ad campaigns in hopes of improving vaccination rates in the city. Additionally, the patient pre-existing conditions can help to determine priority of distribution for new vaccines to particularly vulnerable groups. The Philadelphia Covid Vaccination Database can also produce reports about specific vaccination sites in the city, including which ones are receiving the most traffic, and which licensed medical professionals are helping to vaccinate the most patients. Additionally, our database will be able to track patient adverse reactions to the vaccine made by each of the vaccine manufacturers. This information can again be utilized by PDPH for public awareness about common reactions to the vaccine to help increase transparency and trust in the city’s COVID-19 vaccination campaign. Finally, we also track vaccine manufacturer sites and vaccine shipments to ensure quality control in vaccine doses and document vaccine costs on the individual vaccination site level for future budgets and resource allocation.  

As the COVID-19 pandemic is still ongoing and continues to be a dynamic situation, this database has been designed with flexibility in mind. There is no limit on the maximum number of vaccine doses patients may receive, as new booster shots continue to be made available to the public. Additionally, we have opted to track anyone who has received a vaccine within the city of Philadelphia, not just registered residents. This helps to determine allocation of resources and could be important when coordinating vaccination efforts with other departments of public health in surrounding areas.

<b> (2) Project Statement </b>

<b> 2.1 Overall Goals of the System </b>

- This project is a COVID-19 vaccine database system designed for the city of Philadelphia. The system will store information regarding vaccine administration to depict vaccination levels within the different locales of Philadelphia. The goal of this system is to assist the Philadelphia Department of Public Health in tracking COVID-19 vaccine administration data in the city of Philadelphia, patient demographic information, the pre-existing conditions of different patient populations, vaccine adverse reactions, and other information related to vaccination sites and vaccine administration.  

 

<b> 2.2 Context and Importance of the System </b>

- Many people within the United States still refuse to get vaccinated against COVID-19, while others still have not received the full COVID-19 vaccine regimen. According to the CDC, only 80% of the eligible US population has received 1 COVID-19 vaccine dose, while only 68.2% have completed their primary series (CDC, 2020). Creating one system that tracks patient vaccination data across different patient demographics would allow for a coordinated effort across different Philadelphia Department of Public Health divisions to create public health campaigns for COVID-19 vaccination and increase vaccination rates within the city. 
- Because we have opted to also track individual vaccine administrators and vaccination site data in this system, we would be able to see which vaccination sites and their employees were most successful in vaccinating their patient populations and identify these sites as clinics of interest to study. Additionally, we would be able to track which vaccines are received the most by patients (Pfizer, Moderna, J&J, etc.), potentially helping the city of Philadelphia to make informed purchasing decisions of vaccines. The system we have designed would also help the city of Philadelphia with mandatory reporting on COVID-19 vaccination information to state and national level government entities. 

 

<b> 2.3 Scope of the Project  </b>

<b> 2.3.1 In-Scope </b>

- This system will store data about patients in the city of Philadelphia (regardless of whether they have received a vaccine dose or not), patient pre-existing conditions, patient adverse reactions to vaccines, and the insurance plans of patients. We will store data about patients’ vaccination status, which could be either vaccinated, partially vaccinated, fully vaccinated, fully vaccinated with a single booster, or fully vaccinated with a double booster, and their vaccination card record. 
- We will also store data about individual vaccine doses and their manufacturers and the shipment the vaccines were received in. Finally, we will track data about where vaccine doses were administered and who administered the dose to each patient.  

<b> 2.3.2 Out-of-Scope </b>

- This system will only store data on patients who were vaccinated within the city of Philadelphia, not Philadelphia residents who have been vaccinated at other sites outside of the city limits. This system also will not store information regarding billing insurance companies for vaccines nor total costs associated with purchasing and administering vaccines. Additionally, this database does not track reporting of adverse events experienced by patients after vaccination to the manufacturing company. 

 

<b> 2.4 Related systems and any open-source tools  </b>

- This project was inspired by the COVID-19 vaccination information depicted on the Philadelphia Department of Public Health’s website (Vaccine data | Programs and initiatives). Additionally, a related system called PhilaVax, run by the City of Philadelphia, tracks Philadelphia citizen vaccination data for all diseases (Philavax). Finally, this system could be used to report to the Pennsylvania Department of Health’s COVID-19 Vaccine Dashboard (COVID-19 Vaccine Dashboard.). We designed the Entity Relationship Diagram using the https://app.diagrams.net/  open source tool. 

<b> (3) REQUIREMENTS SPECIFICATION </b>

<b> 3.1 Data Requirements  </b>

- The Philadelphia Covid Database system needs to track information for every patient that enters the database. Patient Government ID, first name, last name, date of birth, gender, race, address, and residency status. Also, we need to be able to record current patient medical conditions. Disease name, date of disease onset and the type of disease will be recorded. 

- The database needs to track information regarding vaccine manufacturers, siteID (building identifier), the name of the pharmaceutical company producing the vaccine, and the location (street, city, state, and zip). 

- Vaccine manufactures will produce shipments of their vaccine to send to vaccination sites and for each shipment tracking information will be needed, quantity shipped, cost, shipment date, storage temperature, expiration date, and the batch number. 

- For a given vaccine received by a patient the covid database needs to record the serial number, vaccine name, and the date the vaccine was administered, in addition to who administered the shot, where it was given, and which shipment it arrived in. 

- For each patient who receives a vaccine the database needs to track if an adverse reaction took place, and we need to know the vaccine serial number for the suspected shot, reaction name, reaction type, and reaction onset date and end date. 

- After a vaccine is administered a patient will receive a vaccine card with a record number and activation date. 

- The covid database needs to store information on vaccination sites. Location ID (building number), site name, location (street, city, state, and zip), and site type need to be recorded. Vaccine sites can be either hospitals, pharmacies, or clinics. 

- Information about vaccine administrators and where they are employed will also be tracked by the covid database. The database will need practitioner license numbers, first name, last name, and credentials. 

- Lastly the covid database will need to record insurance information for each patient in the database. Insurance member number, group number and insurance carrier name will be tracked.  

 
 

<b> 3.2 Business Rules and Logic </b> 

- Each Patient can suffer from zero or many conditions and each condition can at most be suffered from one patient. 

- Each patient can receive zero to many vaccine doses and each vaccine dose can be given to zero or one patient. When a vaccine is given to a patient their vaccine number is incremented. 

- Each patient can have zero to one vaccine card (depending on vaccination status) and a vaccine card will be given to one patient. 

- Each patient will be covered by zero to one insurance plans and insurance plans can cover that patient once. 

- A vaccination site can order zero or many vaccine shipments and each shipment can be delivered to only one vaccination site. 

- A vaccination site provides one to many vaccines and a vaccine dose comes from only one vaccination site  

- A vaccinator can work for one-to-many vaccination sites and vaccination sites can have zero to many vaccination workers. 

- A vaccinator can administer zero to many vaccines and a vaccine can be administered by only one vaccinator. 

- A vaccine card records one to many vaccine doses and a vaccine can only be recorded on one vaccine card. 

- A vaccine shipment contains one to many vaccine doses and a vaccine dose will come from only one vaccine shipment  

 

<b> 3.3 Other Assumptions </b>

- It is assumed that only one vaccine card will be given to a patient, though in real world situations vaccine cards are lost or destroyed all the time and patients may receive more than one. 

- A patient can receive multiple shots from different vaccination sites. 

- Presumably our database would have all Philadelphia resident information already. That is how we would be able to track unvaccinated residents in this system. 

- The Covid database would focus on Philadelphia residents, however, we expect not all patients will be from Philadelphia and that is why we track resident status. 

- We assume each patient waits for the proper inoculation time between vaccination shots and they are of proper age to receive the vaccine.  

 

<b> 3.4 How Data Was Obtained </b>

- Patient – Data was acquired from the Kaggle website, and a random generator was used for government patient government IDs. 

- Patient Condition – Random afflictions were chosen, and patients were randomly assigned according to their age and their gender. 

- Insurance Plan - insurance carrier names were picked from active insurance companies, member and group numbers were generated in random string generators 

- Manufacturer – Data was randomly generated using a string generator. Manufacturer names were picked from active vaccine manufacturer companies. 

- Vaccine Site – Real location and addresses were used that actively provide COVID-19 vaccines in Philadelphia. 

- Vaccine Shipment – Data was randomly generated using a string generator. 

- Vaccinator - Data was randomly generated using a string generator. 

- Vaccine Card - the activation date chosen was the same as the date of the first vaccine for each vaccinated patient that was tracked in the system, record numbers were generated in a random string generator 

- Vaccine Dose - Data was randomly generated using a string generator. 

<b> Conceptual ERD </b>



![Project Conceptual ERD](https://user-images.githubusercontent.com/96182727/206881086-88eca4fd-a576-4e91-8d9c-7f78972f25e9.png)

<b> Explanations on the ERD  </b>

- A patient may or may not suffer from a pre-existing condition prior to receiving a vaccine. As a pre-existing condition cannot exist independently of a patient, it is treated as a weak entity with optional participation. 

- Post first vaccination, every patient will receive a vaccine card which contains details about the vaccines administered to that patient. Because we are tracking both vaccinated and unvaccinated individuals, there is optional participation for a patient in the vaccine card. 

- Additionally, post vaccination, patients may or may not experience adverse reactions. Without an instance of a patient receiving a vaccine, an adverse reaction would not exist and thus, data associated with adverse reactions to a vaccine are treated as relationship attributes on the patient-vaccine relationship. 

- In Philadelphia, a patient may or may not have insurance, which is marked by optional participation for a patient in the insurance plan relationship. 

- A patient’s vaccination status could be either unvaccinated, partially vaccinated, fully vaccinated, fully vaccinated with a single booster, or fully vaccinated with a double booster, and is tracked in the patient-vaccine dose relationship as a relationship attribute “patientVaccineNumber” to indicate which Covid vaccination in the series this was for the patient. 

- We have assumed that a vaccination center could have all types of vaccines.  

- A pharmaceutical company that makes COVID-19 vaccines could have multiple locations that manufacture and ship vaccines, each of which is uniquely identified by a siteID in the manufacturer entity. 

- Vaccines arrive at a vaccination site in a shipment. Each batch of vaccines could be split into multiple shipments, which is why we decided to use the vaccine shipment tracking number as the partial primary key of a vaccine shipment. 

- A vaccinator can work for multiple vaccination sites and a vaccination site could have multiple vaccinators employed, reflected in the many to many relationships between these entities.  

![info605_Final_ERD-Logical ](https://user-images.githubusercontent.com/96182727/206881141-42c7895e-0643-41c3-9c68-24b41a985634.png)

<b> 5.2 Relational Schema </b>

- Patient (patientGovtID, firstName, lastName, DOB, gender, race, street, city, state, zip, resident) 

- PatientCondition (patientGovtID, diseaseName, dateOfOnset, diseaseType) 

Foreign key patientGovtID references Patient (patientGovtID) 

- InsurancePlan (insuranceMemberNumber, groupNumber, carrierName, patientGovtID) 

Foreign key patientGovtID references Patient (patientGovtID) 

- Manufacturer (siteID, pharmaceuticalCompany, street, city, state, zip) 

- VaccinationSite (locationID, siteName, street, city, state, zip, type) 

- VaccineShipment(siteID, trackingNumber, batchNumber, quantity, cost, shipmentDate, storageTemperature, expirationDate, locationID) 

Foreign key siteID references Manufacturer (siteID) 

Foreign key locationID references VaccinationSite (locationID) 

- Vaccinator (licenseNumber, firstName, lastName, credentials) 

- Employment (licenseNumber, locationID) 

Foreign key licenseNumber references Vaccinator (licenseNumber) 

Foreign key locationID references VaccinationSite (locationID) 

- VaccineCard (recordNumber, activationDate, patientGovtID) 

Foreign key patientGovtID references Patient (patientGovtID) 

- VaccineDose (serialNumber, vaccineName, administeredDate, patientGovtID, locationID, licenseNumber, shipmentID, vaccineCardNumber, patientVaccineNumber, adverseReactionType, adverseReactionDescription, adverseReactionBeginDate, adverseReactionEndDate) 

Foreign key patientGovtID references Patient (patientGovtID) 

Foreign key locationID references VaccinationSite (locationID) 

Foreign key licenseNumber references Vaccinator (licenseNumber) 

Foreign key shipmentID references VaccineShipment (siteID, trackingNumber) 

Foreign key vaccineCardNumber references VaccineCard (recordNumber) 

<b> (4) DATA DICTIONARY </b>

<b> 4.1 Data Dictionary </b>
<img width="838" alt="Screenshot 2022-12-10 at 7 49 30 PM" src="https://user-images.githubusercontent.com/96182727/206881454-31003aa8-6fcf-40ae-a4d8-e28e10ca26ec.png">

<b> 4.2 Patient </b>

<img width="802" alt="data dictionary - patient" src="https://user-images.githubusercontent.com/96182727/206881685-8f86e376-621f-431d-aa1f-5aeb855aadf4.png">

<b> 4.3 Patient Condition </b>

<img width="836" alt="patient condition" src="https://user-images.githubusercontent.com/96182727/206881713-9648f45f-081a-4ab4-9a09-3b3767f01359.png">

<b> 4.4 Insurance Plan </b>

<img width="803" alt="insurance Plan" src="https://user-images.githubusercontent.com/96182727/206881734-ec83e1c4-65bb-4916-b8a3-2cee83997303.png">

<b> 4.5 Manufacturer </b>

<img width="805" alt="data dictionary manufacturer" src="https://user-images.githubusercontent.com/96182727/206881761-adc85602-6eb4-4269-8c5c-4a2f58a3ebe9.png">

<b> 4.6 Vaccine Site </b>

<img width="590" alt="vaccine site" src="https://user-images.githubusercontent.com/96182727/206881829-737c8731-7e6d-43e2-a043-2e581f5336be.png">

<b> 4.7 Vaccine Shipment </b>

<img width="796" alt="vaccineshipment" src="https://user-images.githubusercontent.com/96182727/206881843-5866610c-325f-4f55-977d-b6386c15a3b9.png">

<b> 4.8 Vaccinator </b>

<img width="802" alt="vaccinator" src="https://user-images.githubusercontent.com/96182727/206881851-cbdad549-8893-4607-ab1e-3d8cdfb71d33.png">

<b> 4.9 Employment </b>

<img width="783" alt="employement" src="https://user-images.githubusercontent.com/96182727/206881872-e9a5a512-14e8-43eb-8c51-bee500658975.png">

<b> 4.10 Vaccine Card </b>

<img width="782" alt="vaccinecard" src="https://user-images.githubusercontent.com/96182727/206881879-2a77e3bb-bd92-4bf0-99af-2e59a3790023.png">

<b> 4.11 Vaccine Dose </b>

<img width="607" alt="Vaccinedose" src="https://user-images.githubusercontent.com/96182727/206881884-1ff21f29-41e3-4b19-9a69-7e94dd541559.png">

<b> (5) Implmentation </b>

<b> 5.1 Data Queries </b>

<b> 5.1.1 Find the Age of patients with Chronic Disease. List lname, fname, and disease name. Sort by patient lname. </b>

<img width="831" alt="Screenshot 2022-12-04 at 5 19 49 PM" src="https://user-images.githubusercontent.com/96182727/206882416-e42edbe1-1ad2-47ce-beda-ff88df032570.png">

<b> 5.1.2 which is the least used vaccine name along with its administered date and their record number? </b>

<img width="1034" alt="Screenshot 2022-12-04 at 5 20 41 PM" src="https://user-images.githubusercontent.com/96182727/206882454-e9094d79-dcee-453a-bc0a-40351a4d93a5.png">

<b> 5.1.3 Patients who are residents of Philadelphia with activation date between 01-NOV-2020 to 01-JAN-2022 and their address? </b>

<img width="902" alt="Screenshot 2022-12-04 at 5 24 12 PM" src="https://user-images.githubusercontent.com/96182727/206882470-e7666a85-fb8c-4809-a585-40db3185cd77.png">

<b> 5.2 Data Manupilation Queries </b>

<b> 5.2.1 Scenario: If the data has been entered wrong by mistake in the patient condition and need to update it. </b>

<img width="498" alt="Screenshot 2022-12-04 at 6 17 19 PM" src="https://user-images.githubusercontent.com/96182727/206882516-ad81cd23-8b41-47f4-83cb-0ecae8281d06.png">

<img width="582" alt="Screenshot 2022-12-04 at 6 21 27 PM" src="https://user-images.githubusercontent.com/96182727/206882521-faa2ad5b-ac38-4fbc-9272-2c65ca606076.png">

<b> 5.2.2 Scenario: If no longer required to keep track of the patient condition with diabetes? </b>

<img width="633" alt="Screenshot 2022-12-04 at 6 38 13 PM" src="https://user-images.githubusercontent.com/96182727/206882537-a19c2fd2-54ed-4994-866d-984dc9f49caa.png">

<b> (6) SUMMARY </b>
- Being new to SQL and coding this course and project has put me through a lot of learning, understanding the core concept of SQL and its wide applications. This project helped me learn the important concepts of developing a database from scratch and on how to overcome the real life challenges while developing a database. I learnt SQL commands from both the data query and data manipulation side along with the conceptual and logical ERD. We faced some issues while translating the conceptual ERD to logical ERD with foreign keys and partial primary keys but we learned together on how to solve it. The data insertion and table creation had some issues with the value assignment like using BIT operator or VARCHAR for certain data like Resident and Gender on the Patient table where we use only two values to determine the state. The query writing part was challenging for me as that part was making me think about all the possibilities of insights that can be derived from our database and its wide application in real life to solve the problems. We also made use of Excel sheets for initial data gathering and generation. It also helped us to keep track of the tables and the values that had to be entered on the table. We designed the database in a way that it can be put for real use in the future with the actual population data with very few minor changes. The database can be used as even a reference for future developments in the different domains and it can be expanded to derive useful insights. This can be used by the public health department to track the health condition of the patient both before and after getting vaccinated. The insights can be used to take precautionary measures and try to improve the vaccination status by various categories.

- This project was an excellent experience in helping to understand the level of detail and preparation required to implement a professional-use relational database. It was extremely helpful to go through the sequential process of creating the conceptual ERD, then relational schema, then logical ERD, and I continued to return to these diagrams as I wrote my DML create-table commands. I also learned the importance of keeping performance and pertinent queries in mind when constructing the database design. For example, we struggled as a group on where to place data related to patient adverse reactions. Eventually, with Professor Song’s help, we placed this information on individual vaccine instances themselves as these are results of an individual vaccine dose, and this data, if not null, will always need to be queried together. Some of the difficulties we encountered as a group included formatting data into plain text for insert statements into our Oracle Database and mapping foreign-key to primary-key chains in our sample data. We originally created all sample data in an excel spreadsheet, and this created difficulties when trying to import the data through insert statements into the database due to unexpected (and oftentimes invisible) characters. We also had to be extremely careful when implementing the insert statements that were dependent on foreign key constraints. This was a lesson in the importance of having clean and well-checked data before attempting to insert into a database. If we had more time, I would have loved to conduct a more in-depth query from the publicly available Philadelphia Department of Public Health Database and attempt to process then import that data into our own database for practice with cleaning data and attempting larger and more complex queries.

 <b> (7) References </b>

- CDC. (2020, March 28). COVID Data Tracker. Centers for Disease Control and Prevention. https://covid.cdc.gov/covid-data-tracker/#vaccinations_vacc-people-additional-dose-totalpop 

- COVID-19 Vaccine Dashboard. Department of Health. (n.d.). Retrieved October 26, 2022, from https://www.health.pa.gov/topics/disease/coronavirus/Vaccine/Pages/Dashboard.aspx 

- Philavax. Philadelphia Immunization Program. (n.d.). Retrieved October 26, 2022, from https://vax.phila.gov/index.php/our-programs/philavax/  

- Vaccine data | Programs and initiatives. (n.d.). City of Philadelphia. Retrieved October 26, 2022, from https://www.phila.gov/programs/coronavirus-disease-2019-covid-19/vaccines/vaccine-data/ 
