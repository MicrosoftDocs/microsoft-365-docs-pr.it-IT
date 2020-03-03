---
title: Inviare messaggi di posta elettronica come lista di distribuzione in Office 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Vedere altre informazioni su come inviare posta elettronica come lista di distribuzione in Office 365.
ms.openlocfilehash: 076405b54f2a1521e0d9a1fc54c734b172eb82e8
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42361741"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a><span data-ttu-id="43899-103">Inviare messaggi di posta elettronica come lista di distribuzione in Office 365</span><span class="sxs-lookup"><span data-stu-id="43899-103">Send email as a distribution list in Office 365</span></span>

<span data-ttu-id="43899-104">In Office 365, è possibile inviare messaggi di posta elettronica come lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="43899-104">In Office 365, you can send email as a distribution list.</span></span> <span data-ttu-id="43899-105">Quando una persona che fa parte della lista di distribuzione risponde a un messaggio inviato alla lista di distribuzione, la posta elettronica sembra provenire dalla lista di distribuzione, non dal singolo utente.</span><span class="sxs-lookup"><span data-stu-id="43899-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="43899-106">In questo argomento viene illustrato come eseguire questa operazione.</span><span class="sxs-lookup"><span data-stu-id="43899-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="43899-107">Inviare messaggi di posta elettronica come lista di distribuzione</span><span class="sxs-lookup"><span data-stu-id="43899-107">Send email as a distribution list</span></span>

<span data-ttu-id="43899-108">Prima di eseguire questa procedura, verificare di essere stati aggiunti a una lista di distribuzione di Office 365 ed è stata concessa l'autorizzazione Invia come su di esso.</span><span class="sxs-lookup"><span data-stu-id="43899-108">Before you perform these steps, make sure you've been added to an Office 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="43899-109">**Amministratori**: assicurarsi di aver seguito i passaggi nell' [aggiunta di un utente di Office 365 o un contatto a un elenco](../email/add-user-or-contact-to-distribution-list.md) e [consentire ai membri di inviare messaggi di posta elettronica come argomenti di gruppo di Office 365](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) e di aggiungere gli utenti corretti alla lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="43899-109">**Admins**: Make sure you've followed the steps in the [Add an Office 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as an Office 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="43899-110">Aprire Outlook sul Web e passare alla posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="43899-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="43899-111">Aprire un messaggio che è stato inviato alla lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="43899-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="43899-112">Selezionare **Rispondi**.</span><span class="sxs-lookup"><span data-stu-id="43899-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="43899-113">Nella parte inferiore del messaggio, selezionare **altro** \> **Mostra da**.</span><span class="sxs-lookup"><span data-stu-id="43899-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="43899-114">![Seleziona altro e quindi fai clic su Mostra da](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="43899-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="43899-115">Fare clic con il pulsante destro del mouse sull'indirizzo `Ina@weewalter.me` mittente, ad esempio, e scegliere **Rimuovi**.</span><span class="sxs-lookup"><span data-stu-id="43899-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="43899-116">![Rimuovere l'alias da](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="43899-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="43899-117">Digitare quindi l'indirizzo della lista di distribuzione, ad esempio support@contoso.com, e inviare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="43899-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="43899-118">La volta successiva che rispondi dalla lista di distribuzione, il suo indirizzo verrà visualizzato come opzione nell'elenco **da** .</span><span class="sxs-lookup"><span data-stu-id="43899-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="43899-119">![Viene visualizzato l'alias della cassetta postale condivisa](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="43899-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

