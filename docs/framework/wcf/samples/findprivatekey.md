---
title: FindPrivateKey 샘플-WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 72e2f49ae7c39b4a0486ec053ff1164c2d833cbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33501663"
---
# <a name="findprivatekey-sample"></a><span data-ttu-id="794cb-102">FindPrivateKey 샘플</span><span class="sxs-lookup"><span data-stu-id="794cb-102">FindPrivateKey sample</span></span>

<span data-ttu-id="794cb-103">인증서 저장소에서 특정 X.509 인증서와 연결된 개인 키 파일의 위치 및 이름을 찾기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="794cb-104">FindPrivateKey.exe 도구는 이 과정에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-104">The FindPrivateKey.exe tool facilitates this process.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="794cb-105">FindPrivateKey는 사용하기 전에 컴파일되어야 하는 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="794cb-106">참조는 [FindPrivateKey 프로젝트를 빌드하려면](#to-build-the-findprivatekey-project) FindPrivateKey 도구를 작성 하는 방법에 대 한 지침은 섹션.</span><span class="sxs-lookup"><span data-stu-id="794cb-106">See the [To build the FindPrivateKey project](#to-build-the-findprivatekey-project) section for instructions on how to build the FindPrivateKey tool.</span></span>

<span data-ttu-id="794cb-107">X.509 인증서는 관리자 또는 시스템에 있는 모든 사용자가 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="794cb-108">그러나 인증서를 다른 계정으로 실행 되는 서비스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-108">However, the certificate may be accessed by a service running under a different account.</span></span> <span data-ttu-id="794cb-109">예를 들어 네트워크 서비스 계정입니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-109">For example, the NETWORK SERVICE account.</span></span>

<span data-ttu-id="794cb-110">처음에 인증서를 이 계정으로 설치하지 않았기 때문에 이 계정에 개인 키 파일에 대한 액세스 권한이 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-110">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="794cb-111">FindPrivateKey 도구는 지정된 X.509 인증서의 개인 키 파일 위치를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-111">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="794cb-112">특정 X.509 인증서의 개인 키 파일 위치를 알고 나면 이 파일의 사용 권한을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-112">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>

<span data-ttu-id="794cb-113">FindPrivateKey 도구를 사용 하 여 보안에 대 한 인증서를 사용 하는 예제는 *Setup.bat* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-113">The samples that use certificates for security use the FindPrivateKey tool in the *Setup.bat* file.</span></span> <span data-ttu-id="794cb-114">와 같은 다른 도구를 개인 키 파일을 찾은 사용할 수 있습니다 *Cacls.exe* 파일에 적절 한 액세스 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-114">Once the private key file has been found, you can use other tools such as *Cacls.exe* to set the appropriate access rights onto the file.</span></span>

<span data-ttu-id="794cb-115">자체 호스팅된 실행 파일 등의 사용자 계정으로 Windows Communication Foundation (WCF) 서비스를 실행할 때 파일에 사용자 계정에 읽기 전용 권한이 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-115">When running a Windows Communication Foundation (WCF) service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="794cb-116">인터넷 정보 서비스 (IIS)에서 WCF 서비스를 실행 하는 경우에 서비스가 실행 되는 기본 계정은 IIS 7 및 이전 버전에서 네트워크 서비스 또는 IIS 7.5 이상 버전에서 응용 프로그램 풀 Id입니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-116">When running a WCF service under Internet Information Services (IIS) the default accounts that the service runs under are the NETWORK SERVICE on IIS 7 and earlier versions, or Application Pool Identity on IIS 7.5 and later versions.</span></span> <span data-ttu-id="794cb-117">자세한 내용은 참조 [응용 프로그램 풀 Id](/iis/manage/configuring-security/application-pool-identities)합니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-117">For more information, see [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).</span></span>

## <a name="examples"></a><span data-ttu-id="794cb-118">예제</span><span class="sxs-lookup"><span data-stu-id="794cb-118">Examples</span></span>

<span data-ttu-id="794cb-119">프로세스 읽기 권한이 없는 인증서에 액세스할 때는 다음 예와 비슷한 예외 메시지가 표시:</span><span class="sxs-lookup"><span data-stu-id="794cb-119">When accessing a certificate for which the process doesn't have read privilege, you see an exception message similar to the following example:</span></span>

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

<span data-ttu-id="794cb-120">이 경우 FindPrivateKey 도구를 사용 하 여 개인 키 파일을 찾으려고 하 고 서비스에서 실행 중인 프로세스의 액세스 권한을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-120">When this occurs, use the FindPrivateKey tool to find the private key file, and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="794cb-121">예를 들어 이렇게 Cacls.exe 도구와 함께 다음 예제와 같이:</span><span class="sxs-lookup"><span data-stu-id="794cb-121">For example, this can be done with the Cacls.exe tool as shown in the following example:</span></span>

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="794cb-122">FindPrivateKey 프로젝트를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="794cb-122">To build the FindPrivateKey project</span></span>

<span data-ttu-id="794cb-123">프로젝트를 다운로드 하려면 방문 [Windows Communication Foundation (WCF) 및.NET Framework 4에 대 한 Windows WF (Workflow Foundation) 샘플](https://www.microsoft.com/download/details.aspx?id=21459)합니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-123">To download the project, visit [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).</span></span>

1. <span data-ttu-id="794cb-124">열기 [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] 로 이동 하 고는 *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* 샘플을 설치한 디렉터리 위치 아래의 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-124">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* folder under the directory location where you installed the sample.</span></span>

2. <span data-ttu-id="794cb-125">.sln 파일 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-125">Double-click the .sln file icon to open the file in Visual Studio.</span></span>

3. <span data-ttu-id="794cb-126">에 **빌드** 메뉴 선택 **솔루션 다시 빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-126">In the **Build** menu, select **Rebuild Solution**.</span></span>

4. <span data-ttu-id="794cb-127">솔루션을 빌드하면 FindPrivateKey.exe 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-127">Building the solution generates the file: FindPrivateKey.exe.</span></span>

## <a name="conventionscommand-line-entries"></a><span data-ttu-id="794cb-128">규칙 — 명령줄 항목</span><span class="sxs-lookup"><span data-stu-id="794cb-128">Conventions—Command-Line entries</span></span>

 <span data-ttu-id="794cb-129">"[*옵션*]"는 선택적 매개 변수 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-129">"[*option*]" represents an optional set of parameters.</span></span>

 <span data-ttu-id="794cb-130">"{*옵션*}"는 필수 매개 변수 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-130">"{*option*}" represents a mandatory set of parameters.</span></span>

 <span data-ttu-id="794cb-131">"*option1* &#124; *옵션 2*" 옵션 집합이 사이 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-131">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>

 <span data-ttu-id="794cb-132">"\<*값*>"를 입력 매개 변수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-132">"\<*value*>" represents a parameter value to be entered.</span></span>

## <a name="usage"></a><span data-ttu-id="794cb-133">사용법</span><span class="sxs-lookup"><span data-stu-id="794cb-133">Usage</span></span>

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

<span data-ttu-id="794cb-134">여기서</span><span class="sxs-lookup"><span data-stu-id="794cb-134">Where:</span></span>

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

<span data-ttu-id="794cb-135">명령 프롬프트에서 지정 된 매개 변수가 없는 경우이 도움말 텍스트가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-135">If no parameters are specified at the command prompt, then this help text is displayed.</span></span>

## <a name="examples"></a><span data-ttu-id="794cb-136">예제</span><span class="sxs-lookup"><span data-stu-id="794cb-136">Examples</span></span>

<span data-ttu-id="794cb-137">이 예의 주체 이름 가진 인증서의 파일 이름을 찾아 "CN = localhost", 현재 사용자의 개인 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-137">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

<span data-ttu-id="794cb-138">이 예의 주체 이름 가진 인증서의 파일 이름을 찾아 "CN = localhost", 개인 현재 사용자의 저장 및 전체 디렉터리 경로 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-138">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User and output the full directory path.</span></span>

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

<span data-ttu-id="794cb-139">이 예제에서는 로컬 컴퓨터의 개인 저장소에서 지문이 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"인 인증서의 파일 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="794cb-139">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
