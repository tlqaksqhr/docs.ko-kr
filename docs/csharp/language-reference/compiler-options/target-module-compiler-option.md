---
title: "-target:module(C# 컴파일러 옵션)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 679d659b2806fb875f908cee840a62278c99096f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/19/2018
---
# <a name="-targetmodule-c-compiler-options"></a><span data-ttu-id="f16b3-102">-target:module(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f16b3-102">-target:module (C# Compiler Options)</span></span>
<span data-ttu-id="f16b3-103">이 옵션은 컴파일러에서 어셈블리 매니페스트를 생성하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-103">This option causes the compiler to not generate an assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f16b3-104">구문</span><span class="sxs-lookup"><span data-stu-id="f16b3-104">Syntax</span></span>  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a><span data-ttu-id="f16b3-105">설명</span><span class="sxs-lookup"><span data-stu-id="f16b3-105">Remarks</span></span>  
 <span data-ttu-id="f16b3-106">기본적으로 이 옵션으로 컴파일하여 생성되는 출력 파일의 확장명은 .netmodule입니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-106">By default, the output file created by compiling with this option will have an extension of .netmodule.</span></span>  
  
 <span data-ttu-id="f16b3-107">어셈블리 매니페스트가 없는 파일은 .NET Framework 공용 언어 런타임에서 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-107">A file that does not have an assembly manifest cannot be loaded by the .NET Framework common language runtime.</span></span> <span data-ttu-id="f16b3-108">그러나 이러한 파일은 [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md)을 통해 어셈블리의 어셈블리 매니페스트에 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-108">However, such a file can be incorporated into the assembly manifest of an assembly by means of [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).</span></span>  
  
 <span data-ttu-id="f16b3-109">둘 이상의 모듈이 단일 컴파일에서 생성될 경우 한 모듈의 [내부](../../../csharp/language-reference/keywords/internal.md) 형식을 컴파일에 포함된 다른 모듈에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-109">If more than one module is created in a single compilation, [internal](../../../csharp/language-reference/keywords/internal.md) types in one module will be available to other modules in the compilation.</span></span> <span data-ttu-id="f16b3-110">한 모듈의 코드가 다른 모듈의 `internal` 형식을 참조하는 경우 **-addmodule**을 통해 두 모듈을 모두 어셈블리 매니페스트에 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-110">When code in one module references `internal` types in another module, then both modules must be incorporated into an assembly manifest, by means of **-addmodule**.</span></span>  
  
 <span data-ttu-id="f16b3-111">Visual Studio 개발 환경에서는 모듈을 만들 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-111">Creating a module is not supported in the Visual Studio development environment.</span></span>  
  
 <span data-ttu-id="f16b3-112">이 컴파일러 옵션을 프로그래밍 방식으로 설정하는 방법에 대한 자세한 내용은 <xref:VSLangProj80.ProjectProperties3.OutputType%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f16b3-112">For information on how to set this compiler option programmatically, see <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f16b3-113">예</span><span class="sxs-lookup"><span data-stu-id="f16b3-113">Example</span></span>  
 <span data-ttu-id="f16b3-114">`in.cs`를 컴파일하고 `in.netmodule`을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f16b3-114">Compile `in.cs`, creating `in.netmodule`:</span></span>  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="f16b3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f16b3-115">See Also</span></span>  
 [<span data-ttu-id="f16b3-116">-target(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="f16b3-116">-target (C# Compiler Options)</span></span>](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [<span data-ttu-id="f16b3-117">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="f16b3-117">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
