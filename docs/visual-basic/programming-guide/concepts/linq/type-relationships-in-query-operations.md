---
title: "Type Relationships in Query Operations (Visual Basic) | Microsoft Docs"
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
  - "variable relationships [LINQ in Visual Basic]"
  - "type information inferred [LINQ in Visual Basic]"
  - "type relationships [LINQ in Visual Basic]"
  - "queries [LINQ in Visual Basic], type relationships"
  - "data sources [LINQ in Visual Basic], type relationships"
  - "LINQ [Visual Basic], type relationships"
  - "inferring type information [LINQ in Visual Basic]"
  - "relationships [LINQ in Visual Basic]"
ms.assetid: b5ff4da5-f3fd-4a8e-aaac-1cbf52fa16f6
caps.latest.revision: 34
caps.handback.revision: 32
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type Relationships in Query Operations (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] 쿼리 작업에 사용되는 변수는 강력한 형식이며 서로 호환되어야 합니다.  강력한 형식 지정은 데이터 소스, 쿼리 자체 및 쿼리 실행에 사용됩니다.  다음 그림에는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 설명하는 데 사용되는 용어가 나와 있습니다.  쿼리의 구성 요소에 대한 자세한 내용은 [기본 쿼리 작업\(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md)을 참조하십시오.  
  
 ![요소가 강조 표시된 의사 코드 쿼리](../../../../visual-basic/programming-guide/concepts/linq/media/sjltyperels.png "SJLtypeRels")  
LINQ 쿼리의 구성 요소  
  
 쿼리의 범위 변수 형식은 데이터 소스의 요소 형식과 호환되어야 합니다.  쿼리 변수의 형식은 `Select` 절에 정의된 시퀀스 요소와 호환되어야 합니다.  마지막으로 시퀀스 요소의 형식은 쿼리를 실행하는 `For Each` 문에 사용되는 루프 제어 변수 형식과 호환되어야 합니다.  이 강력한 형식 지정 기능을 사용하면 컴파일 시 형식 오류 식별이 용이합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]은 *암시적 형식 지정*으로도 알려진 지역 형식 유추를 구현하여 강력한 형식 지정을 편리하게 만듭니다.  이 기능은 이전 예제에 사용되었으며 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 샘플 및 설명서에도 사용되고 있습니다.  Visual Basic에서의 지역 형식 유추는 `As` 절 없이 `Dim` 문을 사용하여 간단하게 수행됩니다.  다음 예제에서 `city`는 문자열로 강력하게 형식이 지정됩니다.  
  
 [!code-vb[VbLINQTypeRels#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_1.vb)]  
  
> [!NOTE]
>  `Option Infer`가 `On`으로 설정된 경우에만 지역 형식 유추가 작동합니다.  자세한 내용은 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)을 참조하십시오.  
  
 그러나 쿼리에서 지역 형식 유추를 사용하는 경우라도 데이터 소스, 쿼리 변수 및 쿼리 실행 루프의 변수 간에는 동일한 형식 관계가 있습니다.  [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리를 작성하는 경우 또는 설명서에서 샘플 및 코드 예제를 사용하는 경우 이러한 형식 관계를 기본적으로 이해하는 것이 유용합니다.  
  
 데이터 소스에서 반환되는 형식과 일치하지 않는 범위 변수에 대해 명시적 형식을 지정해야 할 수도 있습니다.  범위 변수의 형식은 `As` 절을 사용하여 지정할 수 있습니다.  그러나 이 변환이 [축소 변환](../../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)이고 `Option Strict`가 `On`으로 설정되어 있으면 오류가 발생하게 됩니다.  따라서 데이터 소스에서 검색한 값에 대해 변환을 수행하는 것이 좋습니다.  데이터 소스에서 검색한 값은 <xref:System.Linq.Enumerable.Cast%2A> 메서드를 사용하여 명시적 범위 변수 형식으로 변환할 수 있습니다.  또한 `Select` 절에서 선택된 값을 범위 변수의 형식과 다른 명시적 형식으로 캐스팅할 수도 있습니다.  다음 코드에서 이러한 사항을 확인할 수 있습니다.  
  
 [!code-vb[VbLINQTypeRels#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_2.vb)]  
  
## 소스 데이터의 전체 요소를 반환하는 쿼리  
 다음 예제에서는 소스 데이터에서 선택된 요소의 시퀀스를 반환하는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 작업을 보여 줍니다.  소스인 `names`에는 문자열의 배열이 포함되어 있으며 쿼리 출력은 문자 M으로 시작하는 문자열이 포함된 시퀀스입니다.  
  
 [!code-vb[VbLINQTypeRels#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_3.vb)]  
  
 이는 다음 코드와 동일하지만 작성하기가 훨씬 쉽고 간단합니다.  Visual Basic에서는 쿼리에서 지역 형식 유추에 의존하는 스타일이 선호됩니다.  
  
 [!code-vb[VbLINQTypeRels#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/type-relationships-in-query-operations_4.vb)]  
  
 형식이 암시적으로 결정되는지 또는 명시적으로 결정되는지에 관계없이 앞의 코드 예제 모두에 다음 관계가 있습니다.  
  
1.  데이터 소스의 요소 형식인 `names`는 쿼리에서 범위 변수 형식인 `name`입니다.  
  
2.  선택된 개체의 형식인 `name`은 쿼리 변수의 형식인 `mNames`를 결정합니다.  여기서 `name`은 문자열이므로 쿼리 변수는 Visual Basic에서 IEnumerable\(Of String\)입니다.  
  
3.  `mNames`에 정의된 쿼리는 `For Each` 루프에서 실행됩니다.  루프는 쿼리 실행의 결과를 반복합니다.  `mNames`를 실행할 때 문자열의 시퀀스를 반환하므로 루프 반복 변수인 `nm`도 문자열입니다.  
  
## 선택한 요소에서 한 필드를 반환하는 쿼리  
 다음 예제에서는 데이터 소스에서 선택된 각 요소의 한 부분만 포함하는 시퀀스를 반환하는 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 쿼리 작업을 보여 줍니다.  이 쿼리에서는 `Customer` 개체의 컬렉션을 데이터 소스로 사용하며 `Name` 속성만 결과로 프로젝션합니다.  고객 이름은 문자열이므로 쿼리에서 문자열의 시퀀스를 출력으로 생성합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 변수 간 관계가 더 간단해진 예제의 관계와 유사합니다.  
  
1.  데이터 소스의 요소 형식인 `customers`는 쿼리에서 범위 변수 형식인 `cust`입니다.  이 예제에서 해당 형식은 `Customer`입니다.  
  
2.  `Select` 문은 전체 개체 대신 각 `Customer` 개체의 `Name` 속성을 반환합니다.  `Name`이 문자열이므로 쿼리 변수인 `custNames`는 `Customer`가 아니라 다시 IEnumerable\(Of String\)입니다.  
  
3.  `custNames`는 문자열의 시퀀스를 나타내므로 `For Each` 루프의 반복 변수인 `custName`은 문자열이어야 합니다.  
  
 다음 예제와 같이 지역 형식 유추를 사용하지 않는 경우 앞의 예제는 작성 및 이해가 다소 복잡해질 것입니다.  
  
<CodeContentPlaceHolder>1</CodeContentPlaceHolder>  
## 익명 형식이 필요한 쿼리  
 다음 예제에서는 다소 복잡한 상황을 보여 줍니다.  앞의 예제에서는 모든 변수에 대해 형식을 명시적으로 지정하기가 불편했습니다.  이 예제에서는 형식을 명시적으로 지정할 수 없습니다.  데이터 소스에서 전체 `Customer` 요소를 선택하거나 각 요소에서 단일 필드를 선택하는 대신 이 쿼리의 `Select` 절은 원래 `Customer` 개체의 두 속성인 `Name` 및 `City`를 반환합니다.  `Select` 절에 대한 응답으로 컴파일러는 이러한 두 속성을 포함하는 익명 형식을 정의합니다.  `For Each` 루프에서 `nameCityQuery`를 실행한 결과는 새 익명 형식 인스턴스의 컬렉션입니다.  익명 형식에 사용 가능한 이름이 없으므로 `nameCityQuery` 또는 `custInfo`의 형식을 명시적으로 지정할 수 없습니다.  즉, 익명 형식을 사용하면 `IEnumerable(Of String)`에서 `String`을 대신하여 사용할 형식 이름이 없습니다.  자세한 내용은 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)을 참조하십시오.  
  
<CodeContentPlaceHolder>2</CodeContentPlaceHolder>  
 앞의 예제의 경우 모든 변수에 대해 형식을 지정할 수는 없지만 관계는 동일하게 유지됩니다.  
  
1.  데이터 소스의 요소 형식은 다시 쿼리의 범위 요소 형식입니다.  이 예제에서 `cust`는 `Customer`의 인스턴스입니다.  
  
2.  `Select` 문은 익명 형식을 생성하므로 쿼리 변수인 `nameCityQuery`를 익명 형식으로 암시적으로 형식화해야 합니다.  익명 형식에는 사용 가능한 이름이 없으므로 명시적으로 지정할 수 없습니다.  
  
3.  `For Each` 루프에서 반복 변수의 형식은 2단계에서 만든 익명 형식입니다.  이 형식의 경우 사용 가능한 이름이 없으므로 루프 반복 변수의 형식은 암시적으로 결정되어야 합니다.  
  
## 참고 항목  
 [Getting Started with LINQ in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Anonymous Types](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Queries](../../../../visual-basic/language-reference/queries/queries.md)