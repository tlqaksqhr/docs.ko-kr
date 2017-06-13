---
title: "방법: 쿼리에서 요소 속성의 하위 집합 반환(C# 프로그래밍 가이드) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- anonymous types [C#], for subsets of element properties
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 99768c4b486dd6e8a25af22ab187c673c548ece9
ms.contentlocale: ko-kr
ms.lasthandoff: 06/12/2017

---
# <a name="how-to-return-subsets-of-element-properties-in-a-query-c-programming-guide"></a>방법: 쿼리에서 요소 속성의 하위 집합 반환(C# 프로그래밍 가이드)
이러한 조건이 둘 다 적용되는 경우 쿼리 식에서 무명 형식을 사용합니다.  
  
-   각 소스 요소의 속성 중 일부만 반환하려고 합니다.  
  
-   쿼리가 실행되는 메서드의 범위 외부에 쿼리 결과를 저장할 필요는 없습니다.  
  
 각 소스 요소에서 하나의 속성 또는 필드만 반환하려는 경우 `select` 절에 점 연산자만 사용할 수 있습니다. 예를 들어 각 `student`의 `ID`만 반환하려면 `select` 절을 다음과 같이 작성합니다.  
  
```  
select student.ID;  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 무명 형식을 사용하여 지정된 조건과 일치하는 각 소스 요소의 속성 하위 집합만 반환하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 이름이 지정되지 않은 경우 무명 형식은 소스 요소의 이름을 해당 속성에 사용합니다. 무명 형식의 속성에 새 이름을 지정하려면 `select` 문을 다음과 같이 작성합니다.  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 앞의 예제에서 이 작업을 수행하는 경우 `Console.WriteLine` 문도 변경되어야 합니다.  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
  
-   이 코드를 실행하려면 클래스를 복사하여 [!INCLUDE[vs_current_short](~/includes/vs-current-short-md.md)]에서 생성된 Visual C# 콘솔 응용 프로그램 프로젝트에 붙여넣습니다. 기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 버전 3.5를 대상으로 하며, System.Core.dll에 대한 참조 및 System.Linq에 대한 `using` 지시문을 포함합니다. 이러한 요구 사항 중 하나 이상이 프로젝트에 없는 경우 수동으로 추가할 수 있습니다.   
  
## <a name="see-also"></a>참고 항목  
 [C# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [무명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)
