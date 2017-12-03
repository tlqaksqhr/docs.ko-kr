---
title: "방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0d820fb-41c2-45b8-8f22-0fa5aeebbbaa
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9aeeccc42d5fbbed34ffedf01712b208c98ec58e
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-use-svcutilexe-to-validate-compiled-service-code"></a><span data-ttu-id="e108c-102">방법: Svcutil.exe를 사용하여 컴파일된 서비스 코드 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="e108c-102">How to: Use Svcutil.exe to Validate Compiled Service Code</span></span>
<span data-ttu-id="e108c-103">사용할 수는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 서비스를 호스팅하지 않고 서비스 구현 및 구성에 오류를 검색 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-103">You can use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to detect errors in service implementations and configurations without hosting the service.</span></span>  
  
### <a name="to-validate-a-service"></a><span data-ttu-id="e108c-104">서비스의 유효성을 검사하려면</span><span class="sxs-lookup"><span data-stu-id="e108c-104">To validate a service</span></span>  
  
1.  <span data-ttu-id="e108c-105">서비스를 실행 파일과 하나 이상의 종속 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-105">Compile your service into an executable file and one or more dependent assemblies.</span></span>  
  
2.  <span data-ttu-id="e108c-106">SDK 명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-106">Open an SDK command prompt</span></span>  
  
3.  <span data-ttu-id="e108c-107">명령 프롬프트에서 다음 형식을 사용하여 Svcutil.exe 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-107">At the command prompt, launch the Svcutil.exe tool using the following format.</span></span> <span data-ttu-id="e108c-108">서비스 Validationsection 다양 한 매개 변수에 대 한 자세한 내용은 참조는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 항목입니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-108">For more information on the various parameters, see the Service Validationsection of the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) topic.</span></span>  
  
    ```  
    svcutil.exe /validate /serviceName:<serviceConfigName>  <assemblyPath>*  
    ```  
  
     <span data-ttu-id="e108c-109">유효성을 검사할 서비스의 구성 이름을 나타내려면 `/serviceName` 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-109">You must use the `/serviceName` option to indicate the configuration name of the service you want to validate.</span></span>  
  
     <span data-ttu-id="e108c-110">`assemblyPath` 인수는 유효성을 검사할 서비스 형식이 포함된 하나 이상의 어셈블리와 서비스에 대한 실행 파일 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-110">The `assemblyPath` argument specifies the path to the executable file for the service and one or more assemblies that contain the service types to be validated.</span></span> <span data-ttu-id="e108c-111">서비스 구성을 제공하려면 실행 가능한 어셈블리에 연결된 구성 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-111">The executable assembly must have an associated configuration file to provide the service configuration.</span></span> <span data-ttu-id="e108c-112">표준 명령줄 와일드카드를 사용하여 여러 어셈블리를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-112">You can use standard command-line wildcards to provide multiple assemblies.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e108c-113">예제</span><span class="sxs-lookup"><span data-stu-id="e108c-113">Example</span></span>  
 <span data-ttu-id="e108c-114">다음 명령은 myServiceHost.exe 실행 파일에 구현된 myServiceName 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-114">The following command the service myServiceName implemented in the myServiceHost.exe executable file.</span></span>  <span data-ttu-id="e108c-115">서비스(myServiceHost.exe.config)에 대한 구성 파일이 자동으로 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="e108c-115">The configuration file for the service (myServiceHost.exe.config) is automatically loaded.</span></span>  
  
```  
svcutil /validate /serviceName:myServiceName myServiceHost.exe  
```  
  
## <a name="see-also"></a><span data-ttu-id="e108c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e108c-116">See Also</span></span>  
 [<span data-ttu-id="e108c-117">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="e108c-117">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
