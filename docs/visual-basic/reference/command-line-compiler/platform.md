---
title: "/platform (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- platform compiler option [Visual Basic]
- /platform compiler option [Visual Basic]
- -platform compiler option [Visual Basic]
ms.assetid: f9bc61e6-e854-4ae1-87b9-d6244de23fd1
caps.latest.revision: 34
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 98248f378cec211a257f30a8bd7589c61451faf3
ms.contentlocale: ko-kr
ms.lasthandoff: 04/12/2017

---
# <a name="platform-visual-basic"></a><span data-ttu-id="2d2ac-102">/platform(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2d2ac-102">/platform (Visual Basic)</span></span>
<span data-ttu-id="2d2ac-103">출력 파일을 실행할 수 있는 CLR(공용 언어 런타임) 플랫폼 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-103">Specifies which platform version of common language runtime (CLR) can run the output file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2d2ac-104">구문</span><span class="sxs-lookup"><span data-stu-id="2d2ac-104">Syntax</span></span>  
  
```  
/platform:{ x86 | x64 | Itanium | arm | anycpu | anycpu32bitpreferred }  
```  
  
## <a name="arguments"></a><span data-ttu-id="2d2ac-105">인수</span><span class="sxs-lookup"><span data-stu-id="2d2ac-105">Arguments</span></span>  
  
|<span data-ttu-id="2d2ac-106">용어</span><span class="sxs-lookup"><span data-stu-id="2d2ac-106">Term</span></span>|<span data-ttu-id="2d2ac-107">정의</span><span class="sxs-lookup"><span data-stu-id="2d2ac-107">Definition</span></span>|  
|---|---|  
|`x86`|<span data-ttu-id="2d2ac-108">32비트, x86 호환 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-108">Compiles your assembly to be run by the 32-bit, x86-compatible CLR.</span></span>|  
|`x64`|<span data-ttu-id="2d2ac-109">AMD64 또는 EM64T 명령 집합을 지원하는 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-109">Compiles your assembly to be run by the 64-bit CLR on a computer that supports the AMD64 or EM64T instruction set.</span></span>|  
|`Itanium`|<span data-ttu-id="2d2ac-110">Itanium 프로세서 탑재 컴퓨터에서 64비트 CLR에 의해 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-110">Compiles your assembly to be run by the 64-bit CLR on a computer with an Itanium processor.</span></span>|  
|`arm`|<span data-ttu-id="2d2ac-111">ARM(고급 RISC 컴퓨터) 프로세서를 탑재한 컴퓨터에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-111">Compiles your assembly to be run on a computer with an ARM (Advanced RISC Machine) processor.</span></span>|  
|`anycpu`|<span data-ttu-id="2d2ac-112">임의의 플랫폼에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-112">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="2d2ac-113">응용 프로그램은 32비트 버전 Windows에서는 32비트 응용 프로그램으로, 64비트 버전 Windows에서는 64비트 응용 프로그램으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-113">The application will run as a 32-bit application on 32-bit versions of Windows and as a 64-bit application on 64-bit versions of Windows.</span></span> <span data-ttu-id="2d2ac-114">이 플래그가 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-114">This flag is the default value.</span></span>|  
|`anycpu32bitpreferred`|<span data-ttu-id="2d2ac-115">임의의 플랫폼에서 실행되도록 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-115">Compiles your assembly to run on any platform.</span></span> <span data-ttu-id="2d2ac-116">응용 프로그램은 32비트 및 64비트 버전 Windows 둘 다에서 32비트 응용 프로그램으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-116">The application will run as a 32-bit application on both 32-bit and 64-bit versions of Windows.</span></span> <span data-ttu-id="2d2ac-117">이 플래그는 실행 파일(.EXE)에 대해서만 유효하며, 사용하려면 [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)]가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-117">This flag is valid only for executables (.EXE) and requires [!INCLUDE[net_v45](../../../csharp/language-reference/compiler-options/includes/net_v45_md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2d2ac-118">설명</span><span class="sxs-lookup"><span data-stu-id="2d2ac-118">Remarks</span></span>  
 <span data-ttu-id="2d2ac-119">출력 파일의 대상 프로세서 유형을 지정하려면 `/platform` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-119">Use the `/platform` option to specify the type of processor targeted by the output file.</span></span>  
  
 <span data-ttu-id="2d2ac-120">일반적으로 Visual Basic에서 작성된 .NET Framework 어셈블리는 플랫폼에 관계없이 동일하게 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-120">In general, .NET Framework assemblies written in Visual Basic will run the same regardless of the platform.</span></span> <span data-ttu-id="2d2ac-121">그러나 플랫폼별로 동작이 다른 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-121">However, there are some cases that behave differently on different platforms.</span></span> <span data-ttu-id="2d2ac-122">이러한 경우의 일반적인 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-122">These common cases are:</span></span>  
  
-   <span data-ttu-id="2d2ac-123">포인터 형식과 같이 플랫폼에 따라 크기가 달라지는 멤버를 포함하는 구조체</span><span class="sxs-lookup"><span data-stu-id="2d2ac-123">Structures that contain members that change size depending on the platform, such as any pointer type.</span></span>  
  
-   <span data-ttu-id="2d2ac-124">상수 크기를 포함하는 포인터 산술 연산</span><span class="sxs-lookup"><span data-stu-id="2d2ac-124">Pointer arithmetic that includes constant sizes.</span></span>  
  
-   <span data-ttu-id="2d2ac-125">잘못 된 플랫폼 호출 또는 COM 선언 사용 하는 `Integer` <xref:System.IntPtr>.</xref:System.IntPtr> 대신 핸들에 대 한</span><span class="sxs-lookup"><span data-stu-id="2d2ac-125">Incorrect platform invoke or COM declarations that use `Integer` for handles instead of <xref:System.IntPtr>.</span></span>  
  
-   <span data-ttu-id="2d2ac-126">캐스팅 <xref:System.IntPtr>를 `Integer`.</xref:System.IntPtr></span><span class="sxs-lookup"><span data-stu-id="2d2ac-126">Casting <xref:System.IntPtr> to `Integer`.</span></span>  
  
-   <span data-ttu-id="2d2ac-127">일부 플랫폼에만 있는 구성 요소를 통한 플랫폼 호출 또는 COM interop 사용</span><span class="sxs-lookup"><span data-stu-id="2d2ac-127">Using platform invoke or COM interop with components that do not exist on all platforms.</span></span>  
  
 <span data-ttu-id="2d2ac-128">**/platform** 옵션 프로그램 코드를 실행할 아키텍처에 대 한 가정을 알고 있는 경우 몇 가지 문제를 완화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-128">The **/platform** option will mitigate some issues if you know you have made assumptions about the architecture your code will run on.</span></span> <span data-ttu-id="2d2ac-129">구체적으로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-129">Specifically:</span></span>  
  
-   <span data-ttu-id="2d2ac-130">응용 프로그램이 32비트 컴퓨터에서 실행되는데 64비트 플랫폼을 대상으로 지정하는 경우에는 오류 메시지가 훨씬 더 일찍 표시되며, 이 스위치를 사용하지 않아 발생하는 오류보다는 문제 자체에 대한 내용이 중점적으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-130">If you decide to target a 64-bit platform, and the application is run on a 32-bit machine, the error message comes much earlier and is more targeted at the problem than the error that occurs without using this switch.</span></span>  
  
-   <span data-ttu-id="2d2ac-131">옵션에 대해 `x86` 플래그를 설정한 후 응용 프로그램을 64비트 컴퓨터에서 실행하면 응용 프로그램이 기본적으로 실행되지 않고 WOW 하위 시스템에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-131">If you set the `x86` flag on the option and the application is subsequently run on a 64-bit machine, the application will run in the WOW subsystem instead of running natively.</span></span>  
  
 <span data-ttu-id="2d2ac-132">64비트 Windows 운영 체제:</span><span class="sxs-lookup"><span data-stu-id="2d2ac-132">On a 64-bit Windows operating system:</span></span>  
  
-   <span data-ttu-id="2d2ac-133">`/platform:x86`으로 컴파일된 어셈블리는 WOW64에서 실행되는 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-133">Assemblies compiled with `/platform:x86` will execute on the 32-bit CLR running under WOW64.</span></span>  
  
-   <span data-ttu-id="2d2ac-134">`/platform:anycpu`로 컴파일된 실행 파일은 64비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-134">Executables compiled with the `/platform:anycpu` will execute on the 64-bit CLR.</span></span>  
  
-   <span data-ttu-id="2d2ac-135">`/platform:anycpu`로 컴파일된 DLL은 이 DLL이 로드된 프로세스와 동일한 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-135">A DLL compiled with the `/platform:anycpu` will execute on the same CLR as the process into which it loaded.</span></span>  
  
-   <span data-ttu-id="2d2ac-136">`/platform:anycpu32bitpreferred`로 컴파일된 실행 파일은 32비트 CLR에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-136">Executables that are compiled with `/platform:anycpu32bitpreferred` will execute on the 32-bit CLR.</span></span>  
  
 <span data-ttu-id="2d2ac-137">64 비트 버전의 Windows에서 실행할 응용 프로그램을 개발 하는 방법에 대 한 자세한 내용은 참조 [64 비트 응용 프로그램](https://msdn.microsoft.com/library/ms241064)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-137">For more information about how to develop an application to run on a 64-bit version of Windows, see [64-bit Applications](https://msdn.microsoft.com/library/ms241064).</span></span>  
  
### <a name="to-set-platform-in-the-visual-studio-ide"></a><span data-ttu-id="2d2ac-138">Visual Studio IDE에서 /platform을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="2d2ac-138">To set /platform in the Visual Studio IDE</span></span>  
  
1.  <span data-ttu-id="2d2ac-139">**솔루션 탐색기**, 프로젝트를 선택한 열고는 **프로젝트** , 메뉴를 클릭 한 다음 **속성**합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-139">In **Solution Explorer**, choose the project, open the **Project** menu, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="2d2ac-140">자세한 내용은 참조 [NIB: 프로젝트 디자이너를 사용 하 여 프로젝트 속성 관리](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-140">For more information, see [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/en-us/983f3c18-832f-4666-afec-74b716ff3e0e).</span></span>  
  
2.  <span data-ttu-id="2d2ac-141">에 **컴파일** 탭을 선택 하거나 선택을 취소는 **32 비트 선호** 확인란 또는 **대상 CPU** 목록에서 값을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-141">On the **Compile** tab, select or clear the **Prefer 32-bit** check box, or, in the **Target CPU** list, choose a value.</span></span>  
  
     <span data-ttu-id="2d2ac-142">자세한 내용은 참조 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic)합니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-142">For more information, see [Compile Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/compile-page-project-designer-visual-basic).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2d2ac-143">예제</span><span class="sxs-lookup"><span data-stu-id="2d2ac-143">Example</span></span>  
 <span data-ttu-id="2d2ac-144">다음 예제에서는 `/platform` 컴파일러 옵션을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2d2ac-144">The following example illustrates how to use the `/platform` compiler option.</span></span>  
  
```  
vbc /platform:x86 myFile.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="2d2ac-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2d2ac-145">See Also</span></span>  
 <span data-ttu-id="2d2ac-146">[/target (Visual Basic)](target.md) </span><span class="sxs-lookup"><span data-stu-id="2d2ac-146">[/target (Visual Basic)](target.md) </span></span>  
<span data-ttu-id="2d2ac-147"> [Visual Basic 명령줄 컴파일러](index.md) </span><span class="sxs-lookup"><span data-stu-id="2d2ac-147"> [Visual Basic Command-Line Compiler](index.md) </span></span>  
<span data-ttu-id="2d2ac-148"> [샘플 컴파일 명령줄](sample-compilation-command-lines.md)</span><span class="sxs-lookup"><span data-stu-id="2d2ac-148"> [Sample Compilation Command Lines](sample-compilation-command-lines.md)</span></span>
