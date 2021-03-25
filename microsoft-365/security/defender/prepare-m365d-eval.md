---
title: Preparare l'ambiente lab di valutazione di Microsoft 365 Defender
description: Preparare l'approvazione delle parti interessate, le tempistiche, le considerazioni sull'ambiente e l'ordine di adozione durante la configurazione del lab di valutazione o dell'ambiente pilota di Microsoft 365 Defender
keywords: Preparazione di prova MTP, preparazione pilota MTP, preparazione per l'esecuzione di un progetto pilota MTP, esecuzione di un progetto pilota MTP, distribuzione, preparazione, parti interessate, sequenza temporale, ambiente, endpoint, server, gestione, adozione
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
ms.openlocfilehash: dada110faca71c9e8fcf384eb5bb0a78faefaad9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199138"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Preparare il laboratorio di valutazione o l'ambiente pilota di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La creazione di un laboratorio di valutazione o di un ambiente pilota di Microsoft 365 Defender e la distribuzione è un processo in tre fasi:

|![Fase 1: preparare](../../media/phase-diagrams/prepare.png)<br/>Fase 1: preparare |[![Fase 2: configurazione](../../media/phase-diagrams/setup.png)](setup-m365deval.md)<br/>[Fase 2: configurazione](setup-m365deval.md) |[![Fase 3: onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Fase 3: onboard](config-m365d-eval.md) | [![Torna al progetto pilota](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Torna al playbook pilota](m365d-pilot.md) |
|--|--|--|--|
|*Sei qui!* | || |

È in corso la fase di preparazione.


La preparazione è fondamentale per una distribuzione corretta. In questa sezione verranno trattate le informazioni necessarie per preparare la creazione di un laboratorio di valutazione o di un ambiente pilota per la distribuzione di Microsoft 365 Defender.

## <a name="prerequisites"></a>Prerequisiti
Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per il provisioning e l'uso di Microsoft 365 Defender. Vedere i requisiti minimi per [Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/defender/prerequisites) [Microsoft Defender for Endpoint,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements) [Microsoft Defender per Office 365,](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) [Microsoft Defender for Identity,](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites) [Microsoft Cloud App Security.](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)

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

## <a name="prepare-your-azure-active-directory"></a>Preparare Azure Active Directory
Ignorare questo passaggio se è già stata abilitata la sincronizzazione tra Active Directory e Azure Active Directory in locale. Esaminare la documentazione sulle procedure consigliate esistenti da Azure Active Directory. I passaggi seguenti sono ottimizzati per valutare o eseguire un progetto pilota di Microsoft 365 Defender.

1. Passare al portale [di Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > Azure AD **Connect**. 
![Immagine della pagina del portale di Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Fare **clic su** Scarica da Microsoft Azure Active Directory **Connect** e trasferirlo nel controller di dominio.
![Immagine della pagina di download di Azure Active Directoru Connect](../../media/mtp-eval-2.png) <br>

3. Nel controller di dominio, seguire la procedura guidata Azure Active Directory Connect. Leggi le condizioni di licenza e l'informativa sulla privacy e seleziona la casella di controllo se accetti. Fare clic su **Continua**.
![Immagine della pagina di benvenuto di Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Passare a **Impostazioni rapide**.
![Immagine della pagina Impostazioni rapide](../../media/mtp-eval-4.png) <br>

5. Immettere le credenziali di amministratore globale. Fare clic su **Avanti**.
![Immagine della pagina Connetti ad Azure AD in cui immettere le credenziali di amministratore globale](../../media/mtp-eval-5.png) <br>

6. Immettere le credenziali di amministratore dell'organizzazione di Servizi di dominio Active Directory. Fare clic su **Avanti**.
![Immagine della pagina Connessione ad AD DS in cui immettere le credenziali](../../media/mtp-eval-6.png) <br>

7. Fare **clic su** Installa per confermare la configurazione.
![Immagine della pagina di conferma della configurazione](../../media/mtp-eval-7.png) <br>

8. Congratulazioni, azure Active Directory Connect è stato configurato correttamente.
![Immagine di una pagina di Azure Active Directory Connect configurata correttamente](../../media/mtp-eval-8.png) <br>

È ora possibile [aggiungere utenti e gruppi ad Active Directory e](/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) configurare un criterio [SAM-R.](/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)  


## <a name="configuration-order"></a>Ordine di configurazione
La tabella seguente indica l'ordine consigliato da Microsoft per la configurazione dei componenti di Microsoft 365 Defender per la distribuzione del laboratorio di valutazione o dell'ambiente pilota.

| Componente                               | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificazione dell'ordine di configurazione |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender per Office 365|Microsoft Defender per Office 365 protegge l'organizzazione dalle minacce dannose rappresentate da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. <br> [Ulteriori informazioni.](/microsoft-365/security/office-365-security/defender-for-office-365)                                                                                                                                                                                                                                             | 1                   |
|Microsoft Defender per identità|Microsoft Defender for Identity usa i segnali di Active Directory per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni insider dannose indirizzate all'organizzazione. <br> [Altre informazioni](/azure-advanced-threat-protection/).| 2  |
|Microsoft Cloud App Security| Microsoft Cloud App Security è un Cloud Access Security Broker (CASB) che opera su più cloud. Offre una visibilità completa, un controllo sui trasferimenti di dati e analisi sofisticate per identificare e combattere le minacce informatiche in tutti i servizi cloud. <br> [Altre informazioni](/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                    |
|Microsoft Defender per endpoint | Le funzionalità di rilevamento e di risposta degli endpoint disponibili in Microsoft Defender per endpoint forniscono il rilevamento di attacchi avanzati quasi in tempo reale. I responsabili della sicurezza possono assegnare priorità agli avvisi in modo efficace, ottenere una visibilità completa su una violazione e adottare azioni di risposta per correggere le minacce. <br> [Ulteriori informazioni.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Passaggio successivo
|![Fase 2: installazione](../../media/setup.png) <br>[Fase 2: installazione](setup-m365deval.md) | Configurare il laboratorio di valutazione o l'ambiente pilota di Microsoft 365 Defender
|:-------|:-----|
