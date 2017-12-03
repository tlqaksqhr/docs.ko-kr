---
title: FindPrivateKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 81ca357ccdcbe76f36f3ba56caf2013a80143728
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="findprivatekey"></a><span data-ttu-id="8c128-102">FindPrivateKey</span><span class="sxs-lookup"><span data-stu-id="8c128-102">FindPrivateKey</span></span>
<span data-ttu-id="8c128-103">인증서 저장소에서 특정 X.509 인증서와 연결된 개인 키 파일의 위치 및 이름을 찾기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-103">It can be difficult to find the location and name of the private key file associated with a specific X.509 certificate in the certificate store.</span></span> <span data-ttu-id="8c128-104">FindPrivateKey.exe 도구는 이 과정에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-104">The FindPrivateKey.exe tool facilitates this process.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8c128-105">FindPrivateKey는 사용하기 전에 컴파일되어야 하는 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-105">FindPrivateKey is a sample that needs to be compiled prior to use.</span></span> <span data-ttu-id="8c128-106">FindPrivateKey 도구를 작성 하는 방법에 "FindPrivateKey 프로젝트를 빌드" 절을 아래의 지침은 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8c128-106">See the "To build the FindPrivateKey project" section below for instructions on how to build the FindPrivateKey tool.</span></span>  
  
 <span data-ttu-id="8c128-107">X.509 인증서는 관리자 또는 시스템에 있는 모든 사용자가 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-107">X.509 certificates are installed by an Administrator or any user in the machine.</span></span> <span data-ttu-id="8c128-108">하지만 다른 계정(예: [!INCLUDE[wxp](../../../../includes/wxp-md.md)]의 ASPNET 또는 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]의 NETWORK SERVICE 계정)에서 실행되는 서비스에서 인증서에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-108">However the certificate may be accessed by a service running under a different account (for example, the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE accounts on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]).</span></span>  
  
 <span data-ttu-id="8c128-109">처음에 인증서를 이 계정으로 설치하지 않았기 때문에 이 계정에 개인 키 파일에 대한 액세스 권한이 없을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-109">This account may not have access to the private key file because the certificate was not installed by it originally.</span></span> <span data-ttu-id="8c128-110">FindPrivateKey 도구는 지정된 X.509 인증서의 개인 키 파일 위치를 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-110">The FindPrivateKey tool gives you the location of a given X.509 Certificate's private key file.</span></span> <span data-ttu-id="8c128-111">특정 X.509 인증서의 개인 키 파일 위치를 알고 나면 이 파일의 사용 권한을 추가하거나 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-111">You can add permissions or remove permissions to this file once you know the location of the particular X.509 certificates' private key file.</span></span>  
  
 <span data-ttu-id="8c128-112">보안에 인증서를 사용하는 샘플의 경우 Setup.bat 파일에서 FindPrivateKey 도구를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-112">The samples that use certificates for security use the FindPrivateKey tool in the Setup.bat file.</span></span> <span data-ttu-id="8c128-113">개인 키 파일을 찾고 나면 Cacls.exe 등의 다른 도구를 사용하여 파일에 적절한 액세스 권한을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-113">Once the private key file has been found you can use other tools such as Cacls.exe to set the appropriate access rights onto the file.</span></span>  
  
 <span data-ttu-id="8c128-114">자체 호스팅 실행 파일 등의 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 사용자 계정에서 실행하는 경우에는 사용자 계정에 파일에 대한 읽기 전용 권한이 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-114">When running a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under a user account, such as a self-hosted executable, ensure that the user account has read-only access to the file.</span></span> <span data-ttu-id="8c128-115">IIS(인터넷 정보 서비스)에서 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스를 실행하는 경우 서비스가 실행되는 기본 계정은 [!INCLUDE[wxp](../../../../includes/wxp-md.md)]의 ASPNET 또는 [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)]의 NETWORK SERVICE이며, 기본적으로 개인 키 파일에 대한 액세스 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-115">When running a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under Internet Information Services (IIS) the default accounts that the service runs under are the ASPNET on [!INCLUDE[wxp](../../../../includes/wxp-md.md)] or the NETWORK SERVICE on [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)], which by default do not have access to the private key file.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8c128-116">예제</span><span class="sxs-lookup"><span data-stu-id="8c128-116">Examples</span></span>  
 <span data-ttu-id="8c128-117">프로세스에 읽기 권한이 없는 인증서에 액세스하면 다음 예와 비슷한 예외 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-117">When accessing a certificate for which the process does not have read privilege, you see an exception message similar to the following example.</span></span>  
  
```  
System.ArgumentException was unhandled  
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."  
Source="System.ServiceModel"  
```  
  
 <span data-ttu-id="8c128-118">이 경우 FindPrivateKey 도구를 사용하여 개인 키 파일을 찾은 다음 서비스가 실행 중인 프로세스의 액세스 권한을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-118">When this occurs use the FindPrivateKey tool to find the private key file and then set the access right for the process that the service is running under.</span></span> <span data-ttu-id="8c128-119">예를 들어, 다음 예와 같이 Cacls.exe 도구를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-119">For example, this can be done with the Cacls.exe tool as shown in the following example.</span></span>  
  
```  
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R  
```  
  
#### <a name="to-build-the-findprivatekey-project"></a><span data-ttu-id="8c128-120">FindPrivateKey 프로젝트를 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="8c128-120">To build the FindPrivateKey project</span></span>  
  
1.  <span data-ttu-id="8c128-121">[!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)]를 열고 샘플을 설치한 디렉터리 위치 아래의 언어별 하위 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-121">Open [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)] and navigate to the language-specific subdirectory under the directory location where you installed the sample.</span></span>  
  
2.  <span data-ttu-id="8c128-122">.sln 파일 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-122">Double-click the .sln file icon to open the file in Visual Studio.</span></span>  
  
3.  <span data-ttu-id="8c128-123">에 **빌드** 메뉴 선택 **솔루션 다시 빌드**합니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-123">In the **Build** menu, select **Rebuild Solution**.</span></span> <span data-ttu-id="8c128-124">클라이언트 프로그램 파일이 client\bin에 빌드되고 서비스 프로그램 파일이 service\bin에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-124">The client program files are built to client\bin and the service program files are built to service\bin.</span></span>  
  
4.  <span data-ttu-id="8c128-125">솔루션을 빌드하면 FindPrivateKey.exe 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-125">Building the solution generates the file: FindPrivateKey.exe.</span></span>  
  
## <a name="conventionscommand-line-entries"></a><span data-ttu-id="8c128-126">규칙—명령줄 항목</span><span class="sxs-lookup"><span data-stu-id="8c128-126">Conventions—Command-Line Entries</span></span>  
 <span data-ttu-id="8c128-127">"[*옵션*]"는 선택적 매개 변수 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-127">"[*option*]" represents an optional set of parameters.</span></span>  
  
 <span data-ttu-id="8c128-128">"{*옵션*}"는 필수 매개 변수 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-128">"{*option*}" represents a mandatory set of parameters.</span></span>  
  
 <span data-ttu-id="8c128-129">"*option1* &#124; *옵션 2*"옵션 집합이 사이 선택을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-129">"*option1* &#124; *option2*" represents a choice between sets of options.</span></span>  
  
 <span data-ttu-id="8c128-130">"\<*값*>"를 입력 매개 변수 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-130">"\<*value*>" represents a parameter value to be entered.</span></span>  
  
## <a name="usage"></a><span data-ttu-id="8c128-131">용도</span><span class="sxs-lookup"><span data-stu-id="8c128-131">Usage</span></span>  
  
```  
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]  
```  
  
 <span data-ttu-id="8c128-132">다음은 각 항목에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-132">Where:</span></span>  
  
```  
       <subjectName> The subject name of the certificate  
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)  
       -f            output file name only  
       -d            output directory only  
       -a            output absolute file name  
```  
  
 <span data-ttu-id="8c128-133">명령 프롬프트에 매개 변수가 지정되지 않은 경우에는 이 도움말 텍스트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-133">If no parameters are specified at the command prompt then this help text is displayed.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="8c128-134">예제</span><span class="sxs-lookup"><span data-stu-id="8c128-134">Examples</span></span>  
 <span data-ttu-id="8c128-135">이 예제에서는 현재 User.FindPrivateKey My CurrentUser -n "CN=localhost"의 개인 저장소에서 제목 이름이 "CN=localhost"인 인증서의 파일 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-135">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current User.FindPrivateKey My CurrentUser -n "CN=localhost".</span></span>  
  
 <span data-ttu-id="8c128-136">이 예제에서는 현재 사용자의 개인 저장소에서 제목 이름이 "CN=localhost"인 인증서의 파일 이름을 찾아 전체 디렉터리 경로를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-136">This example finds the filename of the certificate with a subject name of "CN=localhost", in the Personal store of the Current and output the full directory path.</span></span>  
  
```  
User.FindPrivateKey My CurrentUser -n "CN=localhost" -a  
```  
  
 <span data-ttu-id="8c128-137">이 예제에서는 로컬 컴퓨터의 개인 저장소에서 지문이 "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"인 인증서의 파일 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8c128-137">This example finds the filename of the certificate with a thumbprint of "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", in the Personal store of the Local Computer.</span></span>  
  
```  
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52" –c  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c128-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8c128-138">See Also</span></span>
