---
title: "LINQ and Generic Types (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], generic types"
  - "generic types [LINQ]"
  - "generics [LINQ]"
ms.assetid: 660e3799-25ca-462c-8c4a-8bce04fbb031
caps.latest.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 16
---
# LINQ and Generic Types (C#)
[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] 버전 2.0에서 새로 도입된 제네릭 형식을 기반으로 합니다.  쿼리 작성을 시작하기 전에 제네릭에 대해 세밀히 알고 있을 필요는 없지만  다음 두 가지 기본 개념은 이해하는 것이 좋습니다.  
  
1.  <xref:System.Collections.Generic.List%601>와 같은 제네릭 컬렉션 클래스의 인스턴스를 만들 때 "T"를 목록에서 유지할 개체 형식으로 바꿉니다.  예를 들어 문자열의 목록은 `List<string>`으로 표현되며 `Customer` 개체의 목록은 `List<Customer>`로 표현됩니다.  제네릭 목록은 강력한 형식이므로 해당 요소를 <xref:System.Object>로 저장하는 컬렉션에 비해 많은 장점을 제공합니다.  `Customer`를 `List<string>`에 추가하려는 경우 컴파일 시 오류가 발생합니다.  런타임 형식 캐스팅을 수행할 필요가 없으므로 제네릭 컬렉션을 사용하기가 쉽습니다.  
  
2.  <xref:System.Collections.Generic.IEnumerable%601>은 `foreach` 문을 사용하여 제네릭 컬렉션 클래스가 열거될 수 있게 해주는 인터페이스입니다.  제네릭 컬렉션 클래스는 <xref:System.Collections.ArrayList>와 같은 제네릭이 아닌 컬렉션 클래스가 <xref:System.Collections.IEnumerable>을 지원하는 것처럼 <xref:System.Collections.Generic.IEnumerable%601>을 지원합니다.  
  
 제네릭에 대한 자세한 내용은 [제네릭](../../../../csharp/programming-guide/generics/index.md)을 참조하십시오.  
  
## LINQ 쿼리의 IEnumerable\<T\> 변수  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리 변수는 <xref:System.Collections.Generic.IEnumerable%601> 형식으로 지정되거나 <xref:System.Linq.IQueryable%601>과 같은 파생 형식입니다.  형식이 `IEnumerable<Customer>`로 지정된 쿼리 변수가 표시되는 경우 해당 쿼리가 실행될 때 0개 이상의 `Customer` 개체 시퀀스를 생성한다는 것을 의미할 뿐입니다.  
  
 [!code-cs[csLINQGettingStarted#34](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_1.cs)]  
  
 자세한 내용은 [Type Relationships in LINQ Query Operations](../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하십시오.  
  
## 컴파일러에서 제네릭 형식 선언 처리  
 원하는 경우 [var](../../../../csharp/language-reference/keywords/var.md) 키워드를 사용하여 제네릭 구문을 피할 수 있습니다.  `var` 키워드는 `from` 절에 지정된 데이터 소스를 검사하여 쿼리 변수의 형식을 추론하도록 컴파일러에 지시합니다.  다음 예제에서는 이전 예제와 동일하게 컴파일된 코드를 생성합니다.  
  
 [!code-cs[csLINQGettingStarted#35](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/linq-and-generic-types_2.cs)]  
  
 변수 형식이 확실하거나 그룹 쿼리에 의해 생성되는 경우처럼 중첩된 제네릭 형식을 명시적으로 지정하는 것이 중요하지 않은 경우 `var` 키워드가 유용합니다.  일반적으로 `var`을 사용하면 다른 사용자가 코드를 읽기가 더 복잡해집니다.  자세한 내용은 [암시적으로 형식화한 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)를 참조하십시오.  
  
## 참고 항목  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [제네릭](../../../../csharp/programming-guide/generics/index.md)