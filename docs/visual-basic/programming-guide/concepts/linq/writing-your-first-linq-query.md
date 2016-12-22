---
title: "LINQ 쿼리 처음 작성(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "쿼리[Visual Basic의 LINQ], 작성"
  - "LINQ 쿼리[Visual Basic]"
  - "LINQ[Visual Basic], 쿼리 작성"
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
caps.latest.revision: 56
caps.handback.revision: 54
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# LINQ 쿼리 처음 작성(Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

*쿼리*는 데이터 소스에서 데이터를 검색하는 식입니다.  쿼리는 전용 쿼리 언어로 표현됩니다.  관계형 데이터베이스 SQL이나 XML용 XQuery와 같은 다양한 유형의 데이터 소스를 위한 여러 언어가 개발되었습니다.  이로 인해 응용 프로그램 개발자는 지원되는 각 데이터 소스 형식이나 데이터 형식에 대해 새 쿼리 언어를 배워야 합니다.  
  
 [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]는 다양한 종류의 데이터 소스와 형식에서 일관성 있는 데이터 작업 모델을 제공하여 이러한 상황을 개선합니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리에서는 항상 개체를 사용합니다.  XML 문서, SQL 데이터베이스, ADO.NET 데이터 집합과 엔터티, .NET Framework 컬렉션 및 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 공급자를 사용할 수 있는 다른 모든 소스나 형식의 데이터를 쿼리 및 변환하기 위해 동일한 기본 코딩 패턴을 사용합니다.  이 문서에서는 기본 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 만들고 사용하는 세 단계에 대해 설명합니다.  
  
 ![비디오에 링크](../../../../csharp/programming-guide/concepts/linq/media/playvideo.png "PlayVideo") 관련 비디오 데모를 보려면 [How Do I: Get Started with LINQ?](http://go.microsoft.com/fwlink/?LinkId=133021)를 참조하십시오.  
  
## 쿼리 작업의 세 단계  
 모든 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 작업은 다음 세 가지 작업으로 구성됩니다.  
  
1.  한 개 이상의 데이터 소스를 가져옵니다.  
  
2.  쿼리를 만듭니다.  
  
3.  쿼리를 실행합니다.  
  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]에서 쿼리 실행은 쿼리 만들기와 다릅니다.  단순히 쿼리를 만드는 경우 데이터를 검색하지 않습니다.  이 내용에 대해서는 이 항목의 뒷부분에서 자세히 설명합니다.  
  
 다음 예제에서는 쿼리 작업의 세 부분을 보여 줍니다.  이 예제에서는 데모 목적을 위해 정수 배열을 편리한 데이터 소스로 사용합니다.  그러나 다른 데이터 소스에도 동일한 개념이 적용됩니다.  
  
> [!NOTE]
>  에 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic), 되도록  **Option infer** 로 설정 된  **의**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 출력  
  
 `0 2 4 6`  
  
## 데이터 소스  
 앞의 예제에서는 데이터 소스가 배열이기 때문에 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스가 암시적으로 지원됩니다.  이러한 사실로 인해 배열을 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리의 데이터 소스로 사용할 수 있습니다.  형식을 지 원하는 <xref:System.Collections.Generic.IEnumerable%601> 또는 제네릭 같은 파생된 인터페이스 <xref:System.Linq.IQueryable%601> 이라고  *쿼리 가능한 형식*을.  
  
 암시적으로 쿼리 가능한 형식인 배열은 특별한 처리나 수정 없이 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 데이터 소스로 사용할 수 있습니다.  지 원하는 모든 컬렉션 형식에 대해 마찬가지입니다 <xref:System.Collections.Generic.IEnumerable%601>, 제네릭 등 <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>, 및 기타.NET Framework 클래스 라이브러리의 클래스입니다.  
  
 소스 데이터가 이미 구현 하지 않는 경우 <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 공급자를 필요로 하는 기능을 구현 하는  *표준 쿼리 연산자* 해당 데이터 원본에 대 한.  예를 들어 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]은 다음 예제와 같이 XML 문서를 쿼리 가능한 <xref:System.Xml.Linq.XElement> 형식으로 로드하는 작업을 처리합니다.  표준 쿼리 연산자에 대한 자세한 내용은 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조하십시오.  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]에서는 먼저 개체 관계형 매핑을 디자인 타임에 수동으로 만들거나 [O\/R 디자이너\(개체 관계형 디자이너\)](/visual-studio/data-tools/linq-to-sql-tools-in-visual-studio2)를 사용하여 만듭니다.  사용자가 개체에 대한 쿼리를 작성하고 런타임에 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)]은 데이터베이스와의 통신을 처리합니다.  다음 예제에서 `customers`는 데이터베이스의 특정 테이블을 나타내고 <xref:System.Data.Linq.Table%601>은 제네릭 <xref:System.Linq.IQueryable%601>을 지원합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 특정 데이터 소스 형식을 만드는 방법에 대한 자세한 내용은 다양한 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 공급자에 대한 설명서를 참조하십시오.  이러한 공급자 목록을 보려면 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)를 참조하십시오. 기본 규칙은 간단합니다. 즉, [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 데이터 소스는 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스 또는 이 인터페이스에서 상속되는 인터페이스를 지원하는 모든 개체입니다.  
  
> [!NOTE]
>  제네릭이 아닌 <xref:System.Collections.IEnumerable> 인터페이스를 지원하는 <xref:System.Collections.ArrayList>와 같은 형식을 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 데이터 소스로 사용할 수도 있습니다.  <xref:System.Collections.ArrayList>를 사용하는 예제를 보려면 [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md)를 참조하십시오.  
  
## 쿼리  
 쿼리에서는 데이터 소스에서 검색할 정보를 지정합니다.  해당 정보를 반환하기 전에 정렬 또는 그룹화하거나 구조를 지정하는 방법을 지정할 수도 있습니다.  쿼리를 만들 수 있도록 Visual Basic에서는 새 쿼리 구문을 언어에 통합했습니다.  
  
 다음 예제에서 쿼리를 실행하면 정수 배열 `numbers`의 모든 짝수가 반환됩니다.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 쿼리 식에는 세 개의 절인 `From`, `Where` 및 `Select`가 포함되어 있습니다.  각 쿼리 식 절의 특정 기능과 용도에 대해서는 [기본 쿼리 작업\(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)에서 설명합니다.  자세한 내용은 [Queries](../../../../visual-basic/language-reference/queries/queries.md)을 참조하십시오.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]에서는 쿼리 정의를 변수에 저장한 후 나중에 실행하는 경우가 많습니다.  쿼리 변수 같이 `evensQuery` 이전 예에서 쿼리 가능한 형식 이어야 합니다. 종류를 `evensQuery` 는 `IEnumerable(Of Integer)`, 로컬 형식 유추를 사용 하 여 컴파일러에 의해 할당 된.  
  
 쿼리 변수 자체는 아무 작업도 수행하지 않으며 데이터를 반환하지 않습니다.  쿼리 변수는 쿼리 정의를 저장하는 기능만 수행합니다.  앞의 예제에서 쿼리를 실행하는 것은 `For Each` 루프입니다.  
  
## 쿼리 실행  
 쿼리 실행은 쿼리 만들기와 별개의 작업입니다.  쿼리 만들기는 쿼리를 정의하지만 실행은 다른 메커니즘으로 트리거됩니다.  쿼리를 정의하자마자 실행할 수도 있고\(*즉시 실행*\) 정의를 저장한 다음 나중에 쿼리를 실행할 수도 있습니다\(*지연된 실행*\).  
  
### 지연된 실행  
 일반적인 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리는 앞의 예제에서 `evensQuery`를 정의하는 쿼리와 유사합니다.  쿼리를 만들지만 즉시 실행하지는 않습니다.  대신 쿼리 정의가 쿼리 변수 `evensQuery`에 저장됩니다.  나중에 쿼리를 실행할 때는 일반적으로 값 시퀀스를 반환하는 `For Each` 루프를 사용하거나 `Count` 또는 `Max`와 같은 표준 쿼리 연산자를 적용합니다.  이 프로세스를 *지연된 실행*이라고 합니다.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 값 시퀀스의 경우 `For Each` 루프\(앞의 예제에서 `number`\)에 반복 변수를 사용하여 검색된 데이터에 액세스합니다.  쿼리 변수 `evensQuery`는 쿼리 결과가 아니라 쿼리 정의를 저장하므로 쿼리 변수를 두 번 이상 사용하여 언제든지 쿼리를 실행할 수 있습니다.  예를 들어 별개의 응용 프로그램에 의해 계속 업데이트되는 데이터베이스가 응용 프로그램에 있다고 가정해 봅니다.  해당 데이터베이스에서 데이터를 검색하는 쿼리를 만든 후 `For Each` 루프를 사용하여 반복해서 쿼리를 실행하고 매번 가장 최근 데이터를 검색할 수 있습니다.  
  
 다음 예제에서는 지연된 실행의 작동 방식을 보여 줍니다.  앞의 예제와 같이 `For Each` 루프를 사용하여 `evensQuery2`를 정의하고 실행하면 데이터 소스 `numbers`의 일부 요소가 변경됩니다.  그런 다음 두 번째 `For Each` 루프에서 다시 `evensQuery2`를 실행합니다.  두 번째에는 `For Each` 루프가 `numbers`의 새 값을 사용하여 쿼리를 다시 실행하므로 결과가 다릅니다.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 출력  
  
 `Evens in original array:`  
  
 `0 2 4 6`  
  
 `Evens in changed array:`  
  
 `0 10 2 22 8`  
  
### 즉시 실행  
 쿼리의 지연된 실행에서 쿼리 정의는 나중에 실행하기 위해 쿼리 변수에 저장됩니다.  즉시 실행에서는 정의할 때 쿼리가 실행됩니다.  쿼리 결과의 개별 요소에 액세스해야 하는 메서드를 적용하면 실행이 트리거됩니다.  단일 값을 반환하는 표준 쿼리 연산자 중 하나를 사용하여 즉시 실행을 강제하는 경우가 많습니다.  예를 들어 `Count`, `Max`, `Average`, `First` 등이 있습니다.  표준 쿼리 연산자는 singleton 결과를 계산 및 반환하기 위해 적용되는 즉시 쿼리를 실행합니다.  단일 값을 반환하는 표준 쿼리 연산자에 대한 자세한 내용은 [Aggregation Operations](../../../../visual-basic/programming-guide/concepts/linq/aggregation-operations.md), [Element Operations](../../../../visual-basic/programming-guide/concepts/linq/element-operations.md) 및 [Quantifier Operations](../../../../visual-basic/programming-guide/concepts/linq/quantifier-operations.md)을 참조하십시오.  
  
 다음 쿼리는 정수 배열의 짝수 개수를 반환합니다.  쿼리 정의가 저장되지 않으며 `numEvens`는 간단한 `Integer`입니다.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 `Aggregate` 메서드를 사용하면 동일한 결과를 얻을 수 있습니다.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 다음 코드와 같이 쿼리\(즉시 실행\) 또는 쿼리 변수\(지연된 실행\)에서 `ToList` 또는 `ToArray` 메서드를 호출하여 쿼리 실행을 강제할 수도 있습니다.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 앞의 예제에서 `evensQuery3`은 쿼리 변수이지만 `evensList`는 목록이고 `evensArray`는 배열입니다.  
  
 `ToList` 또는 `ToArray`를 사용하여 즉시 실행을 강제하는 기능은 즉시 쿼리를 실행하고 그 결과를 단일 컬렉션 개체에 캐시하는 경우에 특히 유용합니다.  이러한 메서드에 대한 자세한 내용은 [Converting Data Types](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)을 참조하십시오.  
  
 <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> 메서드와 같은 `IEnumerable` 메서드를 사용하여 쿼리를 실행할 수도 있습니다.  
  
## 관련 비디오 데모  
 [How Do I: Get Started with LINQ?](http://go.microsoft.com/fwlink/?LinkId=133021)  
  
 [Video How to: Writing Queries in Visual Basic](http://go.microsoft.com/fwlink/?LinkID=100356)  
  
## 참고 항목  
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [LINQ 샘플](../Topic/LINQ%20Samples.md)   
 [O\/R 디자이너 개요](../Topic/LINQ%20to%20SQL%20Tools%20in%20Visual%20Studio1.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)