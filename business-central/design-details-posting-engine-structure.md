---
title: Design Details - Posting Engine Structure | Microsoft Docs
description: Posting interface and some other functions in codeunit 12 use posting engine functions to prepare and insert general ledger entry and GST entry records. The posting engine is also responsible for general ledger register creation.
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: e37bd2be3d0a30c3274e27d7ccbce7a3e14c30b1
ms.contentlocale: en-nz
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-posting-engine-structure"></a>Design Details: Posting Engine Structure
Posting interface and some other functions in codeunit 12 use posting engine functions to prepare and insert general ledger entry and GST entry records. The posting engine is also responsible for general ledger register creation.  
  
 The functions in the following table provide a standard framework for designing posting procedures (such as Code, CustPostApplyCustledgEntry, VendPostApplyVendLedgEntry, UnapplyCustLedgEntry, UnapplyVendLedgEntry, and Reverse) and exclusive access to table 17, G/L Entry.  
  
|Routine|Description|  
|-------------|---------------------------------------|  
|StartPosting|Initialises posting buffer TempGLEntryBuf, locks G/L Entry and GST Entry tables, and initialises Accounting Period, G/L Register, and Exchange Rate. Should be called only once, then NextEntryNo is 0.|  
|ContinuePosting|Checks and posts unrealised GST for previous transaction increment NextTransactionNo and prepares post of next line.|  
|FinishPosting|Completes posting by inserting G/L entries from temporary buffer into database table. Always used together with StartPosting. Checks for inconsistencies.|  
|InitGLEntry|Used to initialise new G/L entry for Gen. Jnl Line. Returns GLEntry as parameter.|  
|InitGLEntryVAT|Same as InitGLEntry, but also assigns Bal. Account No. and SummarizeVAT.|  
|InitGLEntryVATCopy|Similar to InitGLEntryGST, but also copies posting groups data from GST Entry before SummariseGST.|  
|InsertGLEntry|The only function that inserts G/L entry into global TempGLEntryBuf table. Always use this function for insert.|  
|CreateGLEntry|Performs an InitGLEntry, assigns Additional Currency Amount, and then performs InsertGLEntry. Replaces several lines of code with a single function call.|  
|CreateGLEntryBalAcc|Same as CreateGLEntry, but also assigns Bal. Account Type and Bal. Account No.|  
|CreateGLEntryVAT|Same as CreateGLEntry, but with additional processing for posting groups and saving to temporary GST buffer:<br /><br /> `GLEntry.CopyPostingGroupsFromDtldCVBuf(DtldCVLedgEntryBuf,GenJnlLine."Gen. Posting Type");`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryVATCollectAdj|Same as CreateGLEntry, but with additional collection of adjustments and saving to temporary GST buffer:<br /><br /> `CollectAdjustment(AdjAmount,GLEntry.Amount,GLEntry."Additional-Currency Amount",OriginalDateSet);`<br /><br /> `InsertVATEntriesFromTemp(DtldCVLedgEntryBuf,GLEntry);`|  
|CreateGLEntryFromVATEntry|Same as CreateGLEntry, but also copies posting groups from GST entry.|  
  
## <a name="see-also"></a>See Also  
 [Design Details: Posting Interface Structure](design-details-posting-interface-structure.md)