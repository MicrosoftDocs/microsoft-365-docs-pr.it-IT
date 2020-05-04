---
title: Aggiornare gli utenti di Microsoft 365 per le aziende all'ultimo client di Office
f1.keywords:
- NOCSH
ms.author: kwekuako
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
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Informazioni su come aggiornare gli utenti all'ultimo client di Office.
ms.openlocfilehash: 2140e246882d9d9b30481bc20b78142708408f88
ms.sourcegitcommit: bd8d55f82ca008af1b93a9bb4d1545f68e8188ad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2020
ms.locfileid: "44011274"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Aggiornare gli utenti di Microsoft 365 per le aziende all'ultimo client di Office

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 raggiunge la fine del supporto tecnico

Office 2010 raggiungerà la fine del supporto il 13 ottobre 2020. Quando Office 2010 raggiunge la fine del supporto, Microsoft non fornirà più gli elementi seguenti:

- Supporto tecnico per i problemi

- Correzioni dei bug per i problemi individuati

- Correzioni per la sicurezza per le vulnerabilità individuate

Per ulteriori informazioni, vedere la Guida [di orientamento alla fine del supporto tecnico di Office 2010](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) .

 **Questo è l'argomento giusto per te?**
  
 Se l'amministratore è responsabile dell'abbonamento a Microsoft 365 for business nell'organizzazione, è il posto giusto. Gli amministratori sono in genere responsabili di attività come la gestione degli utenti, la reimpostazione delle password, la gestione delle installazioni di Office e l'aggiunta o la rimozione di licenze.

 Se non si è un amministratore e si dispone di un prodotto [Microsoft 365 Family](https://support.office.com/article/28cbc8cf-1332-4f04-9123-9b660abb629e.aspx#BKMK_OfficePlans) , vedere [How do I upgrade Office](https://support.office.com/article/ee68f6cf-422f-464a-82ec-385f65391350.aspx) per informazioni sull'aggiornamento delle versioni precedenti di Office.

## <a name="get-ready-to-upgrade"></a>Prepararsi all'aggiornamento

Come amministratore, è possibile controllare quale versione di Office people nell'organizzazione è in grado di installare. È consigliabile aiutare gli utenti dell'organizzazione a eseguire le versioni precedenti di Office, ad esempio Office 2010, Office 2013 o Office 2016, per l'aggiornamento alla versione più recente per trarre vantaggio dai miglioramenti relativi alla sicurezza e alla produttività.

## <a name="upgrade-steps"></a>Passaggi di aggiornamento

I passaggi riportati di seguito illustrano il processo per aggiornare gli utenti al client desktop di Office più recente. È consigliabile leggere questi passaggi prima di avviare il processo di aggiornamento.
  
## <a name="step-1---check-system-requirements"></a>Passaggio 1: Verificare i requisiti di sistema

[Controllare i requisiti di sistema](https://products.office.com/office-system-requirements) per Office per assicurarsi che i dispositivi siano compatibili con la versione più recente di Office. Ad esempio, le versioni più recenti di Office non possono essere installate nei computer che eseguono Windows XP o Windows Vista.
  
> [!TIP]
> Se nell'organizzazione sono presenti utenti che eseguono versioni precedenti di Windows sui PC o laptop, è consigliabile eseguire l'aggiornamento a Windows 10. Windows 7 ha raggiunto la fine del supporto. Leggere il [supporto per Windows 7 termina nel gennaio 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) per altre info.

Consultare i [requisiti di sistema di Windows 10](https://www.microsoft.com/windows/windows-10-specifications) per verificare se è possibile aggiornare i propri sistemi operativi.

### <a name="check-application-compatibility"></a>Verificare la compatibilità delle applicazioni

Per assicurare la riuscita dell'aggiornamento, è importante identificare le applicazioni di Office, inclusi script VBA, macro, componenti aggiuntivi di terze parti e documenti e fogli di calcolo complessi, e valutarne la compatibilità con la versione più recente di Office.
  
Ad esempio, se si usano componenti aggiuntivi di terze parti con la versione installata di Office, contattare il produttore per assicurarsi che siano compatibili con la versione più recente di Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Passaggio 2: Controllare il piano di abbonamento esistente

Alcuni piani di Microsoft 365 non includono le versioni complete desktop di Office e i passaggi per l'aggiornamento sono diversi se il piano non include Office.
  
Non si è sicuri di quale piano di sottoscrizione si ha? [Per sapere quali abbonamenti di Microsoft 365 for business sono](../admin-overview/what-subscription-do-i-have.md) consentiti?
  
Se il piano esistente include Office, passare al [Passaggio 3: Disinstallare Office](#step-3---uninstall-office).
  
Se il piano esistente non include Office, scegliere tra le opzioni seguenti:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Opzioni di aggiornamento per i piani che non includono Office

 **Opzione 1: cambiare le sottoscrizioni di Office**

Passare a un abbonamento che include Office. Vedere [passare a un piano Microsoft 365 for business diverso](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Opzione 2: acquistare singoli, acquisti una tantum di Office o acquistare Office tramite una licenza volume**

 - Acquistare un singolo acquisto di Office. Vedere [Office Home &amp; business](https://products.office.com/home-and-business) o [Office Professional](https://products.office.com/professional)

     OPPURE

 - Acquistare più copie di Office tramite una licenza volume. Vedere [Confronto tra le famiglie di prodotti con contratto multilicenza](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Passaggio 3: Disinstallare Office

Prima di installare la versione più recente di Office, è consigliabile disinstallare tutte le versioni precedenti di Office. Tuttavia, se si cambia idea sull'aggiornamento di Office, si notino le seguenti istanze in cui non sarà possibile reinstallare Office dopo averlo disinstallato.
  
Se si dispone di componenti aggiuntivi di terze parti, contattare il produttore per verificare se è presente un aggiornamento che funzionerà con la versione più recente di Office.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Selezionare la versione di Office da disinstallare

- [Da un PC](https://support.office.com/article/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx)

- [Da un Mac](https://support.office.com/article/eefa1199-5b58-43af-8a3d-b73dc1a8cae3.aspx)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Problemi noti relativi alla reinstallazione di versioni precedenti di Office dopo averle disinstallate

 **Office tramite una licenza volume** Se non si ha più accesso ai file di origine di queste versioni di Office per contratti multilicenza, non sarà possibile reinstallarlo.

 **Office preinstallato nel computer in uso** Se non si ha più un disco o un codice Product Key (se Office è fornito con uno), non sarà possibile reinstallarlo.

 **Sottoscrizioni non supportate** Se la copia di Office è stata ottenuta tramite sottoscrizioni sospese, ad esempio Office 365 Small Business Premium o Office 365 Mid-Size business, non è possibile installare una versione precedente di Office a meno che non si disponga del codice Product Key fornito con l'abbonamento.

Se si preferisce installare la versione precedente di Office affiancato alla versione più recente, in [Installare e usare più versioni di Office nello stesso PC](https://support.office.com/article/6ebb44ce-18a3-43f9-a187-b78c513788bf.aspx) è riportato un elenco delle versioni che lo consentono. Un'installazione affiancata potrebbe essere la scelta giusta se, ad esempio, sono stati installati componenti aggiuntivi di terze parti che vengono usati con la versione precedente di Office e non si è ancora sicuri che siano compatibili con la versione più recente.

## <a name="step-4---assign-office-licenses-to-users"></a>Passaggio 4: Assegnare licenze di Office agli utenti

Se non è stato ancora fatto, assegnare licenze a qualsiasi utente dell'organizzazione che ha bisogno di installare Office, vedere [assegnare licenze agli utenti in Microsoft 365 for business](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Passaggio 5: Installare Office

Dopo aver verificato che gli utenti che si desidera aggiornare dispongono di licenze, il passaggio finale consiste nell'installare Office, vedere [scaricare e installare o reinstallare Office nel PC o nel Mac](https://support.office.com/article/4414eaaf-0478-48be-9c42-23adc4716658.aspx).
  
> [!TIP]
> Se non si desidera che gli utenti installino Office autonomamente, vedere [manage software Download Settings in office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365). È possibile utilizzare lo [strumento di distribuzione di Office](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) per scaricare il software di Office nella rete locale e quindi distribuire Office utilizzando il metodo di distribuzione del software utilizzato in genere.
