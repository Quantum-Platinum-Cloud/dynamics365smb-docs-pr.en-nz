---
title: How to Subcontract Manufacturing | Microsoft Docs
description: When the purchase order has been created from the subcontractor worksheet, then it can be posted.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/16/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 9c62f99c4baddedaaff6629c573d898f0fbd7f1a
ms.contentlocale: en-nz
ms.lasthandoff: 03/22/2018

---
# <a name="subcontract-manufacturing"></a>Subcontract Manufacturing
Subcontracting selected operations to vendor is common in many manufacturing companies. Subcontracting can be a rare occurrence or can be an integral part of all production processes.

The program provides several tools for managing subcontract work:  

- Work Centres with assigned vendor: This feature enables you to set up a work centre that is associated with a vendor (subcontractor). This is called a subcontract work centre. You can specify a subcontract work centre on a routing operation, which allows you to easily process the subcontracted activity. In addition, the cost of the operation can be designated at the routing or the work centre level.  
- Work Centre cost based on units or time: This feature enables you to specify whether costs associated with the work centre are based on the production time or a flat charge per unit. Although subcontractors commonly use a flat charge per unit to charge for their services, the program can handle both options (production time and flat charge per unit).  
- Subcontracting Worksheet: This feature allows you to find the production orders with material ready to send to a subcontractor and to automatically create purchase orders for subcontract operations from production order routings. Then the program automatically posts the purchase order charges to the production order during the posting of the purchase order. Only production orders with a status of released can be accessed and used from a subcontracting worksheet.  

## <a name="subcontract-work-centers"></a>Subcontract Work Centres  
Subcontract Work Centres are set up the same as regular work centres with additional information. They are assigned to routings in the same manner as other work centres.  

### <a name="subcontract-work-center-fields"></a>Subcontract Work Centre Fields  
This **Subcontractor No.** field designates the work centre as a subcontract work centre. You can enter the number of a subcontractor who supplies the work centre. This field can be used to administer work centres, which are not in-house but perform processing under contract.  

If you subcontract with the vendor for a different rate for each process, then select the **Specific Unit Cost** field. This lets you set up a cost on each routing line and saves the time of re-entering each purchase order. The cost on the routing line is used in processing instead of the cost on the work centre cost fields. Selecting the **Specific Unit Cost** field calculates costs for the vendor by the routing operation.  

If you subcontract at a single rate per vendor, leave the **Specific Unit Cost** field blank. The costs will be set up by filling in **Direct Unit Cost**, **Indirect Cost %**, and **Overhead Rate** fields.  

### <a name="routings-that-use-subcontract-work-centers"></a>Routings that use Subcontract Work Centres  
Subcontract work centres can be used for operations on routings in the same way as regular work centres.  

You can set up a routing that uses an outside work centre as a standard operational step. Alternatively, you can modify the routing for a particular production order to include an outside operation. This might be needed in an emergency such as a server not working correctly, or during a temporary period of higher demand, where the work generally performed in-house must be sent to a subcontractor.  

For more information, see [Create Routings](production-how-to-create-routings.md).  

## <a name="calculate-subcontracting-worksheets-and-create-subcontract-purchase-orders"></a>Calculate Subcontracting Worksheets and Create Subcontract Purchase Orders  
Once you have calculated the subcontracting worksheet, the relevant document, in this case a purchase order, is created.  

The **Subcontracting Worksheet** window functions like the **Planning Worksheet** by calculating the needed supply, in this case purchase orders, which you review in the worksheet and then create with the **Carry Out Action Message** function.  

> [!NOTE]  
>  Only production orders with status **Released** can be accessed and used from a subcontracting worksheet.  

### <a name="to-calculate-the-subcontracting-worksheet"></a>To calculate the subcontracting worksheet  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Worksheet**, and then choose the related link.  
2.  To calculate the worksheet, choose the **Calculate Subcontracts** action.  
3.  In the **Calculate Subcontracts** window, set filters for the subcontracted operations, or the work centres where they are performed, to calculate only the relevant production orders.  
4.  Choose the **OK** button.  

    Review the lines in the **Subcontracting Worksheet** window. The information in this worksheet comes from the production order and production order routing lines and flows to the purchase order when that document is created. You can delete a row from the worksheet without affecting the original information, just as you can with the other worksheets. The information will reappear the next time you run the **Calculate Subcontracts** function.  

### <a name="to-create-the-subcontract-purchase-order"></a>To create the subcontract purchase order  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Subcontracting Worksheet**, and then choose the related link.  
2.  On the **Actions** tab, in the **Process** group, choose **Carry Out Action Message**.  
3.  Select the **Print Orders** field to print the purchase order as it is created.  
4.  Choose the **OK** button.  

If all subcontracted operations are sent to the same vendor location, then only one purchase order is created.  

The worksheet line that was turned into a purchase order is deleted from the worksheet. Once a purchase order is created, it will not appear in the worksheet again.  

## <a name="posting-subcontract-purchase-orders"></a>Posting Subcontract Purchase Orders  
Once the Subcontractor Purchase Orders have been created, they can be posted. Receiving the order posts a Capacity Ledger Entry to the production order and invoicing the order posts the direct cost of the purchase order to the production order.  

When the purchase is posted as received, then an output journal entry is automatically posted for the production order. This only applies if the subcontract operation is the last operation on the production order routing.  

> [!CAUTION]  
>  Posting output automatically for an ongoing production order when subcontracted items are received may not be desired. Reasons for this could be that the expected output quantity that is posted may be different from the actual quantity and that the posting date of the automatic output is misleading.  
>   
>  To avoid that the expected output of a production order is posted when subcontract purchases are received, make sure the subcontracted operation is not the last one. Alternatively, insert a new last operation for the final output quantity.

## <a name="to-post-a-subcontract-purchase-order"></a>To post a subcontract purchase order  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Orders**, and then select the related link.  
2.  Open a purchase order that is created from the subcontracting worksheet.  

    On the purchase order lines, you see the same information that was in the worksheet. The **Prod. Order No.**, **Prod. Order Line No.**, **Operation No.**, and **Work Centre No.** fields are filled in with the information from the source production order.  

3.  Choose the **Post** action.  

When the purchase is posted as received, then an output journal entry is automatically posted for the production order. This only applies if the subcontract operation is the last operation on the production order routing.  

> [!CAUTION]  
>  Posting output automatically for an ongoing production order when subcontracted items are received may not be desired. Reasons for this could be that the expected output quantity that is posted may be different from the actual quantity and that the posting date of the automatic output is misleading.  
>   
>  To avoid that the expected output of a production order is posted when subcontract purchases are received, make sure the subcontracted operation is not the last one. Alternatively, insert a new last operation for the final output quantity.  

When the purchase order is posted as invoiced, then the direct cost of the purchase order is posted to the production.  

## <a name="see-also"></a>See Also  
[Manufacturing](production-manage-manufacturing.md)    
[Setting Up Manufacturing](production-configure-production-processes.md)  
[Planning](production-planning.md)      
[Inventory](inventory-manage-inventory.md)  
[Purchasing](purchasing-manage-purchasing.md)  
[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
