---
title: "방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용(C# 프로그래밍 가이드)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- indexed properties [C#]
- Office programming [C#], indexed properties
- properties [C#], indexed
ms.assetid: 756bfc1e-7c28-4d4d-b114-ac9288c73882
caps.latest.revision: 20
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
ms.openlocfilehash: 19e620415adefd6190d3896377eaf6a7cf944f28
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-use-indexed-properties-in-com-interop-programming-c-programming-guide"></a><span data-ttu-id="4cd3e-102">방법: COM Interop 프로그래밍에서 인덱싱된 속성 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4cd3e-102">How to: Use Indexed Properties in COM Interop Programming (C# Programming Guide)</span></span>
<span data-ttu-id="4cd3e-103">*인덱싱된 속성*은 매개 변수가 있는 COM 속성이 C# 프로그래밍에서 사용되는 방식을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-103">*Indexed properties* improve the way in which COM properties that have parameters are consumed in C# programming.</span></span> <span data-ttu-id="4cd3e-104">인덱싱된 속성은 Visual C#의 다른 기능(예: [명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md)), 새 형식([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), [포함된 형식 정보](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md)와 함께 작동하여 Microsoft Office 프로그래밍을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-104">Indexed properties work together with other features in Visual C#, such as [named and optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md), a new type ([dynamic](../../../csharp/language-reference/keywords/dynamic.md)), and [embedded type information](../../../csharp/programming-guide/concepts/assemblies-gac/walkthrough-embedding-types-from-managed-assemblies-in-visual-studio.md), to enhance Microsoft Office programming.</span></span>  
  
 <span data-ttu-id="4cd3e-105">이전 버전의 C#에서는 `get` 메서드에 매개 변수가 없고 `set` 메서드에 하나의 값 매개 변수가 있는 경우에만 메서드를 속성으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-105">In earlier versions of C#, methods are accessible as properties only if the `get` method has no parameters and the `set` method has one and only one value parameter.</span></span> <span data-ttu-id="4cd3e-106">그러나 모든 COM 속성이 이러한 제한을 충족하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-106">However, not all COM properties meet those restrictions.</span></span> <span data-ttu-id="4cd3e-107">예를 들어 Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) 속성에는 `get` 접근자가 있으며, 범위 이름에 대한 매개 변수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-107">For example, the Excel [Range](http://go.microsoft.com/fwlink/?LinkId=166053) property has a `get` accessor that requires a parameter for the name of the range.</span></span> <span data-ttu-id="4cd3e-108">이전에는 `Range` 속성에 직접 액세스할 수 없었기 때문에 다음 예제와 같이 `get_Range` 메서드를 대신 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-108">In the past, because you could not access the `Range` property directly, you had to use the `get_Range` method instead, as shown in the following example.</span></span>  
  
 <span data-ttu-id="4cd3e-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4cd3e-109">[!code-cs[csProgGuideIndexedProperties#1](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_1.cs)]</span></span>  
  
 <span data-ttu-id="4cd3e-110">인덱싱된 속성을 사용하면 대신 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-110">Indexed properties enable you to write the following instead:</span></span>  
  
 <span data-ttu-id="4cd3e-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4cd3e-111">[!code-cs[csProgGuideIndexedProperties#2](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_2.cs)]</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4cd3e-112">또한 앞의 예제에서는 [선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) 기능을 사용하므로 `Type.Missing`을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-112">The previous example also uses the [optional arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) feature, which enables you to omit `Type.Missing`.</span></span>  
  
 <span data-ttu-id="4cd3e-113">마찬가지로, Visual C# 2008 및 이전 버전에서 [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) 개체의 `Value` 속성 값을 설정하려면 두 개의 인수가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-113">Similarly to set the value of the `Value` property of a [Range](https://msdn.microsoft.com/library/microsoft.office.interop.excel.range.aspx) object in Visual C# 2008 and earlier, two arguments are required.</span></span> <span data-ttu-id="4cd3e-114">하나는 범위 값의 형식을 지정하는 선택적 매개 변수의 인수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-114">One supplies an argument for an optional parameter that specifies the type of the range value.</span></span> <span data-ttu-id="4cd3e-115">다른 하나는 `Value` 속성의 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-115">The other supplies the value for the `Value` property.</span></span> <span data-ttu-id="4cd3e-116">다음 예제에서는 이러한 기법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-116">The following examples illustrate these techniques.</span></span> <span data-ttu-id="4cd3e-117">둘 다 A1 셀의 값을 `Name`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-117">Both set the value of the A1 cell to `Name`.</span></span>
  
 <span data-ttu-id="4cd3e-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="4cd3e-118">[!code-cs[csProgGuideIndexedProperties#3](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_3.cs)]</span></span>  
  
 <span data-ttu-id="4cd3e-119">인덱싱된 속성을 사용하면 대신 다음 코드와 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-119">Indexed properties enable you to write the following code instead.</span></span>  
  
 <span data-ttu-id="4cd3e-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="4cd3e-120">[!code-cs[csProgGuideIndexedProperties#4](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_4.cs)]</span></span>  
  
 <span data-ttu-id="4cd3e-121">인덱싱된 속성을 직접 만들 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-121">You cannot create indexed properties of your own.</span></span> <span data-ttu-id="4cd3e-122">이 기능은 기존 인덱싱된 속성의 사용만을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-122">The feature only supports consumption of existing indexed properties.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cd3e-123">예제</span><span class="sxs-lookup"><span data-stu-id="4cd3e-123">Example</span></span>  
 <span data-ttu-id="4cd3e-124">다음 코드에서는 전체 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-124">The following code shows a complete example.</span></span> <span data-ttu-id="4cd3e-125">Office API에 액세스하는 프로젝트를 설정하는 방법에 대한 자세한 내용은 [방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4cd3e-125">For more information about how to set up a project that accesses the Office API, see [How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md).</span></span>  
  
 <span data-ttu-id="4cd3e-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span><span class="sxs-lookup"><span data-stu-id="4cd3e-126">[!code-cs[csProgGuideIndexedProperties#5](../../../csharp/programming-guide/interop/codesnippet/CSharp/how-to-use-indexed-properties-in-com-interop-rogramming_5.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cd3e-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cd3e-127">See Also</span></span>  
 <span data-ttu-id="4cd3e-128">[명명된 인수 및 선택적 인수](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span><span class="sxs-lookup"><span data-stu-id="4cd3e-128">[Named and Optional Arguments](../../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md) </span></span>  
 <span data-ttu-id="4cd3e-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="4cd3e-129">[dynamic](../../../csharp/language-reference/keywords/dynamic.md) </span></span>  
 <span data-ttu-id="4cd3e-130">[dynamic 형식 사용](../../../csharp/programming-guide/types/using-type-dynamic.md) </span><span class="sxs-lookup"><span data-stu-id="4cd3e-130">[Using Type dynamic](../../../csharp/programming-guide/types/using-type-dynamic.md) </span></span>  
 <span data-ttu-id="4cd3e-131">[방법: Office 프로그래밍에서 명명된 인수 및 선택적 인수 사용](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span><span class="sxs-lookup"><span data-stu-id="4cd3e-131">[How to: Use Named and Optional Arguments in Office Programming](../../../csharp/programming-guide/classes-and-structs/how-to-use-named-and-optional-arguments-in-office-programming.md) </span></span>  
 <span data-ttu-id="4cd3e-132">[방법: Visual C# 기능을 사용하여 Office Interop 개체에 액세스](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span><span class="sxs-lookup"><span data-stu-id="4cd3e-132">[How to: Access Office Interop Objects by Using Visual C# Features](../../../csharp/programming-guide/interop/how-to-access-office-onterop-objects.md) </span></span>  
 [<span data-ttu-id="4cd3e-133">연습: Office 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="4cd3e-133">Walkthrough: Office Programming</span></span>](../../../csharp/programming-guide/interop/walkthrough-office-programming.md)

