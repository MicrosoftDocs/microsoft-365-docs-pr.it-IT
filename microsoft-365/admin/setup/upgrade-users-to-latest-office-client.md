---
title: Aggiornare il Office 2010 a Microsoft 365 - Microsoft 365 amministratore
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Informazioni su come aggiornare i Microsoft Office al client Office più recente per gli utenti dell'organizzazione.
ms.topic: article
ms.openlocfilehash: 877659e420079ed607adc13e5bbe44bdc979f5ac
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924696"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Aggiornare il Microsoft 365 per gli utenti aziendali al client Office più recente

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 raggiunge la fine del supporto

Office 2010 ha raggiunto la fine del supporto il 13 ottobre 2020. Microsoft non fornirà più quanto segue:

- Supporto tecnico per i problemi

- Correzioni di bug per i problemi individuati

- Correzioni della sicurezza per le vulnerabilità individuate

Per Office roadmap di fine supporto per la fine del [2010,](/deployoffice/endofsupport/office-2010-end-support-roadmap) vedere .

 **Questo è l'argomento giusto per te?**
  
 Se sei l'amministratore responsabile dell'abbonamento Microsoft 365 per le aziende nell'organizzazione, sei nel posto giusto. Gli amministratori sono in genere responsabili di attività quali la gestione degli utenti, la reimpostazione delle password, la gestione Office le installazioni e l'aggiunta o la rimozione di licenze.

 Se non si è un amministratore e si dispone di un prodotto [Microsoft 365 Family,](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) vedere How [do I upgrade Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) per informazioni sull'aggiornamento della versione precedente per uso domestico di Office.

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Prepararsi per l'aggiornamento a Microsoft 365

Gli amministratori controllano la versione di Office utenti dell'organizzazione che possono installare. È consigliabile aiutare gli utenti dell'organizzazione che eseguono versioni precedenti di Office, ad esempio Office 2010, Office 2013 o Office 2016, eseguire l'aggiornamento alla versione più recente per sfruttare i miglioramenti apportati alla sicurezza e alla produttività.

## <a name="upgrade-steps"></a>Passaggi di aggiornamento

I passaggi riportati di seguito illustrano il processo per aggiornare gli utenti al client desktop di Office più recente. È consigliabile leggere questi passaggi prima di avviare il processo di aggiornamento.
  
## <a name="step-1---check-system-requirements"></a>Passaggio 1: Verificare i requisiti di sistema

[Controlla i requisiti di sistema](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) per Office verificare che i dispositivi siano compatibili con la versione più recente di Office. Ad esempio, le versioni più recenti Office non possono essere installate nei computer che eseguono Windows XP o Windows Vista.
  
> [!TIP]
> Se nell'organizzazione sono presenti utenti che eseguono versioni precedenti di Windows nei propri PC o portatili, è consigliabile eseguire l'aggiornamento a Windows 10. Windows 7 ha raggiunto la fine del supporto. Per [altre info, Windows supporto per le 7 termina a gennaio 2020.](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1)

Vedere i requisiti [Windows 10 di sistema](https://www.microsoft.com/windows/windows-10-specifications) per verificare se è possibile aggiornare i propri sistemi operativi.

### <a name="check-application-compatibility"></a>Verificare la compatibilità delle applicazioni

Per assicurare la riuscita dell'aggiornamento, è importante identificare le applicazioni di Office, inclusi script VBA, macro, componenti aggiuntivi di terze parti e documenti e fogli di calcolo complessi, e valutarne la compatibilità con la versione più recente di Office.
  
Ad esempio, se si usano componenti aggiuntivi di terze parti con la versione installata di Office, contattare il produttore per assicurarsi che siano compatibili con la versione più recente di Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Passaggio 2: Controllare il piano di abbonamento esistente

Alcuni Microsoft 365 non includono le versioni desktop complete di Office e i passaggi per l'aggiornamento sono diversi se il piano non include Office.
  
Non si è certi del piano di sottoscrizione di cui si dispone? Vedere [Quali Microsoft 365 per le aziende?](../admin-overview/what-subscription-do-i-have.md)
  
Se il piano esistente include Office, passare al [Passaggio 3: Disinstallare Office](#step-3---uninstall-office).
  
Se il piano esistente non include Office, scegliere tra le opzioni seguenti:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Opzioni di aggiornamento per i piani che non includono Office

 **Opzione 1: cambiare Office abbonamenti**

Passare a un abbonamento che include Office. Vedere [Switch to a different Microsoft 365 for business plan](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Opzione 2: acquistare singoli acquisti di Office o acquistare Office tramite un contratto multilicenza**

 - Acquistare un singolo acquisto di Office. Vedere [Office Home &amp; Business](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) [o Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     OPPURE

 - Acquistare più copie di Office tramite un contratto multilicenza. Vedere [Confronto tra le famiglie di prodotti con contratto multilicenza](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Passaggio 3: Disinstallare Office

Prima di installare la versione più recente di Office, è consigliabile disinstallare tutte le versioni precedenti di Office. Tuttavia, se si cambia idea sull'aggiornamento di Office, tenere presente i casi seguenti in cui non sarà possibile reinstallare Office dopo la disinstallazione.
  
Se si dispone di componenti aggiuntivi di terze parti, contattare il produttore per verificare se è disponibile un aggiornamento che funzionerà con la versione più recente di Office.

> [!TIP]
> Se si verificano problemi durante la disinstallazione di Office, è possibile utilizzare lo strumento Microsoft Assistente supporto e ripristino per rimuovere Office: Scaricare ed eseguire [Microsoft Assistente supporto e ripristino](https://go.microsoft.com/fwlink/?LinkID=2155008).

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Selezionare la versione di Office da disinstallare

- [Da un PC](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Da un Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Problemi noti relativi alla reinstallazione di versioni precedenti di Office dopo averle disinstallate

 **Office tramite un contratto multilicenza** Se non hai più accesso ai file di origine di queste versioni con contratto multilicenza di Office, non potrai reinstallarlo.

 **Office preinstallato nel computer** Se non si dispone più di un disco o di un codice Product Key (Office fornito con uno) non sarà possibile reinstallarlo.

 **Sottoscrizioni non supportate** Se la copia di Office è stata ottenuta tramite sottoscrizioni sospese, ad esempio Office 365 Small Business Premium o Office 365 Mid-size Business, non sarà possibile installare una versione precedente di Office a meno che non si abbia il codice Product Key fornito con l'abbonamento.

Se si preferisce installare la versione precedente di Office affiancato alla versione più recente, in [Installare e usare più versioni di Office nello stesso PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf) è riportato un elenco delle versioni che lo consentono. Un'installazione affiancata potrebbe essere la scelta giusta se, ad esempio, sono stati installati componenti aggiuntivi di terze parti che vengono usati con la versione precedente di Office e non si è ancora sicuri che siano compatibili con la versione più recente.

## <a name="step-4---assign-office-licenses-to-users"></a>Passaggio 4: Assegnare licenze di Office agli utenti

Se non è già stato fatto, assegnare licenze agli utenti dell'organizzazione che devono installare Office, vedere [Assegnare](../manage/assign-licenses-to-users.md)licenze agli utenti in Microsoft 365 per le aziende .
  
## <a name="step-5---install-office"></a>Passaggio 5: Installare Office

Dopo aver verificato gli utenti che vuoi aggiornare tutti hanno licenze, il passaggio finale consiste nel fare in modo che installino Office, vedi Scaricare e installare o reinstallare Office nel PC o [nel Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)
  
> [!TIP]
> Se non vuoi che gli utenti installino Office, vedi Gestire le impostazioni di [download del software in Office 365](/DeployOffice/manage-software-download-settings-office-365). È possibile utilizzare lo strumento di distribuzione di [Office](/DeployOffice/overview-office-deployment-tool) per scaricare il software Office nella rete locale e quindi distribuire Office utilizzando il metodo di distribuzione del software utilizzato in genere.