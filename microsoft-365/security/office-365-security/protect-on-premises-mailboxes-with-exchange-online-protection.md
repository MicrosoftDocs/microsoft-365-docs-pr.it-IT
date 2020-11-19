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
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori in Cina che utilizzano Office 365 gestito da 21Vianet possono imparare a usare standalone Exchange Online Protection (EOP) per proteggere le cassette postali locali.
ms.openlocfilehash: 9b91abec8d258df2b549cee1d538d2f65d2974ab
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356896"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>Proteggere caselle di posta elettronica locali in Cina con Exchange Online Protection autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Questo articolo si applica solo a Office 365 gestito da 21Vianet in Cina.

Anche se si prevede di ospitare alcune o tutte le cassette postali locali, è comunque possibile proteggere le cassette postali con Exchange Online Protection (EOP). Per configurare i connettori, è necessario che l'account sia un amministratore globale o che sia membro di Exchange Company Administrator (gruppo di ruoli di gestione dell'organizzazione). Per informazioni su come le autorizzazioni di Office 365 riguardano le autorizzazioni di Exchange, vedere [assegnazione di ruoli di amministratore in Office 365 gestito da 21ViaNet](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet&preserve-view=true). Se tutte le cassette postali di Exchange sono in locale, attenersi alla procedura seguente per configurare il servizio EOP.

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Passaggio 1: utilizzare l'interfaccia di amministrazione di Microsoft 365 per aggiungere e verificare il dominio

1. Nell'interfaccia di amministrazione di Microsoft 365, passare a installazione per aggiungere il dominio al servizio.

2. Seguire la procedura descritta nel portale per aggiungere i record DNS applicabili al provider di hosting DNS per verificare la proprietà del dominio.

> [!TIP]
> [Aggiungere il dominio e gli utenti a office 365 gestito da 21ViaNet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet&preserve-view=true) e [creare record dns per Office 365 quando si gestiscono i record DNS](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet&preserve-view=true) sono risorse utili da fare riferimento quando si aggiunge il dominio al servizio e si configura DNS.

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>Passaggio 2: aggiungere destinatari e configurare il tipo di dominio

Prima di configurare il flusso di posta da e verso il servizio EOP, si consiglia di aggiungere i destinatari al servizio. Esistono diversi modi in cui è possibile farlo, come documentato in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md). Inoltre, se si desidera abilitare il blocco Edge basato su directory (DBEB) per migliorare la verifica dei destinatari all'interno del servizio dopo averli aggiunti, è necessario impostare il tipo di dominio su Autorevole. Per ulteriori informazioni su DBEB, vedere [use directory based Edge Blocking to Reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Passaggio 3: Configurazione del flusso di posta tramite EAC

Creare i connettori nell'Interfaccia di amministrazione di Exchange (EAC) per abilitare il flusso di posta tra EOP e i server di posta locali. Per istruzioni dettagliate, vedere [Configure Mail Flow using Connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

 Come verificare se l'operazione ha avuto esito positivo

 Vedere [test Mail Flow convalidando i connettori di Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Passaggio 4: Consentire alla porta in ingresso 25 accesso SMTP

Dopo aver configurato i connettori, attendere 72 ore per consentire la propagazione degli aggiornamenti dei record DNS. In questo modo, limitare il traffico SMTP in ingresso 25 nel firewall o nei server di posta elettronica per accettare la posta solo dai datacenter di EOP, in particolare dagli indirizzi IP elencati in [URL e intervalli di indirizzi IP per Office 365](https://docs.microsoft.com/microsoft-365/enterprise/managing-office-365-endpoints). In tal modo si protegge l'ambiente locale limitando l'ambito dei messaggi in arrivo che è possibile ricevere. Inoltre, se sul server di posta sono state definite impostazioni per il controllo degli indirizzi IP a cui è consentita la connessione per l'inoltro della posta, è necessario aggiornare anche tali impostazioni.

> [!TIP]
> Configurare le impostazioni sul server SMTP con una tempo di timeout di connessione pari a 60 secondi. Questa impostazione è accettabile nella maggior parte delle situazioni perché consente un certo ritardo, ad esempio in caso di messaggi inviati con allegati di grandi dimensioni.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Passaggio 5: verificare che la posta indesiderata venga instradata alla cartella posta indesiderata di ogni utente

Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. I passaggi vengono forniti in [Configure standalone EOP per recapitare la posta indesiderata alla cartella posta indesiderata in ambienti ibridi](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Se non si desidera spostare i messaggi nella cartella posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione da posta indesiderata (noti anche come criteri di filtro dei contenuti). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Passaggio 6: utilizzare l'interfaccia di amministrazione di Microsoft 365 per puntare il record MX a EOP

Seguire la procedura di configurazione del dominio di Office 365 per aggiornare il record MX per il dominio, in modo che il flusso di posta elettronica in ingresso attraversi EOP. Per ulteriori informazioni, è possibile fare riferimento a [create DNS Records for Office 365 quando si gestiscono i record DNS](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

Come verificare se l'operazione ha avuto esito positivo

 Vedere [test Mail Flow convalidando i connettori di Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

A questo punto, l'erogazione del servizio è stata verificata per un connettore locale in uscita adeguatamente configurato ed è stato appurato che il record MX punta a EOP. Ora è possibile scegliere di eseguire ulteriori test per verificare che un messaggio di posta elettronica sia recapitato correttamente dal servizio all'ambiente locale:

- Nell'Analizzatore connettività remota, fare clic sulla scheda **Office 365**, quindi eseguire il test **Test posta elettronica SMTP** situato sotto **Test per posta elettronica Internet**.

- Inviare un messaggio di posta elettronica da un account di posta elettronica basato su Web a un destinatario di posta dell'organizzazione il cui dominio corrisponde al dominio aggiunto al servizio. Verificare il recapito del messaggio alla cassetta postale locale utilizzando Microsoft Outlook o un altro client di posta elettronica,

- Per eseguire un test della posta elettronica in uscita, è possibile inviare un messaggio di posta elettronica da un utente nell'organizzazione a un account di posta elettronica basato su Web e verificare che sia stato ricevuto.

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>Meno comuni: una configurazione ibrida con le cassette postali locali e nel cloud

Se si dispone di cassette postali di Exchange in locale e di una o più cassette postali nel cloud in Exchange Online, si dispone di una configurazione *ibrida* . In una configurazione ibrida, funzionalità come la condivisione del calendario delle informazioni sulla disponibilità e il routing della posta funzionano insieme negli ambienti locali e cloud. È possibile che si disponga di una configurazione ibrida sul posto durante la transizione delle cassette postali a Exchange Online. Un ambiente ibrido è configurato in modo diverso rispetto alla protezione autonoma di EOP.

È possibile scegliere uno scenario ibrido per sfruttare la posta elettronica basata sul cloud per la maggior parte dei dipendenti. È possibile eseguire questa operazione anche ospitando alcune cassette postali in locale. ad esempio, per il reparto legale.

Una configurazione ibrida può essere complessa, ma presenta numerosi vantaggi. Per ulteriori informazioni sulla configurazione di scenari ibridi con Exchange, vedere [distribuzioni ibride di Exchange Server](https://docs.microsoft.com/Exchange/exchange-hybrid).
