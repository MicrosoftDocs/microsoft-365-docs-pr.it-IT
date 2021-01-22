---
title: Preparare l'ambiente lab di valutazione di Microsoft 365 Defender
description: Preparare l'approvazione delle parti interessate, le sequenze temporali, le considerazioni sull'ambiente e l'ordine di adozione durante la configurazione del lab di valutazione o dell'ambiente pilota di Microsoft 365 Defender
keywords: Preparazione di prova MTP, preparazione pilota MTP, preparazione per l'esecuzione di un progetto pilota MTP, eseguire un progetto pilota MTP, distribuire, preparare, stakeholder, sequenza temporale, ambiente, endpoint, server, gestione, adozione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 35f1d3f0b5cefb0f14508571511449fc2c7d58a9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930151"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Preparare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La creazione di un ambiente pilota o un lab di valutazione di Microsoft 365 Defender e la sua distribuzione è un processo in tre fasi:

|![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)<br/>Fase 1: preparazione |[![Fase 2: configurazione](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)<br/>[Fase 2: configurazione](setup-mtpeval.md) |[![Fase 3: onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Fase 3: onboard](config-mtpeval.md) | [![Tornare al progetto pilota](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Tornare al playbook pilota](mtp-pilot.md) |
|--|--|--|--|
|*Sei qui!* | || |

È in corso la fase di preparazione.


La preparazione è fondamentale per una distribuzione corretta. Questa sezione contiene informazioni su cosa è necessario considerare durante la preparazione per la creazione di un ambiente di prova o pilota per la distribuzione di Microsoft 365 Defender.

## <a name="prerequisites"></a>Prerequisiti
Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per il provisioning e l'uso di Microsoft 365 Defender. Vedere i requisiti minimi per [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites) [Microsoft Defender per Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) [Microsoft Defender per Office 365,](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) [Microsoft Defender for Identity,](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites) [Microsoft Cloud App Security.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)

## <a name="stakeholders-and-sign-off"></a>Parti interessate e disconnessione
Identificare tutti i cointeressati coinvolti nel progetto e chi potrebbe dover firmare, rivedere o rimanere informati, sia per la valutazione che per l'esecuzione di un progetto pilota.

>[!NOTE]
>Non tutte le organizzazioni potrebbero avere la maturità dell'organizzazione della sicurezza per avere tali ruoli. In tal caso, consultare il team di leadership sulle responsabilità di revisione e approvazione.

Aggiungere le parti interessate alla tabella seguente in base alle esigenze dell'organizzazione.

-   SO = Sign-off on this project

-   R = Rivedere questo progetto e fornire l'input

-   I = Informato di questo progetto

| Nome                 | Ruolo                                                                                                                                                                                                          | Azione |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Immettere nome e posta elettronica | **Chief Information Security Officer (CISO)** Un rappresentante esecutivo che funge da sponsor all'interno dell'organizzazione *per la distribuzione della nuova tecnologia.*                                                  | Allora     |
| Immettere nome e posta elettronica | **Head of Cyber Defense Operations Center (CDOC)** *A representative from the CDOC team in charge of defining how this change is aligned with the processes in the customers security operations team.*       | Allora     |
| Immettere nome e posta elettronica | **Security Architect** *A representative from the Security team in charge of defining how this change is aligned with the core Security architecture in the organization.*                         | R      |
| Immettere nome e posta elettronica | **Workplace Architect** Un rappresentante del team IT incaricato di definire in che modo questa modifica è allineata all'architettura aziendale di base *dell'organizzazione.*                             | R      |
| Immettere nome e posta elettronica | Security Analyst *A representative from the CDOC team who can provide feedback on the detection capabilities, user experience, and overall usefulness of this change from a security operations perspective.*  | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparare Azure Active Directory
Ignorare questo passaggio se è già stata abilitata la sincronizzazione tra Active Directory e Azure Active Directory in locale. Esaminare la documentazione delle procedure consigliate esistenti da Azure Active Directory. I passaggi seguenti sono ottimizzati per valutare o eseguire un progetto pilota di Microsoft 365 Defender.

1. Passare al [portale di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > Azure AD **Connect.** 
![Immagine della pagina del portale di Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Fare **clic su** Scarica da Microsoft Azure Active Directory **Connect** e trasferirlo nel controller di dominio.
![Immagine della pagina di download di Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. Nel controller di dominio, seguire la procedura guidata azure Active Directory Connect. Leggi le condizioni di licenza e l'informativa sulla privacy e seleziona la casella di controllo se accetti. Fare clic su **Continua**.
![Immagine della pagina di benvenuto di Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Passare a **Impostazioni rapide.**
![Immagine della pagina Impostazioni rapide](../../media/mtp-eval-4.png) <br>

5. Immettere le credenziali di amministratore globale. Fare clic su **Avanti**.
![Immagine della pagina Connetti ad Azure AD in cui immettere le credenziali di amministratore globale](../../media/mtp-eval-5.png) <br>

6. Immettere le credenziali di amministratore dell'organizzazione di Servizi di dominio Active Directory. Fare clic su **Avanti**.
![Immagine della pagina Connetti a Servizi di dominio Active Directory in cui immettere le credenziali](../../media/mtp-eval-6.png) <br>

7. Fare **clic su** Installa per confermare la configurazione.
![Immagine della pagina di conferma della configurazione](../../media/mtp-eval-7.png) <br>

8. Congratulazioni, Azure Active Directory Connect è stato configurato correttamente.
![Immagine di una pagina di Azure Active Directory Connect configurata correttamente](../../media/mtp-eval-8.png) <br>

È ora possibile [aggiungere utenti e gruppi ad Active Directory e](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) configurare un criterio [SAM-R.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Ordine di configurazione
La tabella seguente indica l'ordine consigliato da Microsoft per la configurazione dei componenti di Microsoft 365 Defender per la distribuzione del lab di valutazione o dell'ambiente pilota.

| Componente                               | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificazione dell'ordine di configurazione |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender per Office 365|Microsoft Defender per Office 365 protegge l'organizzazione dalle minacce dannose rappresentate da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. <br> [Ulteriori informazioni.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|Che cosa è Microsoft Defender per identità?|Microsoft Defender for Identity usa i segnali di Active Directory per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni Insider dannose indirizzate all'organizzazione. <br> [Altre informazioni](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security è un Cloud Access Security Broker (CASB) che opera su più cloud. Offre visibilità completa, controllo sui viaggi dei dati e analisi sofisticate per identificare e contrastare le minacce informatiche in tutti i servizi cloud. <br> [Altre informazioni](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender per endpoint | Le funzionalità di rilevamento e risposta degli endpoint di Microsoft Defender per endpoint forniscono rilevamenti avanzati di attacchi quasi in tempo reale e utilizzabili. I responsabili della sicurezza possono assegnare priorità agli avvisi in modo efficace, ottenere una visibilità completa su una violazione e adottare azioni di risposta per correggere le minacce. <br> [Ulteriori informazioni.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Passaggio successivo
|![Fase 2: installazione](../../media/setup.png) <br>[Fase 2: installazione](setup-mtpeval.md) | Configurare il lab di valutazione o l'ambiente pilota di Microsoft 365 Defender
|:-------|:-----|

