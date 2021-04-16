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
ms.openlocfilehash: 362222e4737b1a8dd6b8a0a284bf3bfb1903c288
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861447"
---
# <a name="deploy-defender-for-endpoint-on-linux-with-chef"></a><span data-ttu-id="a54b0-104">Distribuire Defender per Endpoint su Linux con Chef</span><span class="sxs-lookup"><span data-stu-id="a54b0-104">Deploy Defender for Endpoint on Linux with Chef</span></span>

<span data-ttu-id="a54b0-105">Informazioni preliminari:</span><span class="sxs-lookup"><span data-stu-id="a54b0-105">Before you begin:</span></span>

- <span data-ttu-id="a54b0-106">Installare decomprimere se non è già installato.</span><span class="sxs-lookup"><span data-stu-id="a54b0-106">Install unzip if it’s not already installed.</span></span> <span data-ttu-id="a54b0-107">I componenti di Chef sono già installati ed è presente un repository di Chef (chef generate repo) per archiviare il manuale di riferimento che verrà utilizzato per la distribuzione in Defender for Endpoint nei server Linux gestiti da <reponame> Chef.</span><span class="sxs-lookup"><span data-stu-id="a54b0-107">The Chef components are already installed and a Chef repository exists (chef generate repo <reponame>) to store the cookbook that will be used to deploy to Defender for Endpoint on Chef managed Linux servers.</span></span>

<span data-ttu-id="a54b0-108">È possibile creare un nuovo manuale di cucina nel repository esistente eseguendo il comando seguente dall'interno della cartella cookbooks presente nel repository degli chef:</span><span class="sxs-lookup"><span data-stu-id="a54b0-108">You can create a new cookbook in your existing repository by running the following command from inside the cookbooks folder that is in your chef repository:</span></span></br>
`chef generate cookbook mdatp`

<span data-ttu-id="a54b0-109">Questo comando creerà una nuova struttura di cartelle per il nuovo manuale di cucina denominato mdatp.</span><span class="sxs-lookup"><span data-stu-id="a54b0-109">This command will create a new folder structure for the new cookbook called mdatp.</span></span>  <span data-ttu-id="a54b0-110">Puoi anche usare un manuale di cucina esistente se ne hai già uno che vuoi usare per aggiungere la distribuzione MDE.</span><span class="sxs-lookup"><span data-stu-id="a54b0-110">You can also use an existing cookbook if you already have one you’d like to use to add the MDE deployment into.</span></span>
<span data-ttu-id="a54b0-111">Dopo aver creato il manuale di cucina, crea una cartella di file all'interno della cartella del manuale di cucina appena creata:</span><span class="sxs-lookup"><span data-stu-id="a54b0-111">After the cookbook is created, create a files folder inside the cookbook folder that just got created:</span></span>

`mkdir mdatp/files`

<span data-ttu-id="a54b0-112">Trasferire il file ZIP di onboarding di Linux Server che può essere scaricato dal portale di Microsoft Defender Security Center in questa nuova cartella di file.</span><span class="sxs-lookup"><span data-stu-id="a54b0-112">Transfer the Linux Server Onboarding zip file that can be downloaded from the Microsoft Defender Security Center portal to this new files folder.</span></span>

<span data-ttu-id="a54b0-113">In Workstation di Chef passare alla cartella mdatp/recipes.</span><span class="sxs-lookup"><span data-stu-id="a54b0-113">On the Chef Workstation, navigate to the mdatp/recipes folder.</span></span> <span data-ttu-id="a54b0-114">Questa cartella viene creata al momento della generazione del manuale di cucina.</span><span class="sxs-lookup"><span data-stu-id="a54b0-114">This folder is created when the cookbook was generated.</span></span> <span data-ttu-id="a54b0-115">Usa l'editor di testo preferito (ad esempio vi o nano) per aggiungere le istruzioni seguenti alla fine del file default.rb:</span><span class="sxs-lookup"><span data-stu-id="a54b0-115">Use your preferred text editor (like vi or nano) to add the following instructions to the end of the default.rb file:</span></span>
-   <span data-ttu-id="a54b0-116">include_recipe '::onboard_mdatp'</span><span class="sxs-lookup"><span data-stu-id="a54b0-116">include_recipe '::onboard_mdatp'</span></span>
- <span data-ttu-id="a54b0-117">include_recipe '::install_mdatp'</span><span class="sxs-lookup"><span data-stu-id="a54b0-117">include_recipe '::install_mdatp'</span></span>

<span data-ttu-id="a54b0-118">Quindi salvare e chiudere il file default.rb.</span><span class="sxs-lookup"><span data-stu-id="a54b0-118">Then save and close the default.rb file.</span></span>
<span data-ttu-id="a54b0-119">Crea quindi un nuovo file di ricetta denominato install_mdatp.rb nella cartella delle ricette e aggiungi questo testo al file:</span><span class="sxs-lookup"><span data-stu-id="a54b0-119">Next create a new recipe file named install_mdatp.rb in the recipes folder and add this text to the file:</span></span>

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

<span data-ttu-id="a54b0-120">Dovrai modificare il numero di versione, la distribuzione e il nome del riposino in modo che corrispondano alla versione che stai distribuendo e al canale che vuoi distribuire.</span><span class="sxs-lookup"><span data-stu-id="a54b0-120">You’ll need to modify the version number, distribution, and repo name to match the version you’re deploying to and the channel you’d like to deploy.</span></span>
<span data-ttu-id="a54b0-121">Successivamente, è necessario creare un file onboard_mdatp.rb nella cartella mdatp/recipies.</span><span class="sxs-lookup"><span data-stu-id="a54b0-121">Next you should create an onboard_mdatp.rb file in the mdatp/recipies folder.</span></span>  <span data-ttu-id="a54b0-122">Aggiungere il testo seguente al file:</span><span class="sxs-lookup"><span data-stu-id="a54b0-122">Add the following text to that file:</span></span>

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

<span data-ttu-id="a54b0-123">Assicurati di aggiornare il nome del percorso al percorso del file di onboarding.</span><span class="sxs-lookup"><span data-stu-id="a54b0-123">Make sure to update the path name to the location of the onboarding file.</span></span>
<span data-ttu-id="a54b0-124">Per testare la distribuzione nella workstation Chef, è sufficiente eseguire ``sudo chef-client -z -o mdatp`` .</span><span class="sxs-lookup"><span data-stu-id="a54b0-124">To test deploy it on the Chef workstation, just run ``sudo chef-client -z -o mdatp``.</span></span>
<span data-ttu-id="a54b0-125">Dopo la distribuzione, è consigliabile creare e distribuire un file di configurazione nei server in base a Imposta preferenze per  [Microsoft Defender ATP per Linux - Windows security | Documenti Microsoft](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span><span class="sxs-lookup"><span data-stu-id="a54b0-125">After your deployment you should consider creating and deploying a configuration file to the servers based on  [Set preferences for Microsoft Defender ATP for Linux - Windows security | Microsoft Docs](/windows/security/threat-protection/microsoft-defender-atp/linux-preferences).</span></span>  
<span data-ttu-id="a54b0-126">Dopo aver creato e testato il file di configurazione, puoi posizionarlo nella cartella cookbook/mdatp/files in cui hai inserito anche il pacchetto di onboarding.</span><span class="sxs-lookup"><span data-stu-id="a54b0-126">After you've created and tested your configuration file, you can place it into the cookbook/mdatp/files folder where you also placed the onboarding package.</span></span>  <span data-ttu-id="a54b0-127">Puoi quindi creare un file settings_mdatp.rb nella cartella mdatp/recipies e aggiungere questo testo:</span><span class="sxs-lookup"><span data-stu-id="a54b0-127">Then you can create a settings_mdatp.rb file in the mdatp/recipies folder and add this text:</span></span>

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

<span data-ttu-id="a54b0-128">Per includere questo passaggio come parte della ricetta basta aggiungere include_recipe ':: settings_mdatp' al file default.rb all'interno della cartella della ricetta.</span><span class="sxs-lookup"><span data-stu-id="a54b0-128">To include this step as part of the recipe just add include_recipe ':: settings_mdatp' to your default.rb file within the recipe folder.</span></span>
<span data-ttu-id="a54b0-129">Puoi anche usare crontab per pianificare gli aggiornamenti automatici [Pianificare un aggiornamento di Microsoft Defender for Endpoint (Linux).](linux-update-MDE-Linux.md)</span><span class="sxs-lookup"><span data-stu-id="a54b0-129">You can also use crontab to schedule automatic updates [Schedule an update of the Microsoft Defender for Endpoint (Linux)](linux-update-MDE-Linux.md).</span></span>

<span data-ttu-id="a54b0-130">Uninstall MDATP cookbook:</span><span class="sxs-lookup"><span data-stu-id="a54b0-130">Uninstall MDATP cookbook:</span></span>

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

