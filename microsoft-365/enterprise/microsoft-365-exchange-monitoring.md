---
title: Monitoraggio di Exchange Online per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/03/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: Usare il monitoraggio di Exchange Online per informazioni sugli incidenti di posta elettronica o gli avvisi in Microsoft 365.
ms.openlocfilehash: 3d88378449879d451b21ba8bf2a7b5c3032a2c07
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286442"
---
# <a name="exchange-online-monitoring-for-microsoft-365"></a><span data-ttu-id="61cf4-103">Monitoraggio di Exchange Online per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="61cf4-103">Exchange Online monitoring for Microsoft 365</span></span>

<span data-ttu-id="61cf4-104">È possibile usare il monitoraggio di Exchange Online nell'interfaccia di amministrazione di Microsoft 365 per monitorare l'integrità del servizio Exchange per l'abbonamento a Microsoft 365 dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61cf4-104">You can use Exchange Online monitoring in the Microsoft 365 admin center to monitor the health of the Exchange service for your organization’s Microsoft 365 subscription.</span></span> <span data-ttu-id="61cf4-105">Il monitoraggio di Exchange Online fornisce informazioni sugli incidenti e avvisi raccolti nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="61cf4-105">Exchange Online monitoring provides you with information about incidents and advisories that are collected in these categories:</span></span>

- <span data-ttu-id="61cf4-106">**Infrastruttura**: il problema viene rilevato nell'infrastruttura Microsoft 365 di proprietà di Microsoft, usata per fornire aggiornamenti regolari e risolvere i problemi.</span><span class="sxs-lookup"><span data-stu-id="61cf4-106">**Infrastructure**: Issue is detected in the Microsoft 365 infrastructure that Microsoft owns for providing regular updates and resolving the issue.</span></span> <span data-ttu-id="61cf4-107">Ad esempio, gli utenti non possono accedere a Exchange Online a causa di problemi di Exchange o di un'altra infrastruttura cloud di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61cf4-107">For example, users cannot access Exchange Online because of issues with Exchange or other Microsoft 365 cloud infrastructure.</span></span>
- <span data-ttu-id="61cf4-108">**Infrastruttura di terze parti**: il problema è rilevato nell'infrastruttura di terze parti da cui l'organizzazione dipende e per risolverlo occorre l'intervento dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="61cf4-108">**Third-party infrastructure**: Issue is detected in third-party infrastructure on which your organization has taken a dependency and requires action from your organization for resolution.</span></span> <span data-ttu-id="61cf4-109">Ad esempio, le transazioni di autenticazione degli utenti vengono limitate da un provider del servizio token di sicurezza (STS) di terze parti, che impedisce agli utenti di connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="61cf4-109">For example, user authentication transactions are getting throttled by a third-party security token service (STS) provider that prevents users from connecting to Exchange Online.</span></span>
- <span data-ttu-id="61cf4-110">**Infrastruttura clienti**: il problema è rilevato nell'infrastruttura dell'organizzazione, che deve intervenire per risolverlo.</span><span class="sxs-lookup"><span data-stu-id="61cf4-110">**Customer infrastructure**: Issue is detected in your organization's infrastructure and requires action from your organization for resolution.</span></span> <span data-ttu-id="61cf4-111">Ad esempio, gli utenti non possono accedere a Exchange Online perché non riescono a ottenere un token di autenticazione dal provider STS ospitato dall'organizzazione a causa di un certificato scaduto.</span><span class="sxs-lookup"><span data-stu-id="61cf4-111">For example, users cannot access Exchange Online because they are unable to obtain an authentication token from STS provider hosted by your organization because of an expired certificate.</span></span>

<span data-ttu-id="61cf4-112">Ecco un esempio della pagina **Integrità dei servizi** nell'interfaccia di amministrazione di Microsoft 365, accessibile da **Integrità > Integrità dei servizi**.</span><span class="sxs-lookup"><span data-stu-id="61cf4-112">Here is an example of the **Service health** page in the Microsoft 365 admin center, available from **Health > Service health**.</span></span>

![Pagina Integrità dei servizi nell'interfaccia di amministrazione di Microsoft 365](../media/microsoft-365-exchange-monitoring/service-health-dashboard-example.png)

<span data-ttu-id="61cf4-114">Il valore della colonna **Stato** indica se il servizio è integro oppure presenta incidenti o avvisi basati sui servizi cloud gestiti da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="61cf4-114">The value of the **Status** column indicates whether the service is healthy or has advisories or incidents based on the cloud services that Microsoft maintains.</span></span> 

<span data-ttu-id="61cf4-115">Il valore della colonna **Problemi dell'organizzazione e di terza parte** indica che l'infrastruttura dell'organizzazione o un software di terze parti influisce sull'esperienza degli utenti rispetto all'integrità dei servizi di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="61cf4-115">The value of the **Your org and 3rd party issues** column indicates that your organization's infrastructure or third-party software affects your users service health experience with Exchange Online.</span></span> <span data-ttu-id="61cf4-116">Per la risoluzione degli avvisi o degli incidenti è necessario l'intervento *dell'amministratore*.</span><span class="sxs-lookup"><span data-stu-id="61cf4-116">Advisories or incidents require *your* actions to resolve.</span></span>

<span data-ttu-id="61cf4-117">Ecco un esempio della pagina di monitoraggio di **Exchange Online** nell'interfaccia di amministrazione di Microsoft 365, accessibile da **Integrità > Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="61cf4-117">Here is an example of the **Exchange Online** monitoring page in the Microsoft 365 admin center, available from **Health > Service health > Exchange Online**.</span></span>

![Pagina di monitoraggio di Exchange Online nell'interfaccia di amministrazione di Microsoft 365](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example.png)

<span data-ttu-id="61cf4-119">Nella pagina di monitoraggio di **Exchange Online** è possibile verificare l’integrità del servizio Exchange Online e se sono presenti incidenti o avvisi associati.</span><span class="sxs-lookup"><span data-stu-id="61cf4-119">With the **Exchange Online** monitoring page, you can see whether the Exchange Online service is healthy or not and whether there are any associated incidents or advisories.</span></span> <span data-ttu-id="61cf4-120">Con il monitoraggio di Exchange Online, è possibile esaminare l'integrità del servizio per specifici scenari di posta elettronica e visualizzare segnali in tempo quasi reale per determinare l'impatto in base allo scenario.</span><span class="sxs-lookup"><span data-stu-id="61cf4-120">With Exchange Online monitoring, you can look at the service health for specific email scenarios and view near real-time signals to determine the impact by scenario.</span></span> 

## <a name="requirements"></a><span data-ttu-id="61cf4-121">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61cf4-121">Requirements</span></span>

<span data-ttu-id="61cf4-122">Questa anteprima è abilitata per i clienti che soddisfano i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="61cf4-122">This preview is enabled for customers who meet these requirements:</span></span> 

- <span data-ttu-id="61cf4-123">L'organizzazione deve avere almeno 5.000 licenze per uno o una combinazione dei prodotti seguenti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="61cf4-123">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 

  <span data-ttu-id="61cf4-124">Ad esempio, l'organizzazione può avere 3.000 licenze di Office 365 E3 e 2.500 Microsoft 365 E5, per un totale di 5.500 licenze dei prodotti idonei.</span><span class="sxs-lookup"><span data-stu-id="61cf4-124">For example, your organization can have 3,000 Office 365 E3 licenses and 2,500 Microsoft 365 E5, for a total of 5,500 licenses from the qualifying products.</span></span>

- <span data-ttu-id="61cf4-125">L’organizzazione deve avere almeno 50 utenti Exchange Online attivi al mese</span><span class="sxs-lookup"><span data-stu-id="61cf4-125">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="61cf4-126">Con il monitoraggio di Exchange Online è possibile visualizzare lo stato di integrità dei client di posta elettronica seguenti, in base alle attività di lettura della posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="61cf4-126">With Exchange Online monitoring you can view the health for the following email clients based on email read activity:</span></span>

- <span data-ttu-id="61cf4-127">Outlook Desktop</span><span class="sxs-lookup"><span data-stu-id="61cf4-127">Outlook Desktop</span></span>
- <span data-ttu-id="61cf4-128">Outlook sul Web</span><span class="sxs-lookup"><span data-stu-id="61cf4-128">Outlook on the Web</span></span>
- <span data-ttu-id="61cf4-129">Client di posta elettronica nativi di iOS e Android</span><span class="sxs-lookup"><span data-stu-id="61cf4-129">Native mail clients of iOS and Android</span></span> 
- <span data-ttu-id="61cf4-130">App Outlook Mobile per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="61cf4-130">Outlook Mobile app in iOS and Android</span></span> 
- <span data-ttu-id="61cf4-131">Client Outlook per Mac</span><span class="sxs-lookup"><span data-stu-id="61cf4-131">Outlook Mac client</span></span>

<span data-ttu-id="61cf4-132">Per questi client è possibile visualizzare il numero di utenti attivi negli ultimi 30 minuti, in base agli utenti che leggono un messaggio di posta elettronica, oltre al numero di incidenti e avvisi nel dashboard.</span><span class="sxs-lookup"><span data-stu-id="61cf4-132">For these clients, you can see the number of active users in the last 30 minutes based on users reading an email, along with number of incidents and advisories in the dashboard.</span></span> <span data-ttu-id="61cf4-133">Questi dati vengono confrontati con lo stesso intervallo della settimana precedente, per controllare se si è verificato un problema.</span><span class="sxs-lookup"><span data-stu-id="61cf4-133">This data is compared to the same interval for the previous week to see if there’s an issue.</span></span> 

>[!Note]
> <span data-ttu-id="61cf4-134">Il numero di utenti attivi viene misurato in base a una singola attività, ad esempio quando un utente legge un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="61cf4-134">Active user count is measured by a single activity, for example, when a user reads an email.</span></span> <span data-ttu-id="61cf4-135">Vengono considerati solo gli ultimi 30 minuti di attività.</span><span class="sxs-lookup"><span data-stu-id="61cf4-135">It only accounts for the last 30 minutes of activity.</span></span>
>

<span data-ttu-id="61cf4-136">È anche possibile monitorare l'integrità di Exchange Online per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="61cf4-136">You can also monitor Exchange Online health for the following scenarios:</span></span>

- <span data-ttu-id="61cf4-137">**Flusso di posta**: il numero di messaggi correttamente recapitati a una cassetta postale senza alcun ritardo dopo che il messaggio ha raggiunto la rete di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61cf4-137">**Mail flow**: The number of messages successfully delivered to a mailbox without any delay after the message reached the Microsoft 365 network.</span></span> 
- <span data-ttu-id="61cf4-138">**Autenticazione di base e autenticazione moderna**: il numero di utenti convalidati correttamente nel servizio Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="61cf4-138">**Basic Authentication and Modern Authentication**: The number of users successfully validated in the Exchange Online service.</span></span>

![Esempio di monitoraggio dell'integrità di Exchange per il recapito della posta](../media/microsoft-365-exchange-monitoring/exhange-monitoring-scenario-example.png)

<span data-ttu-id="61cf4-140">Per tutti questi scenari, i numeri chiave nel dashboard principale sono relativi agli ultimi 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="61cf4-140">For all these scenarios, the key numbers are for the last 30 minutes in the main dashboard.</span></span> <span data-ttu-id="61cf4-141">Le visualizzazioni dettagliate di ognuno di questi scenari mostrano la tendenza in tempo quasi reale per sette giorni, con aggregazioni di 30 minuti, rispetto alla settimana precedente.</span><span class="sxs-lookup"><span data-stu-id="61cf4-141">Detailed views for each of these scenarios shows the near real-time trend for seven days with the 30-minute aggregate compared with the previous week.</span></span> 

## <a name="send-us-feedback"></a><span data-ttu-id="61cf4-142">Inviare feedback</span><span class="sxs-lookup"><span data-stu-id="61cf4-142">Send us feedback</span></span>

<span data-ttu-id="61cf4-143">È possibile inviare un feedback in due modi:</span><span class="sxs-lookup"><span data-stu-id="61cf4-143">There are two ways you can provide feedback:</span></span>

- <span data-ttu-id="61cf4-144">Usando l'opzione **Invia feedback** disponibile in tutte le pagine dell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61cf4-144">Use the **Give feedback** option available on every page of the Microsoft 365 admin center.</span></span>
- <span data-ttu-id="61cf4-145">Usando il collegamento **È stato utile questo post?** per uno specifico incidente o avviso.</span><span class="sxs-lookup"><span data-stu-id="61cf4-145">Submit feedback using the **Is this post helpful?** link for a specific incident or advisory.</span></span>

![Il collegamento "È stato utile questo post?"](../media/microsoft-365-exchange-monitoring/exhange-monitoring-example-incident-feedback.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="61cf4-148">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="61cf4-148">Frequently asked questions</span></span>

#### <a name="1-why-dont-i-see-exchange-online-monitoring-under-health-in-the-microsoft-365-admin-center"></a><span data-ttu-id="61cf4-149">1. Perché non vedo l'opzione "Monitoraggio di Exchange Online" in Integrità nell'interfaccia di amministrazione di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="61cf4-149">1. Why don’t I see “Exchange Online monitoring” under Health in the Microsoft 365 admin center?</span></span> 

<span data-ttu-id="61cf4-150">Verificare prima di tutto che la nuova interfaccia di amministrazione sia stata abilitata nella **Home** page dell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61cf4-150">First, make sure you’ve enabled the new admin center on the **Home** page of the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="61cf4-151">Quindi, verificare che siano soddisfatti i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="61cf4-151">Then make sure you meet both of the following requirements:</span></span> 

- <span data-ttu-id="61cf4-152">L'organizzazione deve avere almeno 5.000 licenze per uno o una combinazione dei prodotti seguenti: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span><span class="sxs-lookup"><span data-stu-id="61cf4-152">Your organization needs to have a license count of at least 5,000, from one or a combination of these products: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5.</span></span> 
- <span data-ttu-id="61cf4-153">L’organizzazione deve avere almeno 50 utenti Exchange Online attivi al mese.</span><span class="sxs-lookup"><span data-stu-id="61cf4-153">Your organization needs to have at least 50 monthly active Exchange Online users.</span></span>

<span data-ttu-id="61cf4-154">Se il numero di licenze dell'organizzazione è inferiore ai 5.000 utenti e gli utenti attivi mensili sono meno di 50, il monitoraggio di Exchange Online non viene abilitato finché non vengono soddisfatti questi requisiti.</span><span class="sxs-lookup"><span data-stu-id="61cf4-154">If the license count for your organization goes below 5,000 users and the monthly active users goes below 50 users, Exchange Online monitoring won’t be enabled until these requirements are met.</span></span>

#### <a name="2-the-active-user-count-in-the-dashboard-for-each-client-appears-to-be-low-we-have-a-lot-of-active-licenses-assigned-to-users-what-does-this-mean"></a><span data-ttu-id="61cf4-155">2. Il numero di utenti attivi nel dashboard per ogni client sembra basso.</span><span class="sxs-lookup"><span data-stu-id="61cf4-155">2. The active user count in the dashboard for each client appears to be low.</span></span> <span data-ttu-id="61cf4-156">Abbiamo molte licenze attive assegnate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="61cf4-156">We have a lot of active licenses assigned to users.</span></span> <span data-ttu-id="61cf4-157">Che cosa significa?</span><span class="sxs-lookup"><span data-stu-id="61cf4-157">What does this mean?</span></span> 

<span data-ttu-id="61cf4-158">Il numero di utenti attivi mostrato è basato su una finestra di 30 minuti in cui gli utenti hanno eseguito l'attività osservata dalla funzionalità di monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="61cf4-158">The active user count shown in monitoring is based on a 30-minute window where users have performed the activity called out in the feature.</span></span> <span data-ttu-id="61cf4-159">Questo dato non va confuso con i dati sull'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="61cf4-159">This shouldn’t be confused with usage numbers.</span></span> <span data-ttu-id="61cf4-160">Per visualizzare i dati sull'utilizzo, usare i report attività nell'interfaccia di amministrazione di Microsoft 365 (**Report > Utilizzo**).</span><span class="sxs-lookup"><span data-stu-id="61cf4-160">To view usage numbers, use activity reports in the Microsoft 365 admin center (**Reports > Usage**).</span></span>

#### <a name="3-will-there-be-other-monitoring-scenarios-for-other-services-such-as-teams-and-sharepoint"></a><span data-ttu-id="61cf4-161">3. Saranno aggiunti altri scenari di monitoraggio per altri servizi, ad esempio Teams e SharePoint?</span><span class="sxs-lookup"><span data-stu-id="61cf4-161">3. Will there be other monitoring scenarios for other services such as Teams and SharePoint?</span></span> 

<span data-ttu-id="61cf4-162">Microsoft ha integrato questa esperienza direttamente nel dashboard Integrità dei servizi nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61cf4-162">Microsoft is integrating this experience directly inside the Service Health dashboard in the Microsoft 365 admin center.</span></span> <span data-ttu-id="61cf4-163">Questo consentirà di estendere gli scenari di monitoraggio ad altri servizi. In tal caso, verrà pubblicato un annuncio.</span><span class="sxs-lookup"><span data-stu-id="61cf4-163">This will provide opportunities for Microsoft to extend monitoring scenarios for other services, which will be announced when there is news to share.</span></span> 

#### <a name="4-what-is-the-plan-for-general-availability-of-this-experience"></a><span data-ttu-id="61cf4-164">4. Qual è il piano per la disponibilità generale di quest'esperienza?</span><span class="sxs-lookup"><span data-stu-id="61cf4-164">4. What is the plan for general availability of this experience?</span></span> 

<span data-ttu-id="61cf4-165">Microsoft ha integrato il monitoraggio di Exchange Online direttamente nel dashboard **Integrità dei servizi** nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="61cf4-165">Microsoft has integrated Exchange Online monitoring directly on the **Service Health** dashboard in the Microsoft 365 admin center.</span></span> 

<span data-ttu-id="61cf4-166">Con questa nuova esperienza integrata, Microsoft intende raccogliere il feedback degli utenti e quindi definire il piano per la disponibilità generale.</span><span class="sxs-lookup"><span data-stu-id="61cf4-166">With this new integrated experience, Microsoft's plan is to collect your feedback and then define our plan for general availability.</span></span>

#### <a name="5-is-this-a-free-included-or-paid-extra-feature"></a><span data-ttu-id="61cf4-167">5. Si tratta di una funzionalità gratuita (inclusa) o a pagamento (extra)?</span><span class="sxs-lookup"><span data-stu-id="61cf4-167">5. Is this a free (included) or paid (extra) feature?</span></span> 

<span data-ttu-id="61cf4-168">Questa funzionalità è in anteprima pubblica ed è disponibile solo per i clienti che soddisfano i requisiti di cui alla domanda 1.</span><span class="sxs-lookup"><span data-stu-id="61cf4-168">This feature is in Public preview and only available for customers that meet the requirements in question 1.</span></span>

<!--
>[!Note]
>INTERNAL: That decision is pending
>
--> 

#### <a name="6-how-do-i-provide-feedback"></a><span data-ttu-id="61cf4-169">6. Come si fa a fornire un feedback?</span><span class="sxs-lookup"><span data-stu-id="61cf4-169">6. How do I provide feedback?</span></span> 

<span data-ttu-id="61cf4-170">Per feedback generale, usare l'icona **Invia feedback** nell'angolo in basso a destra della pagina di monitoraggio di **Exchange Online**.</span><span class="sxs-lookup"><span data-stu-id="61cf4-170">For general feedback, use the **Give feedback** icon on the bottom-right corner of the **Exchange Online** monitoring page.</span></span> 

<span data-ttu-id="61cf4-171">Per inviare feedback su incidenti o avvisi, usare il collegamento **È stato utile questo post?**.</span><span class="sxs-lookup"><span data-stu-id="61cf4-171">For feedback on incidents or advisories, use the **Is this post helpful?** link.</span></span>

#### <a name="7-where-is-the-data-instrumented-for-the-scenarios-that-show-activity-trends"></a><span data-ttu-id="61cf4-172">7. Dove sono i dati instrumentati per gli scenari che mostrano le tendenze delle attività?</span><span class="sxs-lookup"><span data-stu-id="61cf4-172">7. Where is the data instrumented for the scenarios that show activity trends?</span></span>

<span data-ttu-id="61cf4-p114">I dati sono instrumentati nel servizio Exchange Online. Se si verifica un errore prima che la richiesta raggiunga Exchange Online o se si verifica un errore in Exchange Online, viene visualizzato un calo nel segnale di attività.</span><span class="sxs-lookup"><span data-stu-id="61cf4-p114">The data is instrumented in the Exchange Online service. If there is a failure that happens before the request reaches Exchange Online or there is a failure in Exchange Online, you will see a drop in the activity signal.</span></span>
