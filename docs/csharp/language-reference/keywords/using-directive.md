---
title: using 지시문(C# 참조)
ms.date: 07/20/2015
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
ms.openlocfilehash: 180c038987e7de6b39a8eae0e86871eea41a40bb
ms.sourcegitcommit: 60645077dc4b62178403145f8ef691b13ffec28e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37960042"
---
# <a name="using-directive-c-reference"></a><span data-ttu-id="12edd-102">using 지시문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="12edd-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="12edd-103">`using` 지시문에는 다음 세 가지 용도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="12edd-104">네임스페이스에서 형식 사용을 한정할 필요가 없도록 해당 네임스페이스에서 형식 사용을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="12edd-105">형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="12edd-106">자세한 내용은 [using 정적 지시문](using-static.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12edd-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="12edd-107">네임스페이스 또는 형식에 대한 별칭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="12edd-108">이를 *using 별칭 지시문*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="12edd-109">`using` 키워드는 파일 및 글꼴과 같은 <xref:System.IDisposable> 개체가 제대로 처리될 수 있게 도와주는 *using 문*을 만드는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="12edd-110">자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12edd-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="12edd-111">정적 형식 사용</span><span class="sxs-lookup"><span data-stu-id="12edd-111">Using Static Type</span></span>  
 <span data-ttu-id="12edd-112">형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
```csharp  
using static System.Console;   
using static System.Math;  
class Program   
{   
    static void Main()   
    {   
        WriteLine(Sqrt(3*3 + 4*4));   
    }   
}  
```  
  
## <a name="remarks"></a><span data-ttu-id="12edd-113">설명</span><span class="sxs-lookup"><span data-stu-id="12edd-113">Remarks</span></span>  
 <span data-ttu-id="12edd-114">`using` 지시문의 범위는 지시문이 나타내는 파일로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="12edd-115">`using` 별칭을 만들면 네임스페이스 또는 형식에 대한 식별자를 더 쉽게 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="12edd-116">using alias 지시문의 오른쪽은 지시문 앞에 나오는 using 지시문과 관계없이 항상 정규화된 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="12edd-117">`using` 지시문을 만들어서 네임스페이스를 지정할 필요 없이 네임스페이스에서 이 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="12edd-118">`using` 지시문은 지정한 네임스페이스에 중첩된 모든 네임스페이스에 대한 액세스 권한을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="12edd-119">네임스페이스는 두 가지 범주인 사용자 정의 및 시스템 정의로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="12edd-120">사용자 정의 네임스페이스는 코드에서 정의된 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="12edd-121">시스템 정의 네임스페이스 목록을 보려면 [.NET Framework 클래스 라이브러리 개요](../../../standard/class-library-overview.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12edd-121">For a list of the system-defined namespaces, see [.NET Framework Class Library Overview](../../../standard/class-library-overview.md).</span></span>  
  
 <span data-ttu-id="12edd-122">다른 어셈블리의 메서드를 참조하는 예제는 [명령줄을 사용하여 어셈블리 만들기 및 사용](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12edd-122">For examples on referencing methods in other assemblies, see [Create and Use Assemblies Using the Command Line](../../programming-guide/concepts/assemblies-gac/how-to-create-and-use-assemblies-using-the-command-line.md).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="12edd-123">예제 1</span><span class="sxs-lookup"><span data-stu-id="12edd-123">Example 1</span></span>  
  
 <span data-ttu-id="12edd-124">다음 예제에서는 `using` 네임스페이스에 대한 별칭을 정의 및 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]  
  
 <span data-ttu-id="12edd-125">using alias 지시문의 오른쪽에는 공개 제네릭 형식이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-125">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="12edd-126">예를 들어 List\<T>에 대해서는 using 별칭을 만들 수 없지만 List\<int>에 대해서는 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-126">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="12edd-127">예제 2</span><span class="sxs-lookup"><span data-stu-id="12edd-127">Example 2</span></span>  
  
 <span data-ttu-id="12edd-128">다음 예제에서는 클래스에 대한 `using` 지시문 및 `using` 별칭을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="12edd-128">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 [!code-csharp[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="12edd-129">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="12edd-129">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="12edd-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12edd-130">See Also</span></span>  
 [<span data-ttu-id="12edd-131">C# 참조</span><span class="sxs-lookup"><span data-stu-id="12edd-131">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="12edd-132">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="12edd-132">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="12edd-133">네임스페이스 사용</span><span class="sxs-lookup"><span data-stu-id="12edd-133">Using Namespaces</span></span>](../../../csharp/programming-guide/namespaces/using-namespaces.md)  
 [<span data-ttu-id="12edd-134">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="12edd-134">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="12edd-135">네임스페이스 키워드</span><span class="sxs-lookup"><span data-stu-id="12edd-135">Namespace Keywords</span></span>](../../../csharp/language-reference/keywords/namespace-keywords.md)  
 [<span data-ttu-id="12edd-136">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="12edd-136">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)  
 [<span data-ttu-id="12edd-137">using 문</span><span class="sxs-lookup"><span data-stu-id="12edd-137">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)
