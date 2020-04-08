---
title: Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Determinare se il tenant e gli utenti di Office 365 soddisfano i requisiti, in modo che sia possibile utilizzare la distribuzione centralizzata per distribuire i componenti aggiuntivi di Office.
ms.openlocfilehash: d6b81a5ac5ef3b5287810110e5d0582bf34bff93
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189021"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a>Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione

La distribuzione centralizzata è il metodo consigliato e più ricco di funzionalità per la maggior parte dei clienti per distribuire i componenti aggiuntivi per Office agli utenti e ai gruppi all'interno dell'organizzazione di Office 365. Se si è un amministratore, utilizzare queste linee guida per determinare se il tenant e gli utenti soddisfano i requisiti affinché sia possibile utilizzare la distribuzione centralizzata.
La distribuzione centralizzata supporta le app di Office, Windows, Mac, iOS, Android e online.
È possibile richiedere fino a 24 ore affinché un componente aggiuntivo venga visualizzato per il client per tutti gli utenti.
  
## <a name="requirements"></a>Requisiti

La distribuzione centralizzata dei componenti aggiuntivi richiede che gli utenti utilizzino Office 365 ProPlus (e siano firmati in Office utilizzando l'ID dell'organizzazione) e dispongano di cassette postali di Exchange Online e Active Exchange Online. È necessario che la directory di sottoscrizione sia in o federata in Azure Active Directory.
È possibile visualizzare i requisiti specifici per Office ed Exchange di seguito oppure utilizzare la [Verifica compatibilità della distribuzione centralizzata di office 365](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins?view=o365-worldwide#office-365-centralized-deployment-compatibility-checker).

La distribuzione centralizzata non supporta quanto segue:
  
- Componenti aggiuntivi per Word, Excel o PowerPoint in Office 2013
    
- Servizio di directory locale
    
- Distribuzione di componenti aggiuntivi in SharePoint  

- App Teams
   
- Distribuzione dei componenti aggiuntivi Component Object Model (COM) o Visual Studio Tools per Office (VSTO)
    
- Distribuzioni di Office 365 che non includono Exchange, come Office 365 Business

### <a name="office-requirements"></a>Requisiti di Office

- Per i componenti aggiuntivi di Word, Excel e PowerPoint, è necessario che gli utenti utilizzino uno dei seguenti elementi:
  - In un dispositivo Windows, versione 1704 o successiva di Office 365 ProPlus.
  - Su un Mac, versione 15,34 o successiva.

- Per Outlook, è necessario che gli utenti utilizzino una delle opzioni seguenti: 
  - Versione 1701 o successiva di Office 365 ProPlus.
  - Versione 1808 o successiva di Office Professional Plus 2019 o Office standard 2019.
  - Version 16.0.4494.1000 o versione successiva di Office Professional Plus 2016 (MSI) o Office standard 2016 (MSI)\*
  - Version 15.0.4937.1000 o versione successiva di Office Professional Plus 2013 (MSI) o Office Standard 2013 (MSI)\*
  - Version 16.0.9318.1000 o versione successiva di Office 2016 per Mac 
- Version 2.75.0 o versione successiva di Outlook Mobile per iOS 
- Version 2.2.145 o versione successiva di Outlook Mobile per Android 
    
    * Le versioni MSI di Outlook visualizzano i componenti aggiuntivi installati dall'amministratore nella barra multifunzione di Outlook appropriata e non nella sezione "componenti aggiuntivi".
    

#### <a name="find-out-if-office-365-proplus-is-installed"></a>Scoprire se Office 365 ProPlus è installato

Per utilizzare Office 365 ProPlus, un utente deve disporre di un account di Office 365 e deve disporre di una licenza. Per altre informazioni, vedere [Panoramica di Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846328).

Il modo più semplice per rilevare se un utente dispone di Office 365 ProPlus installato e lo ha utilizzato di recente consiste nell'utilizzare il rapporto attivazioni di Microsoft Office, disponibile nell'interfaccia di amministrazione di Microsoft 365. Il report fornisce un elenco di tutti gli utenti che hanno attivato Office 365 ProPlus negli ultimi 7, 30, 90 o 180 giorni. Ai fini della distribuzione centralizzata, le attivazioni desktop per Windows o Mac rappresentano le colonne più importanti del report. È possibile esportare il report in Excel. Per altre informazioni sul report, vedere [Report di Office 365 nell'interfaccia di amministrazione - Attivazioni di Microsoft Office](../activity-reports/microsoft-office-activations.md).
  
Se non si desidera utilizzare il rapporto attivazioni, è possibile chiedere a un utente di aprire un'applicazione di Office come Word nel computer in uso e quindi scegliere **File** \> **account**file. In **informazioni sui prodotti** dovrebbe essere visualizzato **Prodotto a sottoscrizione** e **Microsoft Office 365 ProPlus**, come mostrato nell'immagine seguente.

![Informazioni sul prodotto in un'applicazione di Office](../../media/4bff2bb8-0690-4d22-ac1f-b8881807fa39.png)
  
Per assistenza con Office 365 ProPlus, vedere [Suggerimenti per la risoluzione dei problemi per Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=846339).


### <a name="exchange-online-requirements"></a>Requisiti di Exchange Online

Microsoft Exchange archivia i manifesti del componente aggiuntivo all'interno del tenant dell'organizzazione. Gli amministratori che distribuiscono i componenti aggiuntivi e gli utenti che ricevono i componenti aggiuntivi devono trovarsi in una versione di Exchange Online che supporta l'autenticazione OAuth.
  
Contattare l'amministratore di Exchange dell'organizzazione per sapere quale configurazione è in uso. La connettività OAuth per ogni utente può essere verificata usando il cmdlet di PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351). 


### <a name="office-365-centralized-deployment-compatibility-checker"></a>Verifica compatibilità della distribuzione centralizzata di Office 365

Con Verifica compatibilità della distribuzione centralizzata di Office 365, è possibile verificare se gli utenti del tenant sono configurati per l'uso della distribuzione centralizzata per Word, Excel e PowerPoint. Verifica compatibilità non è necessario per il supporto di Outlook. Scaricare Verifica compatibilità [qui](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).
  
#### <a name="run-the-compatibility-checker"></a>Esecuzione di verifica compatibilità
  
1. Avviare una finestra di PowerShell. exe con privilegi elevati.
    
2. Eseguire il comando riportato di seguito:

```powershell
Import-Module O365CompatibilityChecker
```
    
3. Eseguire il comando **Invoke-CompatabilityCheck** :

```powershell
Invoke-CompatibilityCheck
```
   in cui viene richiesto di *_TenantDomain_* (ad esempio, *TailspinToysIncorporated. onmicrosoft.</span> com*) e le credenziali di *_TenantAdmin_* (utilizzare le credenziali di amministratore globale) e quindi richiede il consenso.
    
> [!NOTE]
> A seconda del numero di utenti nel tenant, la verifica potrebbe richiedere minuti o ore. 
  
Al termine dell'esecuzione dello strumento, viene generato un file di output in formato CSV (valori separati da virgola). Il file viene salvato in **C:\Windows\System32** per impostazione predefinita. Il file di output contiene le informazioni seguenti:
  
- Nome utente
    
- ID utente (indirizzo di posta elettronica dell'utente)
    
- Distribuzione centralizzata pronta: se gli elementi rimanenti sono veri
    
- Piano di Office: il piano di Office in cui sono concessi in licenza
    
- Office attivato: se Office è stato attivato
    
- Cassetta postale supportata: se la cassetta postale è abilitata per OAuth


  
## <a name="user-and-group-assignments"></a>Assegnazioni di utenti e gruppi

La funzionalità Distribuzione centralizzata attualmente supporta la maggior parte dei gruppi supportati da Azure Active Directory, tra cui Gruppi di Office 365, le liste di distribuzione e i gruppi di sicurezza.
  
> [!NOTE]
> I gruppi di sicurezza non abilitati alla posta elettronica non sono attualmente supportati. 
  
La distribuzione centralizzata supporta le assegnazioni a singoli utenti, gruppi e tutti i clienti del tenant. La distribuzione centralizzata supporta gli utenti in gruppi di primo livello o in gruppi senza gruppi padre, ma non gli utenti in gruppi annidati o in gruppi con gruppi padre.
   
Esaminare l'esempio seguente, in cui Valeria, Pupetta e il gruppo Reparto vendite vengono assegnati a un componente aggiuntivo. Reparto vendite costa occidentale è un gruppo annidato, quindi Gianni e Albertino non sono assegnati a un componente aggiuntivo.
  
![Diagramma del reparto vendite](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a>Scoprire se un gruppo contiene gruppi annidati

Il modo più semplice per rilevare se un gruppo contiene gruppi annidati consiste nel visualizzare la scheda contatto del gruppo in Outlook. Se si immette il nome del gruppo all'interno del campo **a** di un messaggio di posta elettronica e quindi si seleziona il nome del gruppo quando viene risolto, verrà visualizzato se contiene utenti o gruppi nidificati. Nell'esempio seguente la scheda **Membri** della scheda contatto di Outlook per il gruppo di test non visualizza utenti e contiene solo due sottogruppi. 
  
![Scheda membri della scheda contatto di Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
È possibile eseguire la query opposta risolvendo il gruppo per vedere se è un membro di un gruppo. Nell'esempio seguente nella scheda **Appartenenza** della scheda contatto di Outlook si vede che il sottogruppo 1 è un membro del gruppo di test. 
  
![Scheda appartenenza della scheda contatto di Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
In alternativa, è possibile usare l'API di Azure Active Directory Graph per eseguire query per trovare l'elenco dei gruppi all'interno di un gruppo. Per altre informazioni, vedere [Operazioni su gruppi | Riferimento API Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).
  
### <a name="contacting-microsoft-for-support"></a>Contattare Microsoft per assistenza

Se l'utente o gli utenti riscontrano problemi durante il caricamento del componente aggiuntivo utilizzando le app di Office per il Web (Word, Excel e così via), che sono state distribuite in modo centralizzato, potrebbe essere necessario contattare il supporto tecnico Microsoft ([informazioni su come](../contact-support-for-business-products.md)). Specificare le informazioni seguenti sull'ambiente di Office 365 nel ticket di supporto.
  
|**Piattaforma**|**Informazioni di debug**|
|:-----|:-----|
|Office  <br/> | Log di Charles/Fiddler  <br/>  ID tenant ( [informazioni](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b.aspx))  <br/>  CorrelationId. Visualizzare l'origine di una delle pagine di Office e cercare il valore dell'ID correlazione e inviarlo al supporto:  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|Rich client (Windows, Mac)  <br/> | Log di Charles/Fiddler  <br/>  Creare numeri dell'app client (preferibilmente come schermata da **file/account**)  <br/> |
   

