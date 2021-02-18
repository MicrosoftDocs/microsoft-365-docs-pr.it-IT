---
title: Proteggere caselle di posta elettronica locali in Cina con Exchange Online Protection autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori in Cina che utilizzano Office 365 gestito da 21Vianet possono imparare a usare Exchange Online Protection (EOP) autonomo per proteggere le cassette postali locali.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f4f27fa9237d76422e936555c9872b83655d7b6b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289426"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Proteggere caselle di posta elettronica locali in Cina con Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Questo articolo si applica solo a Office 365 gestito da 21Vianet in Cina.

Anche se si prevede di ospitare alcune o tutte le cassette postali in locale, è comunque possibile proteggere le cassette postali con Exchange Online Protection (EOP). Per configurare i connettori, l'account deve essere un amministratore globale o un amministratore aziendale di Exchange (gruppo di ruoli Gestione organizzazione). Per informazioni sulle relazioni tra le autorizzazioni di Office 365 e le autorizzazioni di Exchange, vedere Assegnazione di ruoli di amministratore [in Office 365 gestito da 21Vianet.](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet&preserve-view=true) Se tutte le cassette postali di Exchange sono locali, seguire questa procedura per configurare il servizio EOP.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Passaggio 1: Usare l'interfaccia di amministrazione di Microsoft 365 per aggiungere e verificare il dominio

1. Nell'interfaccia di amministrazione di Microsoft 365 passare a Configurazione per aggiungere il dominio al servizio.

2. Seguire i passaggi nel portale per aggiungere i record DNS applicabili al provider di hosting DNS per verificare la proprietà del dominio.

> [!TIP]
> Aggiungere il dominio e gli utenti a Office 365 gestito da [21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet&preserve-view=true) e creare record DNS per [Office 365](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet&preserve-view=true) quando si gestiscono i record DNS sono risorse utili per fare riferimento quando si aggiunge il dominio al servizio e si configura DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Passaggio 2: Aggiungere destinatari e configurare il tipo di dominio

Prima di configurare il flusso di posta da e verso il servizio EOP, si consiglia di aggiungere i destinatari al servizio. Esistono diversi modi in cui è possibile farlo, come documentato in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md). Inoltre, se si desidera abilitare il blocco Edge basato su directory (DBEB) per migliorare la verifica dei destinatari all'interno del servizio dopo averli aggiunti, è necessario impostare il tipo di dominio su Autorevole. Per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to reject messages sent to invalid recipients.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Passaggio 3: Configurazione del flusso di posta tramite EAC

Creare i connettori nell'Interfaccia di amministrazione di Exchange (EAC) per abilitare il flusso di posta tra EOP e i server di posta locali. Per istruzioni dettagliate, vedere [Configurare il flusso di posta tramite i connettori in Office 365.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)

 Come verificare se l'operazione ha avuto esito positivo

 Vedere [Testare il flusso di posta convalidando i connettori di Office 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Passaggio 4: Consentire alla porta in ingresso 25 accesso SMTP

Dopo aver configurato i connettori, attendere 72 ore per consentire la propagazione degli aggiornamenti dei record DNS. In seguito, limitare il traffico SMTP della porta in ingresso 25 sul firewall o sui server di posta elettronica in modo da accettare la posta solo dai datacenter EOP, in particolare dagli indirizzi IP elencati negli URL e negli intervalli di indirizzi IP per [Office 365.](../../enterprise/managing-office-365-endpoints.md) In tal modo si protegge l'ambiente locale limitando l'ambito dei messaggi in arrivo che è possibile ricevere. Inoltre, se sul server di posta sono state definite impostazioni per il controllo degli indirizzi IP a cui è consentita la connessione per l'inoltro della posta, è necessario aggiornare anche tali impostazioni.

> [!TIP]
> Configurare le impostazioni sul server SMTP con una tempo di timeout di connessione pari a 60 secondi. Questa impostazione è accettabile nella maggior parte delle situazioni perché consente un certo ritardo, ad esempio in caso di messaggi inviati con allegati di grandi dimensioni.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Passaggio 5: Verificare che la posta indesiderata sia instradata alla cartella Posta indesiderata di ogni utente

Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. I passaggi sono disponibili in Configurare EOP autonomo per recapitare la posta indesiderata alla [cartella Posta indesiderata negli ambienti ibridi.](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md) Se non si desidera spostare i messaggi nella cartella Posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione dalla posta indesiderata (noti anche come criteri di filtro dei contenuti). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Passaggio 6: Usare l'interfaccia di amministrazione di Microsoft 365 per puntare il record MX a EOP

Seguire i passaggi di configurazione del dominio di Office 365 per aggiornare il record MX per il dominio, in modo che la posta elettronica in ingresso passi attraverso EOP. Per ulteriori informazioni, è possibile fare di nuovo riferimento [a Creare record DNS per Office 365 quando si gestiscono i record DNS.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider?view=o365-21vianet&preserve-view=true)

Come verificare se l'operazione ha avuto esito positivo

 Vedere [Testare il flusso di posta convalidando i connettori di Office 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)

A questo punto, l'erogazione del servizio è stata verificata per un connettore locale in uscita adeguatamente configurato ed è stato appurato che il record MX punta a EOP. Ora è possibile scegliere di eseguire ulteriori test per verificare che un messaggio di posta elettronica sia recapitato correttamente dal servizio all'ambiente locale:

- Nell'Analizzatore connettività remota, fare clic sulla scheda **Office 365**, quindi eseguire il test **Test posta elettronica SMTP** situato sotto **Test per posta elettronica Internet**.

- Inviare un messaggio di posta elettronica da un account di posta elettronica basato su Web a un destinatario di posta dell'organizzazione il cui dominio corrisponde al dominio aggiunto al servizio. Verificare il recapito del messaggio alla cassetta postale locale utilizzando Microsoft Outlook o un altro client di posta elettronica,

- Per eseguire un test della posta elettronica in uscita, è possibile inviare un messaggio di posta elettronica da un utente nell'organizzazione a un account di posta elettronica basato su Web e verificare che sia stato ricevuto.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Meno comune: configurazione ibrida con cassette postali locali e nel cloud

Se si dispone di cassette postali di Exchange in locale e di una o più cassette postali nel cloud in Exchange Online, si dispone di una *configurazione* ibrida. In una configurazione ibrida, funzionalità quali la condivisione del calendario sulla disponibilità e il routing della posta funzionano insieme negli ambienti locali e cloud. Potrebbe essere presente una configurazione ibrida durante la transizione delle cassette postali a Exchange Online. Un ambiente ibrido è configurato in modo diverso rispetto alla protezione autonoma di EOP.

È possibile scegliere uno scenario ibrido per sfruttare la posta elettronica basata sul cloud per la maggior parte dei dipendenti. È possibile eseguire questa operazione ospitando anche alcune cassette postali in locale; ad esempio per il reparto legale.

Una configurazione ibrida può essere complessa, ma presenta numerosi vantaggi. Per ulteriori informazioni sulla configurazione di scenari ibridi con Exchange, [vedere Exchange Server distribuzioni ibride.](https://docs.microsoft.com/Exchange/exchange-hybrid)
