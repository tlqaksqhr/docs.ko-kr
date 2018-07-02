---
title: 개발하는 동안 응용 프로그램 비밀 저장
description: 컨테이너화된 .NET 응용 프로그램을 위한 .NET 마이크로 서비스 아키텍처 | 개발하는 동안 응용 프로그램 비밀 저장
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.openlocfilehash: 560120db35ae190bdef1f95d72ac1e5de697124e
ms.sourcegitcommit: 979597cd8055534b63d2c6ee8322938a27d0c87b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/29/2018
ms.locfileid: "37105948"
---
# <a name="storing-application-secrets-safely-during-development"></a>개발하는 동안 응용 프로그램 비밀 저장

보호된 리소스 및 기타 서비스에 연결하려면 ASP.NET Core 응용 프로그램은 일반적으로 연결 문자열, 암호 또는 중요한 정보를 포함하는 다른 자격 증명을 사용해야 합니다. 이러한 정보의 중요한 부분을 *암호*라고 합니다. 소스 코드에 암호를 포함하지 않고 소스 제어에서 암호를 저장하지 않도록 하는 것이 좋습니다. 대신 ASP.NET Core 구성 모델을 사용하여 보다 안전한 위치에서 암호를 읽어야 합니다.

여러 사용자가 다양한 해당 암호 집합에 액세스해야 하기 때문에 프로덕션 리소스에 액세스할 때 사용되는 암호와 개발에 액세스하고 리소스를 스테이징하기 위한 암호를 분리해야 합니다. 개발 중에 사용되는 암호를 저장하는 일반적인 방법은 환경 변수에서 암호를 저장하거나 ASP.NET Core 암호 관리자 도구를 사용하는 것입니다. 프로덕션 환경에 있는 보다 안전한 저장소의 경우 마이크로 서비스는 Azure Key Vault에 암호를 저장할 수 있습니다.

## <a name="storing-secrets-in-environment-variables"></a>환경 변수에 암호 저장

소스 코드에서 암호를 유지하는 한 가지 방법은 개발자가 해당 개발 컴퓨터에서 [환경 변수](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables)로 문자열 기반 암호를 설정하는 것입니다. 환경 변수를 사용하여 계층적 이름을 가진 암호를 저장할 때(구성 섹션에서 중첩됨) 콜론(:)으로 구분된 암호의 이름의 전체 계층 구조를 포함하는 환경 변수에 대한 이름을 생성합니다.

예를 들어 Logging:LogLevel:Default 환경 변수를 Debug로 설정하는 작업은 다음과 같은 JSON 파일의 구성 값에 해당합니다.

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

환경 변수의 이러한 값에 액세스하려면 응용 프로그램이 IConfigurationRoot 개체를 생성할 때 해당 ConfigurationBuilder에서 AddEnvironmentVariables를 호출해야 합니다.

환경 변수가 일반 텍스트로 저장됩니다. 따라서 환경 변수의 컴퓨터 또는 프로세스가 손상된 경우 환경 변수 값이 표시됩니다.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>ASP.NET Core 암호 관리자를 사용하여 암호 저장

ASP.NET Core [암호 관리자](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) 도구는 소스 코드에서 암호를 유지하는 또 다른 방법을 제공합니다. 암호 관리자 도구를 사용하려면 프로젝트 파일에서 Microsoft.Extensions.SecretManager.Tools 패키지에 도구 참조(DotNetCliToolReference)를 포함합니다. 해당 종속성이 표시되고 복원되면 dotnet 사용자 암호 명령은 명령줄에서 암호 값을 설정하는 데 사용할 수 있습니다. 이러한 암호는 소스 코드와 다르게 사용자의 프로필 디렉터리에 있는 JSON 파일에 저장됩니다(세부 정보는 운영 체제에 따라 다름).

암호 관리자 도구에 의해 설정된 암호는 암호를 사용하는 프로젝트의 UserSecretsId 속성으로 구성됩니다. 따라서 프로젝트 파일에서 UserSecretsId 속성을 설정해야 합니다(아래 코드 조각에 표시된 대로). ID로 사용되는 실제 문자열은 프로젝트에서 고유하기만 하면 됩니다.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

응용 프로그램에서 암호 관리자를 사용하여 저장된 암호를 사용하는 작업은 해당 구성에서 응용 프로그램의 암호를 포함하도록 ConfigurationBuilder 인스턴스에서 AddUserSecrets&lt;T&gt;를 호출하여 수행됩니다. 제네릭 매개 변수 T는 UserSecretId를 적용할 어셈블리의 형식이어야 합니다. 일반적으로 AddUserSecrets&lt;Startup&gt;을 사용하는 것이 좋습니다.


>[!div class="step-by-step"]
[이전](authorization-net-microservices-web-applications.md)
[다음](azure-key-vault-protects-secrets.md)
