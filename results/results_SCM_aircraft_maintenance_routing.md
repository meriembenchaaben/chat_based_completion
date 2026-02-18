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
