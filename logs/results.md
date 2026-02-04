### Scenario: Food delivery application
- CONFIG: C-Full
- Time : 110 mins
  ### Summary (Key Metrics)

# Results of what is generated:
### ARCH (classes)
  \# unique shown = 7
   \# Total generated occurrences= 20
- review — 11
- FoodItem — 3
- PaymentMethod — 2
- Driver — 1
- Menu — 1
- Order — 1
- Restaurant — 1

### CONNECTIONS (associations)
*(counted as undirected: e.g., `Order - Driver` and `Driver - Order` are merged)*
  \# unique shown = 8
- order - Driver — 5
- Customer - paymentMethod — 4
- Menu - order — 3
- user - order — 3
- Restaurant - Menu — 1
- Driver - Delivery — 1
- order - MenuItem — 1
- customer - MenuIordertem — 1

### CHARACTERISTICS (attributes / properties)
  \# unique shown = 5
 
- Rating — 13
- user.location — 3
- username — 1
- orderstatus — 1
- Restaurant.address — 1

# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections)
### ARCH (classes)

- Driver
- Menu
- PaymentMethod
- Restaurant
- Order

### CONNECTIONS (associations / inheritance)
- Driver - Delivery
- Restaurant - Menu
- customer - order
- order - MenuItem


### CHARACTERISTICS (attributes / properties)
- address
- orderstatus
- username


## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY (ITERATION …)” sections)
### ARCH (classes)
- Customer
- Delivery
- MenuItem
- Notification

### CONNECTIONS (associations, inheritance, composition)
- Driver - User
- MenuItem - Menu
- Restaurant - User
- order - Delivery
- user - notification
- Customer - User

### CHARACTERISTICS (attributes / properties)
- Notification.sendTime
- user.email
- Delivery.status

### Result
- Acc_ARCH = 5/20 = 0.25 = 25.0%
- Acc_CONN = 4/19 = 0.2105 = 21.1%
- Acc_CHAR = 3/19 = 0.1579 = 15.8%
- Acc_ALL = (5 + 4 + 3) / (20 + 19 + 19) = 12/58 = 0.2069 = 20.7%
- AI_Contribution = 12 / (12 + 13) = 12/25 = 0.48 = 48.0%





