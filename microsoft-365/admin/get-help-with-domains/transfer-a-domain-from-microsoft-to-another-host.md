---
title: Trasferire un dominio da Microsoft a un altro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Individuare i passaggi riportati di seguito per trasferire un dominio da Microsoft a un altro registrar. '
ms.openlocfilehash: 7e00f5ae2c36a06803a3f7a8acd825dcab90805c
ms.sourcegitcommit: 6fb2a1c404ea3c3573b0f7803bf17459a9387891
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788983"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Trasferire un dominio da Microsoft a un altro host

Non è possibile trasferire un dominio Microsoft 365 a un altro registrar per 60 giorni dopo l'acquisto del dominio da Microsoft.

> [!NOTE]
> Una query _Whois_   Visualizza un registrar Microsoft acquistato come Wild West Domains LLC. Tuttavia, solo Microsoft dovrebbe essere contattato per quanto riguarda il dominio acquistato Microsoft 365.

Seguire questa procedura per ottenere un codice in Microsoft 365, quindi passare all'altro sito Web registrar per impostare il trasferimento del nome di dominio nel nuovo registrar.

## <a name="transfer-a-domain"></a>Trasferire un dominio

1. Nell'interfaccia di amministrazione, andare a  **Settings**   >  **Domains**Settings.

2. <nella pagina **Domains** selezionare il dominio Microsoft 365 che si desidera trasferire a un altro registrar, quindi selezionare **Verifica integrità**.

3. Nella parte superiore della pagina, selezionare **trasferimento dominio**.

4. Nella pagina **scegliere il percorso di trasferimento del dominio** selezionare **un registrar diverso**e quindi fare clic su **Avanti**.

5. Nella pagina **sblocco del dominio** , selezionare **Sblocca trasferimento per <_il dominio_ > **, quindi selezionare **Avanti**.

6. Controllare le informazioni di contatto del trasferimento del dominio, quindi selezionare **Avanti**.

7. Copiare il codice di autorizzazione e attendere circa 30 minuti perché lo stato di trasferimento del dominio venga modificato in **sbloccato per il trasferimento** nella scheda **registrazione** prima di procedere con i passaggi successivi.

8. Passare al sito Web del registrar che si desidera gestire il nome di dominio in futuro. Seguire le istruzioni per il trasferimento di un dominio (cercare assistenza sul proprio sito Web).

È possibile trovare la scheda di **registrazione** del codice di autorizzazione nella pagina  **Domains** in Microsoft 365.

9. Una volta completato il trasferimento, si rinnoverà il dominio presso il nuovo registrar.

10. Per completare il processo, tornare alla pagina **Domains** nell'interfaccia di amministrazione, quindi selezionare  **completa trasferimento del dominio**.

> [!NOTE]
> I domini acquistati da Microsoft 365 non sono idonei per le modifiche ai server dei nomi o per il trasferimento del dominio tra organizzazioni Microsoft 365. Se uno di questi due requisiti è necessario, la registrazione del dominio deve essere trasferita a un altro registrar.
