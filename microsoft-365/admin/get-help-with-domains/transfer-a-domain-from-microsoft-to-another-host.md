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
ms.openlocfilehash: d960b57a2c82b804d61ead1c672c00f0543b3ae8
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370325"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Trasferire un dominio da Microsoft a un altro host

Non è possibile trasferire un dominio Microsoft 365 a un altro registrar per 60 giorni dopo l'acquisto del dominio da Microsoft.

> [!NOTE]
> Una query _Whois_   Visualizza un registrar Microsoft acquistato come Wild West Domains LLC. Tuttavia, solo Microsoft dovrebbe essere contattato per quanto riguarda il dominio acquistato Microsoft 365.

Seguire questa procedura per ottenere un codice in Microsoft 365, quindi passare all'altro sito Web registrar per impostare il trasferimento del nome di dominio nel nuovo registrar.

## <a name="transfer-a-domain"></a>Trasferire un dominio

1. Nell'interfaccia di amministrazione, andare a  **Settings**   >  **Domains**Settings.

2. Nella pagina **Domains** selezionare il dominio Microsoft 365 che si desidera trasferire a un altro registrar, quindi selezionare **Verifica integrità**.

3. Nella parte superiore della pagina, selezionare **trasferimento dominio**.

4. Nella pagina **scegliere il percorso di trasferimento del dominio** selezionare **un registrar diverso**e quindi fare clic su **Avanti**.

5. Nella pagina **sblocco del dominio** , selezionare **Sblocca trasferimento per <_il dominio_ > **, quindi selezionare **Avanti**.

6. Controllare le informazioni di contatto del trasferimento del dominio, quindi selezionare **Avanti**.

7. Copiare il codice di autorizzazione e attendere circa 30 minuti perché lo stato di trasferimento del dominio venga modificato in **sbloccato per il trasferimento** nella scheda **registrazione** prima di procedere con i passaggi successivi.

8. Passare al sito Web del registrar che si desidera gestire il nome di dominio in futuro. Seguire le istruzioni per il trasferimento di un dominio (cercare assistenza sul proprio sito Web). Questo solitamente significa pagare le commissioni di trasferimento e assegnare il authcode al nuovo registrar in modo che possano avviare il trasferimento. Microsoft invierà un messaggio di posta elettronica per confermare che è stata ricevuta la richiesta di trasferimento e il dominio verrà trasferito entro 5 giorni.

    È possibile trovare la scheda di **registrazione** del codice di autorizzazione nella pagina  **Domains** in Microsoft 365.
    
    > [!TIP]
    > i domini. uk richiedono una procedura diversa. Contattare il supporto tecnico Microsoft e richiedere la modifica di un **tag IPS** in modo che corrisponda al registrar che si desidera gestire il dominio in futuro. Dopo la modifica del tag, il dominio trasferisce immediatamente il nuovo registrar. Sarà quindi necessario collaborare con il nuovo registrar per completare il trasferimento, probabilmente pagando le spese di trasferimento e aggiungendo il dominio trasferito al proprio account con il nuovo registrar.

9. Una volta completato il trasferimento, si rinnoverà il dominio presso il nuovo registrar.

10. Per completare il processo, tornare alla pagina **Domains** nell'interfaccia di amministrazione, quindi selezionare  **completa trasferimento del dominio**. In questo modo il dominio non verrà più acquistato da Microsoft 365 e disattiverà la sottoscrizione di dominio. Il dominio non verrà rimosso dal tenant e non influisce sugli utenti e le cassette postali esistenti nel dominio.

> [!NOTE]
> I domini acquistati da Microsoft 365 non sono idonei per le modifiche ai server dei nomi o per il trasferimento del dominio tra organizzazioni Microsoft 365. Se uno di questi due requisiti è necessario, la registrazione del dominio deve essere trasferita a un altro registrar.
