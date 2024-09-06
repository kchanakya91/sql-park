# sql-park
sql code for park tables 
Create the following tables for a tool rental database with appropriate primary keys & foreign keys.

Assumptions: You will create a set of tables for managing amusement parks
1.	There are multiple parks. Each park has a scheduled open/close time each day. 
2.	Each park has a number of rides. Each ride has a minimal height requirement. 
3.	Customers can buy one-day ticket for a park. 
4.	There are two ways a customer can have a ride: 1) just showing up, and the customer has to wait at the end of the queue (potentially high wait time); 
2) use a reservation function to book up to 3 rides per ticket (like Disney's fastpass). Each reservation has a reserved time and the customer needs to come around that time. Each ride has a return time which is the earliest reserved time could be. E.g., if a ride has a returned time of 4 pm, any reservation must be after 4 pm. 

Once the customer used a reservation, the customer can make another reservation as long as the customer has no more than three (including the new one) unused reservations on that ticket. 
   
The list of tables is: 

Park table:
Columns:
pid: park ID 
pname: park name 
 

Park_schedule table
Columns:
pid: park ID 
sdate: schedule date 
open_time: opening time (using timestamp)
close_time: closing time. 

Ride table: 
Columns:
rid: ride ID 
rname: ride name.
pid: park ID 
min_height: minimal height in inches 
capacity: number of people can be on the ride at the same time 
ride_time: estimated ride time for a ride, using interval day to second. 
wait_time: current wait time in minutes, using integer or number 
return_time: time for users to use free reservation to come  


Customer table:
Columns: 
cid: customer ID 
cname: customer name 
age: age 
height: height 

Ticket table: 
Columns:
tid: ticket ID 
cid: customer ID
pid: park ID 
tdate: date to use the ticket 
price: price paid 

Reservation table:
Columns
rsid: reservation ID 
tid: ticket ID 
rid: ride ID 
rtime: reserved ride time, must be after the return_time 
status: 1 used, 0 not used. 
utime: used time.

