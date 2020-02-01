---
title: Proteggere le informazioni
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/26/2019
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: pagina di destinazione per la protezione delle informazioni
ms.openlocfilehash: f5153373d73ec542f2a21561ce32c37368ff02e4
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601673"
---
# <a name="protect-information"></a>Proteggere le informazioni

Microsoft 365 e Office 365 includono funzionalità che possono essere applicate a tipi specifici di dati per proteggere le informazioni.


|**Funzionalità**|**Ulteriori informazioni**|
|:-----|:-----|
|[Etichette di riservatezza](sensitivity-labels.md) <br/> |Con le etichette di riservatezza è possibile classificare e proteggere i contenuti sensibili. Le opzioni di protezione includono etichette, filigrane e crittografia. Le etichette di riservatezza utilizzano Azure Information Protection. Se si utilizzano le etichette di Azure Information Protection, è consigliabile evitare di creare nuove etichette in altri centri di amministrazione finché non si è completata la migrazione. Vedere [Azure Information Protection Migration](https://docs.microsoft.com/azure/information-protection/configure-policy-migrate-labels). <br/> Le [etichette di conservazione](retention-policies.md) sono diverse dalle etichette di riservatezza. Le etichette di conservazione consentono di conservare o eliminare il contenuto in base ai criteri definiti. Queste organizzazioni di assistenza sono conformi alle normative industriali e ai criteri interni.|
|[Prevenzione della perdita di dati](data-loss-prevention-policies.md) (DLP)  <br/> |Con i criteri DLP, è possibile identificare, monitorare e proteggere automaticamente le informazioni riservate in Office 365. I criteri di prevenzione della perdita di dati possono utilizzare etichette di riservatezza e tipi di informazioni riservate per identificare informazioni riservate. <br/> |
|[Tipi di informazioni riservate](what-the-sensitive-information-types-look-for.md) <br/> |Microsoft 365 include numerosi tipi di informazioni riservate pronte per l'uso nei criteri DLP e per la classificazione automatica con etichette di riservatezza e conservazione. I tipi di informazioni riservate possono essere utilizzati anche con lo [scanner di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) per classificare e proteggere i file in locale. I tipi di informazioni riservate definiscono in che modo il processo automatico riconosce tipi di informazioni specifiche quali numeri di servizi di integrità e numeri di carta di credito.   <br/> |
|[Crittografia messaggi di Office 365](ome.md) (OME)  <br/> |Con la crittografia dei messaggi di Office 365, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra utenti all'interno e all'esterno dell'organizzazione. La crittografia dei messaggi di Office 365 è compatibile con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica consente di verificare che solo i destinatari previsti possano visualizzare il contenuto del messaggio. <br/> |
|[Azure Information Protection](https://docs.microsoft.com/azure/information-protection/)<br/> |Azure Information Protection (a volte indicato come AIP) consente a un'organizzazione di classificare, etichettare e facoltativamente proteggere documenti e messaggi di posta elettronica. Gli amministratori possono applicare automaticamente le etichette definendo regole e condizioni. Gli utenti possono applicare manualmente le etichette ai file e alla posta. È inoltre possibile fornire agli utenti suggerimenti su quando applicare le etichette.<br/> Se si utilizzano le etichette di riservatezza o la crittografia dei messaggi di Office, si stanno già utilizzando le funzionalità di classificazione e protezione. Se non è ancora stata eseguita la migrazione delle etichette di Azure Information Protection a Office 365, continuare a gestire queste informazioni in Azure Information Protection.  <br/>È possibile eseguire lo [scanner di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner) in locale per classificare e proteggere i file su Windows Server, le condivisioni di rete e i siti e le raccolte di SharePoint Server. Questo può essere un primo passo verso l'identificazione dei dati per la migrazione a Office 365.
|Protezione delle informazioni di Azure con la chiave di crittografia gestita dal cliente <br/> |Alcune organizzazioni dispongono di un requisito aziendale o di conformità per mantenere il controllo di una chiave di crittografia. Non si tratta di una cosa comune. Azure Information Protection consente alle organizzazioni di portare la propria chiave (BYOK) al servizio. Per ulteriori informazioni, vedere [Bring your own key (BYOK) for Azure Information Protection](https://docs.microsoft.com/azure/information-protection/byok-price-restrictions). È disponibile un'altra opzione più complessa per i clienti che hanno il requisito di mantenere una chiave di crittografia in locale, denominata Hold Your Own Key (HYOK).  Per ulteriori informazioni, vedere [tenere la propria chiave (HYOK) per Azure Information Protection](https://docs.microsoft.com/azure/information-protection/configure-adrms-restrictions). <br/> |
    

