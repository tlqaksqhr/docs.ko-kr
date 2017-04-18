---
title: ".NET Framework의 기타 문자열 구문 분석 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "문자 데이터 형식, 문자열 구문 분석"
  - "열거형[.NET Framework], 문자열 구문 분석"
  - "기본 형식, 문자열 구문 분석"
  - "문자열 구문 분석, 기타 문자열"
  - "부울 데이터 형식, 문자열 구문 분석"
ms.assetid: d139bc00-3c4e-4d78-ac9a-5c951b258d28
caps.latest.revision: 15
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# .NET Framework의 기타 문자열 구문 분석
숫자 및 <xref:System.DateTime> 문자열 외에 <xref:System.Char>, <xref:System.Boolean> 및 <xref:System.Enum> 형식을 나타내는 문자열을 데이터 형식으로 구문 분석할 수도 있습니다.  
  
## Char  
 **Char** 데이터 형식과 연관된 정적 구문 분석 메서드는 단일 문자가 들어 있는 문자열을 해당 유니코드 값으로 변환하는 데 유용합니다.  다음 코드 예제에서는 문자열을 유니코드 문자로 구문 분석합니다.  
  
 [!code-cpp[Conceptual.String.Parse#2](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#2)]
 [!code-csharp[Conceptual.String.Parse#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#2)]
 [!code-vb[Conceptual.String.Parse#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#2)]  
  
## Boolean  
 **Boolean** 데이터 형식에는 부울 값을 나타내는 문자열을 실제 **Boolean** 형식으로 변환하는 데 사용할 수 있는 **Parse** 메서드가 있습니다.  이 메서드는 대\/소문자를 구분하지 않으며 "True" 또는 "False"가 들어 있는 문자열을 올바르게 구문 분석할 수 있습니다. **Boolean** 형식과 연관된 **Parse** 메서드는 공백으로 둘러싸인 문자열만 구문 분석할 수 있습니다.  다른 문자열이 전달되면 <xref:System.FormatException>이 throw됩니다.  
  
 다음 코드 예제에서는 **Parse** 메서드를 사용하여 문자열을 부울 값으로 변환합니다.  
  
 [!code-cpp[Conceptual.String.Parse#3](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#3)]
 [!code-csharp[Conceptual.String.Parse#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#3)]
 [!code-vb[Conceptual.String.Parse#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#3)]  
  
## 열거형  
 정적 **Parse** 메서드를 사용하여 열거형 형식을 문자열의 값으로 초기화할 수 있습니다.  이 메서드에서는 구문 분석하려는 열거형과 구문 분석할 문자열, 그리고 구문 분석의 대\/소문자 구분 여부를 나타내는 선택적 부울 플래그를 받아 들입니다.  구문 분석할 문자열에는 몇 개의 값이 쉼표로 구분되어 들어 있을 수 있으며, 이 값의 앞이나 뒤에는 하나 이상의 공백이 있을 수 있습니다.  문자열에 여러 개의 값이 들어 있는 경우 반환되는 개체의 값은 지정된 모든 값을 비트 OR 연산으로 결합한 값입니다.  
  
 다음 예제에서는 **Parse** 메서드를 사용하여 문자열 표현을 열거형 값으로 변환합니다.  <xref:System.DayOfWeek> 열거형은 문자열에서 **Thursday**로 초기화됩니다.  
  
 [!code-cpp[Conceptual.String.Parse#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.string.parse/cpp/parse.cpp#4)]
 [!code-csharp[Conceptual.String.Parse#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.parse/cs/parse.cs#4)]
 [!code-vb[Conceptual.String.Parse#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.parse/vb/parse.vb#4)]  
  
## 참고 항목  
 [문자열 구문 분석](../../../docs/standard/base-types/parsing-strings.md)   
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)   
 [.NET Framework의 형식 변환](../../../docs/standard/base-types/type-conversion.md)