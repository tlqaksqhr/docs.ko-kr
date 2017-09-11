---
title: "using 지시문(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using directive [C#]
ms.assetid: b42b8e61-5e7e-439c-bb71-370094b44ae8
caps.latest.revision: 31
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 1129efd8a1c4058a9648eab61f98cdcef7e9f2f7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-directive-c-reference"></a><span data-ttu-id="d63e7-102">using 지시문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="d63e7-102">using Directive (C# Reference)</span></span>
<span data-ttu-id="d63e7-103">`using` 지시문에는 다음 세 가지 용도가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-103">The `using` directive has three uses:</span></span>  
  
-   <span data-ttu-id="d63e7-104">네임스페이스에서 형식 사용을 한정할 필요가 없도록 해당 네임스페이스에서 형식 사용을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-104">To allow the use of types in a namespace so that you do not have to qualify the use of a type in that namespace:</span></span>  
  
    ```csharp  
    using System.Text;  
    ```  
  
-   <span data-ttu-id="d63e7-105">형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-105">To allow you to access static members of a type without having to qualify the access with the type name.</span></span> 
  
    ```csharp  
    using static System.Math;  
    ```  
     
    <span data-ttu-id="d63e7-106">자세한 내용은 [using 정적 지시문](using-static.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d63e7-106">For more information, see the [using static directive](using-static.md).</span></span>

-   <span data-ttu-id="d63e7-107">네임스페이스 또는 형식에 대한 별칭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-107">To create an alias for a namespace or a type.</span></span> <span data-ttu-id="d63e7-108">이를 *using 별칭 지시문*이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-108">This is called a *using alias directive*.</span></span>  
  
    ```csharp  
    using Project = PC.MyCompany.Project;  
    ```  
  
 <span data-ttu-id="d63e7-109">`using` 키워드는 파일 및 글꼴과 같은 <xref:System.IDisposable> 개체가 제대로 처리될 수 있게 도와주는 *using 문*을 만드는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-109">The `using` keyword is also used to create *using statements*, which help ensure that <xref:System.IDisposable> objects such as files and fonts are handled correctly.</span></span> <span data-ttu-id="d63e7-110">자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d63e7-110">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) for more information.</span></span>  
  
## <a name="using-static-type"></a><span data-ttu-id="d63e7-111">정적 형식 사용</span><span class="sxs-lookup"><span data-stu-id="d63e7-111">Using Static Type</span></span>  
 <span data-ttu-id="d63e7-112">형식 이름을 사용하여 액세스를 한정할 필요 없이 형식의 정적 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-112">You can access static members of a type without having to qualify the access with the type name:</span></span>  
  
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
  
## <a name="remarks"></a><span data-ttu-id="d63e7-113">설명</span><span class="sxs-lookup"><span data-stu-id="d63e7-113">Remarks</span></span>  
 <span data-ttu-id="d63e7-114">`using` 지시문의 범위는 지시문이 나타내는 파일로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-114">The scope of a `using` directive is limited to the file in which it appears.</span></span>  
  
 <span data-ttu-id="d63e7-115">`using` 별칭을 만들면 네임스페이스 또는 형식에 대한 식별자를 더 쉽게 한정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-115">Create a `using` alias to make it easier to qualify an identifier to a namespace or type.</span></span> <span data-ttu-id="d63e7-116">using alias 지시문의 오른쪽은 지시문 앞에 나오는 using 지시문과 관계없이 항상 정규화된 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-116">The right side of a using alias directive must always be a fully-qualified type regardless of the using directives that come before it.</span></span>  
  
 <span data-ttu-id="d63e7-117">`using` 지시문을 만들어서 네임스페이스를 지정할 필요 없이 네임스페이스에서 이 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-117">Create a `using` directive to use the types in a namespace without having to specify the namespace.</span></span> <span data-ttu-id="d63e7-118">`using` 지시문은 지정한 네임스페이스에 중첩된 모든 네임스페이스에 대한 액세스 권한을 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-118">A `using` directive does not give you access to any namespaces that are nested in the namespace you specify.</span></span>  
  
 <span data-ttu-id="d63e7-119">네임스페이스는 두 가지 범주인 사용자 정의 및 시스템 정의로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-119">Namespaces come in two categories: user-defined and system-defined.</span></span> <span data-ttu-id="d63e7-120">사용자 정의 네임스페이스는 코드에서 정의된 네임스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-120">User-defined namespaces are namespaces defined in your code.</span></span> <span data-ttu-id="d63e7-121">시스템 정의 네임스페이스 목록을 보려면 [.NET Framework 클래스 라이브러리](http://go.microsoft.com/fwlink/?LinkID=227195)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d63e7-121">For a list of the system-defined namespaces, see [.NET Framework Class Library](http://go.microsoft.com/fwlink/?LinkID=227195).</span></span>  
  
 <span data-ttu-id="d63e7-122">다른 어셈블리의 메서드를 참조하는 방법에 대한 자세한 내용은 [C# DLL 만들기 및 사용](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d63e7-122">For examples on referencing methods in other assemblies, see [Creating and Using C# DLLs](http://msdn.microsoft.com/library/70f65026-3687-4e9c-ab79-c18b97dd8be4).</span></span>  
  
## <a name="example-1"></a><span data-ttu-id="d63e7-123">예제 1</span><span class="sxs-lookup"><span data-stu-id="d63e7-123">Example 1</span></span>  
  
 <span data-ttu-id="d63e7-124">다음 예제에서는 `using` 네임스페이스에 대한 별칭을 정의 및 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-124">The following example shows how to define and use a `using` alias for a namespace:</span></span>  
  
 <span data-ttu-id="d63e7-125">[!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="d63e7-125">[!code-cs[csrefKeywordsNamespace#8](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_1.cs)]</span></span>  
  
 <span data-ttu-id="d63e7-126">using alias 지시문의 오른쪽에는 공개 제네릭 형식이 포함될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-126">A using alias directive cannot have an open generic type on the right hand side.</span></span> <span data-ttu-id="d63e7-127">예를 들어 List\<T>에 대해서는 using 별칭을 만들 수 없지만 List\<int>에 대해서는 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-127">For example, you cannot create a using alias for a List\<T>, but you can create one for a List\<int>.</span></span>  
  
## <a name="example-2"></a><span data-ttu-id="d63e7-128">예제 2</span><span class="sxs-lookup"><span data-stu-id="d63e7-128">Example 2</span></span>  
  
 <span data-ttu-id="d63e7-129">다음 예제에서는 클래스에 대한 `using` 지시문 및 `using` 별칭을 정의하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d63e7-129">The following example shows how to define a `using` directive and a `using` alias for a class:</span></span>  
  
 <span data-ttu-id="d63e7-130">[!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="d63e7-130">[!code-cs[csrefKeywordsNamespace#9](../../../csharp/language-reference/keywords/codesnippet/CSharp/using-directive_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="d63e7-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="d63e7-131">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d63e7-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d63e7-132">See Also</span></span>  
 <span data-ttu-id="d63e7-133">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="d63e7-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="d63e7-134">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="d63e7-134">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="d63e7-135">[네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="d63e7-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
 <span data-ttu-id="d63e7-136">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="d63e7-136">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="d63e7-137">[네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="d63e7-137">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
 <span data-ttu-id="d63e7-138">[네임스페이스](../../../csharp/programming-guide/namespaces/index.md) </span><span class="sxs-lookup"><span data-stu-id="d63e7-138">[Namespaces](../../../csharp/programming-guide/namespaces/index.md) </span></span>  
 [<span data-ttu-id="d63e7-139">using 문</span><span class="sxs-lookup"><span data-stu-id="d63e7-139">using Statement</span></span>](../../../csharp/language-reference/keywords/using-statement.md)

