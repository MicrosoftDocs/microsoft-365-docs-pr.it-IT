---
title: Installazione del servizio EOP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: In questo argomento viene illustrato come configurare Microsoft Exchange Online Protection (EOP). Se si è arrivati qui dalla configurazione guidata dei domini di Office 365, tornare alla configurazione guidata dei domini di Office 365 se non si desidera utilizzare Exchange Online Protection. Per ulteriori informazioni su come configurare i connettori, vedere Configure mail flow using connectors in Office 365.
ms.openlocfilehash: 189c3bb08609eb2604e77b5140e866711e8f1a09
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38032001"
---
# <a name="set-up-your-eop-service"></a>Configurare il servizio Exchange Online Protection

In questo argomento viene illustrato come configurare Microsoft Exchange Online Protection (EOP). Se si è arrivati qui dalla configurazione guidata dei domini di Office 365, tornare alla configurazione guidata dei domini di Office 365 se non si desidera utilizzare Exchange Online Protection. Per ulteriori informazioni su come configurare i connettori, vedere [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

> [!NOTE]
> In questo argomento si presuppone che siano presenti cassette postali locali e che si desideri proteggerle con EOP, noto come scenario autonomo. Se si desidera ospitare tutte le cassette postali nel cloud con Exchange Online, non è necessario completare tutti i passaggi descritti in questo argomento. Accedere a [Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=286312) per iscriversi e acquistare le cassette postali cloud. Se si desidera ospitare alcune delle cassette postali in locale e alcune nel cloud, questo è conosciuto come uno scenario ibrido. Richiede impostazioni di flusso di posta più avanzate. Le [distribuzioni ibride di Exchange Server](https://docs.microsoft.com/exchange/exchange-hybrid) spiegano il flusso di posta ibrido e dispongono di collegamenti a risorse che illustrano come configurarlo.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento di questa attività: 1 ora

- Per configurare i connettori, l'account deve essere un amministratore globale di Office 365 o un amministratore aziendale di Exchange (gruppo dei ruoli di gestione dell'organizzazione). Per informazioni, vedere [Feature Permissions in EOP](feature-permissions-in-eop.md).

- Se non si è iscritti a EOP, visitare [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?LinkId=282660) e scegliere di acquistare o provare il servizio.

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>Passaggio 1: utilizzare l'interfaccia di amministrazione di Microsoft 365 per aggiungere e verificare il dominio

1. Nell'interfaccia di [amministrazione di Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=521888)passare a **installazione** per aggiungere il dominio al servizio.

2. Seguire la procedura di aggiunta dei record DNS applicabili al provider che ospita i DNS per verificare la proprietà del dominio.

> [!TIP]
> [Aggiungere un dominio a office 365](https://docs.microsoft.com/office365/admin/setup/add-domain) e [creare record DNS in qualsiasi provider di hosting dns per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) sono risorse utili da fare riferimento quando si aggiunge il dominio al servizio e si configura DNS.

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>Passaggio 2: aggiunta di destinatari e abilitazione DBEB (scelta facoltativa)

Prima di configurare il flusso di posta da e verso il servizio EOP, si consiglia di aggiungere i destinatari al servizio. Esistono diversi modi in cui è possibile farlo, come documentato in [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md). Inoltre, se si desidera abilitare il blocco Edge basato su directory (DBEB) per migliorare la verifica dei destinatari all'interno del servizio dopo averli aggiunti, è necessario impostare il tipo di dominio su Autorevole. Per ulteriori informazioni su DBEB, vedere [Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>Passaggio 3: Configurazione del flusso di posta tramite EAC

Creare i connettori nell'Interfaccia di amministrazione di Exchange (EAC) per abilitare il flusso di posta tra EOP e i server di posta locali. Per istruzioni dettagliate, vedere [Set up connectors to route mail between Office 365 and your own email servers](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail).

### <a name="how-do-you-know-this-task-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Controllare il flusso di posta tra il servizio e l'ambiente. Per ulteriori informazioni, vedere [verificare il flusso di posta convalidando i connettori di Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>Passaggio 4: Consentire alla porta in ingresso 25 accesso SMTP

Dopo aver configurato i connettori, attendere 72 ore per consentire la propagazione degli aggiornamenti dei record DNS. Successivamente, limitare il traffico SMTP della porta 25 in ingresso sul firewall o sui server di posta in modo da accettare solo la posta proveniente da datacenter EOP, specificamente dagli indirizzi IP elencati in [Indirizzi IP di EOP (Exchange Online Protection)](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges
). In tal modo si protegge l'ambiente locale limitando l'ambito dei messaggi in arrivo che è possibile ricevere. Inoltre, se sul server di posta sono state definite impostazioni per il controllo degli indirizzi IP a cui è consentita la connessione per l'inoltro della posta, è necessario aggiornare anche tali impostazioni.

> [!TIP]
> Configurare le impostazioni sul server SMTP con una tempo di timeout di connessione pari a 60 secondi. Questa impostazione è accettabile per la maggior parte delle situazioni, consentendo un certo ritardo nel caso di un messaggio inviato con un allegato di grandi dimensioni, ad esempio.

## <a name="step-5-use-the-shell-to-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>Passaggio 5: Utilizzare Shell per garantire che la posta indesiderata sia instradata nella cartella posta indesiderata di ogni utente

Per assicurarsi che la posta indesiderata venga instradata correttamente nella cartella posta indesiderata di ciascun utente, è necessario eseguire un paio di passaggi per la configurazione. I passaggi vengono forniti in [modo che la posta indesiderata venga instradata alla cartella posta indesiderata di ogni utente](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).

Se non si intende spostare i messaggi nella cartella posta indesiderata di ciascun utente, è possibile optare per un'altra azione modificando i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange. Per ulteriori informazioni, vedere [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>Passaggio 6: utilizzare l'interfaccia di amministrazione di Microsoft 365 per puntare il record MX a EOP

Seguire i passaggi di configurazione del dominio di Office 365 per aggiornare il record MX relativo al proprio dominio. In questo modo, la posta elettronica in ingresso attraversa EOP. Assicurarsi di puntare il record MX direttamente verso EOP, invece di consentire a un servizio di filtro di terze parti di inoltrare la posta elettronica in EOP. Per ulteriori informazioni, fare di nuovo riferimento a [Creare record DNS per Office 365](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).

### <a name="how-do-you-know-this-task-worked"></a>Come verificare se l'operazione ha avuto esito positivo

A questo punto, l'erogazione del servizio è stata verificata per un connettore locale in uscita adeguatamente configurato ed è stato appurato che il record MX punta a EOP. Ora è possibile scegliere di eseguire ulteriori test per verificare che un messaggio di posta elettronica sia recapitato correttamente dal servizio all'ambiente locale:

- Controllare il flusso di posta tra il servizio e l'ambiente. Per ulteriori informazioni, vedere [verificare il flusso di posta convalidando i connettori di Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).

- Inviare un messaggio di posta elettronica da un account di posta elettronica basato su Web a un destinatario di posta dell'organizzazione il cui dominio corrisponde al dominio aggiunto al servizio. Verificare il recapito del messaggio alla cassetta postale locale utilizzando Microsoft Outlook o un altro client di posta elettronica,

- Per eseguire un test della posta elettronica in uscita, è possibile inviare un messaggio di posta elettronica da un utente nell'organizzazione a un account di posta elettronica basato su Web e verificare che sia stato ricevuto.

> [!TIP]
> Al termine dell'installazione, non è necessario eseguire ulteriori operazioni perché EOP rimuova posta indesiderata e malware. EOP li rimuove automaticamente. Tuttavia, è possibile utilizzare EAC per ottimizzare le impostazioni in base ai requisiti aziendali. Per ulteriori informazioni, vedere [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md). <br/><br/> Ora che il servizio è in esecuzione, si consiglia di leggere le procedure consigliate [per la configurazione di EOP](best-practices-for-configuring-eop.md), in cui vengono descritte le impostazioni e le considerazioni consigliate per l'installazione di EOP.
