---
title: "방법: 컬렉션 이니셜라이저를 사용하여 사전 초기화(C# 프로그래밍 가이드) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "컬렉션 이니셜라이저[C#], 사전 포함"
ms.assetid: 25283922-f8ee-40dc-a639-fac30804ec71
caps.latest.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 10
---
# 방법: 컬렉션 이니셜라이저를 사용하여 사전 초기화(C# 프로그래밍 가이드)
<xref:System.Collections.Generic.Dictionary%602>는 키\/값 쌍의 컬렉션을 포함합니다.  <xref:System.Collections.Generic.Dictionary%602.Add%2A> 메서드는 하나는 키 그리고 다른 하나는 값인 두 개의 매개 변수를 사용합니다.  <xref:System.Collections.Generic.Dictionary%602> 또는 `Add` 메서드가 여러 매개 변수를 사용하는 모든 컬렉션을 초기화하려면 다음 예제와 같이 각 매개 변수 집합을 괄호로 묶어야 합니다.  
  
## 예제  
 다음 코드 예제에서는 <xref:System.Collections.Generic.Dictionary%602>가 `StudentName` 형식의 인스턴스로 초기화됩니다.  
  
 [!code-cs[csProgGuideLINQ#34](../../../csharp/programming-guide/arrays/codesnippet/csharp/csLINQProgRef/csRef30LangFeatures_2.cs#34)]  
  
 컬렉션의 각 요소에는 중괄호 두 쌍이 있습니다.  가장 안쪽의 중괄호로 `StudentName`에 대한 개체 이니셜라이저를 묶고 가장 바깥쪽 중괄호로 `students` <xref:System.Collections.Generic.Dictionary%602>에 추가될 키\/값 쌍에 대한 이니셜라이저를 묶습니다.  마지막으로 디렉터리에 대한 전체 컬렉션 이니셜라이저를 중괄호로 묶습니다.  
  
## 코드 컴파일  
 이 코드를 실행하려면 [!INCLUDE[vs_current_short](../../../csharp/programming-guide/classes-and-structs/includes/vs-current-short-md.md)]에서 만들어진 Visual C\# 콘솔 응용 프로그램 프로젝트에 클래스를 복사하여 붙여넣습니다.  기본적으로 이 프로젝트는 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] 버전 3.5를 대상으로 하므로 System.Core.dll에 대한 참조와 System.Linq에 대한 using 지시문이 있습니다.  프로젝트에서 이러한 요구 사항 중 하나 이상이 누락된 경우 수동으로 추가할 수 있습니다.  자세한 내용은 [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md)을 참조하십시오.  
  
## 참고 항목  
 [C\# 프로그래밍 가이드](../../../csharp/programming-guide/index.md)   
 [개체 및 컬렉션 이니셜라이저](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)