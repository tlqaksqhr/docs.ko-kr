---
title: "쉽게 디버깅할 수 있도록 이미지 만들기"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- images [.NET Framework], debugging
- executable image for debugging
- debugging [.NET Framework], executable images for
ms.assetid: 7d90ea7a-150f-4f97-98a7-f9c26541b9a3
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 46a9c11f3545e5d2b9f91572a87ee2614810e4d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="making-an-image-easier-to-debug"></a><span data-ttu-id="612c3-102">쉽게 디버깅할 수 있도록 이미지 만들기</span><span class="sxs-lookup"><span data-stu-id="612c3-102">Making an Image Easier to Debug</span></span>
<span data-ttu-id="612c3-103">비관리 코드를 컴파일할 때 IDE 스위치 또는 명령줄 옵션을 설정하여 디버깅할 실행 가능 이미지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-103">When compiling unmanaged code, you can configure an executable image for debugging by setting IDE switches or command-line options.</span></span> <span data-ttu-id="612c3-104">예를 들어 Visual C++에서 /**Zi** 명령줄 옵션을 사용하여 디버그 기호 파일(확장 확장자는 .pdb)을 생성하도록 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-104">For example, you can use the /**Zi** command-line option in Visual C++ to ask it to emit debug symbol files (file extension .pdb).</span></span> <span data-ttu-id="612c3-105">마찬가지로 /**Od** 명령줄 옵션을 사용하면 최적화를 사용하지 않게 설정하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-105">Similarly, the /**Od** command-line option tells the compiler to disable optimization.</span></span> <span data-ttu-id="612c3-106">결과적으로 코드가 더 느리게 실행되지만, 디버그하기가 쉬워지므로 이 옵션은 필수여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-106">The resulting code runs more slowly, but is easier to debug, should this be necessary.</span></span>  
  
 <span data-ttu-id="612c3-107">.NET Framework 관리 코드를 컴파일할 때 Visual C++, Visual Basic 및 C#과 같은 컴파일러가 소스 프로그램을 MSIL(Microsoft Intermediate Language)로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-107">When compiling .NET Framework managed code, compilers such as Visual C++, Visual Basic, and C# compile their source program into Microsoft Intermediate Language (MSIL).</span></span> <span data-ttu-id="612c3-108">그런 다음 MSIL은 실행 직전에 네이티브 기계어 코드로 JIT 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-108">MSIL is subsequently JIT-compiled, just before execution, into native machine code.</span></span> <span data-ttu-id="612c3-109">비관리 코드와 함께 IDE 스위치 또는 명령줄 옵션을 설정하여 디버깅할 실행 가능 이미지를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-109">As with unmanaged code, you can configure an executable image for debugging by setting IDE switches or command-line options.</span></span> <span data-ttu-id="612c3-110">또한 거의 동일한 방식으로 디버깅을 위해 JIT 컴파일을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-110">In addition, you can configure the JIT compilation for debugging in much the same way.</span></span>  
  
 <span data-ttu-id="612c3-111">JIT 구성에는 두 가지 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-111">This JIT configuration has two aspects:</span></span>  
  
-   <span data-ttu-id="612c3-112">추적 정보를 생성하기 위해 JIT 컴파일러를 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-112">You can request the JIT-compiler to generate tracking information.</span></span> <span data-ttu-id="612c3-113">그러면 디버거에서 MSIL 체인을 대응하는 기계어 코드와 일치시키고 지역 변수와 함수 인수가 저장된 위치를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-113">This makes it possible for the debugger to match up a chain of MSIL with its machine code counterpart, and to track where local variables and function arguments are stored.</span></span>  <span data-ttu-id="612c3-114">.NET Framework 버전 2.0에서 JIT 컴파일러는 항상 추적 정보를 생성하므로 요청할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-114">In the .NET Framework version 2.0, the JIT compiler will always generate tracking information, so there is no need to request it.</span></span>  
  
-   <span data-ttu-id="612c3-115">결과적으로 생성되는 기계어 코드를 최적화하지 않도록 JIT 컴파일러에 요청할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-115">You can request the JIT-compiler to not optimize the resulting machine code.</span></span>  
  
 <span data-ttu-id="612c3-116">일반적으로 MSIL을 생성하는 컴파일러는 사용자가 지정하는 명령줄 옵션 또는 IDE 스위치를 기반으로 이러한 JIT 컴파일러 옵션을 적절하게 설정합니다(예: /**Od**).</span><span class="sxs-lookup"><span data-stu-id="612c3-116">Normally, the compiler that generates the MSIL sets these JIT-compiler options appropriately, based upon the IDE switches or command-line options you specify, for example, /**Od**.</span></span>  
  
 <span data-ttu-id="612c3-117">경우에 따라 생성되는 기계어 코드를 더 쉽게 디버깅할 수 있도록 JIT 컴파일러의 동작을 변경하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-117">In some cases, you might want to change the behavior of the JIT compiler so that the machine code it generates is easier to debug.</span></span> <span data-ttu-id="612c3-118">예를 들어, 정품 빌드 또는 제어 최적화를 위해 JIT 추적 정보를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-118">For example, you might want to generate JIT tracking information for a retail build or control optimization.</span></span> <span data-ttu-id="612c3-119">초기화(.ini) 파일을 사용해서도 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-119">You can do so with an initialization (.ini) file.</span></span>  
  
 <span data-ttu-id="612c3-120">예를 들어, 디버깅하려는 어셈블리를 MyApp.exe라고 하면 MyApp.exe와 동일한 폴더에 다음 세 줄을 포함하는 MyApp.ini라는 텍스트 파일을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-120">For example, if the assembly you want to debug is called MyApp.exe, then you can create a text file named MyApp.ini, in the same folder as MyApp.exe, which contains these three lines:</span></span>  
  
```  
[.NET Framework Debugging Control]  
GenerateTrackingInfo=1  
AllowOptimize=0  
```  
  
 <span data-ttu-id="612c3-121">각 옵션의 값은 0 또는 1로 설정되고 비어 있는 옵션은 기본값으로 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-121">You can set the value of each option to 0 or 1, and any absent option defaults to 0.</span></span> <span data-ttu-id="612c3-122">`GenerateTrackingInfo`를 1로 설정하고 `AllowOptimize`를 0으로 설정하면 디버깅이 가장 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-122">Setting `GenerateTrackingInfo` to 1 and `AllowOptimize` to 0 provides the easiest debugging.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612c3-123">.NET Framework 버전 2.0에서 JIT 컴파일러는 `GenerateTrackingInfo`의 값과 상관없이 항상 추적 정보를 생성하지만, `AllowOptimize` 값이 여전히 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-123">In the .NET Framework version 2.0, the JIT compiler always generates tracking information regardless of the value for `GenerateTrackingInfo`; however, the `AllowOptimize` value still has an effect.</span></span> <span data-ttu-id="612c3-124">[Ngen.exe(네이티브 이미지 생성기)](../../../docs/framework/tools/ngen-exe-native-image-generator.md)를 사용하여 최적화하지 않고 네이티브 이미지를 사전 컴파일하는 경우 Ngen.exe가 실행될 때 `AllowOptimize=0`인 대상 폴더에 .ini 파일이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-124">When using the [Ngen.exe (Native Image Generator)](../../../docs/framework/tools/ngen-exe-native-image-generator.md) to precompile the native image without optimization, the .ini file must be present in the target folder with `AllowOptimize=0` when Ngen.exe executes.</span></span> <span data-ttu-id="612c3-125">최적화하지 않고 어셈블리를 사전 컴파일하는 경우 NGen.exe를 다시 실행하여 최적화된 상태로 코드를 다시 컴파일하기 전에 Ngen.exe **/uninstall** 옵션을 사용하여 사전 컴파일된 코드를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-125">If you have precompiled an assembly without optimization, you must remove the precompiled code using the NGen.exe **/uninstall** option before rerunning Ngen.exe to precompile the code as optimized.</span></span> <span data-ttu-id="612c3-126">.ini 파일이 폴더에 없으면 기본적으로 Ngen.exe가 최적화된 상태로 코드를 사전 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-126">If the .ini file is not present in the folder, by default Ngen.exe precompiles the code as optimized.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612c3-127"><xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType>을 통해 어셈블리의 설정을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-127">The <xref:System.Diagnostics.DebuggableAttribute?displayProperty=nameWithType> controls the settings for an assembly.</span></span> <span data-ttu-id="612c3-128">**DebuggableAttribute**에는 JIT 컴파일러를 최적화해야 하는지와 추적 정보를 생성해야 하는지에 관한 설정을 기록하는 두 개의 필드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-128">**DebuggableAttribute** includes two fields that record the settings for whether the JIT compiler should optimize, and/or generate tracking information.</span></span> <span data-ttu-id="612c3-129">.NET Framework 버전 2.0에서 JIT 컴파일러는 항상 추적 정보를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-129">In the .NET Framework version 2.0, the JIT compiler will always generate tracking information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612c3-130">정품 빌드의 경우 컴파일러에서는 **DebuggableAttribute**를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-130">For a retail build, compilers do not set any **DebuggableAttribute**.</span></span> <span data-ttu-id="612c3-131">JIT 컴파일러의 기본 동작은 성능은 가장 높으며 디버깅하기는 가장 어려운 기계어 코드를 생성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-131">The JIT-compiler default behavior is to generate the highest performance, hardest to debug machine code.</span></span> <span data-ttu-id="612c3-132">JIT 추적을 사용하면 성능이 약간 저하되지만 최적화를 사용하지 않게 설정하면 성능이 상당히 저하됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-132">Enabling JIT tracking lowers performance a little, and disabling optimization lowers performance a lot.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612c3-133">**DebuggableAttribute**는 어셈블리에 있는 개별 모듈이 아니라 한 번에 전체 어셈블리에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-133">The **DebuggableAttribute** applies to a whole assembly at a time, not to individual modules within the assembly.</span></span> <span data-ttu-id="612c3-134">따라서 개발 도구에서 사용자 지정 특성을 어셈블리 메타데이터 토큰에 연결하거나, 어셈블리가 이미 생성된 경우 **System.Runtime.CompilerServices.AssemblyAttributesGoHere**라는 클래스에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-134">Development tools must therefore attach custom attributes to the assembly metadata token, if an assembly has already been created, or to the class called **System.Runtime.CompilerServices.AssemblyAttributesGoHere**.</span></span> <span data-ttu-id="612c3-135">그러면 ALink 도구가 각 모듈에서 **DebuggableAttribute** 특성이 일부가 될 어셈블리로 해당 특성을 승격합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-135">The ALink tool will then promote these **DebuggableAttribute** attributes from each module to the assembly they become a part of.</span></span> <span data-ttu-id="612c3-136">충돌이 발생할 경우 ALink 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-136">If there is a conflict, the ALink operation will fail.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="612c3-137">.NET Framework 버전 1.0에서 **/clr** 및 **/Zi** 컴파일러 옵션이 지정된 경우 Microsoft Visual C++ Compiler에서 **DebuggableAttribute**를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-137">In version 1.0 of the .NET Framework, the Microsoft Visual C++ compiler adds the **DebuggableAttribute** when the **/clr** and **/Zi** compiler options are specified.</span></span> <span data-ttu-id="612c3-138">.NET Framework의 버전 1.1에서는 **DebugabbleAttribute**를 코드에 직접 추가하거나 **/ASSEMBLYDEBUG** 링커 옵션을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612c3-138">In version 1.1 of the .NET Framework, you must either add the **DebugabbleAttribute** manually in your code or use the **/ASSEMBLYDEBUG** linker option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="612c3-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="612c3-139">See Also</span></span>  
 [<span data-ttu-id="612c3-140">디버깅, 추적 및 프로파일링</span><span class="sxs-lookup"><span data-stu-id="612c3-140">Debugging, Tracing, and Profiling</span></span>](../../../docs/framework/debug-trace-profile/index.md)  
 [<span data-ttu-id="612c3-141">JIT 연결 디버깅 설정</span><span class="sxs-lookup"><span data-stu-id="612c3-141">Enabling JIT-Attach Debugging</span></span>](../../../docs/framework/debug-trace-profile/enabling-jit-attach-debugging.md)  
 [<span data-ttu-id="612c3-142">프로파일링 설정</span><span class="sxs-lookup"><span data-stu-id="612c3-142">Enabling Profiling</span></span>](http://msdn.microsoft.com/en-us/3b669676-f0e0-4ebf-8674-68986dd2020d)
