### Scenario: Batmobile functional
- DSL: SysML v2
- CONFIG: C-Full
- Log: 20260310-140930
- Iterations 58

# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list (exact)

## ARCH
- {'PartDefinition': 'Chassis'}                    (ITER 1)
- {'PortDefinition ': 'FuelPort'}                 (ITER 7)
- {'PortDefinition ': 'ControlPort'}              (ITER 8)
- {'PartUsage     ': 'navigationSystem'}          (ITER 28)
- {'PartUsage     ': 'axle'}                      (ITER 29)

## CONNECTIONS
- {'DependsOn': 'source :PortUsage  - engine -- target : PortUsage  - axle   '}   (ITER 30)
- {'ConnectsTo ': 'sensors-DataPort'}                                          (ITER 44)

## CHARACTERISTICS
- {'RequirementUsage  ': 'HighSpeedRequirement'}    (ITER 3)
- {'PartUsage  ': 'chassis'}                         (ITER 5)
- {'PartUsage  ': 'engine'}                          (ITER 6)
- {'RequirementUsage    ': 'CrewSafety'}             (ITER 18)


# ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY …” sections) — unique list (exact)

## ARCH
- {'portDefinition': 'PowerPort'}           (ITER 2)
- {'PartDefinition  ': 'Wheels'}            (ITER 9)
- {'PartDefinition  ': 'Sensor'}            (ITER 10)
- {'PartDefinition  ': 'Armor'}             (ITER 13)
- {'partdefinition': 'Panel'}               (ITER 17)
- {'PartUsage': 'Panel'}                    (ITER 18)
- {'PartUsage': 'Armor'}                    (ITER 19)
- {'PartDefinition': 'Axle'}                (ITER 21)
- PortDefinition: DataPort                  (ITER 22)
- {'PartDefinition': 'Navigation'}          (ITER 23)
- {'PartDefinition': 'Frame'}               (ITER 24)
- {'PartDefinition': 'Module'}              (ITER 26)
- {'PartDefinition': 'Body'}                (ITER 27)
- {'PartDefinition': 'Asset'}               (ITER 34)
- {'PartDefinition': 'Component'}           (ITER 35)
- {'PartDefinition': 'element'}             (ITER 36)

## CONNECTIONS
- {'connection- PartDefintion-isTypedBy-PartUsage': {'Engine-Engine'}}      (ITER 14)
- {'connection- PartDefintion-isTypedBy-PartUsage': {'wheels-wheels'}}      (ITER 15)
- {'connection- PartDefintion-isTypedBy-PartUsage': {'Chassis-Chassis'}}    (ITER 16)
- {'connection- PartDefintion-isTypedBy-PartUsage': 'Panel -Panel'}         (ITER 38)
- {'connection- PartDefintion-isTypedBy-PartUsage': 'Axle - Axle'}          (ITER 39)
- {'connection- PartDefintion-isTypedBy-PartUsage': 'component - component'}(ITER 40)
- {'connection- PartDefintion-isTypedBy-PartUsage': 'armor - armor'}        (ITER 41)

## CHARACTERISTICS
- {'PartUsage  ': 'wheels'}                           (ITER 11)
- {'PartUsage  ': 'sensors'}                          (ITER 12)
- {'ConstraintUsage': 'WeaponsOnlyWhenAuthorized'}    (ITER 20)
- {'PartUsage': 'Frame'}                              (ITER 25)
- {'PartUsage': 'Body'}                               (ITER 31)
- {'PartUsage': 'module'}                             (ITER 33)
- {'ConstraintUsage': 'EngineRequiresFuel'}           (ITER 47)
- {'RequirementUsage': 'NavigationAccurate'}          (ITER 50)


# Candidates 

Candidates_ALL = 58 * 3 = 174
Candidates_ARCH = 58
Candidates_CONN = 58
Candidates_CHAR = 58

# Unique 
Unique_ARCH ≈ 11
Unique_CONN ≈ 17
Unique_CHAR ≈ 12
Unique_ALL  ≈ 11 + 17 + 12 = 40

# Redundancy
Redundancy_% = (1 - Unique_ALL / Candidates_ALL) * 100
            = (1 - 40/174) * 100
            = 77.0%

# Counts 

- AI_Accepted_ARCH_per_Iteration = 5/58 = 0.0862 = 8.6%
- AI_Accepted_CONN_per_Iteration = 3/58 = 0.0517 = 5.2%
- AI_Accepted_CHAR_per_Iteration = 4/58 = 0.0690 = 6.9%
- AI_Accepted_per_Iteration = 12/58 = 0.2069 = 20.7%

