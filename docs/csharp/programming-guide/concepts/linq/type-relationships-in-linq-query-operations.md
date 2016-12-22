---
title: "Type Relationships in LINQ Query Operations (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "inferring type information [LINQ in C#]"
  - "data sources [LINQ in C#], type relationships"
  - "queries [LINQ in C#], type relationships"
  - "relationships [LINQ in C#]"
  - "type relationships [LINQ in C#]"
  - "variable relationships [LINQ in C#]"
  - "type information inferred [LINQ in C#]"
  - "data transformations [LINQ in C#]"
  - "LINQ [C#], type relationships"
ms.assetid: 99118938-d47c-4d7e-bb22-2657a9f95268
caps.latest.revision: 25
caps.handback.revision: 23
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Type Relationships in LINQ Query Operations (C#)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

쿼리를 효과적으로 작성하려면 전체 쿼리 작업에 있는 변수 형식 전체가 서로 관련되어 있는 방식을 이해해야 합니다.  이러한 관계를 이해하고 있는 경우 설명서의 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 샘플 및 코드 예제를 좀 더 쉽게 이해할 수 있습니다.  그리고 `var`을 사용하여 변수를 암시적으로 형식화한 경우 내부적으로 어떤 일이 진행되는지 이해할 수 있습니다.  
  
 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 쿼리 작업은 데이터 소스, 쿼리 자체 및 쿼리 식에 강력하게 형식화되어 있습니다.  쿼리에 있는 변수의 형식은 데이터 소스에 있는 요소의 형식 및 `foreach` 문에 있는 반복 변수의 형식과 호환되어야 합니다.  이러한 강력한 형식화가 적용되므로 형식 오류가 있더라도 사용자가 그러한 오류를 발견하기 전에 컴파일 타임에 해당 오류를 catch하여 수정할 수 있습니다.  
  
 이러한 형식 관계를 보여 주기 위해 다음에 오는 대부분의 예제는 모든 변수에 대해 명시적 형식화를 사용합니다.  마지막 예제에서는 [var](../../../../csharp/language-reference/keywords/var.md)을 사용하여 암시적 형식화를 사용할 때도 동일한 원칙을 적용하는 방식을 보여 줍니다.  
  
## 소스 데이터를 변환하지 않는 쿼리  
 다음 그림에서는 데이터에서 변환을 수행하지 않는 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to Objects 쿼리 작업을 보여 줍니다.  소스에는 문자열의 시퀀스가 포함되며 쿼리 출력도 문자열의 시퀀스입니다.  
  
 ![LINQ 쿼리에서 데이터 형식의 관계](../../../../csharp/programming-guide/concepts/linq/media/linq_flow1.png "LINQ\_flow1")  
  
1.  데이터 소스의 형식 인수는 범위 변수의 형식을 결정합니다.  
  
2.  선택된 개체의 형식은 쿼리 변수의 형식을 결정합니다.  여기서 `name`은 문자열입니다.  따라서 쿼리 변수는 `IEnumerable`\<string\>입니다.  
  
3.  쿼리 변수는 `foreach` 문에서 반복됩니다.  쿼리 변수가 문자열의 시퀀스이므로 반복 변수도 문자열입니다.  
  
## 소스 데이터를 변환하는 쿼리  
 다음 그림에서는 데이터에서 간단한 변환을 수행하는 [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq_md.md)] 쿼리 작업을 보여 줍니다.  쿼리에서는 `Customer` 개체의 시퀀스를 입력으로 사용하며 결과에서 `Name` 속성만 선택합니다.  `Name`이 문자열이므로 쿼리에서 문자열의 시퀀스를 출력으로 생성합니다.  
  
 ![데이터 형식을 변환하는 쿼리](../../../../csharp/programming-guide/concepts/linq/media/linq_flow2.png "LINQ\_flow2")  
  
1.  데이터 소스의 형식 인수는 범위 변수의 형식을 결정합니다.  
  
2.  `select` 문은 전체 `Customer` 개체 대신 `Name` 속성을 반환합니다.  `Name`은 문자열이므로 `custNameQuery`의 형식 인수는 `Customer`가 아니라 `string`입니다.  
  
3.  `custNameQuery`는 문자열의 시퀀스이므로 `foreach` 루프의 반복 변수도 `string`이어야 합니다.  
  
 다음 그림에서는 다소 복잡한 변환을 보여 줍니다.  `select` 문은 원래 `Customer` 개체의 두 멤버만 캡처하는 익명 형식을 반환합니다.  
  
 ![데이터 형식을 변환하는 쿼리](../../../../csharp/programming-guide/concepts/linq/media/linq_flow3.png "LINQ\_flow3")  
  
1.  데이터 소스의 형식 인수는 항상 쿼리의 범위 변수 형식입니다.  
  
2.  `select` 문은 익명 형식을 생성하므로 `var`을 사용하여 쿼리 변수를 암시적으로 형식화해야 합니다.  
  
3.  쿼리 변수의 형식은 암시적이므로 `foreach` 루프의 반복 변수도 암시적이어야 합니다.  
  
## 컴파일러에서 형식 정보를 유추하도록 지정  
 쿼리 작업의 형식 관계를 이해해야 하지만 컴파일러에서 사용자를 위해 모든 작업을 수행하게 하는 옵션이 있습니다.  쿼리 작업에 있는 임의의 지역 변수에 대해 키워드 [var](../../../../csharp/language-reference/keywords/var.md)을 사용할 수 있습니다.  다음 그림은 앞에서 설명한 예제 번호 2와 비슷합니다.  하지만 컴파일러는 쿼리 작업의 각 변수에 대해 강력한 형식을 제공합니다.  
  
 ![암시적 형식 지정을 사용하는 형식 흐름](../../../../csharp/programming-guide/concepts/linq/media/linq_flow4.png "LINQ\_flow4")  
  
 `var`에 대한 자세한 내용은 [암시적으로 형식화한 지역 변수](../../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md)을 참조하십시오.  
  
## 참고 항목  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)   
 [Type Relationships in Query Operations \(Visual Basic\)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md)