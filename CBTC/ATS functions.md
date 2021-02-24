

# [CBTC ATS functions]()


## ATS functions Summary

```js
  - 6.3 ATS functions
  - 6.3.1 General
  - 6.3.2 ATS user interface
  - 6.3.3 CBTC train identification and train tracking
  - 6.3.4 Train routing
  - 6.3.5 Automatic train regulation
  - 6.3.5.1 Schedule/headway regulation
  - 6.3.5.2 Junction management
  - 6.3.5.3 Energy optimization

  - 6.3.6 Station stop functions
  - 6.3.6.1 Stop train at next station
  - 6.3.6.2 Hold train at station
  - 6.3.6.3 Skip station stop

  - 6.3.7 Restricting train operations
  - 6.3.7.1 Stopping a train enroute
  - 6.3.7.2 Temporary speed restrictions
  - 6.3.7.4 Work zones

  - 6.3.8 Passenger information system interfaces
  - 6.3.9 Fault reporting
  - 6.3.9.1 CBTC fault reporting
```


## 6.3 ATS functions
### 6.3.1 General
If specified by the authority having jurisdiction, a CBTC may interface to, or be integrated with, an ATS system. Under such circumstances, and to the extent specified by the authority having jurisdiction, CBTC-related ATS functions shall be implemented as defined in this subclause in order to benefit from thecharacteristics of a CBTC system as defined in 4.1, namely:
  - Availability of train location information to a high precision, independent of track circuits;
  - Availability of continuous wayside-to-train and train-to-wayside data communications link;
  - Availability of trainborne and wayside data processing capabilities.

The CBTC-related ATS functions defined in this section shall be fully integrated with other conventionalATS functions, and other non-ATS functions, as may be specified by the authority having jurisdiction, tosupport overall service management for the transit system, and provide for a single consistent user interface.

The CBTC data communications network, inclusive of the wayside-to-train and train-to-wayside data com-munications interface, shall be sufficient to support those CBTC-related ATS functions specified by theauthority having jurisdiction.

### 6.3.2 ATS user interface
Each ATS user interface shall display all information and implement all control actions, as defined in thissubclause, within acceptable latencies as specified by the authority having jurisdiction.The ATS user shall be able to override any automated CBTC-related ATS functions defined in this subclause.Control action validation shall be provided for any safety related functions and functions whose inadvertentimplementation could have an adverse operational impact, as defined by the authority having jurisdiction

### 6.3.3 CBTC train identification and train tracking
Each CBTC-equipped train operating within CBTC territory shall be assigned a train identification. Thistrain identification shall indicate the type of train and other pertinent information about the train.An ATS system shall have the capability to automatically track, maintain records of, and display on the ATSuser interface the locations, identities, train schedule, and other pertinent data for all CBTC-equipped trainsoperating in the CBTC territory. The front and rear position of trains shall be tracked based on CBTC trainlocation reports, and displayed on the ATS user interface. Variations in train length may be displayed eitherproportionally or as a standard length icon supplemented by textural train length data.

### 6.3.4 Train routing
An ATS system shall have the capability to permit CBTC-equipped trains operating in CBTC territory to bemanually and automatically routed based on CBTC train location reports and in accordance with the trainservice data, predefined routing rules, and any ATS user-directed service strategy. Automatic routing shallfacilitate the proper merging and diverging of trains at junctions, turnback of trains, the put-in and lay-up of trains from/to storage areas and, where applicable, the rerouting of trains in response to service disruptionsand/or planned outages. Train routes shall be indicated on the ATS user interface, and may also be indicatedto the train operator and/or conductor on their displays, as specified by the authority having jurisdiction.An ATS system shall also include a means to control and limit movement authorities of CBTC-equippedtrains operating in CBTC territory. CBTC movement authority limits shall be capable of being displayed onthe ATS user interface, and any uncommanded reductions of authority limits shall be alarmed. Movementauthority limits may also be indicated to the train operator and/or conductor on their displays, as specified bythe authority having jurisdiction.

### 6.3.5 Automatic train regulation
#### 6.3.5.1 Schedule/headway regulation
An ATS system shall have the capability to automatically monitor and regulate the performance of CBTC-equipped trains operating in CBTC territory, in relation to schedule and/or headway adherence.An ATS system shall include an automatic dispatching function (based on train identities, CBTC trainlocation reports, scheduled and actual headways between trains, and service strategies implemented byauthorized ATS users).Schedule and headway regulation for CBTC-equipped trains shall be by means of dwell time variance(including train holds), and control of run-times between stations (e.g., through adjustments to train acceler-ation and service brake rates, and cruise speeds), as specified by the authority having jurisdiction. The desired station departure time and desired speed profile between stations shall be indicated to the trainoperator and/or conductor on their displays and, when operating in ATO mode, shall be implemented auto-matically by a CBTC system using the automatic speed regulation function of 6.2.1.An ATS system may provide the capability to adjust the train service braking profiles for CBTC-equippedtrains (e.g., in response to wet rail conditions). A CBTC system shall coordinate implementation of requested changes in service braking profiles to avoid conditions that would result in an emergency brakeapplication.

#### 6.3.5.2 Junction management
An ATS system may include automatic train regulation functions, based on CBTC train location reports, tofacilitate appropriate train meets (such as transfers between local and express tracks, and at the merge pointbetween different lines) in order to minimize overall system delays.

#### 6.3.5.3 Energy optimization
An ATS system may have the capability to implement energy optimization algorithms for CBTC-equippedtrains through the real-time control and coordination of train acceleration, train coasting, and train braking.The priority given to energy optimization versus schedule/headway regulation shall be as specified by theauthority having jurisdiction.

### 6.3.6 Station stop functions
#### 6.3.6.1 Stop train at next station
An ATS system may include the means to direct a single CBTC-equipped train or a group of CBTC-equipped trains to stop at the next station, even if the train is scheduled to bypass that station. ACBTC system shall indicate the ATS train stop information to the train operator and conductor on their dis-plays. In ATO mode, a CBTC-equipped train shall automatically stop at the next station.

#### 6.3.6.2 Hold train at station
An ATS system may include facilities to hold (and subsequently release) a CBTC-equipped train at a station,and to inhibit automatic train door opening. A CBTC system shall indicate the train hold information to thetrain operator and conductor on their displays, and shall prevent a CBTC-equipped train from departingthe station in ATO mode.

#### 6.3.6.3 Skip station stop
An ATS system may include facilities to direct a CBTC-equipped train or group of CBTC-equipped trains topass through a station or group of stations without stopping. A CBTC system shall indicate the skip stationinformation to the train operator and conductor on their displays. In ATO mode, the train shall automaticallyskip the designated stations.

### 6.3.7 Restricting train operations
#### 6.3.7.1 Stopping a train enroute
An ATS system shall provide a means to stop a single CBTC-equipped train or group of CBTC-equippedtrains immediately. A CBTC system shall initiate an immediate brake application on the designated trainsand notify the train operator and conductor via their displays 

#### 6.3.7.2 Temporary speed restrictions
An ATS system shall include facilities to impose (and remove) temporary speed restrictions on any sectionof track in CBTC territory and to modify the ATP profile for CBTC-equipped trains accordingly (see 6.1.3).
6.3.7.3 Switch/track blocking
An ATS system shall include facilities to block (and subsequently unblock) a switch, an exit signal, a routeentry point, or a section of track within CBTC territory. A CBTC system shall prohibit CBTC-equippedtrains from receiving movement authorities over blocked switches or into routes and/or sections of track thathave been blocked (see 6.1.2 and 6.1.13).

#### 6.3.7.4 Work zones
An ATS system shall include facilities to establish (and subsequently remove) temporary work zones for theprotection of work crews and work trains.A CBTC system shall enforce restricted speeds on approach to and through defined work zones (see 6.1.13).Work zone information shall be displayed to the train operator and conductor on their displays, and theCBTC system may preclude ATO mode of operation through a work zone.An ATS system may also provide methods of visually and audibly indicating the approach and direction of trains along the wayside to warn on-track roadway workers in areas where visibility is restricted.

### 6.3.8 Passenger information system interfaces
An ATS system may interface with wayside and/or trainborne passenger information systems to trigger auto-matic passenger information messages, such as train arrival information, based on CBTC train locationreports.Trainborne passenger information system interfaces shall be in accordance with IEEE Std 1477-1998.

### 6.3.9 Fault reporting
#### 6.3.9.1 CBTC fault reporting
Failures and out-of tolerance conditions detected by, or input to, a CBTC system, and any condition requir-ing ATS user attention, shall be automatically indicated on the ATS user interface display. Alarms shall becategorized and prioritized into critical and non-critical alarms and logged. All critical alarms shall requireacknowledgment. CBTC-related alarms shall include, but not be restricted to the following:
  - a) CBTC wayside and trainborne equipment failure alarms;
  - b) Unauthorized entry of a train into CBTC territory;
  - c) Violation of movement authority limit by a CBTC-equipped train;
  - d) Uncommanded train separation.
  - e) Loss or intermittent nature of the data communications channel in excess of limits established by theauthority having jurisdiction;
  - f) Other conditions as specified by the authority having jurisdiction 

#### 6.3.9.2 Train fault reporting
Trainborne CBTC equipment may include interfaces to trainborne subsystems for the purposes of communi-cating train health data to the wayside for display on the ATS user interface displays, as specified by theauthority having jurisdiction.




