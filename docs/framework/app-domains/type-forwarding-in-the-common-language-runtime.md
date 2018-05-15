---
title: 공용 언어 런타임의 형식 전달
ms.date: 03/30/2017
dev_langs:
- csharp
- cpp
helpviewer_keywords:
- assemblies [.NET Framework], type forwarding
- type forwarding
ms.assetid: 51f8ffa3-c253-4201-a3d3-c4fad85ae097
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9945b66f9d9fcdfb075bd48f5f56f30f2fdf7712
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="type-forwarding-in-the-common-language-runtime"></a><span data-ttu-id="a039f-102">공용 언어 런타임의 형식 전달</span><span class="sxs-lookup"><span data-stu-id="a039f-102">Type Forwarding in the Common Language Runtime</span></span>
<span data-ttu-id="a039f-103">형식 전달을 사용하면 원본 어셈블리를 사용하는 응용 프로그램을 다시 컴파일하지 않고도 형식을 다른 어셈블리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-103">Type forwarding allows you to move a type to another assembly without having to recompile applications that use the original assembly.</span></span>  
  
 <span data-ttu-id="a039f-104">예를 들어, 응용 프로그램에서 `Utility.dll`이라는 어셈블리의 `Example` 클래스를 사용할 경우</span><span class="sxs-lookup"><span data-stu-id="a039f-104">For example, suppose an application uses the `Example` class in an assembly named `Utility.dll`.</span></span> <span data-ttu-id="a039f-105">`Utility.dll` 개발자는 어셈블리를 리팩터링하고 해당 과정에서 `Example` 클래스를 다른 어셈블리로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-105">The developers of `Utility.dll` might decide to refactor the assembly, and in the process they might move the `Example` class to another assembly.</span></span> <span data-ttu-id="a039f-106">이전 버전의 `Utility.dll`이 새 버전의 `Utility.dll`과 관련 어셈블리로 바뀐 경우 `Example` 클래스를 사용하는 응용 프로그램은 새 버전의 `Utility.dll`에서 `Example` 클래스를 찾을 수 없기 때문에 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-106">If the old version of `Utility.dll` is replaced by the new version of `Utility.dll` and its companion assembly, the application that uses the `Example` class fails because it cannot locate the `Example` class in the new version of `Utility.dll`.</span></span>  
  
 <span data-ttu-id="a039f-107">`Utility.dll` 개발자는 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> 특성으로 `Example` 클래스에 대한 요청을 전달하여 이를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-107">The developers of `Utility.dll` can avoid this by forwarding requests for the `Example` class, using the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> attribute.</span></span> <span data-ttu-id="a039f-108">새 버전의 `Utility.dll`에 이 특성이 적용된 경우 `Example` 클래스에 대한 요청은 현재 해당 클래스가 들어 있는 어셈블리로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-108">If the attribute has been applied to the new version of `Utility.dll`, requests for the `Example` class are forwarded to the assembly that now contains the class.</span></span> <span data-ttu-id="a039f-109">기존 응용 프로그램은 다시 컴파일하지 않고도 정상적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-109">The existing application continues to function normally, without recompilation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a039f-110">.NET Framework 버전 2.0에서는 Visual Basic으로 작성된 어셈블리의 형식을 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-110">In the .NET Framework version 2.0, you cannot forward types from assemblies written in Visual Basic.</span></span> <span data-ttu-id="a039f-111">그러나 Visual Basic으로 작성된 응용 프로그램에서 전달된 형식을 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-111">However, an application written in Visual Basic can consume forwarded types.</span></span> <span data-ttu-id="a039f-112">즉, 응용 프로그램에서 C# 또는 C++로 코딩된 어셈블리를 사용하며 해당 어셈블리의 형식이 다른 어셈블리로 전달된 경우 Visual Basic 응용 프로그램에서 전달된 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-112">That is, if the application uses an assembly coded in C# or C++, and a type from that assembly is forwarded to another assembly, the Visual Basic application can use the forwarded type.</span></span>  
  
## <a name="forwarding-types"></a><span data-ttu-id="a039f-113">형식 전달</span><span class="sxs-lookup"><span data-stu-id="a039f-113">Forwarding Types</span></span>  
 <span data-ttu-id="a039f-114">다음 네 단계를 통해 형식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-114">There are four steps to forwarding a type:</span></span>  
  
1.  <span data-ttu-id="a039f-115">형식의 소스 코드를 원본 어셈블리에서 대상 어셈블리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-115">Move the source code for the type from the original assembly to the destination assembly.</span></span>  
  
2.  <span data-ttu-id="a039f-116">해당 형식이 있었던 어셈블리에서 이동된 형식에 대해 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-116">In the assembly where the type used to be located, add a <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> for the type that was moved.</span></span> <span data-ttu-id="a039f-117">다음 코드에서는 이동된 `Example` 형식의 특성을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-117">The following code shows the attribute for a type named `Example` that was moved.</span></span>  
  
    ```csharp  
    [assembly:TypeForwardedToAttribute(typeof(Example))]  
    ```  
  
    ```cpp  
    [assembly:TypeForwardedToAttribute(Example::typeid)]  
    ```  
  
3.  <span data-ttu-id="a039f-118">해당 형식이 현재 들어 있는 어셈블리를 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-118">Compile the assembly that now contains the type.</span></span>  
  
4.  <span data-ttu-id="a039f-119">해당 형식이 있었던 어셈블리를 현재 해당 형식이 들어 있는 어셈블리에 대한 참조를 사용하여 다시 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-119">Recompile the assembly where the type used to be located, with a reference to the assembly that now contains the type.</span></span> <span data-ttu-id="a039f-120">예를 들어, 명령줄에서 C# 파일을 컴파일할 경우 [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) 옵션을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-120">For example, if you are compiling a C# file from the command line, use the [/reference (C# Compiler Options)](~/docs/csharp/language-reference/compiler-options/reference-compiler-option.md) option to specify the assembly that contains the type.</span></span> <span data-ttu-id="a039f-121">C++의 경우 소스 파일에서 [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) 지시문을 사용하여 해당 형식이 들어 있는 어셈블리를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a039f-121">In C++, use the [#using](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a) directive in the source file to specify the assembly that contains the type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a039f-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a039f-122">See Also</span></span>  
 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>  
 [<span data-ttu-id="a039f-123">형식 전달(C++/CLI)</span><span class="sxs-lookup"><span data-stu-id="a039f-123">Type Forwarding (C++/CLI)</span></span>](/cpp/windows/type-forwarding-cpp-cli)  
 [<span data-ttu-id="a039f-124">#using 지시문</span><span class="sxs-lookup"><span data-stu-id="a039f-124">#using Directive</span></span>](http://msdn.microsoft.com/library/870b15e5-f361-40a8-ba1c-c57d75c8809a)
