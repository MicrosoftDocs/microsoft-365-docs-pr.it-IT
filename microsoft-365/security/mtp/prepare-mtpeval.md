---
title: Preparare l'ambiente di testing Lab di Microsoft 365 Defender
description: Preparare l'accesso delle parti interessate, le sequenze temporali, le considerazioni sull'ambiente e l'ordine di adozione durante la configurazione del laboratorio di valutazione Microsoft 365 Defender o dell'ambiente pilota
keywords: Preparazione del processo MTP, preparazione pilota MTP, preparazione per l'esecuzione di un progetto pilota MTP, esecuzione di un progetto pilota MTP, deploy, Prepare, stakeholder, Timeline, Environment, endpoint, server, Management, adoption
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: a255c74db030325ba22c2095fba732a93b8c269c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844849"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a>Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

La creazione di un ambiente pilota o di un laboratorio di valutazione di Microsoft 365 Defender è un processo in tre fasi:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab environment" title="Preparare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota" />
      <br/>Fase 1: preparazione </a><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab environment" title="Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota" />
      <br/>Fase 2: installazione </a><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft 365 Defender pillar" title="Configurare ogni pilastro Microsoft 365 Defender e onboard your Endpoints" />
      <br/>Fase 3: configurare & onboard</a><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

Si è attualmente in fase di preparazione.


La preparazione è la chiave per una distribuzione corretta. In questa sezione vengono illustrate le operazioni da prendere in considerazione durante la preparazione per la creazione di un laboratorio di valutazione o un ambiente pilota per la distribuzione di Microsoft 365 Defender.

## <a name="prerequisites"></a>Prerequisiti
Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft 365 Defender. Vedere i requisiti minimi per [microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Microsoft Defender per Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft cloud app Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).

## <a name="stakeholders-and-sign-off"></a>Parti interessate e disconnessione
Identificare tutte le parti interessate coinvolte nel progetto e gli utenti che potrebbero dover disconnettersi, esaminare o rimanere informati, sia per la valutazione che per l'esecuzione di un progetto pilota.

>[!NOTE]
>Non tutte le organizzazioni potrebbero avere la maturità dell'organizzazione di sicurezza per avere tali ruoli. In tal caso, rivolgersi al proprio team di guida per la revisione e l'approvazione responsabilità.

Aggiungere le parti interessate alla tabella seguente in base alle esigenze della propria organizzazione.

-   COSÌ = disconnessione su questo progetto

-   R = esaminare questo progetto e fornire input

-   I = informato del progetto

| Nome                 | Ruolo                                                                                                                                                                                                          | Azione |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| Immettere il nome e la posta elettronica | **Chief Information Security Officer (OICol)** *un rappresentante esecutivo che funge da sponsor all'interno dell'organizzazione per la nuova distribuzione della tecnologia.*                                                  | Allora     |
| Immettere il nome e la posta elettronica | **Responsabile della Cyber Defense Operations Center (CDOC)** *un rappresentante del team di CDOC incaricato di definire in che modo questa modifica è allineata ai processi del team per le operazioni di sicurezza dei clienti.*       | Allora     |
| Immettere il nome e la posta elettronica | **Architetto della sicurezza** *un rappresentante del team di sicurezza incaricato di definire in che modo questa modifica è allineata con l'architettura di sicurezza di base nell'organizzazione.*                         | R      |
| Immettere il nome e la posta elettronica | **Architetto del posto** *di lavoro un rappresentante del team IT incaricato di definire in che modo questa modifica è allineata all'architettura del posto di lavoro principale nell'organizzazione.*                             | R      |
| Immettere il nome e la posta elettronica | **Analista di sicurezza** *un rappresentante del team di CDOC che può fornire commenti e suggerimenti sulle funzionalità di rilevamento, sull'esperienza utente e sull'utilità complessiva di questa modifica da una prospettiva relativa alle operazioni di sicurezza.* | I      |

## <a name="prepare-your-azure-active-directory"></a>Preparare l'Azure Active Directory
Ignorare questo passaggio se è già stata abilitata la sincronizzazione tra Active Directory e Azure Active Directory in locale. Esaminare la documentazione relativa alle procedure consigliate esistente da Azure Active Directory. I passaggi seguenti sono ottimizzati per valutare o eseguire un progetto pilota di Microsoft 365 Defender.

1. Accedere al portale di [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) > **Azure ad Connect**. 
![Immagine della pagina del portale di Azure Active Directory](../../media/mtp-eval-1.png) <br> 

2. Fare clic su **download** da **Microsoft Azure Active Directory Connect** e trasferirlo nel controller di dominio.
![Immagine della pagina di download di Azure Active Directore Connect](../../media/mtp-eval-2.png) <br>

3. Nel controller di dominio, seguire la procedura guidata di Azure Active Directory Connect. Leggere le condizioni di licenza e l'informativa sulla privacy e selezionare la casella di controllo se si è concordi. Fare clic su **Continua**.
![Immagine della pagina di benvenuto di Azure AD Connect](../../media/mtp-eval-3.png) <br>

4. Passare a **Impostazioni espresse**.
![Immagine della pagina impostazioni di Express](../../media/mtp-eval-4.png) <br>

5. Immettere le credenziali di amministratore globale. Fare clic su **Avanti**.
![Immagine della pagina connessione ad Azure AD, in cui è necessario immettere le credenziali di amministratore globale](../../media/mtp-eval-5.png) <br>

6. Immettere le credenziali di amministratore dell'organizzazione di servizi di dominio Active Directory. Fare clic su **Avanti**.
![Immagine della pagina Connetti a servizi di dominio Active Directory in cui inserire le credenziali](../../media/mtp-eval-6.png) <br>

7. Fare clic su **Installa** per confermare la configurazione.
![Immagine della pagina di conferma della configurazione](../../media/mtp-eval-7.png) <br>

8. Congratulazioni, è stata configurata correttamente Azure Active Directory Connect.
![Immagine di una pagina di Azure Active Directory Connect configurata correttamente](../../media/mtp-eval-8.png) <br>

È ora possibile [aggiungere utenti e gruppi a Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) e [configurare un criterio Sam-R](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).  


## <a name="configuration-order"></a>Ordine di configurazione
Nella tabella seguente viene indicato l'ordine consigliato da Microsoft per la configurazione dei componenti di Microsoft 365 Defender per la distribuzione di un laboratorio di valutazione o dell'ambiente pilota.

| Componente                               | Descrizione                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | Classificazione degli ordini di configurazione |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|Microsoft Defender per Office 365|Microsoft Defender per Office 365 salvaguarda la propria organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. <br> [Ulteriori informazioni.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | 1                    |
|Microsoft Defender per identità|Microsoft Defender for Identity utilizza segnali di Active Directory per identificare, rilevare ed esaminare le minacce avanzate, le identità compromesse e le azioni Insider dannose indirizzate alla propria organizzazione. <br> [Altre informazioni](https://docs.microsoft.com/azure-advanced-threat-protection/).| 2 |
|Microsoft Cloud App Security| Microsoft cloud app Security è un broker di sicurezza cloud Access (CASB) che opera su più cloud. Offre una visibilità completa, il controllo dei dati di viaggio e un'analisi avanzata per identificare e combattere Cyberthreats in tutti i servizi cloud. <br> [Altre informazioni](https://docs.microsoft.com/cloud-app-security/).                                                                                                                                                                                                                                                                                                                                                                       |3                   |
|Microsoft Defender ATP | Microsoft Defender per il rilevamento endpoint endpoint e le funzionalità di risposta offrono rilevamenti di attacchi avanzati che sono quasi in tempo reale e utilizzabili. I responsabili della sicurezza possono assegnare priorità agli avvisi in modo efficace, ottenere una visibilità completa su una violazione e adottare azioni di risposta per correggere le minacce. <br> [Ulteriori informazioni.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |4                    |                                                                                                                                                                                                                                    

## <a name="next-step"></a>Passaggio successivo
|![Fase 2: installazione](../../media/setup.png) <br>[Fase 2: installazione](setup-mtpeval.md) | Configurare il laboratorio di valutazione Microsoft 365 Defender o l'ambiente pilota
|:-------|:-----|

