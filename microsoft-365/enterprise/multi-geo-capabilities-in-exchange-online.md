---
title: Exchange Multi-Geo
ms.reviewer: adwood
ms.author: chrisda
author: chrisda
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
description: Informazioni sulle funzionalità multi-Geo in Exchange Online, ad esempio limitazioni delle funzionalità e posizionamento delle cassette postali.
ms.openlocfilehash: ca7203c72f23fd03512bf23eaa5a4687e4bac1b5
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691270"
---
# <a name="multi-geo-capabilities-in-exchange-online"></a>Funzionalità Multi-Geo in Exchange Online

In un ambiente Multi-Geo, è possibile selezionare la posizione del contenuto delle cassette postali di Exchange Online (dati inattivi) per ogni utente.

È possibile inserire cassette postali in posizioni geografiche satelliti per:

- Creare una nuova cassetta postale di Exchange Online direttamente in una posizione geografica satellite.

- Spostare una cassetta postale di Exchange Online esistente in una posizione geografica satellite modificando la posizione preferita dei dati dell'utente.

- Caricare una cassetta postale di un'organizzazione di Exchange locale direttamente in una posizione geografica satellite.

## <a name="mailbox-placement-and-moves"></a>Inserimento e spostamenti delle cassette postali

Dopo che Microsoft ha completato la procedura di configurazione Multi-Geo del prerequisito, Exchange Online riserverà l'attributo **PreferredDataLocation** per gli oggetti utente in Azure AD.

Exchange Online sincronizza la proprietà **PreferredDataLocation** di Azure AD nella proprietà **MailboxRegion** nel servizio directory di Exchange Online. Il valore di **MailboxRegion** determina la posizione geografica in cui verranno inserite le cassette postali degli utenti e le cassette postali di archiviazione associate. Non è possibile configurare la cassetta postale principale di un utente e le cassette postali di archiviazione affinché risiedano in diverse posizioni geografiche. Può essere configurata una sola posizione geografica per ogni oggetto utente.

- Se **PreferredDataLocation** è configurato per un utente con una cassetta postale esistente, la cassetta postale verrà inserita in una coda di rilocazione e spostata automaticamente nella posizione geografica specificata.

- Se **PreferredDataLocation** è configurato per un utente con una cassetta postale esistente, quando si effettua il provisioning, questi sarà effettuato nella posizione geografica specificata.

- Se **PreferredDataLocation** non è specificato per un utente, quando si effettua il provisioning, questi sarà effettuato nella posizione geografica specificata.

- Se il codice **PreferredDataLocation** non è corretto, ad esempio un tipo di NAN anziché NAM, verrà effettuato il provisioning della cassetta postale nella posizione geografica centrale.

**Nota**: le funzionalità Multi-Geo e le riunioni di Skype for Business online ospitate a livello regionale usano la proprietà **PreferredDataLocation** per gli oggetti utente per individuare i servizi. Se si configurano i valori di **PreferredDataLocation** per gli oggetti utente per le riunioni ospitate a livello regionale, la cassetta postale di tali utenti verrà spostata automaticamente nella posizione geografica specificata dopo che il Multi-Geo è abilitato nel tenant di Microsoft 365.

## <a name="feature-limitations-for-multi-geo-in-exchange-online"></a>Limitazioni della funzionalità per il Multi-Geo in Exchange Online

- Le funzionalità di sicurezza e conformità, ad esempio il controllo ed eDiscovery, disponibili nell'interfaccia di amministrazione di Exchange (EAC) non sono disponibili nelle organizzazioni Multi-Geo. È invece necessario usare il [Centro sicurezza e conformità di Microsoft 365](https://support.office.com/article/7e696a40-b86b-4a20-afcc-559218b7b1b8) per configurare le funzionalità di sicurezza e conformità.

- Gli utenti di Outlook per Mac potrebbero riscontrare una perdita temporanea di accesso alla cartella di archiviazione online mentre viene spostata la cassetta postale in una nuova posizione geografica. Questa condizione si verifica quando la cassetta postale primaria e quella di archiviazione dell’utente si trovano in diverse posizioni geografiche, poiché gli spostamenti delle cassette postali tra diverse aree geografiche potrebbero essere completati in momenti diversi.

- Gli utenti non possono condividere le *cartelle della cassetta postale* nelle diverse posizioni geografiche di Outlook sul web (in precedenza noto come Outlook Web App o OWA). Ad esempio, un utente nell'Unione Europea non può usare Outlook sul web per aprire una cartella condivisa in una cassetta postale che si trova negli Stati Uniti d'America. Tuttavia, gli utenti di Outlook sul web possono aprire *altre cassette postali* in posizioni geografiche diverse usando una finestra del browser separata, come descritto in [Aprire la cassetta postale di un'altra persona in una finestra separata del browser in Outlook Web App](https://support.office.com/article/A909AD30-E413-40B5-A487-0EA70B763081#__toc372210362).

  **Nota**: la condivisione delle cartelle della cassetta postale tra diverse aree geografiche è supportata in Outlook per Windows.

- Le cartelle pubbliche sono supportate nelle organizzazioni Multi-Geo. Tuttavia, è necessario che le cartelle pubbliche rimangano nella posizione geografica centrale. Non è possibile spostare le cartelle pubbliche nelle posizioni geografiche satelliti.

- In un ambiente multi-geografico il controllo delle cassette postali in aree geografiche diverse non è supportato. Ad esempio, se a un utente sono assegnate le autorizzazioni per accedere a una cassetta postale condivisa in un'area geografica diversa, le azioni sulla cassetta postale eseguite da tale utente non vengono registrate nel log di controllo della cassetta postale condivisa. Per altre informazioni, vedere [Gestire il controllo delle cassette postali](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing?view=o365-worldwide).
