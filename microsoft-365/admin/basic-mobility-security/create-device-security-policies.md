---
title: Creare criteri di sicurezza per i dispositivi in mobilità e sicurezza di base
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Utilizzare la sicurezza e la mobilità di base per creare criteri per i dispositivi che proteggono le informazioni dell'organizzazione.
ms.openlocfilehash: 077f1e7e0d763aaecfc38fd4b57d9e8912900a3c
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877069"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Creare criteri di sicurezza per i dispositivi in mobilità e sicurezza di base

È possibile utilizzare la sicurezza e la mobilità di base per creare criteri di dispositivo che consentono di proteggere le informazioni dell'organizzazione su Microsoft 365 da accessi non autorizzati. È possibile applicare i criteri a qualsiasi dispositivo mobile dell'organizzazione in cui l'utente del dispositivo dispone di una licenza di Microsoft 365 applicabile e ha registrato il dispositivo in mobilità e sicurezza di base.

## <a name="before-you-begin"></a>Prima di iniziare

> [!IMPORTANT]
> Prima di poter creare un criterio per dispositivi mobili, è necessario attivare e configurare la mobilità e la sicurezza di base. Per altre informazioni, vedere Overview of Basic Mobility and Security.

- Informazioni sui dispositivi, le app per dispositivi mobili e le impostazioni di sicurezza supportate da supporto per la sicurezza e la mobilità di base. Vedere [funzionalità di base per dispositivi mobili e sicurezza](capabilities.md).
- Creare gruppi di sicurezza che includano gli utenti di Microsoft 365 a cui si desidera distribuire i criteri e per gli utenti che potrebbero essere esclusi dall'accesso bloccato a Microsoft 365. Prima di distribuire un nuovo criterio per l'organizzazione verifica i criteri distribuendoli a un numero limitato di utenti. È possibile creare e utilizzare un gruppo di sicurezza che includa solo te stesso o un numero limitato di utenti di Microsoft 365 che possano testare il criterio. Per ulteriori informazioni sui gruppi di sicurezza, vedere [creare, modificare o eliminare un gruppo di sicurezza](https://go.microsoft.com/fwlink/p/?LinkId=518555).
- Per creare e distribuire criteri di sicurezza e mobilità di base in Microsoft 365, è necessario essere un amministratore globale di Microsoft 365. Per altre informazioni, vedere [Permissions in the Security & Compliance Center](https://support.microsoft.com/office/d10608af-7934-490a-818e-e68f17d0e9c1).
- Prima di distribuire i criteri, informare l'organizzazione sull'impatto potenziale di registrazione di un dispositivo in mobilità e sicurezza di base. A seconda di come si configurano i criteri, i dispositivi non conformi possono essere bloccati dall'accesso a Microsoft 365 e ai dati, incluse le applicazioni installate, le foto e le informazioni personali su un dispositivo registrato e i dati possono essere eliminati.

>[!NOTE]
>I criteri e le regole di accesso creati in Basic Mobility and Security for Microsoft 365 business standard eseguono l'override dei criteri cassetta postale per il dispositivo mobile di Exchange ActiveSync e le regole di accesso ai dispositivi creati nell'interfaccia di amministrazione di Exchange Dopo che un dispositivo è stato registrato in mobilità e sicurezza di base per Microsoft 365 business standard, tutti i criteri cassetta postale per il dispositivo mobile di Exchange ActiveSync o la regola di accesso ai dispositivi applicati al dispositivo vengono ignorati. Per ulteriori informazioni su Exchange ActiveSync, vedere [Exchange ActiveSync in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=524380).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Passaggio 1: creare un criterio di dispositivo e distribuirlo a un gruppo di test

Prima di iniziare, assicurarsi di aver attivato e configurato la mobilità e la sicurezza di base. Per istruzioni, vedere [Overview of Basic Mobility and Security](overview.md).

1. Dal browser, digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selezionare **Crea un criterio**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Impostazioni di base per i criteri di sicurezza e mobilità":::

3. Nella pagina **impostazioni dei criteri** specificare i requisiti desiderati applicati ai dispositivi mobili nell'organizzazione.

4. **Richiedi la gestione del profilo di posta elettronica**: quando è abilitato, i dispositivi che non dispongono di un profilo di posta elettronica gestito da mobilità e sicurezza di base sono considerati non conformi. Un dispositivo non può disporre di un profilo di posta elettronica gestito quando non è stato individuato correttamente o se l'utente ha configurato manualmente l'account di posta elettronica sul dispositivo. Quando si lascia **non abilitato** (impostazione predefinita), questa impostazione non viene valutata per la conformità o la mancata conformità. Per istruzioni su come gli utenti possono ottenere la conformità quando questa opzione è selezionata, vedere [un account di posta elettronica esistente trovato](https://docs.microsoft.com/intune-user-help/existing-company-email-account-found).

5. Nella pagina **si desidera applicare il criterio** , scegliere i gruppi a cui si desidera applicare il criterio.

6. Selezionare **crea questo criterio**.

Il criterio viene inserito nel dispositivo di ogni utente a cui si applica il criterio al successivo accesso a Microsoft 365 utilizzando il dispositivo mobile. Se gli utenti non hanno avuto un criterio applicato al proprio dispositivo mobile prima, dopo aver distribuito il criterio, ricevono una notifica sul dispositivo che include i passaggi per la registrazione e l'attivazione della sicurezza e della mobilità di base. Per altre informazioni, vedere [registrazione del dispositivo mobile utilizzando la sicurezza e la mobilità di base](enroll-your-mobile-device.md). Fino a quando non completano la registrazione in mobilità e sicurezza di base ospitate dal servizio Intune, l'accesso a posta elettronica, OneDrive e altri servizi è limitato. Dopo aver completato la registrazione tramite l'app portale aziendale di Intune, è possibile utilizzare i servizi e il criterio viene applicato al dispositivo.

## <a name="step-2-verify-that-your-policy-works"></a>Passaggio 2: verificare che il criterio funzioni

Dopo aver creato un criterio dispositivo, verificare che il criterio funzioni come previsto prima di distribuirlo nell'organizzazione.

1. Dal browser, digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selezionare **Visualizza l'elenco dei dispositivi gestiti**.
3. Verifica lo stato dei dispositivi dell'utente a cui sono stati applicati i criteri. Si desidera che lo **stato** dei dispositivi venga **gestito.**
4. È inoltre possibile eseguire un wipe completo o selettivo su un dispositivo facendo clic su **Factory Reset** o **Remove Company Data** from **Manage** Button dopo aver selezionato un dispositivo. Per istruzioni, vedere [Wipe a Mobile Device in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Passaggio 3: distribuire un criterio all'organizzazione

Dopo aver creato un criterio dispositivo e aver verificato che funzioni come previsto, distribuirlo nell'organizzazione.

1. Dal tipo di browser: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selezionare il criterio che si desidera distribuire e scegliere **modifica** accanto ai gruppi a cui si è **applicati.**
3. Cercare un gruppo da aggiungere e fare clic su **Seleziona**.
4. Selezionare **Chiudi** e **Cambia impostazione.**
5. Selezionare **Chiudi** e **modifica criterio.**

Il criterio viene inserito nel dispositivo mobile di ogni utente a cui si applica il criterio al successivo accesso a Microsoft 365 dal proprio dispositivo mobile. Se gli utenti non hanno avuto un criterio applicato al dispositivo mobile, ricevono una notifica sul dispositivo con i passaggi per la registrazione e l'attivazione per la sicurezza e la mobilità di base. Dopo aver completato la registrazione, il criterio viene applicato al dispositivo. Per altre informazioni, vedere [registrazione del dispositivo mobile utilizzando la sicurezza e la mobilità di base](enroll-your-mobile-device.md).

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Passaggio 4: bloccare l'accesso alla posta elettronica per i dispositivi non supportati

Per proteggere le informazioni dell'organizzazione, è necessario bloccare l'accesso app a Microsoft 365 per i dispositivi mobili che non sono supportati da mobilità e sicurezza di base. Per un elenco dei dispositivi supportati, vedere [dispositivi supportati](https://support.microsoft.com/office/capabilities-of-basic-mobility-and-security-a1da44e5-7475-4992-be91-9ccec25905b0#bkmk_supporteddevices).

**Per bloccare l'accesso alle app:**

1. Dal browser, digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Selezionare **Gestisci impostazioni di accesso ai dispositivi a livello di organizzazione**.
3. Per bloccare i dispositivi non supportati, scegliere **blocca** in **se un dispositivo non è supportato da mobilità e sicurezza di base per Microsoft 365**, quindi selezionare **Salva**.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Opzione di base per mobilità e blocco di sicurezza":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Passaggio 5: Scegliere i gruppi di sicurezza da escludere dai controlli dell'accesso condizionale

Se si desidera escludere alcuni utenti dai controlli dell'accesso condizionale sui relativi dispositivi mobili e sono stati creati uno o più gruppi di sicurezza per tali utenti, è possibile aggiungere qui i gruppi di sicurezza. Gli utenti di questi gruppi non avranno criteri applicati ai propri dispositivi mobili supportati. Questa è l'opzione consigliata se non si desidera più utilizzare la mobilità e la sicurezza di base nell'organizzazione.

1. Dal browser, digitare [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Selezionare **Gestisci impostazioni di accesso ai dispositivi a livello di organizzazione**.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Mobilità e sicurezza di base creare un'opzione per i criteri":::

3. Fare clic su **Aggiungi** per aggiungere il gruppo di sicurezza con gli utenti che si desidera escludere dall'aver bloccato l'accesso a Microsoft 365. Quando un utente è stato aggiunto a questo elenco, può accedere alla posta elettronica Microsoft 365 quando utilizza un dispositivo non supportato.

4. Selezionare il gruppo di sicurezza che si desidera utilizzare nel pannello **Seleziona gruppo** .

5. Selezionare il nome e quindi **aggiungere**  >  **Save**.

6. Nel riquadro **impostazioni di accesso al dispositivo a livello di organizzazione** scegliere **Salva**.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Opzione di base per mobilità e sicurezza Consenti accesso":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Qual è l'impatto dei criteri di sicurezza sui diversi tipi di dispositivo?

Quando si applica un criterio ai dispositivi utente, l'impatto su ogni dispositivo varia leggermente tra i tipi di dispositivi. Vedere la tabella seguente per visualizzare esempi dell'impatto dei criteri su diversi dispositivi.

|**Criterio di sicurezza**|**Android 4 e versioni successive**|**Samsung KNOX**|**iOS 6 e versioni successive**|**Note**|
|:-----|:-----|:-----|:-----|:-----|
|Richiede un backup crittografato|No|Sì|Sì|backup crittografato di iOS necessario.|
|Blocca backup sul cloud|Sì|Sì|Sì|Blocca backup Google su Android (in grigio), backup cloud su IOS.|
|Blocca sincronizzazione documenti|No|No|Sì|iOS: blocca i documenti nel cloud.|
|Blocca sincronizzazione foto |No|No|Sì|iOS (nativo): blocco lo streaming foto.|
|Blocca acquisizione schermata |No|Sì|Sì|Tentativo bloccato.|
|Blocca videoconferenza |No|No|Sì|FaceTime bloccata su iOS, non su Skype o altri.|
|Blocca invio dati di diagnostica |No|Sì|Sì|Blocco invio segnalazione di arresto anomalo di Google su Android.|
|Blocca l'accesso all'app store |No|Sì|Sì|Icona app store mancante nella home page di Android, disattivata in Windows, mancante in IOS.|
|Richiede una password per l'app store |No|No|Sì|iOS: password necessaria per gli acquisti su iTunes.|
|Blocca connessione con archivi rimovibili |No|Sì|N/D|Android: la scheda SD è disattivata nelle impostazioni, Windows notifica all'utente che le app installate non sono disponibili|
|Blocca connessione Bluetooth |Vedere note|Vedere note|Sì|Non è possibile disabilitare BlueTooth come impostazione su Android. Al contrario, vengono disattivate tutte le transazioni che richiedono BlueTooth: distribuzione audio avanzata, controllo remoto audio/video, dispositivi vivavoce, auricolare, accesso rubrica telefonica e porta seriale. Durante una di queste transazioni, viene visualizzato un piccolo messaggio popup in fondo alla pagina.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Cosa accade quando si elimina un criterio o si rimuove un utente dal criterio?

Quando si elimina un criterio o si rimuove un utente da un gruppo a cui è stato distribuito il criterio, è possibile che le impostazioni dei criteri, il profilo di posta elettronica di Microsoft 365 e i messaggi memorizzati nella cache vengano rimossi dal dispositivo dell'utente. Vedere la tabella seguente per vedere cosa viene rimosso per i diversi tipi di dispositivi.

|**Elementi rimossi**|**iOS 6 e versioni successive**|**Android 4 e versioni successive (incluso Samsung KNOX**|
|:-----|:-----|:-----|
|Profili di posta elettronica gestiti<sup>1</sup>|Sì|No|
|Blocca backup sul cloud|Sì|No|

<sup>1</sup> se il criterio è stato distribuito con il **profilo di posta elettronica** dell'opzione gestito selezionato, il profilo di posta elettronica gestito e i messaggi nella cache del profilo vengono eliminati dal dispositivo utente.

Il criterio viene rimosso dal dispositivo mobile per ogni utente a cui si applica il criterio per la successiva verifica del dispositivo con mobilità e sicurezza di base. Se si distribuisce un nuovo criterio che si applica a questi dispositivi utente, viene richiesto di eseguire di nuovo la registrazione in mobilità e sicurezza di base.

È inoltre possibile eliminare completamente un dispositivo o cancellare selettivamente le informazioni dell'organizzazione dal dispositivo. Per altre informazioni, vedere [Wipe a Mobile Device in Basic Mobility and Security](wipe-mobile-device.md).

## <a name="related-topics"></a>Argomenti correlati

[Panoramica Basic Mobility + Security](overview.md)

[Funzionalità Basic Mobility + Security](capabilities.md)
