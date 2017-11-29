---
title: "WCF 개발 도구 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 054adb87-c244-4d5a-83d1-0b2b44bd454b
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f752d2aa2621ff650c864b2aca0928c5244c4917
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="using-the-wcf-development-tools"></a><span data-ttu-id="353e7-102">WCF 개발 도구 사용</span><span class="sxs-lookup"><span data-stu-id="353e7-102">Using the WCF Development Tools</span></span>
<span data-ttu-id="353e7-103">이 단원에서는 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 서비스를 개발하는 데 사용할 수 있는 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)][!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 개발 도구에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-103">This section describes the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[indigo1](../../../includes/indigo1-md.md)] development tools that can assist you in developing your [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]service.</span></span>  
  
 <span data-ttu-id="353e7-104">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 템플릿을 기반으로 사용하여 서비스를 직접 신속하게 빌드한 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트와 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트를 사용하여 서비스를 디버깅하고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-104">You can use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] templates as a foundation to quickly build your own service, then use [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host and [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client to debug and test your service.</span></span> <span data-ttu-id="353e7-105">이러한 도구를 함께 사용하면 디버그 및 테스트를 원활하고 빠르게 수행할 수 있으며 초기 단계에서 호스팅 모델에 주력할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-105">These tools together provide a fast and seamless debug and testing cycle, and preclude the need to commit to a hosting model at an early stage.</span></span>  
  
## <a name="the-wcf-developer-tools"></a><span data-ttu-id="353e7-106">WCF 개발자 도구</span><span class="sxs-lookup"><span data-stu-id="353e7-106">The WCF Developer Tools</span></span>  
 [<span data-ttu-id="353e7-107">WCF Visual Studio 템플릿</span><span class="sxs-lookup"><span data-stu-id="353e7-107">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
  
 <span data-ttu-id="353e7-108">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에서 미리 정의된 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 프로젝트 및 항목 템플릿을 사용하여 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스와 관련 응용 프로그램을 신속하게 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-108">You can use the predefined [!INCLUDE[indigo2](../../../includes/indigo2-md.md)][!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] project and item templates in [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] to quickly build [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services and surrounding applications.</span></span>  
  
 [<span data-ttu-id="353e7-109">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="353e7-109">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
  
 <span data-ttu-id="353e7-110">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트(WcfSvcHost.exe)를 사용하면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 디버거를 시작(F5)하여 구현한 서비스를 자동으로 호스팅하고 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-110">The [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (WcfSvcHost.exe) allows you to launch the [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] debugger (F5) to automatically host and test a service you have implemented.</span></span> <span data-ttu-id="353e7-111">그런 다음 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 테스트 클라이언트(wcfTestClient.exe) 또는 자체 클라이언트로 서비스를 테스트하여 잠재적인 오류를 찾아 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-111">You can then test the service using the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Test Client (wcfTestClient.exe) or your own client to find and fix any potential errors.</span></span>  
  
 [<span data-ttu-id="353e7-112">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="353e7-112">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)  
  
 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]<span data-ttu-id="353e7-113"> 테스트 클라이언트(WcfTestClient.exe)는 임의 형식의 매개 변수를 입력하고, 서비스에 해당 입력 내용을 전송하고, 서비스에서 되돌려 보내는 응답을 보는 데 사용할 수 있는 GUI 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-113"> Test Client (WcfTestClient.exe) is a GUI tool that allows you to input parameters of arbitrary types, submit that input to the service, and view the response the service sends back.</span></span> <span data-ttu-id="353e7-114">[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트와 이 도구를 함께 사용하면 서비스를 매끄럽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-114">It provides a seamless service testing experience when combined with [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host.</span></span>  
  
 [<span data-ttu-id="353e7-115">XML에서 데이터 형식 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="353e7-115">Generating Data Type Classes from XML</span></span>](../../../docs/framework/wcf/generating-data-type-classes-from-xml.md)  
  
 <span data-ttu-id="353e7-116">클립보드에 저장된 XML 데이터는 코드 페이지로 붙여 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-116">XML data stored in the clipboard can be pasted into a code page.</span></span> <span data-ttu-id="353e7-117">데이터에 정의된 클래스는 코드 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-117">The classes defined in the data will be converted to code types.</span></span>  
  
## <a name="using-the-tools-without-administrator-privilege"></a><span data-ttu-id="353e7-118">관리자 권한 없이 도구 사용</span><span class="sxs-lookup"><span data-stu-id="353e7-118">Using the Tools without Administrator privilege</span></span>  
 <span data-ttu-id="353e7-119">관리자 권한이 없는 사용자도 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스를 개발할 수 있도록 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]를 설치하는 동안 "http://+:8731/Design_Time_Addresses" 네임스페이스에 대한 ACL(액세스 제어 목록)이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-119">To enable users without administrator privilege to develop [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] services, an ACL (Access Control List) is created for the namespace "http://+:8731/Design_Time_Addresses" during the installation of [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)].</span></span> <span data-ttu-id="353e7-120">ACL은 (UI)로 설정되며 시스템에 로그온한 모든 대화식 사용자를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-120">The ACL is set to (UI), which includes all interactive users logged on to the machine.</span></span> <span data-ttu-id="353e7-121">관리자는 이 ACL에서 사용자를 추가 또는 제거하거나 추가 포트를 열 수 있습니다. WCF 또는 WF 템플릿에서 이 ACL을 사용하여 데이터를 기본 구성으로 보내거나 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-121">Administrators can add or remove users from this ACL, or open additional ports.This ACL enables WCF or WF templates to send and receive data in their default configuration.</span></span> <span data-ttu-id="353e7-122">또한 관리자 권한이 없는 사용자가 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 자동 호스트(wcfSvcHost.exe)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-122">It also enables users to use the [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] Service Auto Host (wcfSvcHost.exe) without granting them administrator privileges.</span></span>  
  
 <span data-ttu-id="353e7-123">[!INCLUDE[wv](../../../includes/wv-md.md)]의 강화된 관리자 계정으로 Netsh.exe를 사용하여 액세스 권한을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-123">You can modify access using the Netsh.exe tool in [!INCLUDE[wv](../../../includes/wv-md.md)] under the elevated administrator account.</span></span> <span data-ttu-id="353e7-124">다음은 Netsh.exe를 사용하는 예입니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-124">The following is an example of using Netsh.exe.</span></span>  
  
```  
netsh http add urlacl url=http://+:8001/MyService user=<domain>\<user>  
```  
  
 [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="353e7-125">Netsh.exe, 참조 [Netsh.exe 도구 및 명령줄 스위치를 사용 하는 방법을](http://go.microsoft.com/fwlink/?LinkId=97877)합니다.</span><span class="sxs-lookup"><span data-stu-id="353e7-125"> Netsh.exe, see [How to Use the Netsh.exe Tool and Command-Line Switches](http://go.microsoft.com/fwlink/?LinkId=97877).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="353e7-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="353e7-126">See Also</span></span>  
 [<span data-ttu-id="353e7-127">WCF Visual Studio 템플릿</span><span class="sxs-lookup"><span data-stu-id="353e7-127">WCF Visual Studio Templates</span></span>](../../../docs/framework/wcf/wcf-vs-templates.md)  
 [<span data-ttu-id="353e7-128">WCF 서비스 호스트(WcfSvcHost.exe)</span><span class="sxs-lookup"><span data-stu-id="353e7-128">WCF Service Host (WcfSvcHost.exe)</span></span>](../../../docs/framework/wcf/wcf-service-host-wcfsvchost-exe.md)  
 [<span data-ttu-id="353e7-129">WCF 테스트 클라이언트(WcfTestClient.exe)</span><span class="sxs-lookup"><span data-stu-id="353e7-129">WCF Test Client (WcfTestClient.exe)</span></span>](../../../docs/framework/wcf/wcf-test-client-wcftestclient-exe.md)
