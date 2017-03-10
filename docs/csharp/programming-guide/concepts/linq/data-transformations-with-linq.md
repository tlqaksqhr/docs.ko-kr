---
title: "LINQ를 통한 데이터 변환(C#) | Microsoft Docs"
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
  - "LINQ[C#], 데이터 변환"
  - "소스 요소[C#의 LINQ]"
  - "여러 입력 결합[C#의 LINQ]"
  - "단일 출력 시퀀스에 대한 여러 출력[C#의 LINQ]"
  - "소스 요소의 하위 집합[C#의 LINQ]"
  - "데이터 원본[C#의 LINQ], 데이터 변환"
  - "데이터 변환[C#의 LINQ]"
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# LINQ를 통한 데이터 변환(C#)
[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)]는 데이터를 검색할 뿐 아니라  데이터를 변환하는 강력한 도구입니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리를 사용하면 소스 시퀀스를 입력으로 사용하고 다양한 방식으로 수정하여 새 출력 시퀀스를 만들 수 있습니다.  정렬 및 그룹화 하 여 요소 자체를 수정 하지 않고 시퀀스 자체를 수정할 수 있습니다. 하지만 아마도 가장 강력한 기능은 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리 새 형식을 만들 수 있습니다.  이 작업은 [select](../../../../csharp/language-reference/keywords/select-clause.md) 절에서 수행됩니다.  예를 들어, 아래와 같은 작업을 수행할 수 있습니다.  
  
-   여러 개의 입력 시퀀스를 새 형식의 단일 출력 시퀀스로 병합합니다.  
  
-   요소가 소스 시퀀스에 있는 각 요소의 한 속성만으로 또는 여러 속성으로 구성된 출력 시퀀스를 만듭니다.  
  
-   요소가 소스 데이터에서 수행된 작업 결과로 구성된 출력 시퀀스를 만듭니다.  
  
-   다른 형식으로 출력 시퀀스를 만듭니다.  예를 들어 SQL 행 또는 텍스트 파일에서 XML로 데이터를 변환할 수 있습니다.  
  
 다음은 몇 가지 예일 뿐입니다.  물론 동일한 쿼리에서 이러한 변환을 다양한 방식으로 결합할 수 있습니다.  한 쿼리의 출력 시퀀스를 새 쿼리의 입력 시퀀스로 사용할 수도 있습니다.  
  
## 여러 입력을 하나의 출력 시퀀스로 결합  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리를 사용하여 둘 이상의 입력 시퀀스의 요소를 포함하는 출력 시퀀스를 만들 수 있습니다.  다음 예제에서는 두 개의 메모리 내 데이터 구조를 결합하는 방법을 보여 주지만, XML이나 SQL 또는 DataSet 소스의 데이터를 결합하는 경우에도 동일한 원칙을 적용할 수 있습니다.  다음 두 개의 클래스 형식이 있다고 가정합니다.  
  
 [!code-cs[CsLINQGettingStarted#7](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#7)]  
  
 다음 예제에서는 쿼리를 보여 줍니다.  
  
 [!code-cs[CSLinqGettingStarted#8](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#8)]  
  
 자세한 내용은 [join 절](../../../../csharp/language-reference/keywords/join-clause.md) 및 [select 절](../../../../csharp/language-reference/keywords/select-clause.md)을 참조하십시오.  
  
## 각 소스 요소의 하위 집합 선택  
 소스 시퀀스에 있는 각 요소의 하위 집합을 선택하는 두 가지 기본 방법이 있습니다.  
  
1.  소스 요소의 한 멤버만 선택하려면 점 작업을 사용합니다.  다음 예제에서는 `Customer` 개체에 `City`라는 문자열을 포함하는 여러 public 속성이 있다고 가정합니다.  실행할 때 이 쿼리는 문자열의 출력 시퀀스를 생성합니다.  
  
    ```  
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2.  소스 요소의 속성을 둘 이상 포함하는 요소를 만들려면 명명된 개체나 익명 형식으로 개체 이니셜라이저를 사용할 수 있습니다.  다음 예제에서는 익명 형식을 사용하여 각 `Customer` 요소의 두 속성을 캡슐화하는 방법을 보여 줍니다.  
  
    ```  
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 자세한 내용은 [개체 및 컬렉션 이니셜라이저](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) 및 [익명 형식](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md)을 참조하십시오.  
  
## 메모리 내부 개체를 XML로 변환  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] 쿼리를 사용하면 메모리 내부 데이터 구조, SQL 데이터베이스, [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)] 데이터 집합 및 XML 스트림 또는 문서 간에 데이터를 쉽게 변환할 수 있습니다.  다음 예제에서는 메모리 내부 데이터 구조의 개체를 XML 요소로 변환합니다.  
  
 [!code-cs[CsLINQGettingStarted#9](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#9)]  
  
 이 코드는 다음과 같은 XML 출력을 생성합니다.  
  
```  
< Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 자세한 내용은 [C\#에서 XML 트리 만들기](../Topic/Creating%20XML%20Trees%20in%20C%23%20\(LINQ%20to%20XML\)1.md)을 참조하십시오.  
  
## 소스 요소에서 작업 수행  
 출력 시퀀스에 소스 시퀀스의 요소나 요소 속성이 포함되지 않을 수도 있습니다.  대신 출력은 소스 요소를 입력 인수로 사용하여 계산된 값의 시퀀스일 수 있습니다.  아래의 단순한 쿼리를 실행하면 값이 `double` 형식 요소의 소스 시퀀스에 기초한 계산을 나타내는 문자열 시퀀스가 출력됩니다.  
  
> [!NOTE]
>  쿼리가 다른 도메인으로 변환되는 경우 쿼리 식에서 메서드를 호출할 수 없습니다.  예를 들어 SQL Server에 해당 컨텍스트가 없으므로 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)]에서 일반 C\# 메서드를 호출할 수는 없습니다.  그러나 저장 프로시저를 메서드에 매핑하고 호출할 수 있습니다.  자세한 내용은 [저장 프로시저](../Topic/Stored%20Procedures.md)을 참조하십시오.  
  
 [!code-cs[CsLINQGettingStarted#10](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#10)]  
  
## 참고 항목  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)   
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [LINQ 쿼리 식](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [select 절](../../../../csharp/language-reference/keywords/select-clause.md)   
 [How to: Combine Data with Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)