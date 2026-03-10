### Scenario: Flashlight_functional
- DSL: SysML v2
- CONFIG: C-Min
- Log: 20260305-121114
- Model: llama3.3-70b
- Temperature: 0

# Results of what is generated (from all “MANUAL CLASSIFICATION” sections)

### ARCH
# unique shown = 19
# Total generated occurrences = 25
- {'ConstraintDefinition': 'OverheatProtection    '} — 3
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Brightness    '} — 2
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Brightness   '} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability     '} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability'} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability   '} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability    '} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability     '} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability     '} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability   '} — 1
- {'partdefinition': 'Circuit ', 'RequirementDefinition': 'Durability    '} — 1
- {'partdefinition': 'Housing', 'RequirementDefinition': 'Durability'} — 1
- {'partdefinition': 'Housing  ', 'RequirementDefinition': 'Durability '} — 1
- {'partdefinition': 'Housing ', 'RequirementDefinition': 'Durability   '} — 2
- {'partdefinition': 'Housing ', 'RequirementDefinition': 'Durability     '} — 1
- {'partdefinition': 'Lens', 'RequirementDefinition': 'Durability   '} — 1
- {'partdefinition': 'Reflector ', 'RequirementDefinition': 'Durability    '} — 1
- {'ConstraintDefinition': 'PowerConsumption  ', 'PartUsage': 'Housing '} — 2
- {'ConstraintDefinition': 'PowerConsumptionLimit      ', 'PartDefinition': 'Housing '} — 1

### CONNECTIONS
# unique shown = 14
# Total generated occurrences = 16
- {'PortDefinition': 'BatteryCompartment'} — 1
- {'PortDefinition': 'ElectricalConnection  '} — 1
- {'PortDefinition': 'Switch '} — 1
- {'PortDefinition': 'batteryPoint'} — 1
- partUsage - partDefinition : BatteryHolder -isTypedBy- BatteryHolder — 1
- {' partUsage - partDefinition : Reflector -isTypedBy- Reflector'} — 1
- {' partUsage - partDefinition : Switch -isTypedBy- Switch'} — 1
- {'partUsage - partDefinition': 'Led -isTypedBy- BatteryHolder '} — 1
- {'partUsage - partDefinition': 'Led -isTypedBy- Led'} — 1
- {'partUsage - partDefinition': 'Led -isTypedBy- Light'} — 1
- {'partUsage - partDefinition': 'Led -isTypedBy- Reflector'} — 1
- {'partUsage - partDefinition': 'Accent -isTypedBy- Accent'} — 1
- connection: partUsage - partUsage : Led -isConnectedTo- Reflector — 1
- connection: partUsage - partUsage : Led -isConnectedTo- Switch — 1

### CHARACTERISTICS
# unique shown = 12
# Total generated occurrences = 17
- {'ConstraintDefinition': 'BatteryLife  '} — 4
- {'ConstraintDefinition': 'BatteryLife       '} — 2
- {'ConstraintDefinition': 'BatteryLife   '} — 1
- {'ConstraintDefinition': 'BatteryLifeConstraint'} — 1
- {'ConstraintDefinition': 'ThermalLimit '} — 2
- {'ConstraintDefinition': 'battery '} — 1
- {'ConstraintDefinition': 'Light'} — 1
- {'ConstraintDefinition: BatteryLifeConstraint '} — 3
- {'ConstraintDefinition: BatteryLife  '} — 1
- {'ConstraintDefinition: BatteryLife    '} — 1
- {'ConstraintDefinition: ThermalLimit     '} — 1
- {'RequirementUsage': 'BatteryLife'} — 1


# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list

### ARCH
- {'partdefinition': 'BatteryHolder'}
- {'partdefinition': 'Lens'}
- {'partdefinition': 'Reflector'}
- {'partusage': 'BatteryHolder'}

### CONNECTIONS
- {'partUsage - partDefinition': 'BatteryHolder -isTypedBy- BatteryHolder'}
- {'partUsage - partDefinition : Reflector -isTypedBy- Reflector'}
- connection: partUsage - partDefinition: Switch -isTypedBy- Switch

### CHARACTERISTICS
- {'ConstraintDefinition': 'LightOnlyWhenOn'}


## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY …” sections) — unique list

### ARCH
- {'partUsage': {'battery'}}
- {'RequirementDefinition': {'Light'}}
- {'RequirementDefinition': 'Glow'}
- {'Partdefinition': {'Accent'}}
- {'RequirementDefinition': 'Torch'}
- {'RequirementDefinition': 'Lamp'}
- {'partdefinition': 'Switch '}
- {'partdefinition': 'Led '}
- {'partdefinition': 'glow'}
- {'PartUsage': 'Led'}
- {'PartUsage': 'Mount'}
- RequirementDefinition: Lamp
- PartDefinition: Mount
- PartDefinition: Battery
- PartDefinition: Focus
- PortDefinition:PowerPort
- {'ConstraintDefinition': 'LightOnlyWhenOn'}
- requirementDefinition:Beacon

### CONNECTIONS
- {'partUsage - partDefinition': 'Accent -isTypedBy- Accent'}
- {'partUsage - partDefinition': 'Led -isTypedBy- Led'}
- {'partUsage - partDefinition': 'Glow -isTypedBy- Glow'}
- {'partUsage - partDefinition': 'Mount -isTypedBy- Mount'}
- {'partUsage - partDefinition': 'Lens -isTypedBy- Lens'}
- {'partUsage - partDefinition': 'focus -isTypedBy- Focus'}
- connection: RequirementUsage - RequirementDefinition : Light -isTypedBy- Light
- {'portUsage - portDefinition': 'battery.pwr -isTypedBy- PowerPort'}
- {'portUsage - portDefinition': 'sw.in -isTypedBy- PowerPort'}
- {'portUsage - portDefinition': 'sw.out -isTypedBy- PowerPort'}
- {'portUsage - portDefinition': 'led.pwr -isTypedBy- PowerPort'}
- {'portUsage - portDefinition': 'lens.out -isTypedBy- PowerPort'}
- {'portUsage': 'sw.in'}
- {'portUsage': 'sw.out'}

### CHARACTERISTICS
- {'RequirementUsage': {'battery'}}
- {'PartUsage': 'Reflector'}
- {'partUsage': 'accent'}
- {'portUsage': 'battery.pwr'}
- requirementUsage: Light
- {'RequirementUsage': 'Beam'}
- {'RequirementUsage': 'Beacon'}
- {'ConstraintUsage : LightOnlyWhenOn'}
- {'portUsage': 'lens.out'}
- {'portUsage': 'led.pwr'}


### Candidates / Uniqueness
- Candidates_ARCH = 25
- Candidates_CONN = 16
- Candidates_CHAR = 17
- Candidates_ALL  = 25 + 16 + 17 = 58

- Unique_ARCH = 19
- Unique_CONN = 14
- Unique_CHAR = 12
- Unique_ALL  = 19 + 14 + 12 = 45

- Redundancy_% = (1 - 45/58) * 100 = 44.4%


### Metrics (binary acceptance; denominator = total suggestion occurrences)
- Acc_ARCH = 4/25 = 0.1600 = 16.0%
- Acc_CONN = 3/16 = 0.1875 = 18.8%
- Acc_CHAR = 1/17 = 0.0588 = 5.9%
- Acc_ALL  = (4 + 3 + 1) / (25 + 16 + 17) = 8/58 = 0.1379 = 13.8%
- Contr_ALL = 0/58 = 0.0%
- Irrel_ALL = 1 - (8/58) = 50/58 = 0.8621 = 86.2%

#### AI contribution (accepted vs final model = accepted ∪ manual)
- |A| = 8
- |M| = 18 + 14 + 10 = 42
- Overlap(A,M) = 0
- |A ∪ M| = 50
- AI_Contribution = 8/50 = 0.1600 = 16.0%