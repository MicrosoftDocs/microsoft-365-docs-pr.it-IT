---
title: Proteggere le cassette postali locali con Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/1/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: Anche se si prevede di ospitare alcune o tutte le cassette postali locali, è comunque possibile proteggere le cassette postali con Exchange Online Protection (EOP). Per configurare i connettori, l'account deve essere un amministratore globale di Office 365 o un amministratore aziendale di Exchange (gruppo dei ruoli di gestione dell'organizzazione). Per informazioni su come le autorizzazioni di Office 365 riguardano le autorizzazioni di Exchange, vedere Assegnazione di ruoli di amministratore in Office 365 gestito da 21Vianet. Se tutte le cassette postali di Exchange sono in locale, attenersi alla procedura seguente per configurare il servizio EOP.
ms.openlocfilehash: 787c01ff7d06943b51916675b9e30dc3f020d5e1
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084601"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Proteggere le cassette postali locali con Exchange Online Protection

> [!NOTE]
> Questo articolo si applica solo a Office 365 gestito da 21Vianet in Cina. 
  
Anche se si prevede di ospitare alcune o tutte le cassette postali locali, è comunque possibile proteggere le cassette postali con Exchange Online Protection (EOP). Per configurare i connettori, l'account deve essere un amministratore globale di Office 365 o un amministratore aziendale di Exchange (gruppo dei ruoli di gestione dell'organizzazione). Per informazioni su come le autorizzazioni di Office 365 riguardano le autorizzazioni di Exchange, vedere [assegnazione di ruoli di amministratore in Office 365 gestito da 21ViaNet](https://support.office.com/article/d58b8089-cbfd-41ec-b64c-9cfcbef495ac). Se tutte le cassette postali di Exchange sono in locale, attenersi alla procedura seguente per configurare il servizio EOP. 
  
## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Passaggio 1: utilizzare l'interfaccia di amministrazione di Microsoft 365 per aggiungere e verificare il dominio

1. Nell'interfaccia di amministrazione di Microsoft 365, passare a installazione per aggiungere il dominio al servizio.
    
2.  Seguire la procedura descritta nel portale per aggiungere i record DNS applicabili al provider di hosting DNS per verificare la proprietà del dominio. 
    
> [!TIP]
> [Aggiungere il dominio e gli utenti a office 365 gestito da 21ViaNet](https://support.office.com/article/1cd4839b-d051-46b8-ab9b-bc7752024e78) e [creare record dns per Office 365 quando si gestiscono i record DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b) sono risorse utili da fare riferimento quando si aggiunge il dominio al servizio e si configura DNS. 
  
### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Passaggio 2: aggiungere destinatari e configurare il tipo di dominio

Prima di configurare il flusso di posta da e verso il servizio EOP, si consiglia di aggiungere i destinatari al servizio. Esistono diversi modi in cui è possibile farlo, come documentato in [Gestione utenti di posta in EOP](https://go.microsoft.com/fwlink/?LinkId=506782). Inoltre, se si desidera abilitare il blocco Edge basato su directory (DBEB) per migliorare la verifica dei destinatari all'interno del servizio dopo averli aggiunti, è necessario impostare il tipo di dominio su Autorevole. Per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://go.microsoft.com/fwlink/?LinkId=506781).
  
## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Passaggio 3: Configurazione del flusso di posta tramite EAC

Creare i connettori nell'Interfaccia di amministrazione di Exchange (EAC) per abilitare il flusso di posta tra EOP e i server di posta locali. Per istruzioni dettagliate, vedere [creare connettori necessari per configurare il flusso di posta elettronica di base tramite EOP](https://go.microsoft.com/fwlink/?LinkId=506780).
  
 Come verificare se l'operazione ha avuto esito positivo 
  
 Utilizzare Analizzatore connettività remota per eseguire un test che controlla il flusso di posta tra il servizio e l'ambiente. Per ulteriori informazioni, vedere la sezione "utilizzare l'analizzatore connettività remota per verificare il recapito della posta elettronica" in [test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784).
  
## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Passaggio 4: Consentire alla porta in ingresso 25 accesso SMTP

Dopo aver configurato i connettori, attendere 72 ore per consentire la propagazione degli aggiornamenti dei record DNS. In questo modo, limitare il traffico SMTP in ingresso 25 nel firewall o nei server di posta elettronica per accettare la posta solo dai datacenter di EOP, in particolare dagli indirizzi IP elencati in [URL e intervalli di indirizzi IP per Office 365 gestito da 21ViaNet](https://support.office.com/article/5c47c07d-f9b6-4b78-a329-bfdc1b6da7a0#__exchange_online_protection). In tal modo si protegge l'ambiente locale limitando l'ambito dei messaggi in arrivo che è possibile ricevere. Inoltre, se sul server di posta sono state definite impostazioni per il controllo degli indirizzi IP a cui è consentita la connessione per l'inoltro della posta, è necessario aggiornare anche tali impostazioni.
  
> [!TIP]
> Configurare le impostazioni sul server SMTP con una tempo di timeout di connessione pari a 60 secondi. Questa impostazione è accettabile nella maggior parte delle situazioni perché consente un certo ritardo, ad esempio in caso di messaggi inviati con allegati di grandi dimensioni. 
  
## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Passaggio 5: Utilizzare Shell per garantire che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente

Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. I passaggi vengono forniti in [modo che la posta indesiderata venga instradata alla cartella posta indesiderata di ogni utente](https://go.microsoft.com/fwlink/?LinkId=506804). Se non si intende spostare i messaggi nella cartella posta indesiderata di ciascun utente, è possibile optare per un'altra azione modificando i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configure Content Filter Policies](https://go.microsoft.com/fwlink/?LinkId=506805). 
  
## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Passaggio 6: utilizzare l'interfaccia di amministrazione di Microsoft 365 per puntare il record MX a EOP

Seguire la procedura di configurazione del dominio di Office 365 per aggiornare il record MX per il dominio, in modo che il flusso di posta elettronica in ingresso attraversi EOP. Per ulteriori informazioni, è possibile fare riferimento a [create DNS Records for Office 365 quando si gestiscono i record DNS](https://support.office.com/article/0669bf14-414d-4f51-8231-6b710ce7980b).
  
Come verificare se l'operazione ha avuto esito positivo
  
 Utilizzare l'Analizzatore connettività remota per eseguire un test che verifica il record MX. Per ulteriori informazioni, vedere la sezione "utilizzare l'analizzatore connettività remota per verificare il record MX e il connettore in uscita" in [test mail flow with the Remote Connectivity Analyzer](https://go.microsoft.com/fwlink/?LinkId=506784). 
  
A questo punto, l'erogazione del servizio è stata verificata per un connettore locale in uscita adeguatamente configurato ed è stato appurato che il record MX punta a EOP. Ora è possibile scegliere di eseguire ulteriori test per verificare che un messaggio di posta elettronica sia recapitato correttamente dal servizio all'ambiente locale:
  
- Nell'Analizzatore connettività remota, fare clic sulla scheda **Office 365**, quindi eseguire il test **Test posta elettronica SMTP** situato sotto **Test per posta elettronica Internet**.
    
- Inviare un messaggio di posta elettronica da un account di posta elettronica basato su Web a un destinatario di posta dell'organizzazione il cui dominio corrisponde al dominio aggiunto al servizio. Verificare il recapito del messaggio alla cassetta postale locale utilizzando Microsoft Outlook o un altro client di posta elettronica,
    
- Per eseguire un test della posta elettronica in uscita, è possibile inviare un messaggio di posta elettronica da un utente nell'organizzazione a un account di posta elettronica basato su Web e verificare che sia stato ricevuto.
    
## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Meno comuni: una configurazione ibrida con le cassette postali locali e nel cloud

Se si dispone di cassette postali di Exchange in locale e di una o più cassette postali nel cloud in Exchange Online, si dispone di una configurazione *ibrida* . In una configurazione ibrida, funzionalità come la condivisione del calendario delle informazioni sulla disponibilità e il routing della posta funzionano insieme negli ambienti locali e cloud. È possibile che si disponga di una configurazione ibrida sul posto durante la transizione delle cassette postali a Exchange Online. Un ambiente ibrido è configurato in modo diverso rispetto alla protezione autonoma di EOP. 
  
È possibile scegliere uno scenario ibrido per sfruttare la posta elettronica basata sul cloud per la maggior parte dei dipendenti. È possibile eseguire questa operazione anche ospitando alcune cassette postali in locale. ad esempio, per il reparto legale. 
  
Una configurazione ibrida può essere complessa, ma presenta numerosi vantaggi. Per ulteriori informazioni sulla configurazione di scenari ibridi con Exchange, vedere [Configuring Exchange Hybrid deployment features with Office 365 operated by 21ViaNet](https://support.office.com/article/26e7cc26-c980-4cc5-a082-c333de544b6d).
  

