### Scenario: Aircraft maintenance routing system
- CONFIG: C-Min
- Log: 20260217-140917
- Model: llama3.3-70b
- Temperature: 0

# Results of what is generated (from all “MANUAL CLASSIFICATION” sections)

### ARCH (concepts)
# unique shown = 22
# Total generated occurrences = 39
- Entity: supplier — 8
- Entity: maintenance_vendor — 5
- Constraint: parts_availability_constraint — 2
- Entity: regulatory_authority — 2
- Metric: Maintenance Cycle Time — 2
- Metric: shipment_delay_rate — 2
- Resource: diagnostic_equipment — 2
- ressource: maintenance_equipment — 2
- Constraint: Spare Parts Lead Time — 1
- Constraint: pare_parts_lead_time — 1
- Constraint: parts_lead_time — 1
- Entity: Vendor — 1
- Entity: airport — 1
- Entity: maintenance_vendor — 1
- Entity: regulatory_authority — 1
- Entity: spare_parts_depot — 1
- Entity: spare_parts_warehouse — 1
- Entity: weather_station — 1
- Metric: aircraft downtime rate — 1
- Metric: gloss-level — 1
- Metric: parts_lead_time — 1
- Resource: aircraft — 1

### CONNECTIONS (relations)
# unique shown = 14
# Total generated occurrences = 24
- information_flow: aircraft_routing_optimization - spare_parts_allocation — 5
- information_flow: aircraft_routing_optimization - maintenance_execution — 4
- information_flow: maintenance_execution - maintenance_forecasting — 3
- information_flow: aircraft_routing_optimization - slot_reservation — 2
- information_flow: maintenance_execution - shipment planning — 1
- information_flow: maintenance_forecasting - maintenance_scheduling — 1
- information_flow: maintenance_scheduling - aircraft_routing_optimization — 1
- information_flow: maintenance_scheduling - maintenance_forecasting — 1
- information_flow: spare_parts_allocation - aircraft_routing_optimization — 1
- uses: aircraft_routing_optimization - aircraft — 1
- uses: maintenance_execution - maintenance_crew — 1
- uses: maintenance_execution - maintenance_hangar — 1
- uses: maintenance_scheduling - maintenance_crew — 1
- uses: maintenance_scheduling - maintenance_hangar — 1

### CHARACTERISTICS (attributes / constraints)
# unique shown = 4
# Total generated occurrences = 7
- Constraint: aircraft availability — 3
- Constraint: crew_availability — 2
- Constraint: availability_window — 1
- Constraint: spare_parts_availability — 1


# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list

### ARCH (concepts)
- Entity: airport
- Metric: aircraft downtime rate
- Resource: aircraft
- Resource: maintenance_crew
- Resource: maintenance_hangar

### CONNECTIONS (relations)
- information_flow: aircraft_routing_optimization - slot_reservation
- information_flow: maintenance_scheduling - aircraft_routing_optimization
- uses: aircraft_routing_optimization - aircraft
- uses: maintenance_execution - maintenance_crew

### CHARACTERISTICS (attributes / constraints)
- (none)


## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY (ITERATION …)” sections) — unique list

### ARCH (concepts)
- entity: distribution center
- Entity: maintenance planning team
- process: aircraft_routing_optimization
- process: maintenance_execution
- process: maintenance_scheduling
- process: shipment planning
- Process: slot_reservation
- process: spare_parts_allocation
- Metric: maintenance crew utilization
- Metric: parts availability rate
- Resource: spare part

### CONNECTIONS (relations)
- applies_to: maintenance execution - capacity limit
- applies_to: maintenance execution - maintenance deadline
- evaluation: aircraft routing optimization - aircraft downtime rate
- evaluation: maintenance_execution - maintenance crew utilization
- information_flow: maintenance_forecasting
- information_flow: maintenance_scheduling
- information_flow: shipment planning - maintenance_execution
- uses: maintenance_execution - aircraft
- uses: spare_parts_allocation - spare_parts

### CHARACTERISTICS (attributes / constraints)
- Constraint: capacity limit
- Constraint: maintenance deadline


### Candidates / Uniqueness
- Candidates_ARCH = 39
- Candidates_CONN = 24
- Candidates_CHAR = 7
- Candidates_ALL  = 39 + 24 + 7 = 70

- Unique_ARCH = 22
- Unique_CONN = 14
- Unique_CHAR = 4
- Unique_ALL  = 22 + 14 + 4 = 40

- Redundancy_% = (1 - 40/70) * 100 = 42.9%


### Metrics (binary acceptance; denominator = total suggestion occurrences)
- Acc_ARCH = 5/39 = 0.1282 = 12.8%
- Acc_CONN = 4/24 = 0.1667 = 16.7%
- Acc_CHAR = 0/7  = 0.0000 = 0.0%
- Acc_ALL  = (5 + 4 + 0) / (39 + 24 + 7) = 9/70 = 0.1286 = 12.9%
- Contr_ALL = 0/70 = 0.0%  (no contradictory list provided)
- Irrel_ALL = 1 - (9/70) = 61/70 = 0.8714 = 87.1%

#### AI contribution (accepted vs final model = accepted ∪ manual)
- |A| = 5 + 4 + 0 = 9
- |M| = 11 + 9 + 2 = 22
- Overlap(A,M) = 0
- |A ∪ M| = 31
- AI_Contribution = 9/31 = 0.2903 = 29.0%


### Scenario: Aircraft maintenance routing system
- CONFIG: C-Full
- Log: 20260218-150405
- Model: llama3.3-70b
- Temperature: 0

# Results of what is generated (from all “MANUAL CLASSIFICATION” sections)

### ARCH (concepts)
# unique shown = 18
# Total generated occurrences = 26
- {'Entity': ['MaintenanceTeam']} — 6
- {'Entity': 'maintenance team'} — 2
- {'Entity': ['Maintenance Team']} — 2
- {'Relationship': ['distribution center - airport']} — 2
- {' Entity': 'Maintenance Team'} — 1
- {' Resource': ' maintenance_equipment'} — 1
- {'Entity': 'airline'} — 1
- {'Entity': 'regional office'} — 1
- {'Entity': 'supplier'} — 1
- {'Entity': ['Aircraft  Maintenance Team']} — 1
- {'Entity': ['Maintenance Team']} — 1
- {'Entity': ['airport']} — 1
- {'Entity': ['MaintenanceTeam']} — 1
- {'Metric': 'Aircraft Downtime'} — 1
- {'Metric': 'Technician Utilization Rate'} — 1
- {'Metric': ['Maintenance Cost']} — 1
- {'Resource': ['Maintenance Equipment']} — 1
- {'Resource': ['SpareParts']} — 1

### CONNECTIONS (relations)
# unique shown = 50
# Total generated occurrences = 75
- {'collaborates': ['airport - distribution center']} — 3
- {'uses': ['aircraft_routing_optimization', 'technician']} — 3
- {'applies_to': ['Spare Part Availability -  spare time allocation']} — 2
- {'applies_to': ['maintenance_window', 'maintenance_execution']} — 2
- {'collaborates': ['airline - distribution center']} — 2
- {'evaluates': ['maintenance_execution', 'Parts Availability rate']} — 2
- {'information_flow': ['maintenance forecasting - spare parts allocation']} — 2
- {'isUsed': ['Maintenance Equipment - maintenance forecasting']} — 1
- {'isUsed': ['Maintenance Equipment - maintenance scheduling']} — 1
- {'isUsed': ['Maintenance Equipment - spare time allocation']} — 1
- {'isUsed': ['spare parts - maintenance execution']} — 1
- {'measures': [' maintenance execution - Aircraft Downtime']} — 1
- {'measures': ['maintenance forecasting process -  Forecasting Accuracy']} — 1
- {'measures': ['maintenance scheduling - Maintenance Cost']} — 1
- {'measures': ['maintenance execution - Aircraft Downtime']} — 1
- {'measures': ['maintenance execution - Maintenance Cost']} — 1
- {'measures': ['shipment planning', 'Maintenance Cost']} — 1
- {'measures': ['shipment planning - Technician Utilization Rate']} — 1
- {'performs': [' Maintenance Team - maintenance_scheduling']} — 1
- {'performs': ['Maintenance Team -  maintenance execution']} — 1
- {'performs': ['MaintenanceTeam - maintenance forcasting ']} — 1
- {'performs': ['airport - aircraft_routing_optimization']} — 1
- {'performs': ['maintenance team', 'maintenance execution']} — 1
- {'produces': [' maintenance execution - spare parts ']} — 1
- {'produces': ['spare_part_allocation - maintenance_execution']} — 1
- {'uses': [' maintenance execution - spare parts ']} — 1
- {'uses': ['Maintenance Team - SpareParts']} — 1
- {'uses': ['Maintenance forcasting - SpareParts']} — 1
- {'uses': ['aircraft_routing_optimization - spare_parts ']} — 1
- {'uses': ['maintenance execution -spare parts']} — 1
- {'uses': ['maintenance forcasting - SpareParts']} — 1
- {'uses': ['maintenance scheduling -  historical maintenance data']} — 1
- {'uses': ['maintenance scheduling -  spare parts']} — 1
- {'uses': ['maintenance scheduling -  technician']} — 1
- {'uses': ['maintenance scheduling - hangar slot']} — 1
- ... (the remaining 15 unique relations each appear once)

### CHARACTERISTICS (constraints)
# unique shown = 7
# Total generated occurrences = 9
- {'Constraint': 'maintenance_window'} — 2
- {'Constraint': ['Availability']} — 2
- {'Constraint': 'spare_parts_availability'} — 1
- {'Constraint': ['Regulatory Requirements']} — 1
- {'Constraint': ['Spare Part Availability']} — 1
- {'Constraint': ['SparePartsAvailability']} — 1
- {'constraint': 'spare_parts_availability'} — 1


# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list

### ARCH (concepts)
- {'Entity': 'airline'}
- {'Entity': ['airport']}
- {'Metric': 'Aircraft Downtime'}
- {'Metric': 'Technician Utilization Rate'}
- {'Metric': ['Maintenance Cost']}
- {'resource': 'spare parts'}

### CONNECTIONS (relations)
- {'applies_to': [' maintenance execution - maintenance_window']}
- {'applies_to': ['maintenance_window', 'maintenance_execution']}
- {'evaluates': [' aircraft_routing_optimization - Aircraft Downtime']}
- {'evaluates': ['maintenance_execution', 'Parts Availability rate']}
- {'evaluates_': ['spare parts allocation - Parts Availability rate']}
- {'evaluates_': ['spare parts allocation - maintenance_execution']}
- {'information_flow': ['aircraft_routing_optimization', 'maintenance_execution']}
- {'isUsed': ['spare parts - maintenance execution']}
- {'measures': [' maintenance execution - Aircraft Downtime']}
- {'measures': ['maintenance execution - Maintenance Cost']}
- {'measures': ['shipment planning', 'Maintenance Cost']}
- {'performs': ['airport - aircraft_routing_optimization']}
- {'uses': ['maintenance execution -spare parts']}
- {'uses': ['maintenance scheduling - hangar slot']}

### CHARACTERISTICS (constraints)
- {'Constraint': 'maintenance_window'}


## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY (ITERATION …)” sections) — unique list

### ARCH (concepts)
- {'process': ['maintenance_scheduling']}
- {'process': ['spare time allocation']}
- {'process': 'maintenance execution'}
- {'process': 'aircraft_routing_optimization'}
- {'Process': 'slot reservation'}
- {'Process': 'shipment planning'}
- {'Metric': [' Parts Availability rate']}
- {'Resource': 'aircraft'}
- {'resource': 'Technician'}
- {'Resource': 'Hangar slot'}

### CONNECTIONS (relations)
- {'information_flow': ['maintenance_forecasting - maintenance_scheduling']}
- {'information_flow': ['spare parts allocation - shipment planning']}

### CHARACTERISTICS (constraints)
- {'constraint': 'capacity limitation'}


### Metrics (binary acceptance; denominator = total suggestion occurrences)
- Candidates_ARCH = 26
- Candidates_CONN = 75
- Candidates_CHAR = 9
- Candidates_ALL  = 110

- Unique_ARCH = 18
- Unique_CONN = 50
- Unique_CHAR = 7
- Unique_ALL  = 75

- Redundancy_% = (1 - 75/110) * 100 = 31.8%

- Acc_ARCH = 6/26  = 0.2308 = 23.1%
- Acc_CONN = 14/75 = 0.1867 = 18.7%
- Acc_CHAR = 1/9   = 0.1111 = 11.1%
- Acc_ALL  = (6 + 14 + 1) / 110 = 21/110 = 0.1909 = 19.1%

- Contr_ALL = 0/110 = 0.0%
- Irrel_ALL = 1 - (21/110) = 89/110 = 0.8091 = 80.9%

#### AI contribution (accepted vs final model = accepted ∪ manual)
- |A| = 21
- |M| = 13
- Overlap(A,M) = 0
- |A ∪ M| = 34
- AI_Contribution = 21/34 = 0.6176 = 61.8%
