### Scenario: medical appointment scheduling System
- CONFIG: C-Min
- Log: 20260204-094906
- Model: llama3.3-70b
- Temperature: 0
- Time 105 Mins

# Results of what is generated (from all “MANUAL CLASSIFICATION” sections)
### ARCH (classes)
# unique shown = 7
# Total generated occurrences = 23
- Insurance — 9
- MedicalSpecialty — 6
- Receptionist — 3
- Doctor — 2
- Appointment — 1
- Patient — 1
- MedicalRecord — 1

### CONNECTIONS (associations / inheritance as written in manual classification)
# unique shown = 13
# Total generated occurrences = 23
- Patient - MedicalService — 5
- Patient - Notification — 4
- Patient - Doctor — 3
- Patient - Insurance — 2
- User - Appointment — 1
- Appointment - Doctor — 1
- User - Doctore — 1
- Doctor - User — 1
- Patient - Appointment — 1
- Patient - MedicalSpecialty — 1
- Clinic - Doctor — 1
- Appointment - Payment — 1
- Patient - Payment — 1

### CHARACTERISTICS (attributes / properties)
# unique shown = 12
# Total generated occurrences = 23
- Appointment.appointmentDuration — 10
- Appointment.appointmentTime — 2
- Appointment.appointmentType — 2
- User.role — 1
- Appointment.scheduleDate — 1
- Appointment.appointmentStatus — 1
- Doctor.availability — 1
- Appointment.appointmentReason — 1
- Patient.patientHistory — 1
- Appointment.priority — 1
- Appointment.reason — 1
- Appointment.reminder — 1


# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list
### ARCH (classes)
- Appointment
- Doctor
- Patient

### CONNECTIONS (associations / inheritance)
- User - Appointment
- Appointment - Doctor
- User - Doctor
- Patient - Appointment
- Clinic - Doctor
- Appointment - Payment

### CHARACTERISTICS (attributes / properties)
- Appointment.scheduleDate
- Appointment.appointmentStatus
- Doctor.availability
- Patient.patientHistory


## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY (ITERATION …)” sections) — unique list
### ARCH (classes)
- Notification
- Clinic
- Payment
- MedicalService
- TimeSlot

### CONNECTIONS (associations / inheritance)
- Patient - User
- Doctor - User
- User - Notification
- Appointment - MedicalService
- Appointment - TimeSlot

### CHARACTERISTICS (attributes / properties)
- Notification.message
- Doctor.speciality
- Payment.amount
- Payment.method
- TimeSlot.startTime
- TimeSlot.endTime


### Metrics (binary acceptance; denominator = total suggestion occurrences)
- Acc_ARCH = 3/23 = 0.1304 = 13.0%
- Acc_CONN = 6/23 = 0.2609 = 26.1%
- Acc_CHAR = 4/23 = 0.1739 = 17.4%
- Acc_ALL = (3 + 6 + 4) / (23 + 23 + 23) = 13/69 = 0.1884 = 18.8%
- Contr_ALL = 0/69 = 0.0%  (no contradictory list provided)
- Irrel_ALL = 1 - (13/69) = 56/69 = 0.8116 = 81.2%

#### AI contribution (accepted vs final model = accepted ∪ manual)
- |A| = 13
- |M| = 5 + 5 + 6 = 16
- Overlap(A,M) = 0
- |A ∪ M| = 29
- AI_Contribution = 13/29 = 0.4483 = 44.8%

------------------------------------------------------------
### Scenario: medical appointment scheduling System
- CONFIG: C-Full
- Log: 20260204-183525
- Time 80 mins

# Results of what is generated (from all “MANUAL CLASSIFICATION” sections)
### ARCH (classes)
# unique shown = 7
# Total generated occurrences = 21
- Nurse — 6
- Insurance — 6
- Department — 4
- Hospital — 2
- Appointment — 1
- Doctor — 1
- Patient — 1

### CONNECTIONS (associations / inheritance as written in manual classification)
# unique shown = 7
# Total generated occurrences = 21
- Patient-Hospital — 13
- Doctor - appointment — 3
- User - Appointment — 2
- Doctor-patient — 1
- Patient-Notification — 1
- Patient-appointment — 1

### CHARACTERISTICS (attributes / properties)
# unique shown = 13
# Total generated occurrences = 20
- appointment.duration — 7
- Patient.medicalHistory — 2
- appointment.date — 1
- User.username — 1
- Hospital.address — 1
- appointment.time — 1
- Doctor.speciality — 1
- appointment.status — 1
- Patient.insuranceProvider — 1
- appointment.description — 1
- payment.amount — 1
- TimeSlot.duration — 1
- appointment.reason — 1


# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list
### ARCH (classes)
- Appointment
- Doctor
- Hospital
- Patient

### CONNECTIONS (associations / inheritance)
- Doctor - appointment
- Patient - User
- Patient-appointment

### CHARACTERISTICS (attributes / properties)
- Hospital.address
- Patient.medicalHistory
- appointment.date
- appointment.status
- appointment.time
- doctor.speciality


## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY (ITERATION …)” sections) — unique list
### ARCH (classes)
- Notification
- payment
- TimeSlot

### CONNECTIONS (associations, inheritance, composition)
- Doctor - User
- User-Notification
- Doctor- Hospital
- appointment - payment
- appointment - Timeslot

### CHARACTERISTICS (attributes / properties)
- notification.message


### Metrics (binary acceptance; denominator = total suggestion occurrences)
- Acc_ARCH = 4/21 = 0.1905 = 19.0%
- Acc_CONN = 3/21 = 0.1429 = 14.3%
- Acc_CHAR = 6/20 = 0.3000 = 30.0%
- Acc_ALL = (4 + 3 + 6) / (21 + 21 + 20) = 13/62 = 0.2097 = 21.0%
- Contr_ALL = 0/62 = 0.0%
- Irrel_ALL = 1 - (13/62) = 49/62 = 0.7903 = 79.0%

#### AI contribution (accepted vs final model = accepted ∪ manual)
- |A| = 13
- |M| = 3 + 5 + 1 = 9
- Overlap(A,M) = 0
- |A ∪ M| = 22
- AI_Contribution = 13/22 = 0.5909 = 59.1%
