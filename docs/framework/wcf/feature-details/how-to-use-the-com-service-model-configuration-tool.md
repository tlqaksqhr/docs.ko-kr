---
title: "방법: COM+ 서비스 모델 구성 도구 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: COM+ [WCF], using service model configuration tool
ms.assetid: 7e68cd8d-5fda-4641-b92f-290db874376e
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: dd89a3333ab68b7d580c813a4b7741686b46c5b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-com-service-model-configuration-tool"></a><span data-ttu-id="09c16-102">방법: COM+ 서비스 모델 구성 도구 사용</span><span class="sxs-lookup"><span data-stu-id="09c16-102">How to: Use the COM+ Service Model Configuration Tool</span></span>
<span data-ttu-id="09c16-103">적절한 호스팅 모드를 선택한 다음 COM+ 서비스 모델 구성 명령줄 도구(ComSvcConfig.exe)를 사용하여 웹 서비스로 노출될 응용 프로그램 인터페이스를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-103">Once you have selected an appropriate hosting mode, use the COM+ Service Model Configuration command-line tool (ComSvcConfig.exe) to configure the application interfaces that will be exposed as Web services.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="09c16-104">다음 작업을 수행하려면 컴퓨터의 관리자여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-104">You must be an administrator on the machine to perform any of the following tasks.</span></span>  
  
 <span data-ttu-id="09c16-105">Windows 7 컴퓨터에서 ComSvcConfig.exe를 사용하여 웹 서비스가 최신 서비스 모델 버전(현재 v4.5)을 사용하도록 구성하려면 다음 단계를 따르십시오.</span><span class="sxs-lookup"><span data-stu-id="09c16-105">When using ComSvcConfig.exe on a Windows 7 machine to configure a web service to use the latest service model version (currently v4.5), perform the following steps:</span></span>  
  
1.  <span data-ttu-id="09c16-106">레지스트리 키 설정 `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` 0x00000001의 DWORD 값을</span><span class="sxs-lookup"><span data-stu-id="09c16-106">Set the registry key  `[HKEY_LOCAL_COMPUTER\SOFTWARE\Microsoft\.NETFramework]\OnlyUseLatestCLR` to a DWORD value of 0x00000001</span></span>  
  
2.  <span data-ttu-id="09c16-107">Comsvcconfig.exe를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-107">Run comsvcconfig.exe</span></span>  
  
3.  <span data-ttu-id="09c16-108">1단계에서 추가한 레지스트리 키를 원래 값으로 되돌리거나, 원래 값이 없었던 경우에는 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-108">Revert the registry key added in step 1 back to its original value, or delete it if did not exist.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="09c16-109">이 레지스트리 키를 되돌리는 것은 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-109">Reverting this registry key is important.</span></span> <span data-ttu-id="09c16-110">이 키는 호환성 키이므로</span><span class="sxs-lookup"><span data-stu-id="09c16-110">This is a compatibility key.</span></span> <span data-ttu-id="09c16-111">변경 내용을 되돌리지 않으면 컴퓨터에서 실행 중인 다른 .NET 응용 프로그램에 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-111">Not reverting this change may cause issues with other .NET applications running on the machine).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="09c16-112">Windows 8 컴퓨터 대화 상자에서 /install 라는 메시지가 표시 됩니다 ComSvcConfig.exe를 사용 하는 경우 "PC에 응용 프로그램에 다음 Windows 기능이 필요:.NET Framework 3.5 (.NET 2.0 및.NET 3.0 포함".NET Framework 3.5 설치 되지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="09c16-112">When using ComSvcConfig.exe  /install on a Windows 8 machine a dialog is displayed stating "An app on your PC needs the following Windows feature: .NET Framework 3.5 (includes .NET 2.0 and .NET 3.0" if .NET Framework 3.5 is not installed.</span></span> <span data-ttu-id="09c16-113">이 대화 상자는 무시해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-113">This dialog may be ignored.</span></span> <span data-ttu-id="09c16-114">또는 OnlyUseLatestCLR 레지스트리 키를 DWORD 값 0x00000001로 설정해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-114">Alternatively you can sed the OnlyUseLatestCLR registry key to a DWORD value of 0x00000001</span></span>  
  
### <a name="to-add-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="09c16-115">COM+ 호스팅 모드를 사용하여 웹 서비스로 노출될 인터페이스 집합에 인터페이스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="09c16-115">To add an interface to the set of interfaces that are to be exposed as Web services, using the COM+ hosting mode</span></span>  
  
-   <span data-ttu-id="09c16-116">다음 예제에서처럼 `/install` 및 `/hosting:complus` 옵션을 사용하여 ComSvcConfig를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-116">Run ComSvcConfig using the `/install` and `/hosting:complus` options, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="09c16-117">이 명령은 OnlineStore COM+ 응용 프로그램에 있는 `IFinances` 구성 요소의 `ItemOrders.IFinancial` 인터페이스를 웹 서비스로 노출될 인터페이스 집합에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-117">The command adds the `IFinances` interface of the `ItemOrders.IFinancial` component (from the OnlineStore COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="09c16-118">이 서비스는 COM+ 호스팅 모드를 사용하므로 명시적으로 응용 프로그램을 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-118">The service uses the COM+ hosting mode and therefore requires explicit application activation.</span></span>  
  
     <span data-ttu-id="09c16-119">와일드카드 별표(*) 문자를 구성 요소 및 인터페이스에 사용할 수 있지만 선택한 기능만 웹 서비스로 노출하려는 경우가 있을 수도 있으므로 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="09c16-119">While the wildcard asterisk (*) character can be used for the component and the interface, avoid using it because you might want to expose only selected functionality as a Web service.</span></span> <span data-ttu-id="09c16-120">이 구성 요소의 다음 버전으로 실행하는 경우 와일드카드를 사용하면 구성 구문을 확인했을 때 표시되지 않은 인터페이스를 실수로 노출할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-120">If run with a future version of this component, using the wildcard may unintentionally expose interfaces that may not have been present when the configuration syntax was determined.</span></span>  
  
     <span data-ttu-id="09c16-121">/verbose 옵션은 도구에 경고와 오류를 표시하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-121">The /verbose option instructs the tool to display warnings in addition to any errors.</span></span>  
  
     <span data-ttu-id="09c16-122">노출된 서비스에 대한 계약에 `IFinances` 인터페이스의 모든 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-122">The contract for the exposed service will contain all of the methods from the `IFinances` interface.</span></span>  
  
### <a name="to-add-only-specific-methods-from-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-com-hosting-mode"></a><span data-ttu-id="09c16-123">COM+ 호스팅 모드를 사용하여 웹 서비스로 노출될 인터페이스 집합에 인터페이스의 특정 메서드만 추가하려면</span><span class="sxs-lookup"><span data-stu-id="09c16-123">To add only specific methods from an interface to the set of interfaces that are to be exposed as Web services, using the COM+ hosting mode</span></span>  
  
-   <span data-ttu-id="09c16-124">다음 예제에서처럼 `/install` 및 `/hosting:complus` 옵션에 필수 메서드의 명시적 명명을 사용하여 ComSvcConfig를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-124">Run ComSvcConfig using the `/install` and `/hosting:complus` options with explicit naming of the required methods, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineStore /contract:ItemOrders.Financial,IFinances.{Credit,Debit} /hosting:complus /verbose  
    ```  
  
     <span data-ttu-id="09c16-125">이 명령은 `Credit` 인터페이스의 `Debit` 및 `IFinances` 메서드만 노출된 서비스 계약에 작업으로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-125">The command adds only the `Credit` and `Debit` methods from the `IFinances` interface as operations to the exposed service contract.</span></span> <span data-ttu-id="09c16-126">인터페이스의 다른 모든 메서드는 계약에서 생략되고 웹 서비스 클라이언트에서 호출될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-126">All other methods on the interface will be omitted from the contract and will not be callable from Web service clients.</span></span>  
  
### <a name="to-add-an-interface-to-the-set-of-interfaces-that-are-to-be-exposed-as-web-services-using-the-web-hosting-mode"></a><span data-ttu-id="09c16-127">웹 호스팅 모드를 사용하여 웹 서비스로 노출될 인터페이스 집합에 인터페이스를 추가하려면</span><span class="sxs-lookup"><span data-stu-id="09c16-127">To add an interface to the set of interfaces that are to be exposed as Web services, using the Web hosting mode</span></span>  
  
-   <span data-ttu-id="09c16-128">다음 예제에서처럼 `/install` 옵션 및 `/hosting:was` 옵션을 사용하여 ComSvcConfig를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-128">Run ComSvcConfig using the `/install` option and the `/hosting:was` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /install /application:OnlineWarehouse /contract:ItemInventory.Warehouse,IStockLevels /hosting:was /webDirectory:root/OnlineWarehouse /mex /verbose  
    ```  
  
     <span data-ttu-id="09c16-129">이 명령은 OnlineWarehouse COM+ 응용 프로그램에 있는 `IStockLevels` 구성 요소의 `ItemInventory.Warehouse` 인터페이스를 웹 서비스로 노출될 인터페이스의 집합에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-129">The command adds the `IStockLevels` interface on the `ItemInventory.Warehouse` component (from the OnlineWarehouse COM+ application) to the set of interfaces that will be exposed as Web services.</span></span> <span data-ttu-id="09c16-130">이 서비스는 COM+가 아닌 IIS의 OnlineWarehouse 가상 디렉터리에서 웹 호스팅되므로 필요한 경우 응용 프로그램이 자동으로 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-130">The service is Web hosted in the OnlineWarehouse virtual directory of IIS rather than in COM+, and thus the application is automatically activated as required.</span></span>  
  
     <span data-ttu-id="09c16-131">웹 호스팅 in-process 구성을 사용하려면 구성 요소 서비스 관리 콘솔을 사용하여 서버 응용 프로그램이 아닌 라이브러리 응용 프로그램으로 실행되도록 COM+ 응용 프로그램을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-131">To use the Web-hosted in-process configuration, the COM+ application must be configured to run as a Library application rather than a Server application using the Component Services administration console.</span></span> <span data-ttu-id="09c16-132">서버 응용 프로그램으로 구성된 응용 프로그램은 표준 웹 호스팅 모드를 사용하고 프로세스 홉을 수행하여 각 요청을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-132">Applications configured as Server applications use the standard Web-hosted mode and incur a process hop to process each request.</span></span>  
  
     <span data-ttu-id="09c16-133">`/mex` 옵션은 같은 전송을 응용 프로그램의 서비스 끝점으로 사용하는 MEX(메타데이터 교환) 서비스 끝점을 추가하여 서비스에서 계약 정의를 검색하려는 클라이언트를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-133">The `/mex` option adds an additional Metadata Exchange (MEX) service endpoint that uses the same transport as the application's service endpoint to support clients that want to retrieve a contract definition from the service.</span></span>  
  
### <a name="to-remove-a-web-service-for-a-specified-interface"></a><span data-ttu-id="09c16-134">지정된 인터페이스에 대한 웹 서비스를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="09c16-134">To remove a Web service for a specified interface</span></span>  
  
-   <span data-ttu-id="09c16-135">다음 예제에서처럼 `/uninstall` 옵션을 사용하여 ComSvcConfig를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-135">Run ComSvcConfig using the `/uninstall` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /uninstall /application:OnlineStore /contract:ItemOrders.Financial,IFinances /hosting:complus  
    ```  
  
     <span data-ttu-id="09c16-136">이 명령은 OnlineStore COM+ 응용 프로그램의 `IFinances` 구성 요소에서 `ItemOrders.Financial` 인터페이스를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-136">The command removes the `IFinances` interface on the `ItemOrders.Financial` component (from the OnlineStore COM+ application).</span></span>  
  
### <a name="to-list-currently-exposed-interfaces"></a><span data-ttu-id="09c16-137">현재 노출된 인터페이스를 나열하려면</span><span class="sxs-lookup"><span data-stu-id="09c16-137">To list currently exposed interfaces</span></span>  
  
-   <span data-ttu-id="09c16-138">다음 예제에서처럼 `/list` 옵션을 사용하여 ComSvcConfig를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-138">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /list  
    ```  
  
     <span data-ttu-id="09c16-139">이 명령은 현재 노출된 인터페이스와 함께 로컬 컴퓨터에 적용되는 해당 주소 및 바인딩 세부 내용을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-139">The command lists the currently exposed interfaces, along with the corresponding address and binding details, scoped to the local machine.</span></span>  
  
### <a name="to-list-specific-currently-exposed-interfaces"></a><span data-ttu-id="09c16-140">현재 노출된 특정 인터페이스를 나열하려면</span><span class="sxs-lookup"><span data-stu-id="09c16-140">To list specific currently exposed interfaces</span></span>  
  
-   <span data-ttu-id="09c16-141">다음 예제에서처럼 `/list` 옵션을 사용하여 ComSvcConfig를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-141">Run ComSvcConfig using the `/list` option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /list /application:OnlineStore /hosting:complus  
    ```  
  
     <span data-ttu-id="09c16-142">이 명령은 현재 노출된 COM+ 호스팅 인터페이스와 함께 로컬 컴퓨터의 OnlineStore COM+ 응용 프로그램에 대한 해당 주소 및 바인딩 세부 내용을 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-142">The command lists currently exposed COM+-hosted interfaces, along with the corresponding address and binding details, for the OnlineStore COM+ application on the local machine.</span></span>  
  
### <a name="to-display-help-on-the-options-that-can-be-used-with-the-utility"></a><span data-ttu-id="09c16-143">유틸리티에 사용할 수 있는 옵션에 대한 도움말을 표시하려면</span><span class="sxs-lookup"><span data-stu-id="09c16-143">To display help on the options that can be used with the utility</span></span>  
  
-   <span data-ttu-id="09c16-144">다음 예제에서처럼 /?</span><span class="sxs-lookup"><span data-stu-id="09c16-144">Run ComSvcConfig using the /?</span></span> <span data-ttu-id="09c16-145">옵션을 사용하여 ComSvcConfig를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="09c16-145">option, as shown in the following example.</span></span>  
  
    ```  
    ComSvcConfig.exe /?  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="09c16-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09c16-146">See Also</span></span>  
 [<span data-ttu-id="09c16-147">COM+ 응용 프로그램과 통합 개요</span><span class="sxs-lookup"><span data-stu-id="09c16-147">Integrating with COM+ Applications Overview</span></span>](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications-overview.md)
