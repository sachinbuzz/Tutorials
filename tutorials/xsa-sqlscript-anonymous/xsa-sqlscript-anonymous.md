---
title: Anonymous Blocks
description: Leveraging SQLScript in Stored Procedures & User Defined Functions
tags: [  tutorial>intermediate, topic>sql, products>sap-hana, products>sap-hana\,-express-edition ]
---
## Prerequisites  
 - **Proficiency:** Intermediate
 - **Tutorials:** [Debugging Stored Procedures](http://go.sap.com/developer/tutorials/xsa-sqlscript-debugging.html)

## Next Steps
 - [Using Dynamic SQL vs Dynamic Filtering](http://go.sap.com/developer/tutorials/xsa-sqlscript-dynamic.html)

## Details
### You will learn  
In this exercise we will show you how you can invoke SQLScript logic without the need to create a persistent logic container such as a procedure or function. Instead we will use so called anonymous blocks.

### Time to Complete
**15 Min**.

---

1. From the HRTT page, click the "SQL Console" button

    ![SQL console](1.png)

2. To have an anonymous block you need a do begin … end.  Enter the this code in the SQL tab.

    ![SQL tab](2.png)

3. Copy the logic from the procedure `get_po_header_data` into the body.  Make sure to only copy the code between the BEGIN and END statements

    ![logic](3.png)

4. Let’s assume the application executing this block only allows string types. Since we have no signature for defining this we are simply declaring the type of the table variable  `EX_TOP_3_EMP_PO_COMBINED_CNT`.  The columns will then be implicitly converted to the corresponding types. Between the BEGIN statement and the first SELECT statement, enter a DECLARE statement to declare an intermediate table variable called `EX_TOP_3_EMP_PO_COMBINED_CNT` as shown

    ![sql code](4.png)

5. After the last SELECT statement and before the END statement, insert another SELECT against the intermediate table variable which you declared above 

    ![select statement](5.png)

6. The completed code should look very similar to this. If you do not wish to type this code, you can reference the solution web page at `http://<hostname>:51013/workshop/admin/ui/exerciseMaster/?workshop=dev602&sub=ex2_16`

    ```
    DO
    ```
    
7. Click "Run".

    ![run](7.png)

8. You will notice that the SQLScript code is executed and results are shown.  Again, there is no procedure or function created here, just the SQLScript being executed by the engine.

    ![SQL executed](8.png)



## Next Steps
 - [Using Dynamic SQL vs Dynamic Filtering](http://go.sap.com/developer/tutorials/xsa-sqlscript-dynamic.html)