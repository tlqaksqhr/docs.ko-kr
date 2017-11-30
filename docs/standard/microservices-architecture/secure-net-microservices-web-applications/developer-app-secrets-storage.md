---
title: "개발 하는 동안 응용 프로그램 암호를 안전 하 게 저장"
description: "컨테이너 화 된.NET 응용 프로그램에 대 한.NET Microservices 아키텍처 | 개발 하는 동안 응용 프로그램 암호를 안전 하 게 저장"
keywords: "Docker, 마이크로 서비스, ASP.NET, 컨테이너"
author: mjrousos
ms.author: wiwagn
ms.date: 05/26/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.topic: article
ms.openlocfilehash: f1b8b257a3e677c7e665e1d394a8adf7e651bec2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="storing-application-secrets-safely-during-development"></a>개발 하는 동안 응용 프로그램 암호를 안전 하 게 저장

기타 서비스와 보호 된 리소스에 연결 하려면 ASP.NET Core 응용 프로그램 일반적으로 연결 문자열, 암호 또는 중요 한 정보를 포함 하는 다른 자격 증명을 사용 하려면 필요 합니다. 이러한 중요 한 가지 정보 라고 *비밀*합니다. 소스 코드에서 암호를 포함 하지 않도록 고 분명 하지 않는 소스 제어에서 비밀 정보를 저장 한 것이 좋습니다. 대신 보다 안전한 위치에서 비밀 정보를 읽을 수는 ASP.NET Core 구성 모델을 사용 해야 합니다.

개발에 액세스 하 고 서로 다른 개인 비밀 이러한 다양 한 집합에 액세스 해야 하기 때문에 프로덕션 리소스에 액세스할 때 사용 되는 리소스를 준비에 대 한 암호를 두십시오. 개발 중에 사용 되는 암호를 저장 하려면이 방법은 많이 사용 하거나 환경 변수 또는 ASP.NET Core 암호 관리자 도구를 사용 하 여 비밀 정보를 저장 되도록 합니다. 프로덕션 환경에서는 보다 안전한 저장소에 대 한 microservices Azure 키 자격 증명 모음에 암호를 저장할 수 있습니다.

## <a name="storing-secrets-in-environment-variables"></a>환경 변수에서 비밀 정보 저장

로 문자열 기반 보안을 설정 하는 개발자를 위한 한 가지 방법은 소스 코드에서 암호를 유지 하는 [환경 변수](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) 자신의 개발 컴퓨터에 대해 합니다. 환경 변수를 사용 하 여을 암호의 이름의 전체 계층 구조를 포함 하는 환경 변수에 대 한 이름을 입력 (구성 섹션에 중첩 된) 계층적 이름의 비밀 정보를 저장 하는 콜론 (:)으로 구분 합니다.

예를 들어 디버그 로깅을: LogLevel:Default 환경 변수를 설정 합니다. 다음 JSON 파일에서 해당 구성 값에 해당 하는 것:

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

환경 변수에서 이러한 값에 액세스 하려면 응용 프로그램 바로를 IConfigurationRoot 개체를 생성할 때 해당 ConfigurationBuilder에 AddEnvironmentVariables를 호출 해야 합니다.

환경 변수는 일반 텍스트로 저장 저장 일반적으로 하므로 컴퓨터 또는 환경 변수를 사용 하 여 프로세스 손상 된 환경 변수 값 표시 됩니다.

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a>ASP.NET Core 암호 관리자를 사용 하 여 암호 저장

ASP.NET Core [암호 관리자](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) 도구는 소스 코드에서 암호를 유지 하는 또 다른 방법을 제공 합니다. 암호 관리자 도구를 사용 하려면 프로젝트 파일의 Microsoft.Extensions.SecretManager.Tools 패키지에 도구 참조 (DotNetCliToolReference)를 포함 합니다. 해당 종속성 표시 되며 복원 된 후 dotnet 사용자 암호 명령은 명령줄에서 보안의 값을 설정 하려면 사용할 수 있습니다. 이러한 암호는 사용자의 프로필 디렉터리에 (세부 정보는 운영 체제에 따라 다름) 소스 코드에서 JSON 파일에 저장 됩니다.

암호 관리자 도구에 의해 설정 된 암호는 암호를 사용 하는 프로젝트의 UserSecretsId 속성으로 구성 됩니다. 따라서 속성을 설정할 UserSecretsId (아래 코드 조각에 표시)으로 프로젝트 파일의 확인 해야 합니다. 프로젝트에서 고유 하기만 ID로 사용 되는 실제 문자열 중요 하지 않습니다.

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

암호 관리자 사용 하 여 응용 프로그램에서 저장 된 암호를 사용 하 여 AddUserSecrets를 호출 하 여 수행 됩니다&lt;T&gt; ConfigurationBuilder 인스턴스에서 해당 구성의 응용 프로그램에 대 한 암호를 포함 하도록 합니다. 제네릭 매개 변수 T에 적용 되는 UserSecretId 어셈블리에서 형식을 여야 합니다. 일반적으로 AddUserSecrets를 사용 하 여&lt;시작&gt; 괜찮습니다.


>[!div class="step-by-step"]
[이전] (권한 부여-net-microservices-웹-applications.md) [다음] (azure-키-자격 증명 모음-보호-secrets.md)
