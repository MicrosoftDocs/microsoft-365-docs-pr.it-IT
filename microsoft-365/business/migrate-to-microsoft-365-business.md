---
title: Eseguire l'aggiornamento a Microsoft 365 business da Office 365 Business Premium
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Passaggi che aggiornano la propria azienda da Office 365 Business Premium a Microsoft 365 business.
ms.openlocfilehash: 61da9148ccb87654aa2391ff90c4f086a4cbbe24
ms.sourcegitcommit: 3c296126ba69a32af07e339f2f1eacdd8e5b878e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "41120142"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a>Eseguire l'aggiornamento a Microsoft 365 business da Office 365 Business Premium

Se si dispone di un [abbonamento a office 365 per le aziende](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), ad esempio Office 365 Business Premium, è possibile eseguire facilmente l'aggiornamento a Microsoft 365 business. Eseguire l'aggiornamento a Microsoft 365 business se si desidera aggiungere: 
- Windows 10 Pro (per i computer che eseguono Windows 8 o versioni successive)
- Controlli semplici che gestiscono i dati business nei dispositivi
- Funzionalità di sicurezza avanzate.
Per ulteriori informazioni su Microsoft 365 business, vedere [Microsoft.com](https://www.microsoft.com/microsoft-365/business)

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a>Qual è la differenza tra Office 365 Business Premium e Microsoft 365 business?
È stato aggiunto un confronto affiancato di questi due piani alla [Descrizione del servizio Microsoft 365 business](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description). 

## <a name="before-you-get-started"></a>Prima di iniziare

- **Quando si sceglie di eseguire l'aggiornamento?** L'aggiornamento è la scelta giusta quando si desidera aggiornare **tutti gli utenti** assegnati a un singolo piano. Quando si sceglie l'opzione di aggiornamento, tutti i piani di utenti vengono passati a un altro piano contemporaneamente. Se non si desidera aggiornare tutti gli utenti assegnati a un singolo piano, acquistare le licenze per il nuovo piano (in questo caso Microsoft 365 business) e [assegnare tali licenze singolarmente](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) a ogni utente che si desidera aggiornare. 
- **Alcuni componenti aggiuntivi potrebbero impedire l'aggiornamento** Se si tenta di avviare un aggiornamento e si dispone di un componente aggiuntivo che impedisce di continuare, è possibile rimuovere il componente aggiuntivo e quindi aggiungerlo in un secondo momento, se necessario. 
- **Se il piano è stato prepagato** Non esiste un percorso di aggiornamento semplice per i piani prepagati. È possibile sapere se si dispone di un piano prepagato perché si configura il piano utilizzando un ID prodotto che potrebbe essere stato acquistato in un archivio. Contattare un partner, accedere a Microsoft Store oppure attendere che il piano prepagato SCADA per passare a un nuovo piano.

## <a name="upgrade-to-microsoft-365-business"></a>Eseguire l'aggiornamento a Microsoft 365 business
Acquistare le licenze attenendosi alla procedura seguente nella [nuova](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)interfaccia di amministrazione:
1. Accedere all'interfaccia di amministrazione all' <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>indirizzo.
2. Passare al riquadro di spostamento e selezionare prodotti di **fatturazione** \> **& Servizi**. Individuare la sottoscrizione di Office 365 e selezionarla per visualizzare i dettagli. 

    ![Nello screenshot viene mostrato come individuare e selezionare l'abbonamento nell'interfaccia di amministrazione.](media/FindYourSubscription.png)

3. Nella pagina successiva, selezionare **Aggiorna**. 

      ![Nello screenshot viene mostrato dove selezionare l'aggiornamento nell'interfaccia di amministrazione.](media/SelectUpgrade.png)

  > [!NOTE]
  > Se viene visualizzato un messaggio che indica che **l'aggiornamento dell'abbonamento non è supportato con la gestione delle licenze basate su gruppo in Azure Active Directory**, è possibile ignorare questa operazione a meno che non si disponga di un'organizzazione di grandi dimensioni. Le organizzazioni che hanno selezionato questa opzione sapranno di usare le licenze basate su gruppo.

4. Successivamente, è possibile visualizzare un elenco di piani di Office a cui è possibile eseguire l'aggiornamento. In questo caso, trovare il piano aziendale Microsoft 365. È possibile scorrere verso il basso se si desidera visualizzare tutte le app e i servizi di Office inclusi in questo piano. In **microsoft 365 business**, selezionare **upgrade** to Add Microsoft 365 business to your cart.
5. Nel carrello:
    1. Verranno incluse automaticamente le licenze per tutti gli utenti correnti. Se sono necessarie più o meno licenze, è necessario [acquistare e assegnare tali licenze singolarmente](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).  
    2. È possibile modificare la modalità di pagamento: mensile o annuale. Selezionare il menu a discesa per scegliere.
6. Selezionare **Vai a checkout in** cui verrà visualizzato un riepilogo dell'acquisto, incluso il metodo di pagamento per questo account. È anche possibile aggiungere un codice promozionale qui se si dispone di uno.
7. Selezionare l' **ordine** di esecuzione per completare l'acquisto.
Microsoft impiega alcuni minuti per configurare i nuovi piani di servizio. Per verificare lo stato di avanzamento, selezionare **Controlla stato aggiornamento**. 
1. Una volta che il piano è pronto, potrebbe essere necessario completare alcuni passaggi di installazione aggiuntivi nell'interfaccia di amministrazione. Nel riquadro di spostamento, selezionare **Home** per completare i passaggi di installazione aggiuntivi.

> [!NOTE]
> Si riceverà un rimborso proporzionale per le licenze di Office 365 che non è più necessario. Il conto corrente bancario o la carta di credito viene addebitata circa due giorni dopo la configurazione del nuovo piano.
  
## <a name="protect-user-devices-and-files"></a>Protezione dei dispositivi e dei file utente

Ora che sono state assegnate licenze aziendali Microsoft 365, completare i passaggi per avviare la protezione di dispositivi e file. Verranno utilizzate alcune nuove opzioni incluse nel riquadro di spostamento dell'interfaccia di amministrazione.
  
1. Nell'interfaccia di amministrazione, nel riquadro di spostamento, passare ai **** \> **criteri**dei dispositivi.
    
2. Nella pagina **Criteri dispositivo** selezionare **Aggiungi**.
    
3. Nel riquadro **Aggiungi criterio** assegnare un nome al criterio (ad esempio, proteggere i file di lavoro) e quindi scegliere un **tipo di criterio** nell'elenco a discesa. 
    
    È possibile configurare i criteri di applicazione per la protezione dei file su dispositivi Android e iPhone, oltre a Windows 10, ed è possibile configurare i criteri di configurazione del dispositivo per i dispositivi Windows 10 di proprietà dell'azienda. Per informazioni dettagliate, vedere i seguenti collegamenti:
    
  - [Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS](app-protection-settings-for-android-and-ios.md)
    
  - [Configurare le impostazioni di protezione delle app per i dispositivi Windows 10](protection-settings-for-windows-10-devices.md)
    
  - [Impostazione delle impostazioni di protezione dei dispositivi per PC Windows 10](protection-settings-for-windows-10-pcs.md)
    
  
4. Dopo aver configurato i criteri, gli utenti e i dipendenti possono configurare i dispositivi:
    
  - Se i dispositivi Windows non utilizzano già l'aggiornamento di Windows Pro Creator, è necessario aggiornarli [a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
    
  - Vedere [configurare i dispositivi Windows per gli utenti di Microsoft 365 business](set-up-windows-devices.md) per i passaggi per i dispositivi Windows. 
    
  - Vedere [configurare i dispositivi mobili per gli utenti di Microsoft 365 business](set-up-mobile-devices.md) per i passaggi per i telefoni Android e iPhone. 
