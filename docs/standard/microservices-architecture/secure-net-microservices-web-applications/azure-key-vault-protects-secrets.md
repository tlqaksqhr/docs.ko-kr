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
# <a name="using-azure-key-vault-to-protect-secrets-at-production-time"></a>Azure 키 자격 증명 모음을 사용 하 여 프로덕션 시 암호를 보호 하려면

암호 관리자 도구를 통해 또는 환경 변수로 저장 되어 있는 비밀 여전히 로컬로 저장 되 고 컴퓨터에서 암호화 되지 않은 합니다. 암호를 저장 하기 위한 더 안전한 옵션은 [Azure 키 자격 증명 모음](https://azure.microsoft.com/services/key-vault/), 키 및 암호를 저장 하기 위한 안전 하 고 중앙 위치를 제공 하는 합니다.

Microsoft.Extensions.Configuration.AzureKeyVault 패키지에는 ASP.NET Core 응용을 프로그램에서 Azure 키 자격 증명 모음 구성 정보를 읽을 수 있습니다. Azure 키 자격 증명 모음에서 암호를 사용 하 여을 시작 하려면 다음이 단계를 수행 합니다.

첫째, 응용 프로그램을 Azure AD 응용 프로그램으로 등록 합니다. (키 자격 증명 모음에 대 한 액세스는 Azure AD에 의해 관리 됩니다.) Azure 관리 포털을 통해이 작업을 수행할 수 있습니다.

또는, 암호 또는 클라이언트 암호 대신 인증서를 사용 하 여 인증 하는 응용 프로그램을 사용 하도록 하려는 경우 사용할 수 있습니다는 [새로 AzureRmADApplication](https://docs.microsoft.com/powershell/resourcemanager/azurerm.resources/v3.3.0/new-azurermadapplication) PowerShell cmdlet. Azure 키 자격 증명 모음에 등록 하는 인증서는 공개 키로만 필요 합니다. (응용 프로그램에 개인 키를 사용 합니다.)

둘째, 새 서비스 사용자를 만들어 키 자격 증명 모음에 등록 된 응용 프로그램 액세스를 제공 합니다. 다음 PowerShell 명령을 사용 하 여 수행할 수 있습니다.

```powershell
$sp = New-AzureRmADServicePrincipal -ApplicationId "<Application ID guid>"
Set-AzureRmKeyVaultAccessPolicy -VaultName "<VaultName>" -ServicePrincipalName $sp.ServicePrincipalNames[0] -PermissionsToSecrets all -ResourceGroupName "<KeyVault Resource Group>"
```

셋째, IConfigurationRoot 인스턴스를 만들 때 IConfigurationBuilder.AddAzureKeyVault 확장 메서드를 호출 하 여 응용 프로그램에서 구성 소스도 자격 증명 모음 키를 포함 합니다. Note AddAzureKeyVault 호출가 등록 되 고 이전 단계에서 주요 자격 증명 모음에 대 한 액세스를 지정 하는 응용 프로그램 ID 해야 합니다.

  현재 표준.NET 및.NET Core 지원 Azure 키 자격 증명 모음에서 가져오는 구성 정보는 클라이언트 ID 및 클라이언트 암호를 사용 하 여 합니다. .NET framework 응용 프로그램 IConfigurationBuilder.AddAzureKeyVault 클라이언트 암호 대신 인증서를 받아들이는 오버 로드를 사용할 수 있습니다. 작업은이 문서의 작성일 [진행에서](https://github.com/aspnet/Configuration/issues/605) 표준.NET 및.NET Core에서 해당 오버 로드를 사용할 수 있게 합니다. 인증서는 사용할 수 있는 허용 하는 AddAzureKeyVault 오버 로드 될 때까지 ASP.NET Core 응용 프로그램에 액세스할 수는 Azure 키 자격 증명 모음 인증서 기반 인증 KeyVaultClient 개체를 명시적으로 만들어서 다음 예제와 같이.

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

이 예제에서 AddAzureKeyVault에 대 한 호출의 구성 공급자 등록 후에 발생합니다. 기회를 이전 공급자의 구성 값을 재정의 하 고 다른 원본에서 구성 값 설정을 재정의 키 자격 증명 모음에서 마지막 구성 공급자도 Azure 키 자격 증명 모음을 등록 하는 것이 좋습니다.

## <a name="additional-resources"></a>추가 리소스

-   **Azure 키 자격 증명 모음을 사용 하 여 응용 프로그램 암호를 보호 하기 위해**
    [*https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault*](https://docs.microsoft.com/azure/guidance/guidance-multitenant-identity-keyvault)

-   **개발 하는 동안 앱 암호의 안전한 저장소**
    [*https://docs.microsoft.com/aspnet/core/security/app-secrets*](https://docs.microsoft.com/aspnet/core/security/app-secrets)

-   **데이터 보호를 구성**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/overview)

-   **키 관리 및 수명**
    [*https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings\#데이터 보호-기본 설정*](https://docs.microsoft.com/aspnet/core/security/data-protection/configuration/default-settings#data-protection-default-settings)

-   **Microsoft.Extensions.Configuration.DockerSecrets 합니다.** GitHub 리포지토리 합니다.
    [*https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets*](https://github.com/aspnet/Configuration/tree/dev/src/Microsoft.Extensions.Configuration.DockerSecrets)

>[!div class="step-by-step"]
[이전] (개발자-응용 프로그램-암호-storage.md) [다음] (... / takeaways.md 키)
