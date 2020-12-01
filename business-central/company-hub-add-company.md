---
title: Add companies to your company hub
description: Learn how to add companies from other Business Central environments to your company hub so you can manage work across environments.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: accountant, accounting, company hub
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 773731ecc860e7d1ea0d13bbf9e6896a746544be
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: en-NZ
ms.lasthandoff: 10/01/2020
ms.locfileid: "3927850"
---
# <a name="add-companies-to-your-company-hub"></a>Add Companies to Your Company Hub

With the company hub, you can access your work from across multiple companies from multiple [!INCLUDE [prodshort](includes/prodshort.md)] environments. You can add a environments and companies manually, if your companies do not show up automatically in the company hub.  

Right in the company hub landing page, you find the **Setup** menu, from where you can access the **Environment Links** page. Simply choose **New** , and then fill in the fields. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

## <a name="environment-links"></a>Environment links

An environment link is a card where you specify the [!INCLUDE [prodshort](includes/prodshort.md)] environment that hosts one or more companies that you do work in. The data in the card for each environment is specified by you, and you can change it as needed. However, the **Environment Link** field is critical - this is how you can access each company in [!INCLUDE [prodshort](includes/prodshort.md)]. Use the **Test the connection** action in the ribbon to test that you entered the right link. The link that you must enter points at the environment that hosts the company that you are adding and it must include the Azure Active Directory (Azure AD) ID, or the organisation's domain name. For example, if they have specified a domain such as MyBusiness.com, then the link to their [!INCLUDE [prodshort](includes/prodshort.md)] is ```https://businesscentral.dynamics.com/mybusiness.com?redirectedfromsignup=1```. Otherwise, it will look something like this: ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```  

The link is used when you choose the company in the company hub.  

:::image type="content" source="media/company-hub-company-list-actions.png" alt-text="Actions for a company that is listed in the company hub":::

> [!TIP]
> If you're working in the free trial version of [!INCLUDE [prodshort](includes/prodshort.md)], it is easy to add the companies in your tenant. You can find the environment link by copying the Azure Active Directory ID from the **Troubleshooting** section of the Help & Support page. The environment name is probably the default value, PRODUCTION. Add this information to the **Environment Link** field, such as ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```, and then choose **Test the connection** . The evaluation company will be added to the list.
>
> If you have moved to the thirty-day trial company, My Company, you can add that to the list by choosing the **Reload / Reload all Companies** action in the list.

## <a name="load-companies"></a>Load companies

When you have added your environments, your companies show up automatically. However, if you know that a new company has been added to an environment, you can choose the **Reload all companies** action to refresh the list. Use the same action to refresh data from across your companies.  

> [!TIP]
> In order to refresh the data in the company hub, you must have access to the data in the companies that the data comes from.

## <a name="see-also"></a>See also

[Manage Work across Multiple Companies in the Company Hub](company-hub.md)  
[Resources for Help and Support](product-help-and-support.md)  