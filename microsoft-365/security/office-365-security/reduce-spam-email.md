---
title: Come ridurre la posta indesiderata in Office 365
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 06/07/2018
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.assetid: 07824c51-2c45-4005-8596-03c0d7c4ff2a
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_IP
description: Informazioni su vari modi per ridurre la posta indesiderata in Office 365.
ms.openlocfilehash: 5d915759766b122457553a24d2f92f67c3093b34
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031821"
---
# <a name="how-to-reduce-spam-email-in-office-365"></a>Come ridurre la posta indesiderata in Office 365

 **Si riceve troppa posta indesiderata in Office 365? Ecco cosa fare.**
  
È consigliabile segnalare i messaggi falsi positivi [usando il componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) per aiutare a migliorare i filtri. È anche possibile inviare il messaggio usando [Esplora richieste](admin-submission.md).

> [!TIP]
> Se si ritiene che il messaggio è indesiderato e si trova nella cartella Posta indesiderata, questo non costituisce un problema. Se non si vuole visualizzarlo nella cassetta postale, è consigliabile modificare i criteri di filtro posta indesiderata per mettere in quarantena il messaggio. Per altre informazioni su come mettere in quarantena un messaggio, vedere [Mettere in quarantena i messaggi di posta elettronica in Office 365](quarantine-email-messages.md).

## <a name="fixing-allowed-spam"></a>Correzione della posta indesiderata consentita

Capita spesso che i clienti ricevano posta indesiderata nella Posta in arrivo a causa di configurazioni errate. Le configurazioni errate più comuni riguardano la configurazione dei domini in una regola di flusso di posta (nota anche come regola di trasporto) per ignorare i filtri oppure l'inserimento di domini nell'elenco di mittenti consentiti/attendibili. Questa configurazione non è valida perché questi messaggi non sono soggetti al filtro posta indesiderata e diversamente avrebbero potuto essere rilevati. Per questo motivo, la creazione di [elenchi di mittenti attendibili](https://docs.microsoft.com/microsoft-365/security/office-365-security/create-safe-sender-lists-in-office-365) deve essere considerata come soluzione temporanea.  

## <a name="solutions-to-other-common-causes-of-getting-too-much-spam"></a>Soluzioni ad altre cause comuni della quantità elevata di posta indesiderata

Per proteggersi dalla ricezione di troppa posta indesiderata, Exchange Online Protection (EOP) chiede agli amministratori di completare alcune operazioni. Se non si è un amministratore del proprio tenant di Office 365 e si riceve troppa posta indesiderata, eseguire tali operazioni con l'amministratore. In caso contrario, è possibile passare alla sezione per gli utenti.
  
### <a name="for-admins"></a>Per gli amministratori

- **Impostare i record DNS in modo che puntino a Office 365** Affinché EOP fornisca la protezione ottimale, i record DNS di Mail Exchanger (MX) per tutti i domini devono puntare esclusivamente a Office 365. Vedere [Creare i record DNS per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/b0f3fdca-8a80-4e8e-9ef3-61e8a2a9ab23).
    
- **Attivare la regola della posta indesiderata in tutte le cassette postali** Per impostazione predefinita, l'operazione del filtro protezione da posta indesiderata è impostata su **Sposta messaggio nella cartella di posta indesiderata**. Se si tratta dell'azione del criterio di posta indesiderata corrente, allora in ogni cassetta postale [deve anche essere attivata la regola della posta indesiderata](https://support.office.com/article/overview-of-the-junk-email-filter-5ae3ea8e-cf41-4fa0-b02a-3b96e21de089). Per verificarlo, è possibile eseguire il cmdlet Get-MailboxJunkEmailConfiguration su una o più cassette postali. Ad esempio, è possibile verificare tale condizione in tutte le cassette postali eseguendo: Get-MailboxJunkEmailConfiguration -Identity \* | Where {$_.Enabled -eq $false}
    
    Quando si visualizza l'output, la proprietà Enable deve essere impostata su True. Se è impostata su False, è possibile eseguire Set-MailboxJunkEmailConfiguration per impostarla su True come indicato di seguito: Set-MailboxJunkEmailConfiguration -Identity $values.UserPrincipalName -Enabled $true.
    
- **Creare regole del flusso di posta nel server Exchange locale** Se si usa Exchange Online Protection, ma le cassette postali si trovano nel server Exchange locale, è necessario creare due regole del flusso di posta nel server Exchange locale. Vedere le [istruzioni relative solo a Exchange Online Protection](https://docs.microsoft.com/previous-versions/exchange-server/exchange-150/jj900470(v=exchg.150)).
    
- **Contrassegnare la posta elettronica inviata in massa come posta indesiderata** La posta elettronica inviata in massa è costituita da messaggi di posta elettronica per cui gli utenti hanno effettuato la registrazione, ma che potrebbero essere comunque indesiderati. Nell'intestazione del messaggio individuare la proprietà BCL (Bulk Confidence Level) nell'intestazione X-Microsoft-Antispam. Se il valore di BCL è inferiore alla soglia impostata nel filtro protezione da posta indesiderata, è consigliabile modificare la soglia invece di contrassegnare questi tipi di posta elettronica inviata in massa come posta indesiderata. Le tolleranze e le preferenze relative alla gestione della [posta elettronica inviata in massa](https://docs.microsoft.com/office365/SecurityCompliance/bulk-complaint-level-values) variano da utente a utente. È possibile creare regole o criteri diversi in base alle preferenze degli utenti. 
    
- **Bloccare immediatamente un mittente** Se è necessario bloccare immediatamente un mittente, è possibile usare l'indirizzo di posta elettronica, il dominio o l'indirizzo IP. Vedere [Creare elenchi di mittenti bloccati in Office 365](create-block-sender-lists-in-office-365.md). Una voce in un elenco di elementi attendibili dell'utente finale può sostituire un blocco impostato dall'amministratore.
    
- **Attivare il componente aggiuntivo Segnala messaggio per gli utenti** È consigliabile [abilitare il componente aggiuntivo Segnala messaggio per gli utenti](enable-the-report-message-add-in.md).

- **Usare [Esplora richieste](admin-submission.md)** Gli amministratori possono ora inviare messaggi di posta elettronica con ID messaggio di rete o file, URL e file per l'analisi di Microsoft in Office 365. Un amministratore può anche visualizzare il feedback inviato dagli utenti e usare qualsiasi schema per modificare le impostazioni che potrebbero causare problemi.

- **Abilitare [DKIM](use-dkim-to-validate-outbound-email.md)** per firmare tutti i messaggi in uscita e migliorare la sicurezza del dominio e del tenant.
 > [!TIP]
> Dopo aver abilitato DKIM è necessario abilitare [DMARC](use-dkim-to-validate-outbound-email.md) perché questo record verrà convalidato se DKIM e SPF funzionano correttamente e, in generale, i messaggi di posta elettronica di spoofing non includono alcuna firma in quanto O365 gestisce la chiave simmetrica pubblica e privata.
    
### <a name="for-users"></a>Per gli utenti

- **Abilitare la regola della posta indesiderata e controllare l'elenco elementi attendibili** Verificare he la regola di azione della posta indesiderata sia attiva e che il mittente o il dominio del mittente non sia configurato per ignorare l'elenco di elementi attendibili personale. Il modo migliore per accedere a queste impostazioni è da [Blocca o consenti (impostazioni di posta indesiderata)](https://support.office.com/article/48c9f6f7-2309-4f95-9a4d-de987e880e46). Qui, è anche possibile bloccare l'indirizzo di posta elettronica o il dominio del mittente.
    
- **Segnalare la posta indesiderata a Microsoft** Per segnalare messaggi di posta indesiderata a Microsoft, usare il [componente aggiuntivo Segnala messaggio](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).
       
- **Annullare l'iscrizione alla posta elettronica inviata in massa** Se il messaggio proviene da indirizzo alla quale ci si è iscritti (newsletter, prodotti e così via) e contiene un collegamento per annullare iscrizione di una fonte attendibile, è consigliabile semplicemente annullare l'iscrizione. Office 365 generalmente non gestisce questi messaggi come posta indesiderata. È anche possibile bloccare il mittente oppure rivolgersi all'amministratore per apportare una modifica affinché tutta la posta inviata in massa venga considerata posta indesiderata.
