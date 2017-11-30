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
caps.latest.revision: "24"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1beceb2b2d32c500e73cd7786c480fcd84c3001c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="parsing-date-and-time-strings-in-net"></a>날짜 및.net에서 시간 문자열 구문 분석
구문 분석 메서드는 날짜 및 시간의 문자열 표현을 해당 하는 변환 <xref:System.DateTime> 개체입니다. <xref:System.DateTime.Parse%2A> 및 <xref:System.DateTime.TryParse%2A> 메서드는 몇 가지 일반적인 표현 된 날짜 및 시간 중 어느 변환 합니다. <xref:System.DateTime.ParseExact%2A> 및 <xref:System.DateTime.TryParseExact%2A> 메서드 날짜 및 시간 형식 문자열에 의해 지정 된 패턴을 따르는 문자열 표현을 변환 합니다. [표준 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) 및 [사용자 지정 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)의 항목을 참조하세요.  
  
 구문 분석은 날짜 및 시간 구분 기호와 월, 일 및 연대의 이름에 사용되는 문자열과 같은 정보를 제공하는 서식 공급자의 속성에 의해 영향을 받습니다. 형식 공급자가 현재 <xref:System.Globalization.DateTimeFormatInfo> 의해 명시적으로 또는 현재 스레드 문화권에 의해 암시적으로 제공 되는 개체는 <xref:System.IFormatProvider> 구문 분석 방법의 매개 변수입니다. 에 대 한는 <xref:System.IFormatProvider> 매개 변수를 지정 된 <xref:System.Globalization.CultureInfo> 는 문화권을 나타내는 개체 또는 <xref:System.Globalization.DateTimeFormatInfo> 개체입니다.  
  
 구문 분석될 날짜의 문자열 표현은 월을 포함해야 하고 적어도 날이나 연도를 포함해야 합니다. 시간의 문자열 표현은 시간을 포함해야 하고 적어도 분이나 AM/PM 지정자를 포함해야 합니다. 하지만 가능한 경우 구문 분석은 생략된 구성 요소에 대한 기본값을 제공합니다. 누락된 날짜는 기본값으로 현재 날짜를 사용하고 누락된 연도는 현재 연도를 사용하며 누락된 월의 날은 월의 첫 번째 날을 사용하고 누락된 시간은 자정을 사용합니다.  
  
 한 번만 지정 하는 문자열 표현, 경우에 반환 구문 분석 한 <xref:System.DateTime> 개체를 해당 <xref:System.DateTime.Year%2A>, <xref:System.DateTime.Month%2A>, 및 <xref:System.DateTime.Day%2A> 속성이의 해당 값으로 설정는 <xref:System.DateTime.Today%2A> 속성입니다. 그러나 경우는 <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> 구문 분석 방법, 결과 연도, 월, 상수를 지정 하 고 날짜 속성 값으로 설정 된 `1`합니다.  
  
 날짜 및 시간 구성 요소 외에도 날짜 및 시간의 문자열 표현은 시간이 UTC(협정 세계시)와 얼마나 다른지를 나타내는 오프셋을 포함할 수 있습니다. 예를 들어, 문자열 "2/14/2007 5:32:00 -7:00"는 UTC보다 7시간 이전인 시간을 가리킵니다. 오프셋을 한 번의 문자열 표현에서 생략 하면 반환 구문 분석 한 <xref:System.DateTime> 개체를 해당 <xref:System.DateTime.Kind%2A> 속성이로 설정 <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>합니다. 오프셋을 지정 하는 경우 반환 구문 분석 한 <xref:System.DateTime> 개체를 해당 <xref:System.DateTime.Kind%2A> 속성이로 설정 <xref:System.DateTimeKind.Local> 있으며 컴퓨터의 현지 표준 시간대에 해당 값을 조정 합니다. 사용 하 여이 동작을 수정할 수는 <xref:System.Globalization.DateTimeStyles> 구문 분석 방법 상수입니다.  
  
 서식 공급자는 모호한 날짜를 해석하는 데에도 사용됩니다. 예를 들어 "02/03/04" 문자열에서 나타내는 날짜의 구성 요소 중 무엇이 월, 일 및 연도인지가 명확하지 않습니다. 이 경우에 구성 요소는 서식 공급자에서 비슷한 날짜 서식의 순서에 따라 해석됩니다.  
  
## <a name="parse"></a>Parse  
 다음 코드 예제에서는 **구문 분석** 에 문자열을 변환 하는 메서드는 **DateTime**합니다. 이 예제에서는 현재 스레드와 연결된 문화권을 사용하여 구문 분석을 수행합니다. 경우는 <xref:System.Globalization.CultureInfo> 현재와 관련 된 문화권 입력된 문자열을 구문 분석할 수 없습니다는 <xref:System.FormatException> throw 됩니다.  
  
 [!code-csharp[Parsing.DateAndTime#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example.cs#1)]
 [!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example.vb#1)]  
  
 지정할 수 있습니다는 **CultureInfo** 해당 개체에 의해 정의 된 문화권 중 하나를 설정 또는 표준 중 하나를 지정할 수 있습니다 <xref:System.Globalization.DateTimeFormatInfo> 에서 반환 된 개체는 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> 속성입니다. 다음 코드 예제에서는 형식 공급자를 사용 하 여 독일어에 문자열을 구문 분석 하는 **DateTime**합니다. A **CultureInfo** DE-DE 문화권을 나타내는 정의 되 고이 특정 문자열을 성공적으로 구문 분석 되도록 구문 분석 중인 문자열과 함께 전달 합니다. 원하는 설정이이 불가능는 **CurrentCulture** 의 **CurrentThread**합니다.  
  
 [!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example2.cs#2)]
 [!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example2.vb#2)]  
  
 그러나의 오버 로드를 사용할 수 있지만 <xref:System.DateTime.Parse%2A> 사용자 지정 형식 공급자를 지정 하는 메서드는 방법은 비표준 형식 공급자의 사용을 지원 하지 않습니다. 사용 하 여 날짜 및 비표준 형식으로 표현 된 시간을 구문 분석 하려면는 <xref:System.DateTime.ParseExact%2A> 메서드 대신 합니다.  
  
 다음 코드 예제에서는 <xref:System.Globalization.DateTimeStyles> 현재 날짜 및 시간 정보를 하지 추가 되어야 함을 지정 하는 열거형은 **DateTime** 문자열을 정의 하지 않는 필드에 대 한 합니다.  
  
 [!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example3.cs#3)]
 [!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example3.vb#3)]  
  
## <a name="parseexact"></a>ParseExact  
 <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> 메서드를 지정 된 문자열 패턴을 따르는 문자열 변환는 **DateTime** 개체입니다. 지정 된 폼의 하지 않은 문자열을이 메서드에 전달 되 면 한 <xref:System.FormatException> throw 됩니다. 표준 날짜 및 시간 서식 지정자 또는 사용자 지정 날짜 및 시간 서식 지정자의 제한 조합 중 하나를 지정할 수 있습니다. 사용자 지정 서식 지정자를 사용하면 사용자 지정 문자열을 생성할 수 있습니다. 지정자에 대한 설명은 [표준 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md) 및 [사용자 지정 날짜 및 시간 서식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)의 항목을 참조하세요.  
  
 각 오버 로드는 <xref:System.DateTime.ParseExact%2A> 메서드 역시는 <xref:System.IFormatProvider> 일반적으로 문자열의 서식 지정 하는 방법에 대 한 문화권별 정보를 제공 하는 매개 변수입니다. 일반적으로이 <xref:System.IFormatProvider> 개체가 <xref:System.Globalization.CultureInfo> 표준 문화권을 나타내는 개체 또는 <xref:System.Globalization.DateTimeFormatInfo> 에서 반환 되는 개체는 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> 속성입니다. 그러나 다른 날짜 및 시간 함수를 구문 분석, 달리이 방식은 또한 지원는 <xref:System.IFormatProvider> 비표준 날짜 및 시간 형식을 정의 하는 합니다.  
  
 다음 코드 예제에서는 **ParseExact** 메서드에 전달 됩니다 구문 분석, string 개체에는 형식 지정자 다음에 옵니다는 **CultureInfo** 개체입니다. 이 **ParseExact** 메서드 EN-US 문화권의 자세한 날짜 패턴을 수행 하는 문자열 구문 분석만 수 있습니다.  
  
 [!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Parsing.DateAndTime/cs/Example4.cs#4)]
 [!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Parsing.DateAndTime/vb/Example4.vb#4)]  
  
## <a name="see-also"></a>참고 항목  
 [문자열 구문 분석](../../../docs/standard/base-types/parsing-strings.md)  
 [형식 서식 지정](../../../docs/standard/base-types/formatting-types.md)  
 [.NET에서 형식 변환](../../../docs/standard/base-types/type-conversion.md)
