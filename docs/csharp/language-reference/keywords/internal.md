---
title: "internal(C# 참조)"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- internal_CSharpKeyword
- internal
helpviewer_keywords: internal keyword [C#]
ms.assetid: 6ee0785c-d7c8-49b8-bb72-0a4dfbcb6461
caps.latest.revision: "23"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a3b115022ed2b38dfcfbbfad3c5fc00e0203b255
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="internal-c-reference"></a><span data-ttu-id="782e5-102">internal(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="782e5-102">internal (C# Reference)</span></span>
<span data-ttu-id="782e5-103">`internal` 키워드는 형식 및 형식 멤버에 대한 [액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-103">The `internal` keyword is an [access modifier](../../../csharp/language-reference/keywords/access-modifiers.md) for types and type members.</span></span> 
  
 > <span data-ttu-id="782e5-104">이 페이지에서는 `internal` 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-104">This page covers `internal` access.</span></span> <span data-ttu-id="782e5-105">`internal` 키워드 이기도의 일부로 [ `protected internal` ](./protected-internal.md) 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-105">The `internal` keyword is also part of the [`protected internal`](./protected-internal.md) access modifier.</span></span>
  
<span data-ttu-id="782e5-106">내부 형식 또는 멤버는 다음 예제와 같이 동일한 어셈블리의 파일 내에서만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-106">Internal types or members are accessible only within files in the same assembly, as in this example:</span></span>  
  
```  
public class BaseClass   
{  
    // Only accessible within the same assembly  
    internal static int x = 0;  
}  
```  

 <span data-ttu-id="782e5-107">`internal` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) 및 [액세스 한정자](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="782e5-107">For a comparison of `internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) and [Access Modifiers](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md).</span></span>  
  
 <span data-ttu-id="782e5-108">어셈블리에 대한 자세한 내용은 [어셈블리 및 전역 어셈블리 캐시](../../../csharp/programming-guide/concepts/assemblies-gac/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="782e5-108">For more information about assemblies, see [Assemblies and the Global Assembly Cache](../../../csharp/programming-guide/concepts/assemblies-gac/index.md).</span></span>  
  
 <span data-ttu-id="782e5-109">내부 액세스는 구성 요소 그룹이 나머지 응용 프로그램 코드에 노출되지 않고 비공개 방식으로 상호 작용할 수 있도록 하기 때문에 일반적으로 구성 요소 기반 개발에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-109">A common use of internal access is in component-based development because it enables a group of components to cooperate in a private manner without being exposed to the rest of the application code.</span></span> <span data-ttu-id="782e5-110">예를 들어 그래픽 사용자 인터페이스를 빌드하기 위한 프레임워크는 내부 액세스로 멤버를 사용하여 상호 작용하는 `Control` 및 `Form` 클래스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-110">For example, a framework for building graphical user interfaces could provide `Control` and `Form` classes that cooperate by using members with internal access.</span></span> <span data-ttu-id="782e5-111">이러한 멤버는 internal이므로 프레임워크를 사용하는 코드에 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-111">Since these members are internal, they are not exposed to code that is using the framework.</span></span>  
  
 <span data-ttu-id="782e5-112">정의 시 사용된 어셈블리 외부에서 내부 액세스로 형식 또는 멤버를 참조하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-112">It is an error to reference a type or a member with internal access outside the assembly within which it was defined.</span></span>  
  
## <a name="example"></a><span data-ttu-id="782e5-113">예제</span><span class="sxs-lookup"><span data-stu-id="782e5-113">Example</span></span>  
 <span data-ttu-id="782e5-114">이 예제에는 `Assembly1.cs` 및 `Assembly1_a.cs`의 두 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-114">This example contains two files, `Assembly1.cs` and `Assembly1_a.cs`.</span></span> <span data-ttu-id="782e5-115">첫 번째 파일에는 내부 기본 클래스인 `BaseClass`가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-115">The first file contains an internal base class, `BaseClass`.</span></span> <span data-ttu-id="782e5-116">두 번째 파일에서 `BaseClass`를 인스턴스화하려고 하면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-116">In the second file, an attempt to instantiate `BaseClass` will produce an error.</span></span>  
  
```  
// Assembly1.cs  
// Compile with: /target:library  
internal class BaseClass   
{  
   public static int intM = 0;  
}  
```  
  
```  
// Assembly1_a.cs  
// Compile with: /reference:Assembly1.dll  
class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // CS0122  
   }  
}  
```  
  
## <a name="example"></a><span data-ttu-id="782e5-117">예제</span><span class="sxs-lookup"><span data-stu-id="782e5-117">Example</span></span>  
 <span data-ttu-id="782e5-118">이 예제에서는 예제 1에서 사용한 것과 동일한 파일을 사용하고 `BaseClass`의 액세스 가능성 수준을 `public`으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-118">In this example, use the same files you used in example 1, and change the accessibility level of `BaseClass` to `public`.</span></span> <span data-ttu-id="782e5-119">또한 `IntM` 멤버의 액세스 가능성 수준을 `internal`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-119">Also change the accessibility level of the member `IntM` to `internal`.</span></span> <span data-ttu-id="782e5-120">이 경우 클래스를 인스턴스화할 수 있지만 내부 멤버에는 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="782e5-120">In this case, you can instantiate the class, but you cannot access the internal member.</span></span>  
  
```  
// Assembly2.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   internal static int intM = 0;  
}  
```  
  
```  
// Assembly2_a.cs  
// Compile with: /reference:Assembly1.dll  
public class TestAccess   
{  
   static void Main()   
   {  
      BaseClass myBase = new BaseClass();   // Ok.  
      BaseClass.intM = 444;    // CS0117  
   }  
}  
```  
  
## <a name="c-language-specification"></a><span data-ttu-id="782e5-121">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="782e5-121">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="782e5-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="782e5-122">See Also</span></span>  
 [<span data-ttu-id="782e5-123">C# 참조</span><span class="sxs-lookup"><span data-stu-id="782e5-123">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="782e5-124">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="782e5-124">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="782e5-125">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="782e5-125">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="782e5-126">액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="782e5-126">Access Modifiers</span></span>](../../../csharp/language-reference/keywords/access-modifiers.md)  
 [<span data-ttu-id="782e5-127">액세스 수준</span><span class="sxs-lookup"><span data-stu-id="782e5-127">Accessibility Levels</span></span>](../../../csharp/language-reference/keywords/accessibility-levels.md)  
 [<span data-ttu-id="782e5-128">한정자</span><span class="sxs-lookup"><span data-stu-id="782e5-128">Modifiers</span></span>](../../../csharp/language-reference/keywords/modifiers.md)  
 [<span data-ttu-id="782e5-129">public</span><span class="sxs-lookup"><span data-stu-id="782e5-129">public</span></span>](../../../csharp/language-reference/keywords/public.md)  
 [<span data-ttu-id="782e5-130">private</span><span class="sxs-lookup"><span data-stu-id="782e5-130">private</span></span>](../../../csharp/language-reference/keywords/private.md)  
 [<span data-ttu-id="782e5-131">protected</span><span class="sxs-lookup"><span data-stu-id="782e5-131">protected</span></span>](../../../csharp/language-reference/keywords/protected.md)
