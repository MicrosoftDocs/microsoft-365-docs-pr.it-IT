---
title: 'Passaggio 6: configurare la crittografia della posta elettronica'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprendere e configurare la gestione degli accessi con privilegi per Office 365.
ms.openlocfilehash: 7747f5a0905a9477e9d3fd17b00eae740d76f640
ms.sourcegitcommit: 78fa107271252d902e600196a75cfa746bca73e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37050297"
---
# <a name="step-6-configure-email-encryption"></a>Passaggio 6: configurare la crittografia della posta elettronica

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Sono disponibili tre tipi di crittografia della posta elettronica in Microsoft 365.

|||
|:-------|:-----|
| Crittografia messaggi di Office (OME) | Crittografia per la posta elettronica di Exchange Online inviata all'esterno dell'organizzazione. |
| Information Rights Management (IRM) | Crittografia e autorizzazioni che viaggiano con il messaggio di posta elettronica. |
| Secure/Multipurpose Internet Mail Extensions (S/MIME) | Protezione della posta elettronica con crittografia e firme digitali. |
|||

## <a name="office-365-message-encryption"></a>Crittografia dei messaggi di Office 365

Con OME, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra persone all'interno e all'esterno dell'organizzazione. OME è compatibile con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica. La crittografia dei messaggi di posta elettronica aiuta a garantire che solo i destinatari previsti possano visualizzare il messaggio.

![Crittografia OME dei messaggi di posta elettronica](./media/infoprotect-email-encryption/ome-encryption.png)

Si configurano le regole di trasporto che definiscono le condizioni per la crittografia. Quando un utente invia un messaggio che corrisponde a una regola, la crittografia viene applicata automaticamente.

Per visualizzare i messaggi crittografati, i destinatari possono ottenere un codice di accesso una tantum, accedere con un account Microsoft o accedere con un account aziendale o dell'Istituto di istruzione associato a Microsoft 365. I destinatari possono inoltre inviare risposte crittografate. Non è necessario che la propria sottoscrizione Microsoft 365 venga visualizzata per visualizzare i messaggi crittografati o inviare risposte crittografate.

Per ulteriori informazioni, vedere [Crittografia dei messaggi di Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).

## <a name="irm"></a>IRM

IRM in Microsoft 365 consente di proteggere le informazioni con la crittografia aggiuntiva e applicando un criterio intelligente che specifichi chi ha accesso a ciò che può fare. Per i messaggi di posta elettronica, è possibile utilizzare IRM per la crittografia e applicare restrizioni di utilizzo. Ad esempio, è possibile specificare che alcuni destinatari hanno tutte le capacità di gestire il messaggio di posta elettronica e alcuni utenti non hanno la possibilità di stampare o inoltrare il messaggio di posta elettronica. 

I criteri IRM sono configurati all'interno di Microsoft 365 e possono essere applicati ai documenti in SharePoint Online e nei messaggi di posta elettronica. Un messaggio di posta elettronica protetto da IRM include le impostazioni dei criteri applicate e viaggia con esso. 

![Protezione IRM dei messaggi di posta elettronica](./media/infoprotect-email-encryption/irm-protection.png)

Quando il destinatario apre la posta elettronica con il criterio incluso, le impostazioni dei criteri vengono utilizzate per decrittografare il messaggio e determinare cosa può fare il destinatario. 

Per ulteriori informazioni, vedere [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).

## <a name="smime"></a>S/MIME

S/MIME è una soluzione di protezione basata sulla posta elettronica basata su certificato digitale che consente di crittografare e firmare digitalmente un messaggio. La crittografia dei messaggi consente di garantire che solo il destinatario previsto riesca ad aprire e leggere il messaggio. Una firma digitale consente al destinatario di convalidare l'identità del mittente e di determinare che solo il mittente potrebbe averlo inviato.

![Protezione S/MIME dei messaggi di posta elettronica](./media/infoprotect-email-encryption/smime-protection.png)

S/MIME può essere utilizzato per la posta elettronica ad altre cassette postali nell'abbonamento a Microsoft 365 o a utenti esterni.
Sia la crittografia dei messaggi che le firme digitali sono rese possibili mediante l'utilizzo di certificati digitali che contengono le chiavi pubbliche e private per la crittografia o la decrittografia dei messaggi e la creazione e la verifica delle firme digitali.
Per utilizzare S/MIME, è necessario disporre delle chiavi pubbliche per ogni destinatario. I destinatari mantengono le proprie chiavi private, che devono rimanere sicure. Se la chiave privata è compromessa, è necessario ottenere un nuovo certificato digitale e ridistribuire le chiavi pubbliche a tutti i potenziali mittenti.

Per ulteriori informazioni, vedere [S/MIME per la firma e la crittografia dei messaggi](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).


Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step6) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)|[Configurare la gestione degli accessi con privilegi per Office 365](infoprotect-configure-privileged-access-management.md)|
