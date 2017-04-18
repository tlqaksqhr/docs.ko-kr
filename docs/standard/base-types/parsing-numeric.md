---
title: ".NET Framework에서 숫자 문자열 구문 분석 | Microsoft Docs"
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
  - "문자열 구문 분석, 숫자 문자열"
  - "숫자 문자열"
  - "열거형[.NET Framework], 문자열 구문 분석"
  - "기본 형식, 문자열 구문 분석"
ms.assetid: e39324ee-72e5-42d4-a80d-bf3ee7fc6c59
caps.latest.revision: 20
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 20
---
# .NET Framework에서 숫자 문자열 구문 분석
모든 숫자 형식에는 숫자의 문자열 표현을 숫자 형식으로 변환하는 데 사용할 수 있는 두 가지 정적 구문 분석 메서드인 `Parse` 및 `TryParse`가 있습니다.  이러한 메서드를 사용하면 [표준 숫자 형식 문자열](../../../docs/standard/base-types/standard-numeric-format-strings.md) 및 [사용자 지정 숫자 형식 문자열](../../../docs/standard/base-types/custom-numeric-format-strings.md)에서 설명된 형식 문자열을 사용하여 생성된 문자열을 구문 분석할 수 있습니다.  기본적으로 `Parse` 및 `TryParse` 메서드는 정수 계열 10진수만 포함된 문자열을 정수 값으로 변환할 수 있습니다.  이러한 메서드는 정수 계열 및 소수 계열 10진수, 그룹 구분 기호 및 소수 구분 기호가 포함된 문자열을 부동 소수 값으로 변환할 수 있습니다.  `Parse` 메서드는 작업이 실패할 경우 예외를 throw하지만 `TryParse` 메서드는 `false`를 반환합니다.  
  
## 구문 분석 및 형식 공급자  
 일반적으로 숫자 값의 문자열 표현은 문화권마다 다릅니다.  통화 기호, 그룹\(또는 천 단위 자리\) 구분 기호, 소수 구분 기호 같은 숫자 문자열의 요소는 모두 문화권마다 다릅니다.  구문 분석 메서드는 이러한 문화권별 차이를 인식하는 형식 공급자를 암시적으로 또는 명시적으로 사용합니다.  `Parse` 또는 `TryParse` 메서드에 대한 호출에서 형식 공급자가 지정되어 있지 않으면 현재 스레드 문화권\(<xref:System.Globalization.NumberFormatInfo.CurrentInfo%2A?displayProperty=fullName> 속성으로 반환된 <xref:System.Globalization.NumberFormatInfo> 개체\)과 연관된 형식 공급자가 사용됩니다.  
  
 형식 공급자는 <xref:System.IFormatProvider> 구현으로 표현됩니다.  이 인터페이스에는 단일 매개 변수가 형식을 지정할 유형을 나타내는 <xref:System.Type> 개체인 단일 멤버 <xref:System.IFormatProvider.GetFormat%2A> 메서드가 포함됩니다.  이 메서드는 서식 지정 정보를 제공하는 개체를 반환합니다.  .NET Framework는 숫자 문자열의 구문 분석을 위해 다음 두 가지 <xref:System.IFormatProvider> 구현을 지원합니다.  
  
-   <xref:System.Globalization.CultureInfo.GetFormat%2A?displayProperty=fullName> 메서드가 문화권별 서식 지정 정보를 제공하는 <xref:System.Globalization.NumberFormatInfo> 개체를 반환하는 <xref:System.Globalization.CultureInfo> 개체  
  
-   <xref:System.Globalization.NumberFormatInfo.GetFormat%2A?displayProperty=fullName> 메서드가 그 자체를 반환하는 <xref:System.Globalization.NumberFormatInfo> 개체  
  
 다음 예제에서는 배열의 각 문자열을 <xref:System.Double> 값으로 변환하려고 시도합니다.  먼저 영어\(미국\) 문화권의 규칙이 반영된 형식 공급자를 사용하여 문자열을 구문 분석합니다.  이 작업이 <xref:System.FormatException>을 throw하면 프랑스어\(프랑스\) 문화권의 규칙이 반영된 형식 공급자를 사용하여 문자열을 구문 분석합니다.  
  
 [!code-csharp[Parsing.Numbers#1](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/formatproviders1.cs#1)]
 [!code-vb[Parsing.Numbers#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/formatproviders1.vb#1)]  
  
## 구문 분석 및 NumberStyles 값  
 구문 분석 작업으로 처리할 수 있는 스타일 요소\(예: 공백, 그룹 구분 기호, 소수 구분 기호\)는 <xref:System.Globalization.NumberStyles> 열거형 값으로 정의됩니다.  기본적으로 정수 값을 나타내는 문자열은 숫자, 선행 및 후행 공백, 선행 부호만 허용되는 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 값을 사용하여 구문 분석됩니다.  부동 소수 값을 나타내는 문자열은 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 및 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 값의 조합을 사용하여 구문 분석됩니다. 이 조합 스타일은 선행 및 후행 공백, 선행 부호, 소수 구분 기호, 그룹 구분 기호 및 지수와 함께 10진수를 표시할 수 있도록 허용합니다.  <xref:System.Globalization.NumberStyles> 형식의 매개 변수를 포함하는 `Parse` 또는 `TryParse` 메서드의 오버로드를 호출하고 하나 이상의 <xref:System.Globalization.NumberStyles> 플래그를 설정하면 구문 분석 작업을 성공하기 위해 문자열에 제공할 수 있는 스타일 요소를 제어할 수 있습니다.  
  
 예를 들어, 그룹 구분 기호를 포함 하는 문자열은 <xref:System.Int32.Parse%28System.String%29?displayProperty=fullName> 메서드를 사용하여 <xref:System.Int32> 값으로 변환할 수 없습니다.  그러나 다음 예제와 같이 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 플래그를 사용하면 변환에 성공 합니다.  
  
 [!code-csharp[Parsing.Numbers#2](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/styles1.cs#2)]
 [!code-vb[Parsing.Numbers#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/styles1.vb#2)]  
  
> [!WARNING]
>  구문 분석 작업에는 항상 특정 문화권의 서식 지정 규칙이 사용됩니다.  <xref:System.Globalization.CultureInfo> 또는 <xref:System.Globalization.NumberFormatInfo> 개체를 전달하는 방법으로 문화권을 지정하지 않으면 현재 스레드와 연결된 문화권이 사용됩니다.  
  
 다음 표에서는 <xref:System.Globalization.NumberStyles> 열거형의 멤버를 나열하고 이러한 멤버가 구문 분석 작업에 미치는 영향에 대해 설명합니다.  
  
|NumberStyles 값|구문 분석할 문자열에 대한 효과|  
|--------------------|-----------------------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|숫자만 사용할 수 있습니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|소수 구분 기호 및 소수 자릿수를 사용할 수 있습니다.  정수 값의 경우 소수 자릿수로 0만 사용할 수 있습니다.  유효한 소수 구분 기호는 <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A?displayProperty=fullName> 또는 <xref:System.Globalization.NumberFormatInfo.CurrencyDecimalSeparator%2A?displayProperty=fullName> 속성으로 결정됩니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|"e" 또는 "E" 문자를 사용하여 지수 표기를 나타낼 수 있습니다.  자세한 내용은 <xref:System.Globalization.NumberStyles>를 참조하십시오.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|선행 공백을 사용할 수 있습니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|후행 공백을 사용할 수 있습니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|양수 또는 음수 부호를 숫자 앞에 둘 수 있습니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|양수 또는 음수 부호를 숫자 다음에 둘 수 있습니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|괄호를 사용하여 음수 값을 나타낼 수 있습니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|그룹 구분 기호를 사용할 수 있습니다.  그룹 구분 기호 문자는 <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A?displayProperty=fullName> 또는 <xref:System.Globalization.NumberFormatInfo.CurrencyGroupSeparator%2A?displayProperty=fullName> 속성에 의해 결정됩니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|통화 기호를 사용할 수 있습니다.  통화 기호는 <xref:System.Globalization.NumberFormatInfo.CurrencySymbol%2A?displayProperty=fullName> 속성으로 정의됩니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|구문 분석할 문자열이 16진수로 해석됩니다.  여기에는 16진수 숫자인 0\-9, A\-F, 및 a\-f가 포함될 수 있습니다.  이 플래그는 정수 값의 구문을 분석하기 위해서만 사용할 수 있습니다.|  
  
 또한 <xref:System.Globalization.NumberStyles> 열거형은 여러 <xref:System.Globalization.NumberStyles> 플래그를 포함하는 다음과 같은 복합 스타일을 제공합니다.  
  
|복합 NumberStyles 값|포함 멤버|  
|-----------------------|-----------|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|<xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> 및 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 스타일을 포함합니다.  정수 값을 구문 분석하는 데 사용되는 기본 스타일입니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|<xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> 및 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 스타일을 포함합니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|<xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> 및 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 스타일을 포함합니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|<xref:System.Globalization.NumberStyles?displayProperty=fullName> 및 <xref:System.Globalization.NumberStyles?displayProperty=fullName>를 제외한 모든 스타일을 포함합니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|<xref:System.Globalization.NumberStyles?displayProperty=fullName>를 제외한 모든 스타일을 포함합니다.|  
|<xref:System.Globalization.NumberStyles?displayProperty=fullName>|<xref:System.Globalization.NumberStyles?displayProperty=fullName>, <xref:System.Globalization.NumberStyles?displayProperty=fullName> 및 <xref:System.Globalization.NumberStyles?displayProperty=fullName> 스타일을 포함합니다.|  
  
## 구문 분석 및 유니코드 숫자  
 유니코드 표준은 여러 문자 환경에서 숫자에 대한 코드 포인트를 정의합니다.  예를 들어, U\+0030에서 U\+0039의 코드 포인트는 기본 라틴어 숫자 0부터 9까지를 나타내며, U\+09E6에서 U\+09EF의 코드 포인트는 벵골어 숫자 0부터 9까지, U\+FF10에서 U\+FF19의 코드 포인트는 전자 숫자 0부터 9까지를 나타냅니다.  하지만 구문 분석 메서드에서 인식되는 유일한 숫자는 코드 포인트 U\+0030에서 U\+0039의 기본 라틴어 숫자 0\-9가지입니다.  숫자 구문 분석 메서드에 다른 숫자가 포함된 문자열이 전달되면 메서드가 <xref:System.FormatException>을 throw합니다.  
  
 다음 예제에서는 다른 문자 환경의 숫자로 구성되는 문자열을 구문 분석하기 위해 <xref:System.Int32.Parse%2A?displayProperty=fullName> 메서드를 사용합니다.  이 예제의 결과에서와 같이 기본 라틴어 숫자에 대한 구문 분석 시도는 성공하지만 전자, 아랍어\-인도어, 벵골어 숫자에 대한 구문 분석 시도는 실패합니다.  
  
 [!code-csharp[Parsing.Numbers#3](../../../samples/snippets/csharp/VS_Snippets_CLR/parsing.numbers/cs/unicode1.cs#3)]
 [!code-vb[Parsing.Numbers#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/parsing.numbers/vb/unicode1.vb#3)]  
  
## 참고 항목  
 <xref:System.Globalization.NumberStyles>   
 [문자열 구문 분석](../../../docs/standard/base-types/parsing-strings.md)   
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)