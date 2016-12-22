---
title: "방법: 쿼리에서 요소 속성의 하위 집합 반환(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "익명 형식[C#], 요소 속성의 하위 집합"
ms.assetid: fabdf349-f443-4e3f-8368-6c471be1dd7b
caps.latest.revision: 11
caps.handback.revision: 11
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 쿼리에서 요소 속성의 하위 집합 반환(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이러한 조건이 모두 적용되는 경우 쿼리 식에서 익명 형식을 사용합니다.  
  
-   각 소스 개체의 일부 속성만 반환할 수 있습니다.  
  
-   쿼리가 실행되는 메서드의 범위 외부에 쿼리 결과를 저장할 필요가 없습니다.  
  
 각 소스 개체에서 하나의 속성 또는 필드를 반환하기만 하려는 경우 `select` 절에서 도트 연산자를 사용할 수 있습니다.  예를 들어 각 `student`의 `ID`만 반환하려면 다음과 같이 `select` 절을 작성하십시오.  
  
```  
select student.ID;  
```  
  
## 예제  
 다음 예제에서는 익명 형식을 사용하여 지정된 조건과 일치하는 각 소스 개체의 속성 하위 집합만 반환하는 방법을 보여 줍니다.  
  
 [!code-cs[csProgGuideLINQ#31](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-return-subsets-of-element-properties-in-a-query_1.cs)]  
  
 익명 형식은 이름이 지정되지 않은 경우 해당 속성에 대한 소스 요소의 이름을 사용합니다.  익명 형식의 속성에 새 이름을 부여하려면 다음과 같이 `select` 문을 작성하십시오.  
  
```  
select new { First = student.FirstName, Last = student.LastName };  
```  
  
 앞의 예제에서 이를 시도할 경우에는 `Console.WriteLine` 문도 변경해야 합니다.  
  
```  
Console.WriteLine(student.First + " " + student.Last);  
```  
  
## 코드 컴파일  
  
-   이 코드를 실행하려면 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs_current_short_md.md)]에서 만들어진 Visual C\# 콘솔 응용 프로그램 프로젝트에 클래스를 복사하여 붙여넣습니다.  기본적으로 이 프로젝트는 버전 3.5의 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)]를 대상으로 하므로 System.Core.dll에 대한 참조와 System.Linq에 대한 `using` 지시문을 포함합니다.  프로젝트에서 이러한 요구 사항 중 하나 이상이 누락된 경우 수동으로 추가할 수 있습니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)를 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [익명 형식](../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)   
 [LINQ 쿼리 식](../../../csharp/programming-guide/linq-query-expressions/index.md)