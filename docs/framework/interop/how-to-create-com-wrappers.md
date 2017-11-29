---
title: "방법: COM 래퍼 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b8f8e5ef6aa90b1d31c589a82891f0ca1bfa5469
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="847b9-102">방법: COM 래퍼 만들기</span><span class="sxs-lookup"><span data-stu-id="847b9-102">How to: Create COM Wrappers</span></span>
<span data-ttu-id="847b9-103">[!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] 기능이나 .NET Framework 도구인 Tlbimp.exe 및 Regasm.exe를 사용하여 COM(구성 요소 개체 모델) 래퍼를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-103">You can create Component Object Model (COM) wrappers by using [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="847b9-104">두 메서드는 모두 COM 래퍼의 두 가지 형식을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-104">Both methods generate two types of COM wrappers:</span></span>  
  
-   <span data-ttu-id="847b9-105">관리 코드에서 COM 개체를 실행하기 위한 형식 라이브러리의 [런타임 호출 가능 래퍼](../../../docs/framework/interop/runtime-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="847b9-105">A [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>  
  
-   <span data-ttu-id="847b9-106">네이티브 응용 프로그램에서 관리 개체를 실행하기 위한 필수 레지스트리 설정이 포함된 [COM 호출 가능 래퍼](../../../docs/framework/interop/com-callable-wrapper.md).</span><span class="sxs-lookup"><span data-stu-id="847b9-106">A [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>  
  
 <span data-ttu-id="847b9-107">[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]에서 프로젝트에 COM 래퍼를 참조로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-107">In [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can add the COM wrapper as a reference to your project.</span></span>  
  
## <a name="wrapping-com-objects-in-a-managed-application"></a><span data-ttu-id="847b9-108">관리되는 응용 프로그램에서 COM 개체 래핑</span><span class="sxs-lookup"><span data-stu-id="847b9-108">Wrapping COM Objects in a Managed Application</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="847b9-109">Visual Studio를 사용하여 런타임 호출 가능 래퍼를 만들려면</span><span class="sxs-lookup"><span data-stu-id="847b9-109">To create a runtime callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="847b9-110">관리되는 응용 프로그램에 대한 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-110">Open the project for your managed application.</span></span>  
  
2.  <span data-ttu-id="847b9-111">**프로젝트** 메뉴에서 **모든 파일 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-111">On the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="847b9-112">**프로젝트** 메뉴에서 **참조 추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-112">On the **Project** menu, click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="847b9-113">[참조 추가] 대화 상자에서 **COM** 탭을 클릭하고, 사용할 구성 요소를 선택하고, **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>  
  
     <span data-ttu-id="847b9-114">**솔루션 탐색기**에서 COM 구성 요소는 프로젝트의 참조 폴더에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>  
  
 <span data-ttu-id="847b9-115">이제 COM 개체에 액세스하기 위한 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="847b9-116">먼저 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]의 경우 `Imports` 문을 사용하고 [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)]의 경우 `Using` 문을 사용하여 개체를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-116">You can begin by declaring the object, such as with an `Imports` statement for [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] or a `Using` statement for [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="847b9-117">Microsoft Office 구성 요소를 프로그래밍하려면 먼저 Microsoft 다운로드 센터에서 [Microsoft Office PIA](http://go.microsoft.com/fwlink/?LinkId=50479)(주 Interop 어셈블리)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](http://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="847b9-118">4단계에서는 **Microsoft Word 11.0 개체 라이브러리**와 같이 원하는 Office 제품에 사용 가능한 최신 버전의 개체 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="847b9-119">.NET Framework 도구를 사용하여 런타임 호출 가능 래퍼를 만들려면</span><span class="sxs-lookup"><span data-stu-id="847b9-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="847b9-120">[Tlbimp.exe(형식 라이브러리 가져오기)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-120">Run the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="847b9-121">이 도구는 원본 형식 라이브러리에 정의된 형식의 런타임 메타데이터를 포함하는 어셈블리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrapping-managed-objects-in-a-native-application"></a><span data-ttu-id="847b9-122">네이티브 응용 프로그램에서 관리 개체 래핑</span><span class="sxs-lookup"><span data-stu-id="847b9-122">Wrapping Managed Objects in a Native Application</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="847b9-123">Visual Studio를 사용하여 COM 호출 가능 래퍼를 만들려면</span><span class="sxs-lookup"><span data-stu-id="847b9-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="847b9-124">네이티브 코드에서 실행할 관리되는 클래스에 대한 클래스 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="847b9-125">이 클래스에는 기본 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-125">The class must have a default constructor.</span></span>  
  
     <span data-ttu-id="847b9-126">AssemblyInfo 파일에 어셈블리에 대한 전체 4개 부분 버전 번호가 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="847b9-127">Windows 레지스트리에서 버전을 유지 관리하려면 이 번호가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="847b9-128">버전 번호에 대한 자세한 내용은 [어셈블리 버전 관리](../../../docs/framework/app-domains/assembly-versioning.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="847b9-128">For more information about version numbers, see [Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
2.  <span data-ttu-id="847b9-129">**프로젝트** 메뉴에서 **속성**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-129">On the **Project** menu, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="847b9-130">**컴파일** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-130">Click the **Compile** tab.</span></span>  
  
4.  <span data-ttu-id="847b9-131">**COM interop 등록** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="847b9-132">프로젝트를 빌드하면 COM interop에 대한 어셈블리가 자동으로 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="847b9-133">[!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)]에서 네이티브 응용 프로그램을 빌드할 경우 **프로젝트** 메뉴에서 **참조 추가**를 클릭하여 어셈블리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-133">If you are building a native application in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="847b9-134">.NET Framework 도구를 사용하여 COM 호출 가능 래퍼를 만들려면</span><span class="sxs-lookup"><span data-stu-id="847b9-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="847b9-135">[Regasm.exe(어셈블리 등록 도구)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-135">Run the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
 <span data-ttu-id="847b9-136">이 도구는 어셈블리 메타데이터를 읽고 레지스트리에 필요한 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="847b9-137">따라서 COM 클라이언트는 .NET Framework 클래스를 투명하게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="847b9-138">네이티브 COM 클래스인 것처럼 어셈블리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-138">You can use the assembly as if it were a native COM class.</span></span>  
  
 <span data-ttu-id="847b9-139">디렉터리에 있는 어셈블리에서 Regasm.exe를 실행하고 나서 [Gacutil.exe(전역 어셈블리 캐시 도구)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)를 실행하여 어셈블리를 전역 어셈블리 캐시로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="847b9-140">어셈블리가 다른 곳에 있는지 항상 전역 어셈블리 캐시가 검사되므로 어셈블리를 이동해도 위치 레지스트리 항목이 무효화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="847b9-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="847b9-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="847b9-141">See Also</span></span>  
 [<span data-ttu-id="847b9-142">런타임 호출 가능 래퍼</span><span class="sxs-lookup"><span data-stu-id="847b9-142">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [<span data-ttu-id="847b9-143">COM 호출 가능 래퍼</span><span class="sxs-lookup"><span data-stu-id="847b9-143">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)
