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
# <a name="storing-application-secrets-safely-during-development"></a><span data-ttu-id="cf767-104">개발 하는 동안 응용 프로그램 암호를 안전 하 게 저장</span><span class="sxs-lookup"><span data-stu-id="cf767-104">Storing application secrets safely during development</span></span>

<span data-ttu-id="cf767-105">기타 서비스와 보호 된 리소스에 연결 하려면 ASP.NET Core 응용 프로그램 일반적으로 연결 문자열, 암호 또는 중요 한 정보를 포함 하는 다른 자격 증명을 사용 하려면 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-105">To connect with protected resources and other services, ASP.NET Core applications typically need to use connection strings, passwords, or other credentials that contain sensitive information.</span></span> <span data-ttu-id="cf767-106">이러한 중요 한 가지 정보 라고 *비밀*합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-106">These sensitive pieces of information are called *secrets*.</span></span> <span data-ttu-id="cf767-107">소스 코드에서 암호를 포함 하지 않도록 고 분명 하지 않는 소스 제어에서 비밀 정보를 저장 한 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-107">It is a best practice to not include secrets in source code and certainly not to store secrets in source control.</span></span> <span data-ttu-id="cf767-108">대신 보다 안전한 위치에서 비밀 정보를 읽을 수는 ASP.NET Core 구성 모델을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-108">Instead, you should use the ASP.NET Core configuration model to read the secrets from more secure locations.</span></span>

<span data-ttu-id="cf767-109">개발에 액세스 하 고 서로 다른 개인 비밀 이러한 다양 한 집합에 액세스 해야 하기 때문에 프로덕션 리소스에 액세스할 때 사용 되는 리소스를 준비에 대 한 암호를 두십시오.</span><span class="sxs-lookup"><span data-stu-id="cf767-109">You should separate the secrets for accessing development and staging resources from those used for accessing production resources, because different individuals will need access to those different sets of secrets.</span></span> <span data-ttu-id="cf767-110">개발 중에 사용 되는 암호를 저장 하려면이 방법은 많이 사용 하거나 환경 변수 또는 ASP.NET Core 암호 관리자 도구를 사용 하 여 비밀 정보를 저장 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-110">To store secrets used during development, common approaches are to either store secrets in environment variables or by using the ASP.NET Core Secret Manager tool.</span></span> <span data-ttu-id="cf767-111">프로덕션 환경에서는 보다 안전한 저장소에 대 한 microservices Azure 키 자격 증명 모음에 암호를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-111">For more secure storage in production environments, microservices can store secrets in an Azure Key Vault.</span></span>

## <a name="storing-secrets-in-environment-variables"></a><span data-ttu-id="cf767-112">환경 변수에서 비밀 정보 저장</span><span class="sxs-lookup"><span data-stu-id="cf767-112">Storing secrets in environment variables</span></span>

<span data-ttu-id="cf767-113">로 문자열 기반 보안을 설정 하는 개발자를 위한 한 가지 방법은 소스 코드에서 암호를 유지 하는 [환경 변수](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) 자신의 개발 컴퓨터에 대해 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-113">One way to keep secrets out of source code is for developers to set string-based secrets as [environment variables](https://docs.microsoft.com/aspnet/core/security/app-secrets#environment-variables) on their development machines.</span></span> <span data-ttu-id="cf767-114">환경 변수를 사용 하 여을 암호의 이름의 전체 계층 구조를 포함 하는 환경 변수에 대 한 이름을 입력 (구성 섹션에 중첩 된) 계층적 이름의 비밀 정보를 저장 하는 콜론 (:)으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-114">When you use environment variables to store secrets with hierarchical names (those nested in configuration sections), create a name for the environment variables that includes the full hierarchy of the secret’s name, delimited with colons (:).</span></span>

<span data-ttu-id="cf767-115">예를 들어 디버그 로깅을: LogLevel:Default 환경 변수를 설정 합니다. 다음 JSON 파일에서 해당 구성 값에 해당 하는 것:</span><span class="sxs-lookup"><span data-stu-id="cf767-115">For example, setting an environment variable Logging:LogLevel:Default to Debug would be equivalent to a configuration value from the following JSON file:</span></span>

```json
{
    "Logging": {
        "LogLevel": {
            "Default": "Debug"
        }
    }
}
```

<span data-ttu-id="cf767-116">환경 변수에서 이러한 값에 액세스 하려면 응용 프로그램 바로를 IConfigurationRoot 개체를 생성할 때 해당 ConfigurationBuilder에 AddEnvironmentVariables를 호출 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-116">To access these values from environment variables, the application just needs to call AddEnvironmentVariables on its ConfigurationBuilder when constructing an IConfigurationRoot object.</span></span>

<span data-ttu-id="cf767-117">환경 변수는 일반 텍스트로 저장 저장 일반적으로 하므로 컴퓨터 또는 환경 변수를 사용 하 여 프로세스 손상 된 환경 변수 값 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-117">Note that environment variables are generally stored as plain text, so if the machine or process with the environment variables is compromised, the environment variable values will be visible.</span></span>

## <a name="storing-secrets-using-the-aspnet-core-secret-manager"></a><span data-ttu-id="cf767-118">ASP.NET Core 암호 관리자를 사용 하 여 암호 저장</span><span class="sxs-lookup"><span data-stu-id="cf767-118">Storing secrets using the ASP.NET Core Secret Manager</span></span>

<span data-ttu-id="cf767-119">ASP.NET Core [암호 관리자](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) 도구는 소스 코드에서 암호를 유지 하는 또 다른 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-119">The ASP.NET Core [Secret Manager](https://docs.microsoft.com/aspnet/core/security/app-secrets#secret-manager) tool provides another method of keeping secrets out of source code.</span></span> <span data-ttu-id="cf767-120">암호 관리자 도구를 사용 하려면 프로젝트 파일의 Microsoft.Extensions.SecretManager.Tools 패키지에 도구 참조 (DotNetCliToolReference)를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-120">To use the Secret Manager tool, include a tools reference (DotNetCliToolReference) to the Microsoft.Extensions.SecretManager.Tools package in your project file.</span></span> <span data-ttu-id="cf767-121">해당 종속성 표시 되며 복원 된 후 dotnet 사용자 암호 명령은 명령줄에서 보안의 값을 설정 하려면 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-121">Once that dependency is present and has been restored, the dotnet user-secrets command can be used to set the value of secrets from the command line.</span></span> <span data-ttu-id="cf767-122">이러한 암호는 사용자의 프로필 디렉터리에 (세부 정보는 운영 체제에 따라 다름) 소스 코드에서 JSON 파일에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-122">These secrets will be stored in a JSON file in the user’s profile directory (details vary by OS), away from source code.</span></span>

<span data-ttu-id="cf767-123">암호 관리자 도구에 의해 설정 된 암호는 암호를 사용 하는 프로젝트의 UserSecretsId 속성으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-123">Secrets set by the Secret Manager tool are organized by the UserSecretsId property of the project that is using the secrets.</span></span> <span data-ttu-id="cf767-124">따라서 속성을 설정할 UserSecretsId (아래 코드 조각에 표시)으로 프로젝트 파일의 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-124">Therefore, you must be sure to set the UserSecretsId property in your project file (as shown in the snippet below).</span></span> <span data-ttu-id="cf767-125">프로젝트에서 고유 하기만 ID로 사용 되는 실제 문자열 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-125">The actual string used as the ID is not important as long as it is unique in the project.</span></span>

```xml
<PropertyGroup>
    <UserSecretsId>UniqueIdentifyingString</UserSecretsId>
</PropertyGroup>
```

<span data-ttu-id="cf767-126">암호 관리자 사용 하 여 응용 프로그램에서 저장 된 암호를 사용 하 여 AddUserSecrets를 호출 하 여 수행 됩니다&lt;T&gt; ConfigurationBuilder 인스턴스에서 해당 구성의 응용 프로그램에 대 한 암호를 포함 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-126">Using secrets stored with Secret Manager in an application is accomplished by calling AddUserSecrets&lt;T&gt; on the ConfigurationBuilder instance to include secrets for the application in its configuration.</span></span> <span data-ttu-id="cf767-127">제네릭 매개 변수 T에 적용 되는 UserSecretId 어셈블리에서 형식을 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-127">The generic parameter T should be a type from the assembly that the UserSecretId was applied to.</span></span> <span data-ttu-id="cf767-128">일반적으로 AddUserSecrets를 사용 하 여&lt;시작&gt; 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="cf767-128">Usually using AddUserSecrets&lt;Startup&gt; is fine.</span></span>


>[!div class="step-by-step"]
<span data-ttu-id="cf767-129">[이전] (권한 부여-net-microservices-웹-applications.md) [다음] (azure-키-자격 증명 모음-보호-secrets.md)</span><span class="sxs-lookup"><span data-stu-id="cf767-129">[Previous] (authorization-net-microservices-web-applications.md) [Next] (azure-key-vault-protects-secrets.md)</span></span>
