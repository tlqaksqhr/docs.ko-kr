---
title: object(C# 참조)
ms.date: 07/20/2015
f1_keywords:
- object_CSharpKeyword
- object
helpviewer_keywords:
- object keyword [C#]
ms.assetid: 93f60c0b-e17a-40a9-9362-cca5fb77b0e7
ms.openlocfilehash: 67eaf7f1fd2f01e433395ed21701c3b7fad7c7b4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33267924"
---
# <a name="object-c-reference"></a><span data-ttu-id="4a10b-102">object(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4a10b-102">object (C# Reference)</span></span>
<span data-ttu-id="4a10b-103">`object` 형식은 .NET Framework에서 <xref:System.Object>의 별칭입니다.</span><span class="sxs-lookup"><span data-stu-id="4a10b-103">The `object` type is an alias for <xref:System.Object> in the .NET Framework.</span></span> <span data-ttu-id="4a10b-104">C#의 통합 형식 시스템에서 사용자 정의 및 미리 정의된 참조 형식과 값 형식을 비롯한 모든 형식은 직접 또는 간접적으로 <xref:System.Object>에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="4a10b-104">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span> <span data-ttu-id="4a10b-105">`object` 형식의 변수에 모든 형식의 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a10b-105">You can assign values of any type to variables of type `object`.</span></span> <span data-ttu-id="4a10b-106">값 형식의 변수가 개체로 변환된 경우 *boxed*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a10b-106">When a variable of a value type is converted to object, it is said to be *boxed*.</span></span> <span data-ttu-id="4a10b-107">형식 개체의 변수가 값 형식으로 변환된 경우 *unboxed*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a10b-107">When a variable of type object is converted to a value type, it is said to be *unboxed*.</span></span> <span data-ttu-id="4a10b-108">자세한 내용은 [boxing 및 unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a10b-108">For more information, see [Boxing and Unboxing](../../../csharp/programming-guide/types/boxing-and-unboxing.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a10b-109">예</span><span class="sxs-lookup"><span data-stu-id="4a10b-109">Example</span></span>  
 <span data-ttu-id="4a10b-110">다음 샘플은 `object` 형식의 변수가 모든 데이터 형식의 값을 허용할 수 있는 방법 및 `object` 형식의 변수가 .NET Framework의 <xref:System.Object>에 대해 메서드를 사용할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4a10b-110">The following sample shows how variables of type `object` can accept values of any data type and how variables of type `object` can use methods on <xref:System.Object> from the .NET Framework.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#16](../../../csharp/language-reference/keywords/codesnippet/CSharp/object_1.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="4a10b-111">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4a10b-111">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4a10b-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a10b-112">See Also</span></span>  
 [<span data-ttu-id="4a10b-113">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4a10b-113">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4a10b-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4a10b-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4a10b-115">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="4a10b-115">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4a10b-116">참조 형식</span><span class="sxs-lookup"><span data-stu-id="4a10b-116">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="4a10b-117">값 형식</span><span class="sxs-lookup"><span data-stu-id="4a10b-117">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)
