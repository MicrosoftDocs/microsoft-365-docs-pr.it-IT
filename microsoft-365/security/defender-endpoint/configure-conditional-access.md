---
title: Configurare l'accesso condizionale in Microsoft Defender ATP
description: Informazioni sui passaggi da eseguire in Intune, Microsoft Defender Security Center e Azure per implementare l'accesso condizionale
keywords: accesso condizionale, condizionale, accesso, rischio del dispositivo, livello di rischio, integrazione, integrazione intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165862"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Configurare l'accesso condizionale in Microsoft Defender per Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

In questa sezione vengono descritti tutti i passaggi necessari per implementare correttamente l'accesso condizionale.

### <a name="before-you-begin"></a>Prima di iniziare
>[!WARNING]
>È importante notare che i dispositivi registrati in Azure AD non sono supportati in questo scenario.</br>
>Sono supportati solo i dispositivi registrati in Intune.


È necessario assicurarsi che tutti i dispositivi siano registrati in Intune. Puoi usare una delle opzioni seguenti per registrare i dispositivi in Intune:


- Amministratore IT: per ulteriori informazioni su come abilitare la registrazione automatica, vedere [Registrazione di Windows](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- Utente finale: per altre informazioni su come registrare il dispositivo Windows 10 in Intune, vedere Registrare il dispositivo [Windows 10 in Intune](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)
- Alternativa per l'utente finale: per ulteriori informazioni sull'aggiunta a un dominio di Azure AD, vedere [Procedura: Pianificare l'implementazione dell'aggiunta ad Azure AD.](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)



È necessario eseguire alcuni passaggi in Microsoft Defender Security Center, nel portale di Intune e nel portale di Azure AD.

È importante notare i ruoli necessari per accedere a questi portali e implementare l'accesso condizionale:
- **Microsoft Defender Security Center:** dovrai accedere al portale con un ruolo di amministratore globale per attivare l'integrazione.
- **Intune:** è necessario accedere al portale con diritti di amministratore della sicurezza con autorizzazioni di gestione. 
- **Portale di Azure AD:** è necessario accedere come amministratore globale, amministratore della sicurezza o amministratore di accesso condizionale.


> [!NOTE]
> Avrai bisogno di un ambiente Microsoft Intune, con Intune gestito e i dispositivi Windows 10 aggiunti ad Azure AD.

Eseguire la procedura seguente per abilitare l'accesso condizionale:
- Passaggio 1: attivare la connessione a Microsoft Intune da Microsoft Defender Security Center
- Passaggio 2: attivare l'integrazione di Defender for Endpoint in Intune
- Passaggio 3: Creare i criteri di conformità in Intune
- Passaggio 4: Assegnare il criterio 
- Passaggio 5: Creare un criterio di accesso condizionale di Azure AD


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>Passaggio 1: attivare la connessione a Microsoft Intune
1. Nel riquadro di spostamento, selezionare **Impostazioni**  >  **Funzionalità avanzate** Connessione di Microsoft  >  **Intune.**
2. Attiva l'impostazione di Microsoft **Intune.**
3. Fare **clic su Salva preferenze.**


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>Passaggio 2: attivare l'integrazione di Defender for Endpoint in Intune
1. Accedere al [portale di Azure](https://portal.azure.com).
2. Selezionare **Conformità dispositivo** Microsoft Defender  >  **ATP**.
3. Imposta **Connetti dispositivi Windows 10.0.15063+** a Microsoft Defender Advanced Threat Protection su **On.**
4. Fare clic su **Salva**.


### <a name="step-3-create-the-compliance-policy-in-intune"></a>Passaggio 3: Creare i criteri di conformità in Intune
1. Nel portale [di Azure](https://portal.azure.com)seleziona Tutti **i servizi,** filtra **in Intune** e seleziona **Microsoft Intune.**
2. Selezionare **Criteri di conformità** dei  >  **dispositivi** Crea  >  **criterio**.
3. Immettere un **nome** e una **descrizione.**
4. In **Piattaforma** seleziona **Windows 10 e versioni successive.**
5. Nelle impostazioni **integrità dispositivo** imposta Richiedi che **il** dispositivo sia al livello di minaccia del dispositivo o al livello di minaccia del dispositivo al livello preferito:

   - **Protetto**: questo livello è il più sicuro. Il dispositivo non può avere minacce esistenti e accedere comunque alle risorse aziendali. Se vengono rilevate minacce, il dispositivo viene valutato come non conforme.
   - **Low**: il dispositivo è conforme se esistono solo minacce di basso livello. I dispositivi con livelli di minaccia medio o alto non sono conformi.
   - **Medio:** il dispositivo è conforme se le minacce rilevate nel dispositivo sono basse o medie. Se vengono rilevate minacce di alto livello, il dispositivo viene determinato come non conforme.
   - **Alto:** questo livello è il meno sicuro e consente tutti i livelli di minaccia. Pertanto, i dispositivi con livelli di minaccia alti, medi o bassi sono considerati conformi.

6. Selezionare **OK** e **Crea** per salvare le modifiche e creare il criterio.

### <a name="step-4-assign-the-policy"></a>Passaggio 4: Assegnare il criterio
1. Nel portale [di Azure](https://portal.azure.com)seleziona Tutti **i servizi,** filtra **in Intune** e seleziona **Microsoft Intune.**
2. Seleziona **Criteri di conformità**  >  **dei** dispositivi> i criteri di conformità di Microsoft Defender ATP.
3. Selezionare **Attività**.
4. Includi o escludi i gruppi di Azure AD per assegnare loro il criterio.
5. Per distribuire il criterio ai gruppi, selezionare **Salva.** I dispositivi utente destinati ai criteri vengono valutati per la conformità.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>Passaggio 5: Creare un criterio di accesso condizionale di Azure AD
1. Nel portale [di Azure,](https://portal.azure.com)aprire **Azure Active Directory** Conditional  >  **Access**  >  **New policy**.
2. Immettere un nome **di** criterio e selezionare **Utenti e gruppi**. Utilizzare le opzioni Includi o Escludi per aggiungere i gruppi per il criterio e selezionare **Fatto.**
3. Seleziona **App cloud** e scegli le app da proteggere. Ad esempio, scegliere **Seleziona app** e selezionare **Office 365 SharePoint Online** ed Office **365 Exchange Online.** Selezionare **Fine** per salvare le modifiche.

4. Seleziona **Condizioni**  >  **App client** per applicare il criterio ad app e browser. Ad esempio, selezionare **Sì** e quindi abilitare **le app browser** e per dispositivi mobili e i client **desktop.** Selezionare **Fine** per salvare le modifiche.

5. Seleziona **Concedi** per applicare l'accesso condizionale in base alla conformità del dispositivo. Ad esempio, seleziona **Concedi accesso**  >  **Richiedi che il dispositivo sia contrassegnato come conforme.** Scegliere **Seleziona** per salvare le modifiche.

6. Selezionare **Abilita criterio** e quindi Crea **per** salvare le modifiche.

Per altre informazioni, vedi [Abilitare Microsoft Defender ATP con accesso condizionale in Intune.](https://docs.microsoft.com/intune/advanced-threat-protection)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
