---
title: Introduzione alla governance delle app
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Introduzione alle funzionalità di governance delle app per gestire le app.
ms.openlocfilehash: 80487298f2c3c3a93f0083337ddb223bd68e2611
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438037"
---
# <a name="get-started-with-app-governance-in-preview"></a>Introduzione alla governance delle app (in anteprima)

Per iniziare a usare il componente aggiuntivo di governance delle app per Microsoft Cloud App Security:

1. Verifica che il tuo account abbia il livello di licenza appropriato. La governance delle app è una funzionalità componente aggiuntivo per Microsoft Cloud App Security (MCAS) e pertanto MCAS deve essere presente nell'account come prodotto autonomo o come parte dei vari pacchetti di licenza elencati di seguito.
1. Per accedere alle pagine di governance delle app nel portale, è necessario avere uno dei ruoli di amministratore elencati di seguito.

## <a name="licensing-for-app-governance"></a>Licenze per la governance delle app

Prima di iniziare a usare la governance delle app, è necessario confermare gli [abbonamenti all'interfaccia di amministrazione di Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e gli eventuali componenti aggiuntivi. Per accedere e usare la governance delle app, l'organizzazione deve avere uno degli abbonamenti o dei componenti aggiuntivi seguenti:

- Microsoft Cloud App Security
- Microsoft 365 E5
- Conformità Microsoft 365 E5
- Microsoft 365 E5 Developer (senza Windows e audioconferenza)
- Microsoft 365 E5 Information Protection and Governance
- Microsoft 365 E5 Security
- Microsoft 365 E5 con minuti per le chiamate
- Microsoft 365 E5 senza Audioconferenza
- Microsoft 365 A5 Compliance per istituti di istruzione
- Microsoft 365 A5 Compliance per studenti
- Microsoft 365 A5 per istituti di istruzione
- Microsoft 365 A5 per studenti
- Microsoft 365 A5 Information Protection and Governance per istituti di istruzione
- Microsoft 365 A5 Information Protection and Governance per studenti
- Microsoft 365 A5 Security per istituti di istruzione
- Microsoft 365 A5 Security per studenti
- Microsoft 365 A5 student use benefits
- Microsoft 365 A5 con minuti per le chiamate per istituti di istruzione
- Microsoft 365 A5 con minuti per le chiamate per studenti
- Microsoft 365 A5 senza Audioconferenza per istituti di istruzione
- Microsoft 365 A5 senza Audioconferenza per studenti
- Microsoft 365 A5 senza Audioconferenza per studenti

## <a name="administrator-roles"></a>Ruoli di amministratore

Uno dei ruoli di amministratore seguenti è necessario per visualizzare le pagine di governance delle app o gestire criteri e impostazioni:

- Amministratore dell'applicazione
- Amministratore applicazione cloud
- Amministratore azienda
- Amministratore di conformità
- Amministratore dati di conformità
- Lettore di conformità (sola lettura)
- Ruolo con autorizzazioni di lettura globali
- Amministratore della sicurezza
- Operatore della sicurezza
- Amministratore che legge i dati di sicurezza (sola lettura)

> [!NOTE]
> Solo un amministratore globale può attivare la versione di valutazione gratuita della governance delle app.

Ecco le funzionalità per ogni ruolo.

| Ruolo | Usare il dashboard | Leggi tutte le app |Lettura dei criteri | Creare, aggiornare o eliminare criteri | Lettura degli avvisi | Aggiornare gli avvisi | Impostazioni di lettura | Aggiorna impostazioni | Rimedio di lettura | Aggiornamento rimedio |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| Amministratore dell'applicazione | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| Amministratore applicazione cloud | ![Segno di spunta](..\media\checkmark.png) | | | | | | | | | |
| Amministratore azienda | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |
| Amministratore di conformità | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | |
| Amministratore dati di conformità | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | |
| Lettore di conformità | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) |  | | |
| Ruolo con autorizzazioni di lettura globali  | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) |  | | |
| Amministratore della sicurezza | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | |
| Operatore della sicurezza | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | |
| Ruolo con autorizzazioni di lettura per la sicurezza  | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) |  | ![Segno di spunta](..\media\checkmark.png) | |
|||||||||| | |

Per ulteriori informazioni su ogni ruolo, vedi [Autorizzazioni del ruolo Amministratore](/azure/active-directory/roles/permissions-reference).

## <a name="add-app-governance-to-your-microsoft-365-account"></a>Aggiungi la governance delle app all'account Microsoft 365

Per i clienti Microsoft 365 esistenti:

1. Nell’[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) vai a **Fatturazione - Acquistare servizi** e fai clic su **Componenti aggiuntivi**.
1. Nella scheda di governance dell'app, fai clic su **Dettagli**.
1. Fai clic su **Avvia versione di valutazione gratuita**.
1. Completa le informazioni richieste per aggiungere la governance dell'app al tenant selezionato. Se sei un cliente nuovo, devi prima fornire informazioni per stabilire un account e creare un tenant per il periodo di valutazione. Al termine, potrai aggiungere la governance delle app alla versione di valutazione.

Per i nuovi clienti Microsoft 365:

1. Nella parte superiore di questa pagina, fai clic sul pulsante **Account gratuito**.
1. In **Prova Microsoft 365 for business** fai clic su **Prova 1 mese gratis**.

Per entrambi:

1. Nel portale di iscrizione, specifica l'indirizzo di posta elettronica da usare per la versione di valutazione. Se sei un cliente esistente, usa il messaggio di posta elettronica associato al tuo account. Fare clic su **Avanti**.
1. Dopo aver eseguito l'accesso, fai clic su **Prova ora** per ottenere la versione di valutazione gratuita.
1. Fai clic su **Continua** per chiudere la pagina e iniziare la configurazione della versione di valutazione. Per i nuovi clienti di governance delle app, saranno richieste fino a due ore prima che l'istanza di governance delle app diventi disponibile. Per i clienti esistenti, non ci saranno interruzioni dei servizi esistenti.
  > [!NOTE]
Se non hai già un account, verrà richiesto di configurare un nuovo account prima di procedere con la versione di valutazione.

1. Immetti un nome di dominio disponibile per il tenant di AAD e fai clic su **Verifica la disponibilità**. Verrà automaticamente assegnato un ruolo di amministratore (se non hai un ruolo esistente per la governance delle app) e potrai sempre modificare il nome del dominio e/o acquistare altri tenant in un secondo momento tramite l’interfaccia di amministrazione di Microsoft 365.
1. Immetti il nome utente e la password da usare per accedere al tuo account. Fai clic su **Iscriversi**.
1. Fai clic su **Introduzione** per passare al portale di governance dell'app o **Gestione abbonamento** per passare al interfaccia di amministrazione di Microsoft 365.
