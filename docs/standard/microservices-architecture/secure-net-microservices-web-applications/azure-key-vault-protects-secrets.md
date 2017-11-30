---
title: "Azure 키 자격 증명 모음을 사용 하 여 프로덕션 시 암호를 보호 하려면"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | Azure 키 자격 증명 모음을 사용 하 여 프로덕션 시 암호를 보호 하려면"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: 7f922997e8d0c63e206cd68f4efda14985c86b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a><span data-ttu-id="8c378-104">Azure 키 자격 증명 모음을 사용 하 여 프로덕션 시 암호를 보호 하려면</span><span class="sxs-lookup"><span data-stu-id="8c378-104">Using Azure Key Vault to protect secrets at production time</span></span>

<span data-ttu-id="8c378-105">암호 관리자 도구를 통해 또는 환경 변수로 저장 되어 있는 비밀 여전히 로컬로 저장 되 고 컴퓨터에서 암호화 되지 않은 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-105">Secrets stored as environment variables or stored by the Secret Manager tool are still stored locally and unencrypted on the machine.</span></span> <span data-ttu-id="8c378-106">암호를 저장 하기 위한 더 안전한 옵션은 [Azure 키 자격 증명 모음](https://azure.microsoft.com/services/key-vault/), 키 및 암호를 저장 하기 위한 안전 하 고 중앙 위치를 제공 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-106">A more secure option for storing secrets is [Azure Key Vault](https://azure.microsoft.com/services/key-vault/), which provides a secure, central location for storing keys and secrets.</span></span>

<span data-ttu-id="8c378-107">Microsoft.Extensions.Configuration.AzureKeyVault 패키지에는 ASP.NET Core 응용을 프로그램에서 Azure 키 자격 증명 모음 구성 정보를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-107">The Microsoft.Extensions.Configuration.AzureKeyVault package allows an ASP.NET Core application to read configuration information from Azure Key Vault.</span></span> <span data-ttu-id="8c378-108">Azure 키 자격 증명 모음에서 암호를 사용 하 여을 시작 하려면 다음이 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-108">To start using secrets from an Azure Key Vault, you follow these steps:</span></span>

<span data-ttu-id="8c378-109">첫째, 응용 프로그램을 Azure AD 응용 프로그램으로 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-109">First, register your application as an Azure AD application.</span></span> <span data-ttu-id="8c378-110">(키 자격 증명 모음에 대 한 액세스는 Azure AD에 의해 관리 됩니다.) Azure 관리 포털을 통해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-110">(Access to key vaults is managed by Azure AD.) This can be done through the Azure management portal.</span></span>

<span data-ttu-id="8c378-111">또는, 암호 또는 클라이언트 암호 대신 인증서를 사용 하 여 인증 하는 응용 프로그램을 사용 하도록 하려는 경우 사용할 수 있습니다는 [새로 AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8c378-111">Alternatively, if you want your application to authenticate using a certificate instead of a password or client secret, you can use the [New-AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet.</span></span> <span data-ttu-id="8c378-112">Azure 키 자격 증명 모음에 등록 하는 인증서는 공개 키로만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-112">The certificate that you register with Azure Key Vault needs only your public key.</span></span> <span data-ttu-id="8c378-113">(응용 프로그램에 개인 키를 사용 합니다.)</span><span class="sxs-lookup"><span data-stu-id="8c378-113">(Your application will use the private key.)</span></span>

<span data-ttu-id="8c378-114">둘째, 새 서비스 사용자를 만들어 키 자격 증명 모음에 등록 된 응용 프로그램 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-114">Second, give the registered application access to the key vault by creating a new service principal.</span></span> <span data-ttu-id="8c378-115">다음 PowerShell 명령을 사용 하 여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-115">You can do this using the following PowerShell commands:</span></span>

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

<span data-ttu-id="8c378-116">셋째, IConfigurationRoot 인스턴스를 만들 때 IConfigurationBuilder.AddAzureKeyVault 확장 메서드를 호출 하 여 응용 프로그램에서 구성 소스도 자격 증명 모음 키를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-116">Third, include the key vault as a configuration source in your application by calling the IConfigurationBuilder.AddAzureKeyVault extension method when you create an IConfigurationRoot instance.</span></span> <span data-ttu-id="8c378-117">Note AddAzureKeyVault 호출가 등록 되 고 이전 단계에서 주요 자격 증명 모음에 대 한 액세스를 지정 하는 응용 프로그램 ID 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-117">Note that calling AddAzureKeyVault will require the application ID that was registered and given access to the key vault in the previous steps.</span></span>

  <span data-ttu-id="8c378-118">현재 표준.NET 및.NET Core 지원 Azure 키 자격 증명 모음에서 가져오는 구성 정보는 클라이언트 ID 및 클라이언트 암호를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-118">Currently, .NET Standard and .NET Core support getting configuration information from an Azure Key Vault using a client ID and client secret.</span></span> <span data-ttu-id="8c378-119">.NET framework 응용 프로그램 IConfigurationBuilder.AddAzureKeyVault 클라이언트 암호 대신 인증서를 받아들이는 오버 로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-119">.NET Framework applications can use an overload of IConfigurationBuilder.AddAzureKeyVault that takes a certificate in place of the client secret.</span></span> <span data-ttu-id="8c378-120">작업은이 문서의 작성일 [진행에서](https://github.com/aspnet/Configuration/issues/605) 표준.NET 및.NET Core에서 해당 오버 로드를 사용할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-120">As of this writing, work is [in progress](https://github.com/aspnet/Configuration/issues/605) to make that overload available in .NET Standard and .NET Core.</span></span> <span data-ttu-id="8c378-121">인증서는 사용할 수 있는 허용 하는 AddAzureKeyVault 오버 로드 될 때까지 ASP.NET Core 응용 프로그램에 액세스할 수는 Azure 키 자격 증명 모음 인증서 기반 인증 KeyVaultClient 개체를 명시적으로 만들어서 다음 예제와 같이.</span><span class="sxs-lookup"><span data-stu-id="8c378-121">Until the AddAzureKeyVault overload that accepts a certificate is available, ASP.NET Core applications can access an Azure Key Vault with certificate-based authentication by explicitly creating a KeyVaultClient object, as shown in the following example:</span></span>

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

<span data-ttu-id="8c378-122">이 예제에서 AddAzureKeyVault에 대 한 호출의 구성 공급자 등록 후에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-122">In this example, the call to AddAzureKeyVault comes at the end of configuration provider registration.</span></span> <span data-ttu-id="8c378-123">기회를 이전 공급자의 구성 값을 재정의 하 고 다른 원본에서 구성 값 설정을 재정의 키 자격 증명 모음에서 마지막 구성 공급자도 Azure 키 자격 증명 모음을 등록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-123">It is a best practice to register Azure Key Vault as the last configuration provider so that it has an opportunity to override configuration values from previous providers, and so that no configuration values from other sources override those from the key vault.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8c378-124">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="8c378-124">Additional resources</span></span>

-   <span data-ttu-id="8c378-125">**Azure 키 자격 증명 모음을 사용 하 여 응용 프로그램 암호를 보호 하기 위해**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span><span class="sxs-lookup"><span data-stu-id="8c378-125">**Using Azure Key Vault to protect application secrets**
[*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)</span></span>

-   <span data-ttu-id="8c378-126">**개발 하는 동안 앱 암호의 안전한 저장소**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="8c378-126">**Safe storage of app secrets during development**
[*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)</span></span>

-   <span data-ttu-id="8c378-127">**데이터 보호를 구성**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span><span class="sxs-lookup"><span data-stu-id="8c378-127">**Configuring data protection**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)</span></span>

-   <span data-ttu-id="8c378-128">**키 관리 및 수명**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#데이터 보호-기본 설정*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span><span class="sxs-lookup"><span data-stu-id="8c378-128">**Key management and lifetime**
[*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#data-protection-default-settings*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)</span></span>

-   <span data-ttu-id="8c378-129">**Microsoft.Extensions.Configuration.DockerSecrets 합니다.**</span><span class="sxs-lookup"><span data-stu-id="8c378-129">**Microsoft.Extensions.Configuration.DockerSecrets.**</span></span> <span data-ttu-id="8c378-130">GitHub 리포지토리 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c378-130">GitHub repo.</span></span>
    [<span data-ttu-id="8c378-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span><span class="sxs-lookup"><span data-stu-id="8c378-131">*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*</span></span>](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
<span data-ttu-id="8c378-132">[이전] (개발자-응용 프로그램-암호-storage.md) [다음] (... / takeaways.md 키)</span><span class="sxs-lookup"><span data-stu-id="8c378-132">[Previous] (developer-app-secrets-storage.md) [Next] (../key-takeaways.md)</span></span>
