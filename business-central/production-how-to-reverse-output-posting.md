---
title: How to Reverse Output Posting | Microsoft Docs
description: There are times when output posting must be reversed. An example of this would be if a data entry error occurred and an incorrect amount of output is posted to a production order.
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: f2430dcf45303e04baad406880783ab0f74dd4f2
ms.contentlocale: en-nz
ms.lasthandoff: 03/22/2018

---
# <a name="reverse-output-posting"></a>Reverse Output Posting
There are times when output posting must be reversed. An example of this would be if a data entry error occurred and an incorrect amount of output is posted to a production order.  

## <a name="to-reverse-an-output-posting"></a>To reverse an output posting  
1.  Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Output Journal**, and then choose the related link. Select your batch.  
2. Fill in the fields as necessary. For more information, see [Batch Post Output and Run Times](production-how-to-post-output-quantity.md).
3.  In the **Applies-To Entry** field, select the associated item ledger entry. This reverses the capacity and item ledger entries.  
4. Post the reversal by posting the journal.  

The output journal entries are posted to the item ledger as a positive adjustment.  

## <a name="see-also"></a>See Also  
 [Manufacturing](production-manage-manufacturing.md)    
 [Setting Up Manufacturing](production-configure-production-processes.md)  
 [Planning](production-planning.md)      
 [Inventory](inventory-manage-inventory.md)  
 [Purchasing](purchasing-manage-purchasing.md)  
 [Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
