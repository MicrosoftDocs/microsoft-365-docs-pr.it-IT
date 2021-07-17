---
title: Preparare l'Microsoft 365 Defender lab di valutazione
description: Preparare l'approvazione delle parti interessate, le tempistiche, le considerazioni sull'ambiente e l'ordine di adozione durante la configurazione del laboratorio di Microsoft 365 Defender di valutazione o dell'ambiente pilota
keywords: Microsoft 365 Defender preparazione della versione di valutazione, preparazione pilota di Microsoft 365 Defender, preparazione per l'esecuzione di un progetto pilota di Microsoft 365 Defender, esecuzione di un progetto pilota di Microsoft 365 Defender, distribuzione, preparazione, parte interessata, sequenza temporale, ambiente, endpoint, server, gestione, adozione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 7ebb7074b0e06eda96d21142044bd8b9997e094b
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458442"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Preparare il laboratorio di Microsoft 365 Defender o l'ambiente pilota

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La creazione Microsoft 365 Defender laboratorio di valutazione o un ambiente pilota e la distribuzione è un processo in tre fasi:

|![Fase 1: preparazione](../../media/phase-diagrams/prepare.png)<br/>Fase 1: preparazione |[![Fase 2: configurazione](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: configurazione](setup-m365deval.md) |[![Phase 3: onboarding](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fase 3: onboarding](config-m365d-eval.md) | [![Torna al progetto pilota](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Torna al playbook pilota](m365d-pilot.md) |
|--|--|--|--|
|*Sei qui!* | || |

È in corso la fase di preparazione.


La preparazione è fondamentale per una distribuzione corretta. In questa sezione verranno trattate le informazioni necessarie per preparare la creazione di un laboratorio di valutazione o di un ambiente pilota per la Microsoft 365 Defender distribuzione.

## <a name="prerequisites"></a>Prerequisiti
Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per eseguire il provisioning e l'Microsoft 365 Defender. Vedi i requisiti minimi per [Microsoft 365 Defender,](/microsoft-365/security/defender/prerequisites) [Microsoft Defender per Endpoint,](/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) [Microsoft Defender per Office 365,](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) [Microsoft Defender per l'identità,](/azure-advanced-threat-protection/atp-prerequisites) [Microsoft Cloud App Security](/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Parti interessate e disconnessione
Identificare tutti gli stakeholder coinvolti nel progetto e chi potrebbe dover disconnettersi, rivedere o rimanere informati, sia per la valutazione che per l'esecuzione di un progetto pilota.

>[!NOTE]
>Non tutte le organizzazioni potrebbero avere la maturità dell'organizzazione di sicurezza per avere tali ruoli. In tal caso, consultare il team di leadership sulle responsabilità di revisione e approvazione.

Aggiungere le parti interessate alla tabella seguente in base alle esigenze dell'organizzazione.

-   SO = Sign-off on this project

-   R = Rivedere questo progetto e fornire input

-   I = Informato di questo progetto

| Nome                 | Ruolo                                                                                                                                                                                                          | Azione |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Immettere nome e posta elettronica | **Chief Information Security Officer (CISO)** Un rappresentante esecutivo che funge da sponsor all'interno dell'organizzazione *per la distribuzione delle nuove tecnologie.*                                                  | Allora     |
| Immettere nome e posta elettronica | **Head of Cyber Defense Operations Center (CDOC)** Un rappresentante del team CDOC incaricato di definire in che modo questa modifica è allineata ai processi nel team delle operazioni di *sicurezza dei clienti.*       | Allora     |
| Immettere nome e posta elettronica | **Security Architect** Un rappresentante del team di sicurezza responsabile della definizione di come questa modifica è allineata all'architettura di sicurezza di *base dell'organizzazione.*                         | R      |
| Immettere nome e posta elettronica | **Workplace Architect** Un rappresentante del team IT responsabile della definizione del modo in cui questo cambiamento è allineato all'architettura aziendale di *base dell'organizzazione.*                             | R      |
| Immettere nome e posta elettronica | **Security Analyst** *Un rappresentante del team CDOC* che può fornire feedback sulle funzionalità di rilevamento, sull'esperienza utente e sull'utilità complessiva di questo cambiamento dal punto di vista delle operazioni di sicurezza. | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparare la Azure Active Directory
Ignorare questo passaggio se è già stata abilitata la sincronizzazione tra Active Directory e Azure Active Directory locale. Esaminare la documentazione sulle procedure consigliate esistenti Azure Active Directory. I passaggi seguenti sono ottimizzati per valutare o eseguire un progetto pilota Microsoft 365 Defender progetto.

1. Passare al portale [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) di > **Azure AD Connessione**. 
![Immagine della Azure Active Directory portale](../../media/mtp-eval-1.png) <br> 

2. Fare **clic** su **Scarica Microsoft Azure Active Directory Connessione** e trasferirlo nel controller di dominio.
![Immagine della pagina di download di Azure Active Directoru Connessione download](../../media/mtp-eval-2.png) <br>

3. Nel controller di dominio, seguire la procedura guidata Azure Active Directory Connessione guidata. Leggi le condizioni di licenza e l'informativa sulla privacy e seleziona la casella di controllo se accetti. Fare clic su **Continua**.
![Immagine della pagina di benvenuto Connessione azure AD](../../media/mtp-eval-3.png) <br>

4. Passare a **Express Impostazioni**.
![Immagine della pagina express Impostazioni](../../media/mtp-eval-4.png) <br>

5. Immettere le credenziali di amministratore globale. Fare clic su **Avanti**.
![Immagine della Connessione in Azure AD in cui immettere le credenziali di amministratore globale](../../media/mtp-eval-5.png) <br>

6. Immettere le credenziali di amministratore dell'organizzazione di Servizi di dominio Active Directory. Fare clic su **Avanti**.
![Immagine della Connessione in Servizi di dominio Active Directory in cui immettere le credenziali](../../media/mtp-eval-6.png) <br>

7. Fare **clic su** Installa per confermare la configurazione.
![Immagine della pagina di conferma della configurazione](../../media/mtp-eval-7.png) <br>

8. Congratulazioni, hai configurato correttamente Azure Active Directory Connessione.
![Immagine di una pagina Azure Active Directory Connessione configurata correttamente](../../media/mtp-eval-8.png) <br>

È ora possibile [aggiungere utenti e gruppi ad Active Directory e](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) configurare un criterio [SAM-R.](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Ordine di configurazione
La tabella seguente indica l'ordine consigliato da Microsoft per la configurazione dei componenti Microsoft 365 Defender per la distribuzione del laboratorio di valutazione o dell'ambiente pilota.

| Componente                               | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificazione dell'ordine di configurazione |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender per Office 365|Microsoft Defender per Office 365 protegge l'organizzazione dalle minacce dannose rappresentate da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. <br> [Ulteriori informazioni.](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                    |
|Microsoft Defender per identità|Microsoft Defender for Identity usa i segnali di Active Directory per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni insider dannose indirizzate all'organizzazione. <br> [Altre informazioni](/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security è un Cloud Access Security Broker (CASB) che opera su più cloud. Offre una visibilità completa, un controllo sui trasferimenti di dati e analisi sofisticate per identificare e combattere le minacce informatiche in tutti i servizi cloud. <br> [Altre informazioni](/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|Microsoft Defender per endpoint | Le funzionalità di rilevamento e di risposta degli endpoint disponibili in Microsoft Defender per endpoint forniscono il rilevamento di attacchi avanzati quasi in tempo reale. I responsabili della sicurezza possono assegnare priorità agli avvisi in modo efficace, ottenere una visibilità completa su una violazione e adottare azioni di risposta per correggere le minacce. <br> [Ulteriori informazioni.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Passaggio successivo
|![Fase 2: configurazione](../../media/setup.png) <br>[Fase 2: configurazione](setup-m365deval.md) | Configurare il laboratorio di Microsoft 365 Defender o l'ambiente pilota
|:-------|:-----|
