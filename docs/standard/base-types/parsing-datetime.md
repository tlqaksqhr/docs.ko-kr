---
title: ".NET Framework의 날짜 및 시간 문자열 구문 분석"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.assetid: 43bae51e-9b1d-41a6-a187-772c0d096d90
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 6e3ef01abdb615b2850b5a9d07e1208ee22eda95
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/23/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>.NET에서 날짜 및 시간 문자열 구문 분석
구문 분석 메서드는 날짜 및 시간의 문자열 표현을 해당하는 <xref:System.DateTime> 개체로 변환합니다. <xref:System.DateTime.Parse%2A> 및 <xref:System.DateTime.TryParse%2A> 메서드는 날짜 및 시간의 몇 가지 공통된 표현을 변환합니다. <xref:System.DateTime.ParseExact%2A> 및 <xref:System.DateTime.TryParseExact%2A> 메서드는 날짜 및 시간 형식 문자열에 지정된 패턴을 따르는 문자열 표현을 변환합니다. [표준 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) 및 [사용자 지정 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)의 항목을 참조하세요.  
  
 구문 분석은 날짜 및 시간 구분 기호와 월, 일 및 연대의 이름에 사용되는 문자열과 같은 정보를 제공하는 서식 공급자의 속성에 의해 영향을 받습니다. 형식 공급자는 현재 <xref:System.Globalization.DateTimeFormatInfo> 개체이며, 현재 스레드 문화권에 의해 암시적으로 제공되거나 구문 분석 메서드의 <xref:System.IFormatProvider> 매개 변수에 의해 명시적으로 제공됩니다. <xref:System.IFormatProvider> 매개 변수의 경우 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체나 <xref:System.Globalization.DateTimeFormatInfo> 개체를 지정해야 합니다.  
  
 구문 분석될 날짜의 문자열 표현은 월을 포함해야 하고 적어도 날이나 연도를 포함해야 합니다. 시간의 문자열 표현은 시간을 포함해야 하고 적어도 분이나 AM/PM 지정자를 포함해야 합니다. 하지만 가능한 경우 구문 분석은 생략된 구성 요소에 대한 기본값을 제공합니다. 누락된 날짜는 기본값으로 현재 날짜를 사용하고 누락된 연도는 현재 연도를 사용하며 누락된 월의 날은 월의 첫 번째 날을 사용하고 누락된 시간은 자정을 사용합니다.  
  
 문자열 표현이 시간만 지정한 경우 구문 분석은 <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A> 및 <xref:System.DateTime.Day%2A> 속성이 <xref:System.DateTime.Today%2A> 속성의 해당 값으로 설정된 <xref:System.DateTime> 개체를 반환합니다. 그러나 <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> 상수가 구문 분석 메서드에서 지정된 경우 결과 연도, 월 및 일 속성은 `1`로 설정됩니다.  
  
 날짜 및 시간 구성 요소 외에도 날짜 및 시간의 문자열 표현은 시간이 UTC(협정 세계시)와 얼마나 다른지를 나타내는 오프셋을 포함할 수 있습니다. 예를 들어, 문자열 "2/14/2007 5:32:00 -7:00"는 UTC보다 7시간 이전인 시간을 가리킵니다. 시간의 문자열 표현에서 오프셋을 생략하면 구문 분석은 해당 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>로 설정된 <xref:System.DateTime> 개체를 반환합니다. 오프셋을 지정하면 구문 분석은 <xref:System.DateTime.Kind%2A> 속성이 <xref:System.DateTimeKind.Local>로 설정되고 해당 값이 컴퓨터의 로컬 표준 시간대로 조정된 <xref:System.DateTime> 개체를 반환합니다. 구문 분석 메서드에서 <xref:System.Globalization.DateTimeStyles> 상수를 사용하여 이 동작을 수정할 수 있습니다.  
  
 서식 공급자는 모호한 날짜를 해석하는 데에도 사용됩니다. 예를 들어 "02/03/04" 문자열에서 나타내는 날짜의 구성 요소 중 무엇이 월, 일 및 연도인지가 명확하지 않습니다. 이 경우에 구성 요소는 서식 공급자에서 비슷한 날짜 서식의 순서에 따라 해석됩니다.  
  
## <a name="parse"></a>Parse  
 다음 코드 예제에서는 **Parse** 메서드를 사용하여 문자열을 **DateTime**으로 변환하는 방법을 설명합니다. 이 예제에서는 현재 스레드와 연결된 문화권을 사용하여 구문 분석을 수행합니다. 현재 문화권과 연결된 <xref:System.Globalization.CultureInfo>가 입력 문자열을 구문 분석할 수 없는 경우 <xref:System.FormatException>이 throw됩니다.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 또한 해당 개체에서 정의한 문화권 중 하나로 설정된 **CultureInfo**를 지정하거나, <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> 속성에서 반환한 표준 <xref:System.Globalization.DateTimeFormatInfo> 개체 중 하나를 지정할 수 있습니다. 다음 코드 예제에서는 형식 공급자를 사용하여 독일어 문자열을 **DateTime**으로 구문 분석합니다. de-DE 문화권을 나타내는 **CultureInfo**는 구문 분석 중인 문자열과 함께 정의되고 전달되어 이 특정 문자열의 구문 분석이 성공하도록 합니다. 이는 **CurrentThread**의 **CurrentCulture**에 있는 모든 설정을 배제합니다.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 그러나 <xref:System.DateTime.Parse%2A> 메서드의 오버로드를 사용하여 사용자 지정 형식 공급자를 지정할 수 있지만, 이 메서드는 비표준 형식 공급자를 사용하도록 지원하지 않습니다. 비표준 서식으로 표현된 날짜 및 시간을 구문 분석하려면 대신 <xref:System.DateTime.ParseExact%2A> 메서드를 사용합니다.  
  
 다음 코드 예제에서는 <xref:System.Globalization.DateTimeStyles> 열거형을 사용하여 문자열에서 정의하지 않는 필드의 **DateTime**에 현재 날짜 및 시간 정보를 추가하지 않도록 지정합니다.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> 메서드는 지정된 문자열 패턴을 따르는 문자열을 **DateTime** 개체로 변환합니다. 지정된 형식이 아닌 문자열을 이 메서드에 전달하면 <xref:System.FormatException>이 throw됩니다. 표준 날짜 및 시간 서식 지정자 또는 사용자 지정 날짜 및 시간 서식 지정자의 제한 조합 중 하나를 지정할 수 있습니다. 사용자 지정 서식 지정자를 사용하면 사용자 지정 문자열을 생성할 수 있습니다. 지정자에 대한 설명은 [표준 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) 및 [사용자 지정 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)의 항목을 참조하세요.  
  
 또한 <xref:System.DateTime.ParseExact%2A> 메서드의 오버로드 각각에는 일반적으로 문자열의 서식 지정에 대한 문화권별 정보를 제공하는 <xref:System.IFormatProvider> 매개 변수가 있습니다. 일반적으로 이 <xref:System.IFormatProvider> 개체는 표준 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체이거나 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> 속성에서 반환하는 <xref:System.Globalization.DateTimeFormatInfo> 개체입니다. 그러나 다른 날짜 및 시간 구문 분석 함수와 달리 이 메서드는 비표준 날짜 및 시간 서식을 정의하는 <xref:System.IFormatProvider>도 지원합니다.  
  
 다음 코드 예제에서 **ParseExact** 메서드는 구문 분석할 문자열 개체, 형식 지정자, **CultureInfo** 개체를 잇달아 전달받습니다. 이 **ParseExact** 메서드는 en-US 문화권의 자세한 날짜 표기 패턴을 표시하는 문자열만 구문 분석할 수 있습니다.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [Parsing Strings](../../../docs/standard/base-types/parsing-strings.md)  
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)  
 [.NET에서 형식 변환](../../../docs/standard/base-types/type-conversion.md)
