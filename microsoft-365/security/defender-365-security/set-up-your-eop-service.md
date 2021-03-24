---
title: Configurare il servizio EOP autonomo
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: Gli amministratori possono imparare a configurare Exchange Online Protection (EOP) autonomo per proteggere gli ambienti di posta elettronica locali.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bbad39475f87be27a83edc0c27e2bbe46f8e39ac
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064474"
---
# <a name="set-up-your-standalone-eop-service"></a>Configurare il servizio EOP autonomo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
-  [Exchange Online Protection autonomo](exchange-online-protection-overview.md)

In questo argomento viene illustrato come configurare Exchange Online Protection (EOP) autonomo. Se si è arrivati qui dalla configurazione guidata dei domini di Office 365, tornare alla configurazione guidata dei domini di Office 365 se non si desidera utilizzare Exchange Online Protection. Per ulteriori informazioni su come configurare i connettori, vedere [Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> In questo argomento si presuppone che si dispone di cassette postali locali e si desidera proteggerle con EOP, noto come scenario autonomo. Se si desidera ospitare tutte le cassette postali nel cloud con Exchange Online, non è necessario completare tutti i passaggi descritti in questo articolo. Vai a [Confrontare i piani di Exchange Online](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) per iscriversi e acquistare cassette postali cloud.
>
> Se si desidera ospitare alcune cassette postali in locale e altre nel cloud, questo scenario è noto come scenario ibrido. Richiede impostazioni del flusso di posta più avanzate. [Exchange Server distribuzioni ibride](/exchange/exchange-hybrid) spiega il flusso di posta ibrido e include collegamenti a risorse che illustrano come configurarlo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento di questa attività: 1 ora

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in Exchange Online Protection. In particolare, è necessario il **ruolo Domini** remoti e accettati, assegnato  ai gruppi di ruoli **Gestione** organizzazione (amministratori globali) e Amministratore flusso di posta per impostazione predefinita. Per ulteriori informazioni, vedere [Permissions in standalone EOP](feature-permissions-in-eop.md) e [Use the EAC modify the list of members in role groups](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups).

- Se non si è iscritti a EOP, visitare [Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection) e scegliere di acquistare o provare il servizio.

- Per informazioni sui tasti di scelta rapida applicabili alle procedure descritte in questo articolo, vedere Tasti di scelta rapida per l'interfaccia di amministrazione di [Exchange in Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> Problemi? Chiedere assistenza nel forum [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE).

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Passaggio 1: Usare l'interfaccia di amministrazione di Microsoft 365 per aggiungere e verificare il dominio

1. Nell'interfaccia di amministrazione di [Microsoft 365](../../admin/admin-overview/about-the-admin-center.md)passare a **Installazione** per aggiungere il dominio al servizio.

2. Seguire la procedura di aggiunta dei record DNS applicabili al provider che ospita i DNS per verificare la proprietà del dominio.

> [!TIP]
> Aggiungere un dominio [a Office 365](../../admin/setup/add-domain.md) e Creare record DNS presso qualsiasi provider di hosting DNS per [Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) sono risorse utili per fare riferimento quando si aggiunge il dominio al servizio e si configura DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Passaggio 2: aggiunta di destinatari e abilitazione DBEB (scelta facoltativa)

Prima di configurare il flusso di posta da e verso il servizio EOP, si consiglia di aggiungere i destinatari al servizio. Esistono diversi modi in cui è possibile farlo, come documentato in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md). Inoltre, se si desidera abilitare il blocco Edge basato su directory (DBEB) per migliorare la verifica dei destinatari all'interno del servizio dopo averli aggiunti, è necessario impostare il tipo di dominio su Autorevole. Per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Passaggio 3: Configurazione del flusso di posta tramite EAC

Creare i connettori nell'Interfaccia di amministrazione di Exchange (EAC) per abilitare il flusso di posta tra EOP e i server di posta locali. Per istruzioni dettagliate, vedere [Set up connectors to route mail between Microsoft 365 and your own email servers](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Controllare il flusso di posta tra il servizio e l'ambiente. Per ulteriori informazioni, vedere [Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Passaggio 4: Consentire alla porta in ingresso 25 accesso SMTP

Dopo aver configurato i connettori, attendere 72 ore per consentire la propagazione degli aggiornamenti dei record DNS. Successivamente, limitare il traffico SMTP della porta 25 in ingresso sul firewall o sui server di posta in modo da accettare solo la posta proveniente da datacenter EOP, specificamente dagli indirizzi IP elencati in [Indirizzi IP di EOP (Exchange Online Protection)](../../enterprise/urls-and-ip-address-ranges.md). In tal modo si protegge l'ambiente locale limitando l'ambito dei messaggi in arrivo che è possibile ricevere. Inoltre, se sul server di posta sono state definite impostazioni per il controllo degli indirizzi IP a cui è consentita la connessione per l'inoltro della posta, è necessario aggiornare anche tali impostazioni.

> [!TIP]
> Configurare le impostazioni sul server SMTP con una tempo di timeout di connessione pari a 60 secondi. Questa impostazione è accettabile per la maggior parte delle situazioni, consentendo un certo ritardo nel caso di un messaggio inviato con un allegato di grandi dimensioni, ad esempio.

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Passaggio 5: verificare che la posta indesiderata sia instradata alla cartella Posta indesiderata di ogni utente

Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. I passaggi sono disponibili in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Se non si desidera spostare i messaggi nella cartella Posta indesiderata di ogni utente, è possibile scegliere un'altra azione modificando i criteri di protezione da posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Passaggio 6: Usare l'interfaccia di amministrazione di Microsoft 365 per puntare il record MX a EOP

Seguire i passaggi di configurazione del dominio per aggiornare il record MX per il dominio, in modo che la posta elettronica in ingresso fluirà attraverso EOP. Assicurarsi di puntare il record MX direttamente a EOP anziché fare in modo che un servizio di filtro di terze parti inoltri la posta elettronica a EOP. Per ulteriori informazioni, è possibile fare di nuovo riferimento [a Creare record DNS per Office 365.](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

> [!NOTE]
> Se è necessario puntare il record MX a un altro server o servizio che si trova di fronte a EOP, vedere [Enhanced Filtering for Connectors in Exchange Online.](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

### <a name="how-do-you-know-this-task-worked"></a>Come verificare se l'operazione ha avuto esito positivo

A questo punto, l'erogazione del servizio è stata verificata per un connettore locale in uscita adeguatamente configurato ed è stato appurato che il record MX punta a EOP. Ora è possibile scegliere di eseguire ulteriori test per verificare che un messaggio di posta elettronica sia recapitato correttamente dal servizio all'ambiente locale:

- Controllare il flusso di posta tra il servizio e l'ambiente. Per ulteriori informazioni, vedere [Test mail flow by validating your Microsoft 365 connectors](/exchange/mail-flow-best-practices/test-mail-flow).

- Inviare un messaggio di posta elettronica da un account di posta elettronica basato su Web a un destinatario di posta dell'organizzazione il cui dominio corrisponde al dominio aggiunto al servizio. Verificare il recapito del messaggio alla cassetta postale locale utilizzando Microsoft Outlook o un altro client di posta elettronica,

- Per eseguire un test della posta elettronica in uscita, è possibile inviare un messaggio di posta elettronica da un utente nell'organizzazione a un account di posta elettronica basato su Web e verificare che sia stato ricevuto.

> [!TIP]
> Al termine dell'installazione, non è necessario eseguire ulteriori operazioni perché EOP rimuova posta indesiderata e malware. EOP li rimuove automaticamente. Tuttavia, è possibile ottimizzare le impostazioni in base ai requisiti aziendali. Per ulteriori informazioni, vedere Protezione da posta [indesiderata e antimalware in Office 365](anti-spam-and-anti-malware-protection.md) e [Configure spoof intelligence.](learn-about-spoof-intelligence.md)
>
> Ora che il servizio è in esecuzione, è consigliabile leggere Procedure consigliate per la configurazione di [EOP,](best-practices-for-configuring-eop.md)che descrive le impostazioni e le considerazioni consigliate per dopo aver configurato EOP.