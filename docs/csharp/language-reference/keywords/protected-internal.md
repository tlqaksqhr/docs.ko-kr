---
title: protected internal(C# 참조)
ms.date: 11/15/2017
author: sputier
ms.openlocfilehash: 5ba2c811a1a4f095bcee65ed6678a7dc50fe94db
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172243"
---
# <a name="protected-internal-c-reference"></a><span data-ttu-id="f5477-102">protected internal(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f5477-102">protected internal (C# Reference)</span></span>
<span data-ttu-id="f5477-103">`protected internal` 키워드 조합은 멤버 액세스 한정자입니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-103">The `protected internal` keyword combination is a member access modifier.</span></span> <span data-ttu-id="f5477-104">protected internal 멤버는 포함하는 클래스에서 파생된 형식이나 현재 어셈블리에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-104">A protected internal member is accessible from the current assembly or from types that are derived from the containing class.</span></span> <span data-ttu-id="f5477-105">`protected internal` 및 다른 액세스 한정자와 비교는 [액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f5477-105">For a comparison of `protected internal` with the other access modifiers, see [Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md).</span></span> 
   
## <a name="example"></a><span data-ttu-id="f5477-106">예</span><span class="sxs-lookup"><span data-stu-id="f5477-106">Example</span></span>  
 <span data-ttu-id="f5477-107">기본 클래스의 protected internal 멤버는 포함하는 어셈블리 내의 모든 형식에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-107">A protected internal member of a base class is accessible from any type within its containing assembly.</span></span> <span data-ttu-id="f5477-108">또한 액세스가 파생된 클래스 형식의 변수를 통해 발생하는 경우에만 다른 어셈블리에 있는 파생 클래스에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-108">It is also accessible in a derived class located in another assembly only if the access occurs through a variable of the derived class type.</span></span> <span data-ttu-id="f5477-109">예를 들어 다음 코드 세그먼트를 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="f5477-109">For example, consider the following code segment:</span></span>  

```csharp
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```csharp  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 <span data-ttu-id="f5477-110">이 예제에는 `Assembly1.cs` 및 `Assembly2.cs`의 두 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-110">This example contains two files, `Assembly1.cs` and `Assembly2.cs`.</span></span> <span data-ttu-id="f5477-111">첫 번째 파일은 공용 기본 클래스인 `BaseClass`와 다른 클래스인 `TestAccess`을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-111">The first file contains a public base class, `BaseClass`, and another class, `TestAccess`.</span></span> <span data-ttu-id="f5477-112">`BaseClass`는 `TestAccess` 형식으로 액세스되는 protected internal 멤버인 `myValue`를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-112">`BaseClass` owns a protected internal member, `myValue`, which is accessed by the `TestAccess` type.</span></span> <span data-ttu-id="f5477-113">두 번째 파일에서 `BaseClass`의 인스턴스를 통한 `myValue` 액세스의 시도는 오류를 생성하지만 파생된 클래스 `DerivedClass`의 인스턴스를 통한 이 멤버로의 액세스는 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-113">In the second file, an attempt to access `myValue` through an instance of `BaseClass` will produce an error, while an access to this member through an instance of a derived class, `DerivedClass` will succeed.</span></span> 

 <span data-ttu-id="f5477-114">구조체를 상속할 수 없기 때문에 구조체 멤버는 `protected internal`일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5477-114">Struct members cannot be `protected internal` because the struct cannot be inherited.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f5477-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f5477-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f5477-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5477-116">See Also</span></span>  
 <span data-ttu-id="f5477-117">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="f5477-118">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="f5477-119">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-119">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="f5477-120">[액세스 한정자](../../../csharp/language-reference/keywords/access-modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-120">[Access Modifiers](../../../csharp/language-reference/keywords/access-modifiers.md) </span></span>  
 <span data-ttu-id="f5477-121">[액세스 가능성 수준](../../../csharp/language-reference/keywords/accessibility-levels.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-121">[Accessibility Levels](../../../csharp/language-reference/keywords/accessibility-levels.md) </span></span>  
 <span data-ttu-id="f5477-122">[한정자](../../../csharp/language-reference/keywords/modifiers.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-122">[Modifiers](../../../csharp/language-reference/keywords/modifiers.md) </span></span>  
 <span data-ttu-id="f5477-123">[public](../../../csharp/language-reference/keywords/public.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-123">[public](../../../csharp/language-reference/keywords/public.md) </span></span>  
 <span data-ttu-id="f5477-124">[private](../../../csharp/language-reference/keywords/private.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-124">[private](../../../csharp/language-reference/keywords/private.md) </span></span>  
 <span data-ttu-id="f5477-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span><span class="sxs-lookup"><span data-stu-id="f5477-125">[internal](../../../csharp/language-reference/keywords/internal.md) </span></span>  
 <span data-ttu-id="f5477-126">[internal virtual 키워드에 대한 보안 문제](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span><span class="sxs-lookup"><span data-stu-id="f5477-126">[Security concerns for internal virtual keywords](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))</span></span>
