---
title: "Azure Key Vault를 사용하여 프로덕션 시 비밀 보호"
description: "컨테이너화된 .NET 응용 프로그램에 대한 .NET 마이크로 서비스 아키텍처 | Azure Key Vault를 사용하여 프로덕션 시 비밀 보호"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb289c7361362c225eac8b9898bac276c4b623b4
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="408d8-104">Azure Key Vault를 사용하여 프로덕션 시 비밀 보호</span><span class="sxs-lookup"><span data-stu-id="408d8-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="408d8-105">환경 변수로 저장되거나 비밀 관리자 도구로 저장된 비밀은 여전히 로컬로 저장되고 컴퓨터에서 암호화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="408d8-106">비밀을 저장하기 위한 더 안전한 옵션은 키 및 비밀을 저장하기 위해 안전한 중앙 위치를 제공하는 [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)입니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="408d8-107">Microsoft.Extensions.Configuration.AzureKeyVault 패키지를 통해 ASP.NET Core 응용 프로그램에서 Azure Key Vault의 구성 정보를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="408d8-108">Azure Key Vault에서 암호 사용을 시작하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="408d8-109">첫 번째로, 응용 프로그램을 Azure AD 응용 프로그램으로 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="408d8-110">(키 자격 증명 모음에 대한 액세스는 Azure AD에 의해 관리됩니다.) Azure 관리 포털을 통해 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="408d8-111">또는 암호 또는 클라이언트 암호 대신 인증서를 사용하여 응용 프로그램을 인증하려는 경우 [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="408d8-112">Azure Key Vault로 등록하는 인증서는 공개 키만 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="408d8-113">(응용 프로그램은 개인 키를 사용합니다.)</span><span class="sxs-lookup"><span data-stu-id="408d8-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="408d8-114">두 번째로, 새 서비스 사용자를 만들어 등록된 응용 프로그램에 키 자격 증명 모음에 대한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="408d8-115">다음 PowerShell 명령을 사용하여 이를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="408d8-116">세 번째로, IConfigurationRoot 인스턴스를 만들 때 IConfigurationBuilder.AddAzureKeyVault 확장 메서드를 호출하여 응용 프로그램에서 구성 원본으로 키 자격 증명 모음을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="408d8-117">AddAzureKeyVault를 호출하려면 이전 단계에서 등록된 응용 프로그램 ID 및 키 자격 증명 모음에 대한 지정된 액세스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="408d8-118">현재 .NET Standard 및 .NET Core는 클라이언트 ID 및 클라이언트 암호를 사용하여 Azure Key Vault에서 구성 정보 가져오기를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="408d8-119">.NET Framework 응용 프로그램은 클라이언트 암호 대신 인증서를 사용하는 IConfigurationBuilder.AddAzureKeyVault의 오버로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="408d8-120">이 문서의 작성일을 기준으로 오버로드를 .NET Standard 및 .NET Core에서 사용할 수 있도록 작업이 [진행 중입니다](https://github.com/aspnet/Configuration/issues/605).</span><span class="sxs-lookup"><span data-stu-id="408d8-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="408d8-121">인증서를 허용하는 AddAzureKeyVault 오버로드를 사용할 수 있을 때까지 ASP.NET Core 응용 프로그램은 다음 예제에 표시된 것과 같이 KeyVaultClient 개체를 명시적으로 만들어 인증서 기반 인증으로 Azure Key Vault에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

```csharp
// Configure Key Vault client
var kvClient = new KeyVaultClient(new KeyVaultClient.AuthenticationCallback(async
    (authority, resource, scope) =>
    {
        var cert = // Get certificate from local store/file/key vault etc. as needed
        // From the Microsoft.IdentityModel.Clients.ActiveDirectory pacakge
        var authContext = new AuthenticationContext(authority,
            TokenCache.DefaultShared);
        var result = await authContext.AcquireTokenAsync(resource,
            // From the Microsoft.Rest.ClientRuntime.Azure.Authentication pacakge
            new ClientAssertionCertificate("{Application ID}", cert));
        return result.AccessToken;
    }));

    // Get configuration values from Key Vault
    var builder = new ConfigurationBuilder()
        .SetBasePath(env.ContentRootPath)
        // Other configuration providers go here.
        .AddAzureKeyVault("{KeyValueUri}", kvClient,
        new DefaultKeyVaultSecretManager());
```

<span data-ttu-id="408d8-122">이 예제에서 AddAzureKeyVault에 대한 호출은 구성 공급자 등록의 끝에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="408d8-123">이전 공급자에서 구성 값을 재정의할 기회를 갖고 다른 원본의 구성 값이 키 자격 증명 모음의 구성 값을 재정의하지 않도록 마지막 구성 공급자로 Azure Key Vault를 등록하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="408d8-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="408d8-124">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="408d8-124">Additional resources</span></span>

-   <span data-ttu-id="408d8-125">**Azure Key Vault를 사용하여 응용 프로그램 비밀 보호**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="408d8-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="408d8-126">**개발 중 안전한 앱 비밀 저장소**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="408d8-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="408d8-127">**데이터 보호 구성**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="408d8-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="408d8-128">**키 관리 및 수명**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="408d8-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="408d8-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span><span class="sxs-lookup"><span data-stu-id="408d8-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="408d8-130">GitHub 리포지토리</span><span class="sxs-lookup"><span data-stu-id="408d8-130">GitHub repo.</span></span>
    [<span data-ttu-id="408d8-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="408d8-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="408d8-132">[이전] (developer-app-secrets-storage.md) [다음] (../key-takeaways.md)</span><span class="sxs-lookup"><span data-stu-id="408d8-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
