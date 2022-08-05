---
title: Set Up Customer Discount Groups
description: Learn how to set up customer discount groups and create sales line discounts for those groups.
author: rubenseishima
ms.service: dynamics365-business-central
ms.topic: article
ms.date: 06/08/2022
ms.author: a-reishima
ms.openlocfilehash: fc2e5af5792a4c212c56b2e8a8a28b3b48ecff33
ms.sourcegitcommit: 7b6d70798b4da283d1d3e38a05151df2209c2b72
ms.translationtype: HT
ms.contentlocale: en-NZ
ms.lasthandoff: 06/12/2022
ms.locfileid: "8950549"
---
# <a name="set-up-customer-discount-groups"></a>Set Up Customer Discount Groups

You can define sales line discounts for a group of customers instead of applying them individually.

**Customer Discount Groups** work similarly to [customer price groups](sales-how-to-set-up-customer-price-groups.md) but can be combined with Item Discount Groups to quickly set line discounts to many items for selected customers.

## <a name="create-sales-line-discounts-for-a-customer-group"></a>Create sales line discounts for a customer group

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Disc. Groups**, and then choose the related link.
2. On the **Customer Disc. Groups** page, select **New** to create a new discount group and give it a name under the **Code** column and add a description.
3. Select the **Navigate** action, and choose **Sales Line Discounts**.
4. Fill in the **Sales Code** column with the discount group created on the previous page.
5. Fill in the fields on the lines with the **Type** (Item or Item Discount Group), **Code**, **Unit of Measure Code**, and the **Line Discount %**.
6. If the customer group needs to purchase a minimum quantity in order to gain the discount, fill in the **Minimum Quantity** field.
7. If necessary, enter the **Starting Date** and **Ending Date** for the discount group.
8. If relevant, you can also specify the **Currency Code** or **Variant Code** after [personalising the columns](ui-personalization-user.md).

Repeat steps 4 through 8 for each item or item discount group you want to create a sales line discount for.

## <a name="assign-a-customer-to-a-discount-group"></a>Assign a customer to a discount group

After you have set up the customer discount groups, you can enter the customer discount group codes on the customer cards.

1. Choose the ![Lightbulb that opens the Tell Me feature 1.](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customers**, and then choose the related link.
2. Open the **Customer Card** for a customer you want to be part of a customer discount group.
3. On the **Invoicing** FastTab, in the **Customer Disc. Group** field, select the group code.

## <a name="see-also"></a>See also

[Sales](sales-manage-sales.md)  
[Setting Up Sales](sales-setup-sales.md)  
[Recording Special Sales Prices and Discounts](sales-how-record-sales-price-discount-payment-agreements.md)  
[Setting Up Customer Price Groups](sales-how-to-set-up-customer-price-groups.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]