---
title: "typeof(C# 참조)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
dev_langs:
- CSharp
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 21
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
ms.openlocfilehash: fdb335e44a5a3634520d3a86495a4508597b4f70
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="typeof-c-reference"></a><span data-ttu-id="15a28-102">typeof(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="15a28-102">typeof (C# Reference)</span></span>
<span data-ttu-id="15a28-103">형식의 `System.Type` 개체를 가져오는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-103">Used to obtain the `System.Type` object for a type.</span></span> <span data-ttu-id="15a28-104">`typeof` 식의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-104">A `typeof` expression takes the following form:</span></span>  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a><span data-ttu-id="15a28-105">설명</span><span class="sxs-lookup"><span data-stu-id="15a28-105">Remarks</span></span>  
 <span data-ttu-id="15a28-106">식의 런타임 형식을 가져오려면 다음 예제와 같이 .NET Framework 메서드 <xref:System.Object.GetType%2A>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 <span data-ttu-id="15a28-107">`typeof` 연산자를 오버로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-107">The `typeof` operator cannot be overloaded.</span></span>  
  
 <span data-ttu-id="15a28-108">열린 제네릭 형식에서 `typeof` 연산자를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="15a28-109">둘 이상의 형식 매개 변수가 있는 형식의 사양에 적절한 개수의 쉼표가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="15a28-110">다음 예제에서는 메서드의 반환 형식이 제네릭 <xref:System.Collections.Generic.IEnumerable%601>인지 여부를 확인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-110">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="15a28-111">메서드는 MethodInfo 형식의 인스턴스라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-111">Assume that method is an instance of a MethodInfo type:</span></span>  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a><span data-ttu-id="15a28-112">예제</span><span class="sxs-lookup"><span data-stu-id="15a28-112">Example</span></span>  
 <span data-ttu-id="15a28-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="15a28-113">[!code-cs[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="15a28-114">예제</span><span class="sxs-lookup"><span data-stu-id="15a28-114">Example</span></span>  
 <span data-ttu-id="15a28-115">이 샘플에서는 <xref:System.Object.GetType%2A> 메서드를 사용하여 숫자 계산의 결과를 포함하는 데 사용되는 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="15a28-116">이 형식은 결과 숫자의 저장소 요구 사항에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="15a28-116">This depends on the storage requirements of the resulting number.</span></span>  
  
 <span data-ttu-id="15a28-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="15a28-117">[!code-cs[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="15a28-118">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="15a28-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="15a28-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15a28-119">See Also</span></span>  
 <span data-ttu-id="15a28-120"><xref:System.Type?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="15a28-120"><xref:System.Type?displayProperty=fullName></span></span>   
 <span data-ttu-id="15a28-121">[C# 참조](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="15a28-121">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="15a28-122">[C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="15a28-122">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="15a28-123">[C# 키워드](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="15a28-123">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="15a28-124">[is](../../../csharp/language-reference/keywords/is.md) </span><span class="sxs-lookup"><span data-stu-id="15a28-124">[is](../../../csharp/language-reference/keywords/is.md) </span></span>  
 [<span data-ttu-id="15a28-125">연산자 키워드</span><span class="sxs-lookup"><span data-stu-id="15a28-125">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)

