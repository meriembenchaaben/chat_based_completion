### Scenario: Food delivery application
- CONFIG: C-Full
- Time : 140 mins
  ### Summary (Key Metrics)

# Results of what is generated (from all “MANUAL CLASSIFICATION” sections)
### ARCH (classes)
# unique shown = 7
# Total generated occurrences = 20
- review — 11
- FoodItem — 3
- PaymentMethod — 2
- Driver — 1
- Menu — 1
- Order — 1
- Restaurant — 1

### CONNECTIONS (associations)
*(counted as undirected: e.g., `Order - Driver` and `Driver - Order` are merged)*
# unique shown = 8
# Total generated occurrences = 19
- order - Driver — 5
- Customer - paymentMethod — 4
- Menu - order — 3
- user - order — 3
- Restaurant - Menu — 1
- Driver - Delivery — 1
- order - MenuItem — 1
- customer - MenuIordertem — 1

### CHARACTERISTICS (attributes / properties)
# unique shown = 5
# Total generated occurrences = 19
- Rating — 13
- user.location — 3
- username — 1
- orderstatus — 1
- Restaurant.address — 1

# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list
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

## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY (ITERATION …)” sections) — unique list
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

### Metrics (binary acceptance; denominator = total suggestion occurrences)
- Acc_ARCH = 5/20 = 0.25 = 25.0%
- Acc_CONN = 4/19 = 0.2105 = 21.1%
- Acc_CHAR = 3/19 = 0.1579 = 15.8%
- Acc_ALL = (5 + 4 + 3) / (20 + 19 + 19) = 12/58 = 0.2069 = 20.7%
- AI_Contribution = 12 / (12 + 13) = 12/25 = 0.48 = 48.0%


### Scenario: Food delivery application
- CONFIG: C-Full
- Log: 20260203-234543
- Time: 110 mins

# Results of what is generated (from all “MANUAL CLASSIFICATION” sections)
### ARCH (classes)
# unique shown = 9
# Total generated occurrences = 20
- Address — 6
- Review — 5
- FoodItem — 3
- Driver — 1
- Menu — 1
- MenuItem — 1
- Order — 1
- PaymentMethod — 1
- Restaurant — 1

### CONNECTIONS (associations)
# unique shown = 12
# Total generated occurrences = 19
- Restaurant - Driver — 4
- User - Order — 3
- Customer - Order — 2
- Driver - Order — 2
- Customer - Restaurant — 1
- Driver - Delivery — 1
- Order - paymentMethod — 1
- Order - Restaurant — 1
- Restaurant - Menu — 1
- Restaurant - Order — 1
- User - Notification — 1
- User - PaymentMethod — 1

### CHARACTERISTICS (attributes / properties)
# unique shown = 10
# Total generated occurrences = 18
- Restaurant.rating — 6
- order.totalCost — 2
- Order.totalCost — 2
- Restaurant.Rating — 2
- Driver.Rating — 1
- Menu.MenuItems — 1
- Menu.itemPrice — 1
- Order.OrderStatus — 1
- Restaurant,rating — 1
- delivery.estimatedTimeOfArrival — 1

# AI ACCEPTED (from all “ACCEPTED (ITERATION …)” sections) — unique list
### ARCH (classes)
- Driver
- Menu
- MenuItem
- Order
- PaymentMethod
- Restaurant

### CONNECTIONS (associations / inheritance)
- Customer - Order
- Driver - Delivery
- Restaurant - Menu
- User - Notification

### CHARACTERISTICS (attributes / properties)
- delivery.estimatedTimeOfArrival

## ADDED ELEMENTS MANUALLY (from all “ADDED ELEMENTS MANUALLY (ITERATION …)” sections) — unique list
### ARCH (classes)
- Customer
- Delivery
- Notification

### CONNECTIONS (associations, inheritance, composition)
- Customer - User
- inheritance: Customer - User
- Order - MenuItem
- Order - paymentMethod
- Restaurant - User

### CHARACTERISTICS (attributes / properties)
- Notification.sendTime
- User.email
- User.username

### Metrics (binary acceptance; denominator = total suggestion occurrences)
- Acc_ARCH = 6/20 = 0.30 = 30.0%
- Acc_CONN = 4/19 = 0.2105 = 21.1%
- Acc_CHAR = 1/18 = 0.0556 = 5.6%
- Acc_ALL = (6 + 4 + 1) / (20 + 19 + 18) = 11/57 = 0.1930 = 19.3%
- Contr_ALL = 0/57 = 0.0%
- Irrel_ALL = 1 - (11/57) = 46/57 = 0.8070 = 80.7%

#### AI contribution (accepted vs final model = accepted ∪ manual)
- |A| = 11
- |M| = 3 + 5 + 3 = 11
- Overlap(A,M) = 0
- |A ∪ M| = 22
- AI_Contribution = 11/22 = 0.50 = 50.0%
