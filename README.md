# optogurobi
A company wishes to produce six different products.  We have labeled these products P1 through P6.  Each product is produced in batches of 1000.  The company wishes to plan its production for the next 12 weeks.    The demand in thousands for the 12 coming weeks and for each product is given in the following table:


For every product, the initial stock is known as well as the required final stock level (in thousands).  Per batch of each product, the production and storage costs in dollars are given, together with the required working time for workers and machines (in hours).  The required storage space (measured in linear feet) is also provided.
The number of working hours of the personnel is limited to 390 hours per week.  Each product must use two machines types (Type 1 and Type 2) to complete the production process and the Type 1 machines have a weekly capacity of 850 hours while the Type 2 machines only have 830 hours.  Storage space is limited to 1000 linear feet of shelf space.  

# Assumptions
1.	The storage cost and storage space was assumed to pertain to Inventory.
2.	Production costs, storage costs remain steady over the entire 12 week period
3.	Worker time, Machine times remain steady over the entire 12 week period
4.	No workers were absent during the projected weeks
5.	No down-times on machines during the projected weeks.
6.	Variables are assumed to be real numbers. i.e allowed for fractions

# Formulation:
Let Ppw be the number of batches of product p in week w. p=1,2,3…6. w=1,2,3…12 
Let Ipw be the inventory for products in their respective weeks
Let Dpw be the Demand for products in their respective weeks
Minimize: 
Sum(Production Cost per batch of product p produced for week w, Storage cost per batch of inventory in w)
Subject to
- Initial inventory: 	Ip0 = Initial inventory
- Final inventory:		Ip12>= Min Final inventory
- Demand Constraint: 	Ppw – Ipw +Ipw-1 = Dpw
For every week:
- Total worker time <= Max Working hours
- Total Machine Time used <= Available machine hours
- Storage space used by inventory <= Max storage space

# Observations
- Initial inventory covers first week demand for all products except Product 1 and 5.
- Worker times and production costs are the highest for product 5 while storage costs are lowest which results in high inventory accumulation
- Leaving initial and final inventory storage costs, a large contribution to storage costs are by production of Products 1, 5 and 6.
- There is a considerable amount of difference in production and inventory when the variables are declared as taking integer values. Fig2
- Suppose the final inventory was changed from 10 to 15 for all products, the problems becomes infeasible. However it continues to be optimal when the final inventory of Product 1 is changed from 10 to 15. The minimized cost in that case comes to $185537.1 
- Production costs for Product 5 remain highly sensitive to time while other products remain a more or less steady over the 12 week period.
