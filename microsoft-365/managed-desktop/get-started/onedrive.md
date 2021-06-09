---
title: Microsoft OneDrive
description: Come Microsoft Managed Desktop la configurazione OneDrive per i dispositivi registrati
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione, app, app line-of-business, app LINEB
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a26500c1671afffc7b70d509a4242914631b937c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904841"
---
# <a name="microsoft-onedrive"></a>Microsoft OneDrive

Microsoft Managed Desktop usa [OneDrive for Business](/onedrive/plan-onedrive-enterprise) come servizio di archiviazione cloud per tutti i dispositivi Microsoft Managed Desktop per garantire che i dispositivi siano il più possibile senza stato. L'utente sarà in grado di trovare i propri file indipendentemente dal dispositivo a cui accede. Ad esempio, se sostituisci un dispositivo Microsoft Managed Desktop con uno nuovo, i file verranno sincronizzati automaticamente con il nuovo dispositivo.

Queste impostazioni vengono configurate automaticamente per impostazione predefinita nei dispositivi gestiti Microsoft:

- OneDrive viene configurato automaticamente con l'account utente e ha eseguito automaticamente l'accesso (senza interazione dell'utente) all'account utente utilizzato per accedere a Windows. Per ulteriori informazioni, vedere [Silently configure user accounts - OneDrive](/onedrive/use-silent-account-configuration)

- La funzionalità File su richiesta è abilitata in modo che gli utenti possano accedere ai file dall'archiviazione cloud in OneDrive senza dover utilizzare spazio su disco inutilmente. Per ulteriori informazioni, vedere [Save disk space with OneDrive Files On-Demand for Windows 10](https://support.microsoft.com/office/save-disk-space-with-onedrive-files-on-demand-for-windows-10-0e6860d3-d9f3-4971-b321-7092438fb38e).

- La funzionalità di spostamento delle cartelle note è abilitata automaticamente per eseguire il backup dei dati degli utenti nel cloud, che consente loro di accedere ai propri file da qualsiasi dispositivo. Per ulteriori informazioni, vedere [Back up your Documents, Pictures, and Desktop folders with OneDrive](https://support.microsoft.com/office/back-up-your-documents-pictures-and-desktop-folders-with-onedrive-d61a7930-a6fb-4b95-b28a-6552e77c3057).

- Gli utenti non possono disabilitare la funzionalità di spostamento delle cartelle note o modificare il percorso delle cartelle note per garantire un'esperienza coerente Microsoft Managed Desktop dispositivi.

## <a name="user-experience"></a>Esperienza utente

Quando Microsoft Managed Desktop gli utenti ricevono un nuovo dispositivo, passano attraverso un'esperienza di prima esecuzione immettendo le credenziali di Azure durante la configurazione del dispositivo. Al termine di questo processo, possono accedere al desktop e avere la OneDrive completa.

1. Il sistema indica agli utenti che OneDrive è stato configurato e che sono stati connessi automaticamente OneDrive.

:::image type="content" source="media/onedrive-sync.png" alt-text="Lettura delle notifiche in corso di OneDrive ed è possibile modificare i file in OneDrive. fare clic qui per visualizzare i file":::

2. Il sistema comunica agli utenti OneDrive stato configurato lo spostamento delle cartelle note.

:::image type="content" source="media/onedrive-folders.png" alt-text="Lettura delle notifiche Il reparto IT ha eseguito il backup delle cartelle importanti. Il backup delle cartelle viene ora eseguito OneDrive e disponibile da altri dispositivi":::

3. Per evitare icone duplicate sul desktop quando i dispositivi vengono reimpostati o ricreati, il sistema rimuove automaticamente le icone Microsoft Edge e Microsoft Teams dalla sincronizzazione OneDrive, come illustrato in questa visualizzazione in Esplora file.

:::image type="content" source="media/onedrive-teams.png" alt-text="File Explorer showing Teams and Edge listings with cleared check boxes and hover text reading Excluded from sync.":::


## <a name="onedrive-sync-restrictions"></a>OneDrive di sincronizzazione

Se è necessario limitare la sincronizzazione OneDrive, è consigliabile controllare l'accesso con un criterio Azure Active Directory di accesso condizionale. Per altre informazioni, vedi [Abilitare il supporto dell'accesso condizionale nell OneDrive app di sincronizzazione.](/onedrive/enable-conditional-access)

Se non è possibile usare un criterio di accesso condizionale di Azure AD nell'organizzazione, l'amministratore IT deve eseguire la procedura seguente:

1. Se non lo si conosce già, cercare l'ID tenant, come descritto in [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id).
2. Accedi all'interfaccia OneDrive e quindi seleziona **Sincronizza** nel riquadro sinistro. Selezionare la **casella di controllo Consenti** sincronizzazione solo su PC aggiunti a domini specifici e quindi aggiungere l'ID tenant all'elenco dei domini. Per ulteriori informazioni, vedere [Allow syncing only on computers joined to specific domains](/onedrive/allow-syncing-only-on-specific-domains).

> [!NOTE]
> Queste indicazioni si applicano solo ai tenant in Microsoft Managed Desktop. Esistono altre impostazioni in uso che non sono descritte in questo articolo.