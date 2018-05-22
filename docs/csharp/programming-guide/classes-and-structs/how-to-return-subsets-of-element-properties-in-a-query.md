---
title: '방법: 쿼리에서 요소 속성의 하위 집합 반환(C# 프로그래밍 가이드)'
ms.date: 07/20/2015
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
ms.openlocfilehash: 3b43e7e3aafda5ee5b6a49f271f725fb8eeeca59
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2018
---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a><span data-ttu-id="4ad77-102">방법: 쿼리에서 요소 속성의 하위 집합 반환(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4ad77-102">How to: Return Subsets of Element Properties in a Query (C# Programming Guide)</span></span>
<span data-ttu-id="4ad77-103">이러한 조건이 둘 다 적용되는 경우 쿼리 식에서 무명 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-103">Use an anonymous type in a query expression when both of these conditions apply:</span></span>  
  
-   <span data-ttu-id="4ad77-104">각 소스 요소의 속성 중 일부만 반환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-104">You want to return only some of the properties of each source element.</span></span>  
  
-   <span data-ttu-id="4ad77-105">쿼리가 실행되는 메서드의 범위 외부에 쿼리 결과를 저장할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-105">You do not have to store the query results outside the scope of the method in which the query is executed.</span></span>  
  
 <span data-ttu-id="4ad77-106">각 소스 요소에서 하나의 속성 또는 필드만 반환하려는 경우 `select` 절에 점 연산자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-106">If you only want to return one property or field from each source element, then you can just use the dot operator in the `select` clause.</span></span> <span data-ttu-id="4ad77-107">예를 들어 각 `student`의 `ID`만 반환하려면 `select` 절을 다음과 같이 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-107">For example, to return only the `ID` of each `student`, write the `select` clause as follows:</span></span>  
  
```  
select student.ID;  
```  
  
## <a name="example"></a><span data-ttu-id="4ad77-108">예</span><span class="sxs-lookup"><span data-stu-id="4ad77-108">Example</span></span>  
 <span data-ttu-id="4ad77-109">다음 예제에서는 무명 형식을 사용하여 지정된 조건과 일치하는 각 소스 요소의 속성 하위 집합만 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-109">The following example shows how to use an anonymous type to return only a subset of the properties of each source element that matches the specified condition.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 <span data-ttu-id="4ad77-110">이름이 지정되지 않은 경우 무명 형식은 소스 요소의 이름을 해당 속성에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-110">Note that the anonymous type uses the source element's names for its properties if no names are specified.</span></span> <span data-ttu-id="4ad77-111">무명 형식의 속성에 새 이름을 지정하려면 `select` 문을 다음과 같이 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-111">To give new names to the properties in the anonymous type, write the `select` statement as follows:</span></span>  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 <span data-ttu-id="4ad77-112">앞의 예제에서 이 작업을 수행하는 경우 `Console.WriteLine` 문도 변경되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-112">If you try this in the previous example, then the `Console.WriteLine` statement must also change:</span></span>  
  
```csharp  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4ad77-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="4ad77-113">Compiling the Code</span></span>  
  
-   <span data-ttu-id="4ad77-114">이 코드를 실행하려면 클래스를 복사하여 Visual Studio에서 만든 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-114">To run this code, copy and paste the class into a Visual C# console application project that has been created in Visual Studio.</span></span> <span data-ttu-id="4ad77-115">기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 `using` 지시문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-115">By default, this project targets version 3.5 of the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], and it will have a reference to System.Core.dll and a `using` directive for System.Linq.</span></span> <span data-ttu-id="4ad77-116">이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4ad77-116">If one or more of these requirements are missing from the project, you can add them manually.</span></span>   
  
## <a name="see-also"></a><span data-ttu-id="4ad77-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4ad77-117">See Also</span></span>  
 [<span data-ttu-id="4ad77-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4ad77-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4ad77-119">익명 형식</span><span class="sxs-lookup"><span data-stu-id="4ad77-119">Anonymous Types</span></span>](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)  
 [<span data-ttu-id="4ad77-120">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="4ad77-120">LINQ Query Expressions</span></span>](../../../csharp/programming-guide/linq-query-expressions/index.md)
