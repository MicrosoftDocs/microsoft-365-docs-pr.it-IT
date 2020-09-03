---
title: Immutabilità dei dati di Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Informazioni su come Microsoft 365 conserva i dati in un modulo individuabile per soddisfare la conformità normativa, i requisiti di governance interna e i rischi per controversia legale.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce3b3f0f5036ab76be714747d7e95fe86139dd75
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331921"
---
# <a name="immutability-in-microsoft-365"></a>Immutabilità in Microsoft 365

La conformità alle normative, i requisiti di governance interna o i rischi per controversia legale richiedono alle organizzazioni di conservare la posta elettronica e i dati associati in un modulo individuabile. Tutti i dati del sistema devono essere individuabili e nessuno di essi può essere distrutto o alterato. Il termine standard del settore per questo è "immutabilità".

I metodi tradizionali per l'immutabilità in genere hanno funzionato spostando i messaggi di posta elettronica in un percorso di archiviazione separato e di sola lettura. Sebbene tali sistemi servano allo scopo di preservare gli elementi delle cassette postali per l'individuazione, spesso influiscono sull'esperienza degli utenti rimuovendo gli elementi conservati dal flusso di lavoro giornaliero consueto. Per i professionisti IT, questo approccio immutabilità richiede la distribuzione e la manutenzione continua di un'infrastruttura di server e di archiviazione distinta. L'individuazione viene eseguita con gli strumenti esterni al sistema di posta elettronica e include i costi di distribuzione e manutenzione associati.

Tramite le caratteristiche dei criteri di conservazione e conservazione sul posto dell'archiviazione in Microsoft 365 e i relativi servizi, è possibile conservare e mantenere numerose classi di dati in ingresso, interno e in uscita. Ciò include:

- Comunicazioni di posta elettronica in ingresso e in uscita
- Libri e record contenuti in un modulo di posta elettronica o in documenti condivisi online
- Convocazioni di riunioni
- Fax
- Messaggi istantanei
- Documenti condivisi durante le riunioni online
- Voicemails

Inoltre, Microsoft ha sviluppato funzionalità per i componenti aggiuntivi per consentire l' [archiviazione di dati](https://support.office.com/article/Archiving-third-party-data-in-Office-365-0ce338d5-3666-4a18-86ab-c6910ff408cc) da altre origini tramite l'integrazione con l'acquisizione di dati di terze parti e le soluzioni di gestione. Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Microsoft 365 ai dati, tra cui:

- [Conservazione per controversia legale](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)
- [EDiscovery e blocco sul posto](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)
- [Ricerca di conformità](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)
- [Archiviazione sul posto](https://docs.microsoft.com/microsoft-365/compliance/enable-archive-mailboxes)
- [Controllo delle cassette postali](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing)
- [Criteri di conservazione](https://docs.microsoft.com/microsoft-365/compliance/retention-policies)

Ad esempio, quando una cassetta postale viene inserita nella conservazione per controversia legale, vengono conservati i dati di terze parti. È possibile eseguire la ricerca di dati di terze parti utilizzando eDiscovery sul posto o la ricerca di conformità. In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti, esattamente come è possibile per i dati di Microsoft. L'archiviazione dei dati di terze parti in Microsoft 365 aiuta l'organizzazione a rimanere conforme ai criteri governativi e normativi.

L'archiviazione in Microsoft 365 include l'archiviazione conforme alla regola Securities and Exchange Commission (SEC) 17a-4. Microsoft 365 conserva i file permanenti di tutti i dati raccolti in un formato non riscrivibile e non cancellabile utilizzando i criteri di conservazione sul posto e i criteri di conservazione, incluso il blocco di conservazione.

In particolare:

- Tutti i record archiviati utilizzando i criteri di conservazione descritti in alto vengono conservati in un'area di archiviazione dedicata fuori dalla competenza dell'utente ordinario. Solo gli utenti autorizzati possono accedere ai record e cercarli ma non modificarli o cancellarli.
- I metadati per ogni elemento includono un timestamp utilizzato per il calcolo della durata della conservazione. I timestamp vengono applicati quando un nuovo elemento viene ricevuto o creato e non è possibile modificarlo o rimuoverlo dai metadati.
- L'archiviazione in Microsoft 365 consente agli utenti di combinare diversi criteri di conservazione e di mantenere le azioni per creare criteri di conservazione granulare. Questi criteri definiscono il tipo o la posizione degli elementi conservati e la durata della conservazione.
- La funzionalità di blocco di conservazione consente agli utenti di scegliere se rendere il criterio restrittivo. Un criterio restrittivo impedisce a chiunque di avere la possibilità di rimuovere, disabilitare o apportare modifiche al criterio di conservazione. Questo significa che, una volta abilitato il blocco di conservazione, non può essere disabilitato e non esiste alcun meccanismo in base al quale i dati provenienti da depositari esistenti raccolti dai criteri di conservazione sul posto possono essere sovrascritti, modificati, cancellati o eliminati durante il periodo di conservazione. Inoltre, il periodo di attesa impostato dal blocco di conservazione non può essere ridotto o diminuito. Tuttavia, può essere allungato, nel caso di un requisito legale per continuare la conservazione dei dati archiviati, come indicato in alto. Il blocco conservazione garantisce che nessuno, neanche gli amministratori o gli utenti con un determinato accesso al controllo, possano modificare le impostazioni o sovrascrivere o cancellare i dati archiviati, portando l'archiviazione in Microsoft 365 in linea con le indicazioni riportate nella versione 2003 di SEC Rule 17a-4.

Per comprendere in che modo Microsoft 365 aiuta a soddisfare gli obblighi normativi, in particolare per quanto riguarda i requisiti della regola 17a-4, vedere il [white paper](https://www.microsoft.com/microsoft-365/blog/wp-content/uploads/2015/11/Microsoft-EOA-White-Paper.pdf) relativo all'archiviazione di Exchange Online, SharePoint Online, OneDrive for business e Skype for business. Il white paper fornisce inoltre un'analisi approfondita delle caratteristiche e delle funzionalità di archiviazione di Microsoft 365 rispetto a ognuno dei requisiti previsti dalla regola 17a-4 di SEC e dimostra ai clienti regolamentati in che modo l'archiviazione di Microsoft 365 può consentire loro di soddisfare tali requisiti.
