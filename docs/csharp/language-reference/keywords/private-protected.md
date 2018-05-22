---
title: private protected (C# Reference)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: ee36cc713dd5fdb90ae20ef992f8e75eca09597d
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="private-protected-c-reference"></a><span data-ttu-id="4370a-102">private protected (C# Reference)</span><span class="sxs-lookup"><span data-stu-id="4370a-102">private protected (C# Reference)</span></span>
<span data-ttu-id="4370a-103">`private protected` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-103">The `private protected` keyword combination is a member access modifier.</span></span> <span data-ttu-id="4370a-104">private protected 멤버는 포함하는 클래스에서 파생된 형식으로 액세스할 수 있지만 포함하는 어셈블리 내에서만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-104">A private protected member is accessible by types derived from the containing class, but only within its containing assembly.</span></span> <span data-ttu-id="4370a-105">`private protected` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4370a-105">For a comparison of `private protected` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="4370a-106">예</span><span class="sxs-lookup"><span data-stu-id="4370a-106">Example</span></span>  
 <span data-ttu-id="4370a-107">기본 클래스의 private protected 멤버는 변수의 정적 형식이 파생 클래스 형식인 경우에만 포함 어셈블리의 파생된 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-107">A private protected member of a base class is accessible from derived types in its containing assembly only if the static type of the variable is the derived class type.</span></span> <span data-ttu-id="4370a-108">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="4370a-108">For example, consider the following code segment:</span></span>  
  
 ```csharp
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
  
```csharp  
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
 <span data-ttu-id="4370a-109">이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-109">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="4370a-110">첫 번째 파일은 공용 기본 클래스인 `BaseClass`를 포함하고 여기에서 파생된 형식인 `DerivedClass1`을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-110">The first file contains a public base class, `BaseClass`, and a type derived from it, `DerivedClass1`.</span></span> <span data-ttu-id="4370a-111">`BaseClass`는 `DerivedClass1`이 두 가지 방법으로 액세스를 시도하는 private protected 멤버인 `myValue`를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-111">`BaseClass` owns a private protected member, `myValue`, which `DerivedClass1` tries to access in two ways.</span></span> <span data-ttu-id="4370a-112">`BaseClass`의 인스턴스를 통한 `myValue` 액세스의 첫 번째 시도는 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-112">The first attempt to access `myValue` through an instance of `BaseClass` will produce an error.</span></span> <span data-ttu-id="4370a-113">그러나 `DerivedClass1`에서 상속된 멤버로 사용하려는 시도는 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-113">However, the attempt to use it as an inherited member in `DerivedClass1` will succeed.</span></span>
<span data-ttu-id="4370a-114">두 번째 파일에서 `DerivedClass2`의 상속된 멤버로 `myValue`에 액세스하는 시도는 Assembly1에서 파생된 형식으로만 액세스할 수 있으므로 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-114">In the second file, an attempt to access `myValue` as an inherited member of `DerivedClass2` will produce an error, as it is only accessible by derived types in Assembly1.</span></span> 

 <span data-ttu-id="4370a-115">구조체를 상속할 수 없기 때문에 구조체 멤버는 `private protected`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4370a-115">Struct members cannot be `private protected` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4370a-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4370a-116">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4370a-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4370a-117">See Also</span></span>  
 <span data-ttu-id="4370a-118">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-118">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4370a-119">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4370a-120">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-120">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4370a-121">[액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-121">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="4370a-122">[액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-122">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="4370a-123">[한정자](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-123">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="4370a-124">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-124">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="4370a-125">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-125">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="4370a-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="4370a-126">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="4370a-127">[internal virtual 키워드에 대한 보안 문제](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="4370a-127">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
