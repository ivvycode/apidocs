# Property Management Systems



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

The accommodation Namespace on the iVvy API allows users to;

* [Add or Update Room Counts](../../venues/accommodation/add-or-update-room-counts.md),  
* [Add or Update Room Dynamic Rates](../../venues/accommodation/add-or-update-room-dynamic-rates.md), 
* [Remove Room Dynamics Rates](../../venues/accommodation/remove-room-dynamic-rates.md), and
* [Add or Update Rate Plan Booking Rules](property-management-systems.md) 

