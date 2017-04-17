---
title: ".NET Framework의 날짜 및 시간 문자열 구문 분석 | Microsoft Docs"
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
  - "기본 형식, 문자열 구문 분석"
  - "날짜 및 시간 문자열"
  - "DateTime 개체"
  - "열거형[.NET Framework], 문자열 구문 분석"
  - "ParseExact 메서드"
  - "문자열 구문 분석, 날짜 및 시간 문자열"
  - "시간 문자열"
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 24
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 24
---
# .NET Framework의 날짜 및 시간 문자열 구문 분석
구문 분석 메서드는 날짜 및 시간의 문자열 표현을 해당 <xref:System.DateTime> 개체로 변환합니다.  <xref:System.DateTime.Parse%2A> 및 <xref:System.DateTime.TryParse%2A> 메서드는 날짜 및 시간의 몇 가지 일반적인 표현을 모두 변환합니다.  <xref:System.DateTime.ParseExact%2A> 및 <xref:System.DateTime.TryParseExact%2A> 메서드는 날짜 및 시간 형식 문자열로 지정된 패턴을 따르는 문자열 표현을 변환합니다. [표준 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) 및 [사용자 지정 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)에 대한 항목을 참조하십시오.  
  
 구문 분석은 날짜 및 시간 구분 기호와 월, 일 및 연대 이름에 사용되는 문자열과 같은 정보를 제공하는 형식 공급자의 속성에 따라 영향을 받습니다.  형식 공급자는 현재 스레드 문화권에 의해 암시적으로 제공되거나 구문 분석 메서드의 <xref:System.IFormatProvider> 매개 변수에 의해 명시적으로 제공되는 현재 <xref:System.Globalization.DateTimeFormatInfo> 개체입니다.  <xref:System.IFormatProvider> 매개 변수의 경우 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체나 <xref:System.Globalization.DateTimeFormatInfo> 개체를 지정합니다.  
  
 구문 분석할 날짜의 문자열 표현에는 월이 포함되고 일 또는 연도 중 적어도 하나가 포함되어야 합니다.  시간의 문자열 표현에는 시가 포함되고 분 또는 AM\/PM 지정자 중 적어도 하나가 포함되어야 합니다.  그러나 생략된 구성 요소에는 가능하면 구문 분석 시 기본값이 제공됩니다.  날짜, 연도, 일\(월 기준\) 및 시간이 생략되었을 때 기본적으로 제공되는 값은 각각 현재 날짜, 현재 연도, 월의 첫 번째 일 및 자정입니다.  
  
 문자열 표현에 시간만 지정된 경우 구문 분석을 실행하면 <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> 및 <xref:System.DateTime.Day%2A> 속성이 <xref:System.DateTime.Today%2A> 속성의 해당 값으로 설정된 <xref:System.DateTime> 개체가 반환됩니다.  그러나 구문 분석 메서드에 <xref:System.Globalization.DateTimeStyles> 상수가 지정된 경우 결과 연도, 월 및 일 속성은 값 `1`로 설정됩니다.  
  
 날짜 및 시간의 문자열 표현에는 날짜 및 시간 구성 요소뿐 아니라 시간이 UTC\(협정 세계시\)와 얼마나 차이가 나는지를 나타내는 오프셋이 포함될 수 있습니다.  예를 들어, 문자열 "2\/14\/2007 5:32:00 \-7:00"은 UTC보다 7시간 이른 시간을 정의합니다.  시간의 문자열 표현에서 오프셋이 생략된 경우 구문 분석을 실행하면 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind?displayProperty=fullName>로 지정된 <xref:System.DateTime> 개체가 반환됩니다.  오프셋을 지정한 경우 구문 분석을 실행하면 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind>로 지정되고 해당 값이 컴퓨터의 지역 표준 시간대로 조정된 <xref:System.DateTime> 개체가 반환됩니다.  구문 분석 메서드와 <xref:System.Globalization.DateTimeStyles> 상수를 함께 사용하여 이 동작을 수정할 수 있습니다.  
  
 형식 공급자는 모호한 날짜 값을 해석하는 데도 사용됩니다.  예를 들어, 문자열 "02\/03\/04"로 나타낸 날짜의 경우 월, 일 및 연도에 해당하는 구성 요소가 분명하지 않습니다.  이 경우 구성 요소는 형식 공급자의 비슷한 날짜 형식 순서에 따라 해석됩니다.  
  
## Parse  
 다음 코드 예제에서는 **Parse** 메서드를 사용하여 문자열을 **DateTime**으로 변환하는 방법을 보여 줍니다.  이 예제에서는 현재 스레드와 연결된 문화권을 사용하여 구문 분석을 수행합니다.  현재 문화권과 연결된 <xref:System.Globalization.CultureInfo>가 입력 문자열을 구문 분석할 수 없으면 <xref:System.FormatException>이 throw됩니다.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 또한 **CultureInfo**가 해당 개체에서 정의하는 문화권 중 하나로 설정되도록 지정하거나 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName> 속성에서 반환되는 표준 <xref:System.Globalization.DateTimeFormatInfo> 개체 중 하나를 지정할 수도 있습니다.  다음 코드 예제에서는 형식 공급자를 사용하여 독일어 문자열을 **DateTime**으로 구문 분석합니다.  de\-DE culture를 나타내는 **CultureInfo**는 이 특정 문자열을 올바르게 구문 분석할 수 있도록 구문 분석되는 문자열과 함께 정의되고 전달됩니다.  이렇게 하면 **CurrentThread**의 **CurrentCulture**에 있는 설정은 무시됩니다.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 그러나 <xref:System.DateTime.Parse%2A> 메서드의 오버로드를 사용하여 사용자 지정 형식 공급자를 지정할 수 있지만 이 메서드에서는 비표준 형식 공급자를 사용할 수 없습니다.  비표준 형식으로 표시된 날짜 및 시간을 구문 분석하려면 대신 <xref:System.DateTime.ParseExact%2A> 메서드를 사용합니다.  
  
 다음 코드 예제에서는 <xref:System.Globalization.DateTimeStyles> 열거형을 사용하여 해당 문자열이 정의하지 않는 필드에 대해 현재 날짜 및 시간 정보가 **DateTime**에 추가되지 않도록 지정합니다.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## ParseExact  
 <xref:System.DateTime.ParseExact%2A?displayProperty=fullName> 메서드는 지정된 문자열 패턴을 따르는 문자열을 **DateTime** 개체로 변환합니다.  지정된 형식이 아닌 문자열이 이 메서드에 전달되면 <xref:System.FormatException>이 throw됩니다.  표준 날짜 및 시간 서식 지정자 중 하나를 지정하거나 사용자 지정 날짜 및 시간 서식 지정자를 제한적으로 조합하여 지정할 수 있습니다.  사용자 지정 서식 지정자를 사용하면 사용자 지정 인식 문자열을 생성할 수 있습니다.  지정자에 대한 설명은 [표준 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) 및 [사용자 지정 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)에 대한 항목을 참조하십시오.  
  
 <xref:System.DateTime.ParseExact%2A> 메서드의 각 오버로드에는 일반적으로 문자열의 서식 지정에 대한 문화권 관련 정보를 제공하는 <xref:System.IFormatProvider> 매개 변수도 포함되어 있습니다.  일반적으로 이 <xref:System.IFormatProvider> 개체는 표준 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체나 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName> 속성에서 반환되는 <xref:System.Globalization.DateTimeFormatInfo> 개체입니다.  그러나 다른 날짜 및 시간 구문 분석 기능과 달리 이 메서드에서는 비표준 날짜 및 시간 형식을 정의하는 <xref:System.IFormatProvider>도 지원합니다.  
  
 다음 코드 예제에서 **ParseExact** 메서드에는 구문 분석할 문자열 개체와 서식 지정자 및 **CultureInfo** 개체가 차례로 전달됩니다.  이 **ParseExact** 메서드는 en\-US culture에서 긴 날짜 패턴을 표시하는 문자열만 구문 분석합니다.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## 참고 항목  
 [문자열 구문 분석](../../../docs/standard/base-types/parsing-strings.md)   
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)   
 [.NET Framework의 형식 변환](../../../docs/standard/base-types/type-conversion.md)