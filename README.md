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
