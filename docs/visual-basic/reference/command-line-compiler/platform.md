---
title: /platform(Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
caps.latest.revision: "34"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4177b9da15bb89f37a7b3cbb27937e09d1c12635
ms.sourcegitcommit: 685143b62385500f59bc36274b8adb191f573a16
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2017
---
# <a name="platform-visual-basic"></a><span data-ttu-id="4d5da-102">/platform(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d5da-102">/platform (Visual Basic)</span></span>
<span data-ttu-id="4d5da-103">출력 파일을 실행할 수 있는 CLR(공용 언어 런타임) 플랫폼 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d5da-104">구문</span><span class="sxs-lookup"><span data-stu-id="4d5da-104">Syntax</span></span>  
  
```  
/platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="4d5da-105">인수</span><span class="sxs-lookup"><span data-stu-id="4d5da-105">Arguments</span></span>  
  
|<span data-ttu-id="4d5da-106">용어</span><span class="sxs-lookup"><span data-stu-id="4d5da-106">Term</span></span>|<span data-ttu-id="4d5da-107">정의</span><span class="sxs-lookup"><span data-stu-id="4d5da-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="4d5da-108">32비트, x86 호환 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="4d5da-109">AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="4d5da-110">Itanium 프로세서 탑재 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="4d5da-111">ARM(고급 RISC 컴퓨터) 프로세서를 탑재한 컴퓨터에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="4d5da-112">임의의 플랫폼에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="4d5da-113">응용 프로그램은 32비트 버전 Windows에서는 32비트 응용 프로그램으로, 64비트 버전 Windows에서는 64비트 응용 프로그램으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="4d5da-114">이 플래그가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="4d5da-115">임의의 플랫폼에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="4d5da-116">응용 프로그램은 32비트 및 64비트 버전 Windows 둘 다에서 32비트 응용 프로그램으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="4d5da-117">이 플래그는 실행 파일(.EXE)에 대해서만 유효하며, 사용하려면 [!INCLUDE[net_v45](~/includes/net-v45-md.md)]가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-117">This flag is valid only for executables (.EXE) and requires [!INCLUDE[net_v45](~/includes/net-v45-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d5da-118">설명</span><span class="sxs-lookup"><span data-stu-id="4d5da-118">Remarks</span></span>  
 <span data-ttu-id="4d5da-119">출력 파일의 대상 프로세서 유형을 지정하려면 `/platform` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-119">Use the `/platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="4d5da-120">일반적으로 Visual Basic에서 작성된 .NET Framework 어셈블리는 플랫폼에 관계없이 동일하게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="4d5da-121">그러나 플랫폼별로 동작이 다른 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="4d5da-122">이러한 경우의 일반적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-122">These common cases are:</span></span>  
  
-   <span data-ttu-id="4d5da-123">포인터 형식과 같이 플랫폼에 따라 크기가 달라지는 멤버를 포함하는 구조체</span><span class="sxs-lookup"><span data-stu-id="4d5da-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
-   <span data-ttu-id="4d5da-124">상수 크기를 포함하는 포인터 산술 연산</span><span class="sxs-lookup"><span data-stu-id="4d5da-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
-   <span data-ttu-id="4d5da-125">핸들에 대해 `Integer` 대신 <xref:System.IntPtr>를 사용하는 잘못된 플랫폼 호출 또는 COM 선언</span><span class="sxs-lookup"><span data-stu-id="4d5da-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
-   <span data-ttu-id="4d5da-126"><xref:System.IntPtr>을 `Integer`로 캐스팅</span><span class="sxs-lookup"><span data-stu-id="4d5da-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
-   <span data-ttu-id="4d5da-127">일부 플랫폼에만 있는 구성 요소를 통한 플랫폼 호출 또는 COM interop 사용</span><span class="sxs-lookup"><span data-stu-id="4d5da-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="4d5da-128">**/platform** 옵션에 해당 코드가 실행 되는 아키텍처에 대 한 가정을 알고 있는 경우 몇 가지 문제가 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-128">The **/platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="4d5da-129">구체적으로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-129">Specifically:</span></span>  
  
-   <span data-ttu-id="4d5da-130">응용 프로그램이 32비트 컴퓨터에서 실행되는데 64비트 플랫폼을 대상으로 지정하는 경우에는 오류 메시지가 훨씬 더 일찍 표시되며, 이 스위치를 사용하지 않아 발생하는 오류보다는 문제 자체에 대한 내용이 중점적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
-   <span data-ttu-id="4d5da-131">옵션에 대해 `x86` 플래그를 설정한 후 응용 프로그램을 64비트 컴퓨터에서 실행하면 응용 프로그램이 기본적으로 실행되지 않고 WOW 하위 시스템에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="4d5da-132">64비트 Windows 운영 체제:</span><span class="sxs-lookup"><span data-stu-id="4d5da-132">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="4d5da-133">`/platform:x86`으로 컴파일된 어셈블리는 WOW64에서 실행되는 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-133">Assemblies compiled with `/platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="4d5da-134">`/platform:anycpu`로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-134">Executables compiled with the `/platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="4d5da-135">`/platform:anycpu`로 컴파일된 DLL은 이 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-135">A DLL compiled with the `/platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
-   <span data-ttu-id="4d5da-136">`/platform:anycpu32bitpreferred`로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-136">Executables that are compiled with `/platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="4d5da-137">64 비트 버전의 Windows에서 실행 되도록 응용 프로그램을 개발 하는 방법에 대 한 자세한 내용은 참조 [64 비트 응용 프로그램](../../../../docs/framework/64-bit-apps.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](../../../../docs/framework/64-bit-apps.md).</span></span>  
  
### <a name="to-set-platform-in-the-visual-studio-ide"></a><span data-ttu-id="4d5da-138">Visual Studio IDE에서 /platform을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="4d5da-138">To set /platform in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="4d5da-139">**솔루션 탐색기**, 프로젝트를 선택 열고는 **프로젝트** 메뉴를 차례로 클릭 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="4d5da-140">자세한 내용은 참조 [NIB: 프로젝트 디자이너를 사용 하 여 프로젝트 속성 관리](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-140">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="4d5da-141">에 **컴파일** 탭을 선택 하거나 선택을 취소는 **32 비트 선호** 확인란 또는 **대상 CPU** 목록에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-141">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="4d5da-142">자세한 내용은 참조 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-142">For more information, see [Compile Page, Project Designer (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d5da-143">예제</span><span class="sxs-lookup"><span data-stu-id="4d5da-143">Example</span></span>  
 <span data-ttu-id="4d5da-144">다음 예제에서는 `/platform` 컴파일러 옵션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4d5da-144">The following example illustrates how to use the `/platform` compiler option.</span></span>  
  
```  
vbc /platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="4d5da-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4d5da-145">See Also</span></span>  
 [<span data-ttu-id="4d5da-146">/target (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4d5da-146">/target (Visual Basic)</span></span>](target.md)  
 [<span data-ttu-id="4d5da-147">Visual Basic 명령줄 컴파일러</span><span class="sxs-lookup"><span data-stu-id="4d5da-147">Visual Basic Command-Line Compiler</span></span>](index.md)  
 [<span data-ttu-id="4d5da-148">샘플 컴파일 명령줄</span><span class="sxs-lookup"><span data-stu-id="4d5da-148">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
