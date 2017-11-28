---
title: "방법: 서비스 모니커 등록 및 구성"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM [WCF], configure service monikers
- COM [WCF], register service monikers
ms.assetid: e5e16c80-8a8e-4eef-af53-564933b651ef
caps.latest.revision: "20"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 86938301d28cbb0293ece4b3e12a2ef2d2a54e69
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-register-and-configure-a-service-moniker"></a><span data-ttu-id="26c5f-102">방법: 서비스 모니커 등록 및 구성</span><span class="sxs-lookup"><span data-stu-id="26c5f-102">How to: Register and Configure a Service Moniker</span></span>
<span data-ttu-id="26c5f-103">형식화된 계약이 있는 COM 응용 프로그램 내에서 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스 모니커를 사용하려면 먼저 필요한 특성을 사용하는 형식을 COM에 등록하고 필요한 바인딩 구성을 사용하여 COM 응용 프로그램과 모니커를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-103">Before using the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service moniker within a COM application with a typed contract, you must register the required attributed types with COM, and configure the COM application and the moniker with the required binding configuration.</span></span>  
  
### <a name="to-register-the-required-attributed-types-with-com"></a><span data-ttu-id="26c5f-104">필요한 특성을 사용하는 형식을 COM에 등록하려면</span><span class="sxs-lookup"><span data-stu-id="26c5f-104">To register the required attributed types with COM</span></span>  
  
1.  <span data-ttu-id="26c5f-105">사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 도구에서 메타 데이터 계약을 검색 하는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-105">Use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) tool to retrieve the metadata contract from the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="26c5f-106">이렇게 하면 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트 어셈블리와 클라이언트 응용 프로그램 구성 파일에 대한 소스 코드가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-106">This generates the source code for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client assembly and a client application configuration file.</span></span>  
  
2.  <span data-ttu-id="26c5f-107">어셈블리의 형식이 `ComVisible`로 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-107">Ensure that the types in the assembly are marked as `ComVisible`.</span></span> <span data-ttu-id="26c5f-108">이렇게 하려면 Visual Studio 프로젝트의 AssemblyInfo.cs 파일에 다음 특성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-108">To do so, add the following attribute to the AssemblyInfo.cs file in your Visual Studio project.</span></span>  
  
    ```  
    [assembly: ComVisible(true)]  
    ```  
  
3.  <span data-ttu-id="26c5f-109">관리되는 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 클라이언트를 강력한 이름의 어셈블리로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-109">Compile the managed [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client as a strong-named assembly.</span></span> <span data-ttu-id="26c5f-110">이렇게 하려면 암호화된 키 쌍으로 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-110">This requires signing with a cryptographic key pair.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="26c5f-111">[강력한 이름으로 어셈블리 서명](http://go.microsoft.com/fwlink/?LinkId=94874) .NET 개발자 가이드에서.</span><span class="sxs-lookup"><span data-stu-id="26c5f-111"> [Signing an Assembly with a Strong Name](http://go.microsoft.com/fwlink/?LinkId=94874) in the .NET Developer's Guide.</span></span>  
  
4.  <span data-ttu-id="26c5f-112">어셈블리 등록(Regasm.exe) 도구에 `/tlb` 옵션을 사용하여 어셈블리의 형식을 COM에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-112">Use the Assembly Registration (Regasm.exe) tool with the `/tlb` option to register the types in the assembly with COM.</span></span>  
  
5.  <span data-ttu-id="26c5f-113">전역 어셈블리 캐시(Gacutil.exe) 도구를 사용하여 어셈블리를 전역 어셈블리 캐시에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-113">Use the Global Assembly Cache (Gacutil.exe) tool to add the assembly to the global assembly cache.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="26c5f-114">어셈블리에 서명하고 전역 어셈블리 캐시에 추가하는 것은 선택적 단계이지만 런타임에 올바른 위치에서 어셈블리를 로드하는 프로세스를 단순화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-114">Signing the assembly and adding it to the Global Assembly Cache are optional steps, but they can simplify the process of loading the assembly from the correct location at runtime.</span></span>  
  
### <a name="to-configure-the-com-application-and-the-moniker-with-the-required-binding-configuration"></a><span data-ttu-id="26c5f-115">필요한 바인딩 구성을 사용하여 COM 응용 프로그램과 모니커를 구성하려면</span><span class="sxs-lookup"><span data-stu-id="26c5f-115">To configure the COM application and the moniker with the required binding configuration</span></span>  
  
-   <span data-ttu-id="26c5f-116">바인딩 정의 배치 (에 의해 생성 된는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 생성 된 클라이언트 응용 프로그램 구성 파일에서) 클라이언트 응용 프로그램의 구성 파일에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-116">Place the binding definitions (generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in the generated client application configuration file) in the client application's configuration file.</span></span> <span data-ttu-id="26c5f-117">예를 들어 이름이 CallCenterClient.exe인 Visual Basic 6.0 실행 파일에 대해 실행 파일과 동일한 디렉터리 내의 CallCenterConfig.exe.config 파일에 구성을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-117">For example, for a Visual Basic 6.0 executable named CallCenterClient.exe, the configuration should be placed in a file named CallCenterConfig.exe.config within the same directory as the executable.</span></span> <span data-ttu-id="26c5f-118">이제 클라이언트 응용 프로그램에서 모니커를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-118">The client application can now use the moniker.</span></span> <span data-ttu-id="26c5f-119">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 표준 바인딩 형식 중 하나를 사용하는 경우 바인딩 구성이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-119">Note that the binding configuration is not required if using one of the standard binding types provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
     <span data-ttu-id="26c5f-120">다음 형식이 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-120">The following type is registered.</span></span>  
  
    ```  
    using System.ServiceModel;  
  
    ...  
  
    [ServiceContract]   
    public interface IMathService   
    {  
    [OperationContract]  
    public int Add(int x, int y);  
    [OperationContract]  
    public int Subtract(int x, int y);  
    }  
    ```  
  
     <span data-ttu-id="26c5f-121">응용 프로그램은 `wsHttpBinding` 바인딩을 사용하여 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-121">The application is exposed using a `wsHttpBinding` binding.</span></span> <span data-ttu-id="26c5f-122">지정된 형식과 응용 프로그램 구성에 대해 다음 예제 모니커 문자열이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-122">For the given type and application configuration, the following example moniker strings are used.</span></span>  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1  
    ```  
  
     `or`  
  
    ```  
    service4:address=http://localhost/MathService, binding=wsHttpBinding, bindingConfiguration=Binding1, contract={36ADAD5A-A944-4d5c-9B7C-967E4F00A090}  
    ```  
  
     <span data-ttu-id="26c5f-123">다음 샘플 코드와 같이 `IMathService` 형식을 포함하는 어셈블리에 대한 참조를 추가한 후 Visual Basic 6.0 응용 프로그램 내에서 이러한 모니커 문자열 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-123">You can use either of these moniker strings from within a Visual Basic 6.0 application, after adding a reference to the assembly that contains the `IMathService` types, as shown in the following sample code.</span></span>  
  
    ```  
    Dim MathProxy As IMathService  
    Dim result As Integer  
  
    Set MathProxy = GetObject( _  
            "service4:address=http://localhost/MathService, _  
            binding=wsHttpBinding, _  
            bindingConfiguration=Binding1")  
  
    result = MathProxy.Add(3, 5)  
    ```  
  
     <span data-ttu-id="26c5f-124">이 예제에서 바인딩 구성 `Binding1`의 정의는 클라이언트 응용 프로그램에 대한 적절한 이름의 구성 파일(예: vb6appname.exe.config)에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-124">In this example, the definition for the binding configuration `Binding1` is stored in a suitably named configuration file for the client application, such as vb6appname.exe.config.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="26c5f-125">C#, C++ 또는 다른 모든 .NET 언어 응용 프로그램으로 유사한 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-125">You can use similar code in a C#, a C++, or any other .NET Language application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="26c5f-126">모니커가 잘못 작동하거나 서비스를 사용할 수 없는 경우 `GetObject`를 호출하면 "구문이 잘못되었습니다"라는 오류가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-126">: If the moniker is malformed or if the service is unavailable, the call to `GetObject` returns an error of "Invalid Syntax".</span></span> <span data-ttu-id="26c5f-127">이 오류가 발생하면 사용하고 있는 모니커가 올바르고 서비스를 사용할 수 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="26c5f-127">If you receive this error, make sure the moniker you are using is correct and the service is available.</span></span>  
  
     <span data-ttu-id="26c5f-128">이 항목에서는 VB 6.0 코드의 서비스 모니커 사용에 중점을 두지만 다른 언어에서 서비스 모니커를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-128">Although this topic focuses on using the service moniker from VB 6.0 code, you can use a service moniker from other languages.</span></span> <span data-ttu-id="26c5f-129">C++ 코드에서 모니커를 사용하는 경우 다음 코드와 같이 "no_namespace named_guids raw_interfaces_only"를 사용하여 Svcutil.exe에서 생성된 어셈블리를  가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-129">When using a moniker from C++ code the Svcutil.exe generated assembly should be imported with "no_namespace named_guids raw_interfaces_only" as shown in the following code.</span></span>  
  
    ```  
    #import "ComTestProxy.tlb" no_namespace named_guids  
    ```  
  
     <span data-ttu-id="26c5f-130">모든 메서드에서 `HResult`를 반환하도록 가져온 인터페이스 정의를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-130">This modifies the imported interface definitions so that all methods return an `HResult`.</span></span> <span data-ttu-id="26c5f-131">다른 모든 반환 값은 출력 매개 변수로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-131">Any other return values are converted into out parameters.</span></span> <span data-ttu-id="26c5f-132">전체 메서드 실행은 동일하게 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-132">The overall execution of the methods remains the same.</span></span> <span data-ttu-id="26c5f-133">이 경우 프록시에서 메서드를 호출할 때 예외의 원인을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-133">This allows you to determine the cause of an exception when calling a method on the proxy.</span></span> <span data-ttu-id="26c5f-134">이 기능은 C++ 코드에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26c5f-134">This functionality is only available from C++ code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26c5f-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="26c5f-135">See Also</span></span>  
 [<span data-ttu-id="26c5f-136">ServiceModel Metadata 유틸리티 도구(Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="26c5f-136">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
