---
title: "private (C# 참조) 보호"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: 5f7abd2569d5bad5af64161042e4e5d21e741c8c
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2017
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="95b6e-102">private (C# 참조) 보호</span><span class="sxs-lookup"><span data-stu-id="95b6e-102">private protected (C# Reference)</span></span>
<span data-ttu-id="95b6e-103">`private protected` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="95b6e-104">개인 보호 된 멤버는 포함 하는 어셈블리가 내 에서만 않고 포함 하는 클래스에서 파생 된 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="95b6e-105">`private protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95b6e-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="95b6e-106">예제</span><span class="sxs-lookup"><span data-stu-id="95b6e-106">Example</span></span>  
 <span data-ttu-id="95b6e-107">기본 클래스의 보호 된 개인 멤버는 변수의 정적 형식이 파생된 클래스 형식인 경우에 포함 하는 어셈블리가에서 파생된 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="95b6e-108">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="95b6e-108">For example, consider the following code segment:</span></span>  
  
 ```
 // Assembly1.cs  
 // Compile with: /target:library  
 public class BaseClass
 {
     private protected int myValue = 0;
 }
 
 public class DerivedClass1 : BaseClass
 {
     void Access()
     {
         BaseClass baseObject = new BaseClass();
 
         // Error CS1540, because myValue can only be accessed by
         // classes derived from BaseClass.
         // baseObject.myValue = 5;  
 
         // OK, accessed through the current derived class instance
         myValue = 5;
     }
 }
```  
  
```  
 // Assembly2.cs  
 // Compile with: /reference:Assembly1.dll  
 class DerivedClass2 : BaseClass
 {
     void Access()
     {
         // Error CS0122, because myValue can only be
         // accessed by types in Assembly1
         // myValue = 10;
     }
 }
```  
 <span data-ttu-id="95b6e-109">이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="95b6e-110">공용 기본 클래스를 포함 하는 첫 번째 파일 `BaseClass`, 여기에서 파생 된 형식이 고 `DerivedClass1`합니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="95b6e-111">`BaseClass`보호 된 개인 멤버를 소유 하 고 `myValue`이며 `DerivedClass1` 두 가지 방법으로 액세스 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="95b6e-112">에 액세스 하려고 하는 첫 번째 `myValue` 의 인스턴스를 통해 `BaseClass` 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="95b6e-113">그러나에서 상속된 된 멤버와 사용 하려는 시도가 `DerivedClass1` 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="95b6e-114">두 번째 파일에 액세스 하려고에서 `myValue` 의 상속된 된 멤버와 `DerivedClass2` Assembly1에서 파생 된 형식으로 액세스 가능한 경우만 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="95b6e-115">구조체 멤버 수 없습니다 `private protected` 되므로 구조체를 상속할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="95b6e-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="95b6e-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="95b6e-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="95b6e-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="95b6e-117">See Also</span></span>  
 <span data-ttu-id="95b6e-118">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="95b6e-119">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="95b6e-120">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="95b6e-121">[액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="95b6e-122">[액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="95b6e-123">[한정자](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="95b6e-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="95b6e-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="95b6e-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="95b6e-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="95b6e-127">[Internal virtual 키워드에 대 한 보안 문제](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="95b6e-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
