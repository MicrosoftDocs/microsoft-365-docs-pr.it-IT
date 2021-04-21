---
title: Come distribuire Defender per Endpoint su Linux con Chef
description: Scopri come distribuire Defender for Endpoint in Linux con Chef
keywords: microsoft, defender, atp, linux, scansioni, antivirus, microsoft defender for endpoint (linux)
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: aa699aae24b1e6383f5a2afbe7fce31e0f53805c
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903929"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a>Distribuire Defender per endpoint su Linux con Chef

Informazioni preliminari:

- Installare decomprimere se non è già installato. I componenti di Chef sono già installati ed è presente un repository di Chef (chef generate repo) per archiviare il manuale di riferimento che verrà utilizzato per la distribuzione in Defender for Endpoint nei server Linux gestiti da <reponame> Chef.

È possibile creare un nuovo manuale di cucina nel repository esistente eseguendo il comando seguente dall'interno della cartella cookbooks presente nel repository degli chef:</br>
`chef generate cookbook mdatp`

Questo comando creerà una nuova struttura di cartelle per il nuovo manuale di cucina denominato mdatp.  Puoi anche usare un manuale di cucina esistente se ne hai già uno che vuoi usare per aggiungere la distribuzione MDE.
Dopo aver creato il manuale di cucina, crea una cartella di file all'interno della cartella del manuale di cucina appena creata:

`mkdir mdatp/files`

Trasferire il file ZIP di onboarding di Linux Server che può essere scaricato dal portale di Microsoft Defender Security Center in questa nuova cartella di file.

In Workstation di Chef passare alla cartella mdatp/recipes. Questa cartella viene creata al momento della generazione del manuale di cucina. Usa l'editor di testo preferito (ad esempio vi o nano) per aggiungere le istruzioni seguenti alla fine del file default.rb:
-   include_recipe '::onboard_mdatp'
- include_recipe '::install_mdatp'

Quindi salvare e chiudere il file default.rb.
Crea quindi un nuovo file di ricetta denominato install_mdatp.rb nella cartella delle ricette e aggiungi questo testo al file:

```powershell

#Add Microsoft Defender   
Repo  
case node['platform_family']
when 'debian'
 apt_repository 'MDAPRepo' do
   arch               'amd64'
   cache_rebuild      true
   cookbook           false
   deb_src            false
   key                'BC528686B50D79E339D3721CEB3E94ADBE1229CF'
   keyserver          "keyserver.ubuntu.com"
   distribution       'focal'
   repo_name          'microsoft-prod'
   components         ['main']
   trusted            true
   uri                "https://packages.microsoft.com/ubuntu/20.04/prod"
 end
 apt_package "mdatp"
when 'rhel'
 yum_repository 'microsoft-prod' do
   baseurl            "https://packages.microsoft.com/rhel/7/prod/"
   description        "Microsoft Defender for Endpoint"
   enabled            true
   gpgcheck           true
   gpgkey             "https://packages.microsoft.com/keys/microsoft.asc"
 end
 if node['platform_version'] <= 8 then
    yum_package "mdatp"
 else
    dnf_package "mdatp"
 end
end
```

Dovrai modificare il numero di versione, la distribuzione e il nome del riposino in modo che corrispondano alla versione che stai distribuendo e al canale che vuoi distribuire.
Successivamente, è necessario creare un file onboard_mdatp.rb nella cartella mdatp/recipies.  Aggiungere il testo seguente al file:

```powershell

#Create MDATP Directory
mdatp = "/etc/opt/microsoft/mdatp"
zip_path = "/path/to/chef-repo/cookbooks/mdatp/files/WindowsDefenderATPOnboardingPackage.zip"

directory "#{mdatp}" do
  owner 'root'
  group 'root'
  mode 0755
  recursive true
end

#Extract WindowsDefenderATPOnbaordingPackage.zip into /etc/opt/microsoft/mdatp

bash 'Extract Onbaording Json MDATP' do
  code <<-EOS
  unzip #{zip_path} -d #{mdatp}
  EOS
  not_if { ::File.exist?('/etc/opt/microsoft/mdatp/mdatp_onboard.json') }
end
```

Assicurati di aggiornare il nome del percorso al percorso del file di onboarding.
Per testare la distribuzione nella workstation Chef, è sufficiente eseguire ``sudo chef-client -z -o mdatp`` .
Dopo la distribuzione, è consigliabile creare e distribuire un file di configurazione nei server in base a Imposta preferenze [per Microsoft Defender per Endpoint su Linux.](/linux-preferences.md)  
Dopo aver creato e testato il file di configurazione, puoi posizionarlo nella cartella cookbook/mdatp/files in cui hai inserito anche il pacchetto di onboarding.  Puoi quindi creare un file settings_mdatp.rb nella cartella mdatp/recipies e aggiungere questo testo:

```powershell
#Copy the configuration file
cookbook_file '/etc/opt/microsoft/mdatp/managed/mdatp_managed.json' do
  source 'mdatp_managed.json'
  owner 'root'
  group 'root'
  mode '0755'
  action :create
end
```

Per includere questo passaggio come parte della ricetta basta aggiungere include_recipe ':: settings_mdatp' al file default.rb all'interno della cartella della ricetta.
Puoi anche usare crontab per pianificare gli aggiornamenti automatici [Pianificare un aggiornamento di Microsoft Defender for Endpoint (Linux).](linux-update-MDE-Linux.md)

Uninstall MDATP cookbook:

```powershell
#Uninstall the Defender package
case node['platform_family']
when 'debian'
 apt_package "mdatp" do
   action :remove
 end
when 'rhel'
 if node['platform_version'] <= 8 
then
    yum_package "mdatp" do
      action :remove
    end
 else
    dnf_package "mdatp" do
      action :remove
    end
 end
end
```

