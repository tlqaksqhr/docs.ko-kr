---
title: "using 정적 지시문(C# 참조)"
ms.date: 2017-03-10
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- using static directive [C#]
ms.assetid: 8b8f9e34-c75e-469b-ba85-6f2eb4090314
author: rpetrusha
ms.author: ronpet
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
ms.openlocfilehash: b7d69d0262ba6f450e2cc0d5b30692bba181f9d9
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="using-static-directive-c-reference"></a><span data-ttu-id="ee3ad-102">using 정적 지시문(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ee3ad-102">using static Directive (C# Reference)</span></span>

<span data-ttu-id="ee3ad-103">`using static` 지시문은 형식 이름을 지정하지 않고 정적 멤버에 액세스할 수 있는 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-103">The `using static` directive designates a type whose static members you can access without specifying a type name.</span></span> <span data-ttu-id="ee3ad-104">사용되는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-104">Its syntax is:</span></span>

```csharp
using static <fully-qualified-type-name>
```

<span data-ttu-id="ee3ad-105">여기서 *fully-qualified-type-name*은 형식 이름을 지정하지 않고 정적 멤버를 참조할 수 있는 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-105">where *fully-qualified-type-name* is the name of the type whose static members can be referenced without specifying a type name.</span></span> <span data-ttu-id="ee3ad-106">정규화된 형식 이름(전체 네임스페이스 및 형식 이름)을 제공하지 않으면 C#은 컴파일러 오류 CS0246, "'<type-name>' 형식 또는 네임스페이스 이름을 찾을 수 없습니다."를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-106">If you do not provide a fully qualified type name (the full namespace name along with the type name), C# generates compiler error CS0246: "The type or namespace name '<type-name>' could not be found."</span></span>

<span data-ttu-id="ee3ad-107">`using static` 지시문은 정적 멤버가 있는 모든 형식에 적용됩니다(인스턴스 멤버가 있는 경우에도).</span><span class="sxs-lookup"><span data-stu-id="ee3ad-107">The `using static` directive applies to any type that has static members, even if it also has instance members.</span></span> <span data-ttu-id="ee3ad-108">그러나 인스턴스 멤버는 형식 인스턴스를 통해서만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-108">However, instance members can only be invoked through the type instance.</span></span>

<span data-ttu-id="ee3ad-109">`using static` 지시문은 C# 6에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-109">The `using static` directive was introduced in C# 6.</span></span>

## <a name="remarks"></a><span data-ttu-id="ee3ad-110">설명</span><span class="sxs-lookup"><span data-stu-id="ee3ad-110">Remarks</span></span>
 
<span data-ttu-id="ee3ad-111">일반적으로 정적 멤버를 호출할 때 멤버 이름과 함께 형식 이름을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-111">Ordinarily, when you call a static member, you provide the type name along with the member name.</span></span> <span data-ttu-id="ee3ad-112">형식의 멤버를 호출하기 위해 동일한 형식 이름을 반복해서 입력하면 코드가 복잡하고 난해해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-112">Repeatedly entering the same type name to invoke members of the type can result in verbose, obscure code.</span></span> <span data-ttu-id="ee3ad-113">예를 들어 `Circle` 클래스에 대한 다음 정의에서는 @System.Math 클래스의 많은 멤버를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-113">For example, the following definition of a `Circle` class references a number of members of the @System.Math class.</span></span>
  
<span data-ttu-id="ee3ad-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ee3ad-114">[!code-cs[using-static#1](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static1.cs#1)]</span></span>

<span data-ttu-id="ee3ad-115">멤버를 참조할 때마다 @System.Math 클래스를 명시적으로 참조할 필요가 없으므로 `using static` 지시문은 훨씬 깔끔한 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-115">By eliminating the need to explicitly reference the @System.Math class each time a member is referenced, the `using static` directive produces much cleaner code:</span></span>

<span data-ttu-id="ee3ad-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="ee3ad-116">[!code-cs[using-static#2](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static2.cs#1)]</span></span>

<span data-ttu-id="ee3ad-117">`using static`은 액세스 가능한 정적 멤버와 지정된 형식에 선언된 중첩된 형식만 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-117">`using static` imports only accessible static members and nested types declared in the specified type.</span></span>  <span data-ttu-id="ee3ad-118">상속된 멤버는 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-118">Inherited members are not imported.</span></span>  <span data-ttu-id="ee3ad-119">using static 지시문을 사용하여 Visual Basic 모듈을 포함한 모든 명명된 형식에서 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-119">You can import from any named type with a using static directive, including Visual Basic modules.</span></span>  <span data-ttu-id="ee3ad-120">F# 최상위 함수가 메타데이터에서 이름이 유효한 C# 식별자인 명명된 형식의 정적 멤버로 나타나면 F# 함수를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-120">If F# top-level functions appear in metadata as static members of a named type whose name is a valid C# identifier, then the F# functions can be imported.</span></span>  
  
 <span data-ttu-id="ee3ad-121">`using static`을 사용하면 지정된 형식에 선언된 확장 메서드를 확장 메서드 조회에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-121">`using static` makes extension methods declared in the specified type available for extension method lookup.</span></span>  <span data-ttu-id="ee3ad-122">그러나 확장명 메서드의 이름은 코드의 정규화되지 않은 참조에 대한 범위로 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-122">However, the names of the extension methods are not imported into scope for unqualified reference in code.</span></span>  
  
 <span data-ttu-id="ee3ad-123">같은 컴파일 단위 또는 네임스페이스에서 여러 `using static` 지시문을 통해 다양한 형식에서 가져온 같은 이름을 사용하는 메서드는 메서드 그룹을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-123">Methods with the same name imported from different types by different `using static` directives in the same compilation unit or namespace form a method group.</span></span>  <span data-ttu-id="ee3ad-124">이들 메서드 그룹 내에서 오버로드 확인은 일반 C# 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-124">Overload resolution within these method groups follows normal C# rules.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ee3ad-125">예제</span><span class="sxs-lookup"><span data-stu-id="ee3ad-125">Example</span></span>

<span data-ttu-id="ee3ad-126">다음 예제에서는 형식 이름을 지정할 필요 없이 `using static` 지시문을 사용하여 @System.Console, @System.Math 및 @System.String 클래스의 정적 멤버를 사용 가능하게 합니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-126">The following example uses the `using static` directive to make the static members of the @System.Console, @System.Math, and @System.String classes available without having to specify their type name.</span></span>

<span data-ttu-id="ee3ad-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span><span class="sxs-lookup"><span data-stu-id="ee3ad-127">[!code-cs[using-static#3](../../../../samples/snippets/csharp/language-reference/keywords/using/using-static3.cs)]</span></span>

<span data-ttu-id="ee3ad-128">이 예제에서는 `using static` 지시문을 @System.Double 형식에 적용했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-128">In the example, the `using static` directive could also have been applied to the @System.Double type.</span></span> <span data-ttu-id="ee3ad-129">이 경우 형식 이름을 지정하지 않고도 @System.Double.TryParse(System.String,System.Double@) 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-129">This would have made it possible to call the @System.Double.TryParse(System.String,System.Double@) method without specifying a type name.</span></span> <span data-ttu-id="ee3ad-130">그러나 이렇게 하면 코드 가독성이 떨어집니다. 어떤 숫자 형식의 `TryParse` 메서드가 호출되었는지 알아보기 위해 `using static` 문을 확인해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ee3ad-130">However, this creates less readable code, since it becomes necessary to check the `using static` statements to determine which numeric type's `TryParse` method is called.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee3ad-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ee3ad-131">See also</span></span>

<span data-ttu-id="ee3ad-132">[using 지시문](using-directive.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ad-132">[using directive](using-directive.md) </span></span>  
<span data-ttu-id="ee3ad-133">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ad-133">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
<span data-ttu-id="ee3ad-134">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ad-134">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
<span data-ttu-id="ee3ad-135">[네임스페이스 사용](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ad-135">[Using Namespaces](../../../csharp/programming-guide/namespaces/using-namespaces.md) </span></span>  
<span data-ttu-id="ee3ad-136">[네임스페이스 키워드](../../../csharp/language-reference/keywords/namespace-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="ee3ad-136">[Namespace Keywords](../../../csharp/language-reference/keywords/namespace-keywords.md) </span></span>  
[<span data-ttu-id="ee3ad-137">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="ee3ad-137">Namespaces</span></span>](../../../csharp/programming-guide/namespaces/index.md)   

