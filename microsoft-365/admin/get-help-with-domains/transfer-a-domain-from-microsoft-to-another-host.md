---
title: Trasferire un dominio da Microsoft a un altro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'La procedura seguente consente di trasferire un dominio da Microsoft a un altro registrar. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126348"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a>Trasferire un dominio da Microsoft a un altro host

Non è possibile trasferire un dominio Microsoft 365 a un altro registrar per 60 giorni dopo l'acquisto del dominio da Microsoft.

> [!NOTE]
> Una query _Whois_   mostra un registrar acquistato da Microsoft come Wild West Domains LLC. Tuttavia, solo Microsoft deve essere contattato per quanto riguarda il dominio Microsoft 365 acquistato.

Seguire questa procedura per ottenere un codice in Microsoft 365 e quindi passare all'altro sito Web del registrar per configurare il trasferimento del nome di dominio al nuovo registrar.

## <a name="transfer-a-domain"></a>Trasferire un dominio

1. Nell'interfaccia di amministrazione passare a   **Impostazioni**   >  **domini**.

2. Nella pagina **Domini** selezionare il Microsoft 365 che si desidera trasferire a un altro registrar e quindi selezionare **Controlla integrità**.

3. Nella parte superiore della pagina selezionare **Trasferisci dominio.**

4. Nella pagina **Scegliere dove trasferire il dominio** selezionare Un **registrar** diverso e quindi fare clic su **Avanti.**

5. Nella pagina **Sblocca trasferimento dominio** selezionare Sblocca trasferimento per <**_dominio_ >** e quindi selezionare **Avanti**.

6. Controllare le informazioni di contatto per il trasferimento del dominio e quindi selezionare **Avanti**.

7. Copiare il codice di autorizzazione e attendere circa 30 minuti perché  lo stato del trasferimento del dominio cambi in **Sbloccato** per il trasferimento nella scheda Registrazione prima di procedere con i passaggi successivi.

8. Passare al sito Web del registrar che si desidera gestire il nome di dominio in futuro. Seguire le istruzioni per il trasferimento di un dominio (cercare la Guida nel proprio sito Web). Questo significa in genere pagare le tariffe di trasferimento e fornire l'Authcode al nuovo registrar in modo che possa avviare il trasferimento. Microsoft ti invia un'e-mail per confermare che abbiamo ricevuto la richiesta di trasferimento e che il dominio verrà trasferito entro 5 giorni.

    È possibile trovare la scheda **Registrazione** del codice di autorizzazione nella  **pagina Domini** in Microsoft 365.
    
    > [!TIP]
    > I domini .uk richiedono una procedura diversa. Contattare il supporto Tecnico Microsoft e richiedere una **modifica del tag IPS** in modo che corrisponda al registrar che si desidera gestire il dominio in futuro. Una volta modificato il tag, il dominio si trasferisce immediatamente al nuovo registrar. Dovrai quindi collaborare con il nuovo registrar per completare il trasferimento, probabilmente pagando le tariffe di trasferimento e aggiungendo il dominio trasferito al tuo account con il nuovo registrar.

9. Al termine del trasferimento, il dominio verrà rinnovato nel nuovo registrar.

10. Per completare il processo, tornare alla **pagina Domini** nell'interfaccia di amministrazione e quindi selezionare Completa   **trasferimento dominio**. In questo modo il dominio verrà contrassegnato come non più acquistato da Microsoft 365 e verrà disabilitata la sottoscrizione di dominio. Non rimuoverà il dominio dal tenant e non influirà sugli utenti e sulle cassette postali esistenti nel dominio.

> [!NOTE]
> Microsoft 365 domini acquistati non sono idonei per le modifiche al server dei nomi o per il trasferimento del dominio tra Microsoft 365 organizzazioni. Se uno di questi è obbligatorio, la registrazione del dominio deve essere trasferita a un altro registrar.
