---
title: Configurazione delle notifiche di posta indesiderata dell'utente finale in EOP
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: e9947db5-1dd1-4493-872d-7362b24c7ba0
ms.collection:
- M365-security-compliance
description: È possibile configurare le notifiche di posta indesiderata degli utenti finali per il criterio di filtro del contenuto a livello dell'azienda o per i criteri di filtro del contenuto personalizzati applicati ai domini.
ms.openlocfilehash: d20186afaa25b70a40efa88f692a04f3428abb65
ms.sourcegitcommit: 333ecfb8bfeb34f9f08d82d295b40d37de6ba8b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "37772230"
---
# <a name="configure-end-user-spam-notifications-in-eop"></a><span data-ttu-id="77bf8-103">Configurazione delle notifiche di posta indesiderata dell'utente finale in EOP</span><span class="sxs-lookup"><span data-stu-id="77bf8-103">Configure end-user spam notifications in EOP</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="77bf8-104">Questo argomento è rivolto ai clienti delle versioni autonome di Exchange Online Protection (EOP) che devono proteggere le cassette postali locali.</span><span class="sxs-lookup"><span data-stu-id="77bf8-104">This topic is for Exchange Online Protection (EOP) standalone customers who are protecting on-premises mailboxes.</span></span> <span data-ttu-id="77bf8-105">I clienti di Exchange Online che proteggono le cassette postali ospitate nel cloud dovrebbero invece leggere l'argomento seguente: [configurare le notifiche di posta indesiderata dell'utente finale in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span><span class="sxs-lookup"><span data-stu-id="77bf8-105">Exchange Online customers who are protecting cloud-hosted mailboxes should read the following topic instead: [Configure end-user spam notifications in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).</span></span> 
  
<span data-ttu-id="77bf8-p102">È possibile configurare le notifiche di posta indesiderata degli utenti finali per il criterio di filtro del contenuto a livello dell'azienda o per i criteri di filtro del contenuto personalizzati applicati ai domini. L'abilitazione dei messaggi di notifica di posta indesiderata per l'utente finale consente agli utenti di gestire autonomamente i messaggi di posta indesiderata messi in quarantena. Le notifiche di posta indesiderata dell'utente finale non possono essere utilizzate con criteri applicati a utenti o gruppi o a un criterio con eccezioni.</span><span class="sxs-lookup"><span data-stu-id="77bf8-p102">You can configure end-user spam notifications for the default company-wide content filter policy or for custom content filter policies that are applied to domains. Enabling end-user spam notification messages lets your end users self-manage their own spam-quarantined messages. End-user spam notifications cannot be used with policies applied to users or groups, or to a policy with exceptions.</span></span>
  
<span data-ttu-id="77bf8-p103">Le notifiche di posta indesiderata dell'utente finale contengono un elenco di tutti i messaggi di posta indesiderata messi in quarantena ricevuti dall'utente finale durante un periodo di tempo configurato. È possibile specificare un valore compreso tra 1 e 15 giorni. È inoltre possibile configurare la lingua in cui è scritto il messaggio di notifica.</span><span class="sxs-lookup"><span data-stu-id="77bf8-p103">End-user spam notifications contain a list of all spam-quarantined messages that the end user has received during a time period that you configure (you can specify a value between 1 and 15 days). You can also configure the language in which the notification message is written.</span></span>
  
<span data-ttu-id="77bf8-111">Dopo la ricezione di un messaggio di notifica, gli utenti finali possono scegliere tra le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="77bf8-111">After receiving a notification message, end users can choose from the following options:</span></span>

<span data-ttu-id="77bf8-112">**Blocca mittente** se si desidera che in Office 365 venga aggiunto il mittente all'elenco dei mittenti bloccati.</span><span class="sxs-lookup"><span data-stu-id="77bf8-112">**Block Sender** if you want Office 365 to add the sender to your blocked senders list.</span></span>

<span data-ttu-id="77bf8-113">**Revisione** per passare al portale di quarantena all'interno del Centro sicurezza e conformità se si desidera eseguire altre operazioni, ad esempio l'anteprima o il rilascio.</span><span class="sxs-lookup"><span data-stu-id="77bf8-113">**Review** to navigate to the Quarantine Portal within the Security and Compliance Center if you want to take other actions, such as Preview or Release.</span></span>
  
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="77bf8-114">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="77bf8-114">What do you need to know before you begin?</span></span>
<span data-ttu-id="77bf8-115"><a name="sectionSection0"> </a></span><span class="sxs-lookup"><span data-stu-id="77bf8-115"></span></span>

<span data-ttu-id="77bf8-116">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="77bf8-116">Estimated time to complete: 5 minutes</span></span>
  
<span data-ttu-id="77bf8-p104">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Protezione da posta indesiderata" nell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="77bf8-p104">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Anti-spam" entry in the [Feature permissions in EOP](feature-permissions-in-eop.md) topic.</span></span> 
  
<span data-ttu-id="77bf8-119">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="77bf8-119">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>
  
## <a name="use-the-eac-to-configure-end-user-spam-notifications"></a><span data-ttu-id="77bf8-120">Utilizzo dell'interfaccia di amministrazione di Exchange per la configurazione delle notifiche di posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="77bf8-120">Use the EAC to configure end-user spam notifications</span></span>

1. <span data-ttu-id="77bf8-121">Nell'interfaccia di amministrazione di Exchange (EAC), accedere a **protezione** > dalla**posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="77bf8-121">In the Exchange Admin Center (EAC), navigate to **Protection** > **Spam filter**.</span></span>
    
2. <span data-ttu-id="77bf8-122">Selezionare il filtro contenuto per cui si desidera abilitare le notifiche di posta indesiderata dell'utente finale, che sono disabilitate per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="77bf8-122">Select the content filter policy for which you want to enable end-user spam notifications (they are disabled by default).</span></span>
    
3. <span data-ttu-id="77bf8-123">Nel riquadro di destra, in cui sono contenute informazioni di riepilogo sul criterio, fare clic sul collegamento **Configura notifiche spam utente finale**.</span><span class="sxs-lookup"><span data-stu-id="77bf8-123">In the right pane, where the summary information about your policy appears, click the **Configure End-user spam notifications** link.</span></span> 
    
4. <span data-ttu-id="77bf8-124">Nella finestra di dialogo successiva è possibile configurare le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="77bf8-124">In the subsequent dialog box, you can configure the following options:</span></span>
    
1. <span data-ttu-id="77bf8-p105">**Abilita le notifiche di spam all'utente finale** Selezionare questa casella di controllo per abilitare le notifiche di posta indesiderata dell'utente finale per questo criterio. Viceversa, se questo criterio è abilitato, è possibile deselezionare la casella di controllo per disabilitare le notifiche di posta indesiderata dell'utente finale per tale criterio.</span><span class="sxs-lookup"><span data-stu-id="77bf8-p105">**Enable end-user spam notifications** Select this check box in order to enable end-user spam notifications for this policy. (Conversely, if this policy is enabled, you can clear this check box in order to disable end-user spam notifications for this policy.)</span></span> 
    
2. <span data-ttu-id="77bf8-p106">**Invia notifiche di spam agli utenti finali ogni (giorni)** Consente di specificare la frequenza di invio delle notifiche di posta indesiderata dell'utente finale. Il valore predefinito è 3 giorni. È possibile specificare un valore compreso tra 1 e 15 giorni. Se, ad esempio, si specifica 7 giorni, la notifica includerà l'elenco di tutti i messaggi che negli ultimi 7 giorni erano diretti all'utente ma che sono stati invece inviati alla quarantena della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="77bf8-p106">**Send end-user spam notifications every (days)** Specify how often to send end-user spam notifications. The default is 3 days. You can specify between 1 and 15 days. If you specify 7 days, for example, the notification will include a list of all messages intended for that user within the past 7 days that were sent to the spam quarantine instead.</span></span> 
    
3. <span data-ttu-id="77bf8-131">**Lingua delle notifiche** Utilizzando l'elenco a discesa, selezionare la lingua in cui scrivere le notifiche di posta indesiderata dell'utente finale per il criterio in questione.</span><span class="sxs-lookup"><span data-stu-id="77bf8-131">**Notification language** Using the drop-down list, select the language in which to write end-user spam notifications for this policy.</span></span> 
    
5. <span data-ttu-id="77bf8-p107">Fare clic su **Salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni del criterio di filtro del contenuto, incluse quelle relative alle notifiche di posta indesiderata dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="77bf8-p107">Click **save**. A summary of your content filter policy settings, including your end-user spam notification settings, appears in the right pane.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="77bf8-p108">Le notifiche di posta indesiderata dell'utente finale saranno applicate solo ai criteri filtro del contenuto abilitati. >  Le notifiche di posta indesiderata dell'utente finale vengono inviate solo una volta al giorno. Non è possibile garantire l'ora di recapito della notifica per alcun utente specifico e non è possibile configurarla.</span><span class="sxs-lookup"><span data-stu-id="77bf8-p108">End-user spam notifications will only be functional for content filter policies that are enabled. >  End-user spam notifications are only sent once per day. The delivery time of the notification cannot be guaranteed for any specific customer and is not configurable.</span></span> 
  
 <span data-ttu-id="77bf8-137">**Suggerimento:** Se si desidera testare le notifiche di posta indesiderata dell'utente finale inviando un gruppo limitato di utenti prima di implementarle completamente, creare un criterio di filtro del contenuto personalizzato che consenta le notifiche di posta indesiderata dell'utente finale per i domini in cui risiedono gli utenti.</span><span class="sxs-lookup"><span data-stu-id="77bf8-137">**Tip:** If you want to test end-user spam notifications by sending them to a limited set of users before fully implementing them, create a custom content filter policy that enables end-user spam notifications for the domains in which the users reside.</span></span> <span data-ttu-id="77bf8-138">Quindi, nell'interfaccia di amministrazione di Exchange, in **regole del flusso \> di posta**, creare una regola del flusso di posta (nota anche come regola di trasporto) per bloccare i messaggi da Quarantine@messaging.microsoft.com (l'indirizzo di posta elettronica che invia le notifiche) con le eccezioni per gli utenti che si desidera per ricevere le notifiche.</span><span class="sxs-lookup"><span data-stu-id="77bf8-138">Then, in the EAC, under **Mail flow \> rules**, create a mail flow rule (also known as a transport rule) to block messages from quarantine@messaging.microsoft.com (the email address that sends notifications) with exceptions for the users who you want to receive the notifications.</span></span> <span data-ttu-id="77bf8-139">La figura seguente descrive un esempio relativo alla creazione di un'eccezione per due utenti (SaraD e AlexD) dal dominio Contoso.com:</span><span class="sxs-lookup"><span data-stu-id="77bf8-139">The following image is an example of creating an exception for two users (SaraD and AlexD) from domain Contoso.com:</span></span> 
  
![Regola di trasporto per verificare le notifiche di posta indesiderata dell'utente finale](../media/EOP-ESN-testspecificusers.jpg)
  
## <a name="for-more-information"></a><span data-ttu-id="77bf8-141">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="77bf8-141">For more information</span></span>

[<span data-ttu-id="77bf8-142">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="77bf8-142">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)
  
