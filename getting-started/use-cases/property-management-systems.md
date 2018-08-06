# Property Management Systems

## Invoices and Payments

Invoices and Payments will be synced from iVvy into the PMS system automatically to reflect the financial history of the contact and their bookings.

Incrementally: When an invoice is raised within a booking in the iVvy System

1. A contact or company will be generated within the PMS system
2. An invoice will be created and assigned to the aforementioned contact, and its line items will mirror that of the invoice in iVvy. 
3. If a payment is raised against the invoice in iVvy, then the payment will also be copied into the PMS system against the invoice created. 
4. Or alternatively, if a payment is taken in the PMS it will be sent to iVvy against the original invoice. 

![](../../.gitbook/assets/invoices-and-payments-v2-2.jpg)

## Group Accommodation Blocks

Group accommodation blocks will be synced from iVvy to the PMS system. The iVvy system will trigger an event when accommodation bookings are created, and release schedules are due.

Changes made by the user in iVvy will trigger an update event which will result in an update in the PMS.

![](../../.gitbook/assets/group-accommodation-v2-3.jpg)

## Room Reservations

Rooming lists take accommodation blocks one step further by allocating single reservations within the accommodation block to indicate the occupant of the room. These reservations will be synced to the PMS so the user has occupant information.

Any changes to the reservations will trigger an event that will update the rooming list in the PMS.

![](../../.gitbook/assets/room-reservations-v2-4.jpg)

## ARI \(Availability, Rates and Inventory\)

Availability, rates and inventory will be sourced from the PMS to appear in iVvy as real time data from the PMS. This includes in iVvy displaying up to

* rate plans, 
* dynamic inventory and 
* room data. 

