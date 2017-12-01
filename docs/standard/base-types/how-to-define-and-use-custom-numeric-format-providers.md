---
title: "방법: 사용자 지정 숫자 형식 공급자 정의 및 사용"
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
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- number formatting [.NET Framework]
- custom numeric format strings
- numbers [.NET Framework], custom numeric format strings
- displaying date and time data
- format providers [.NET Framework]
- custom format strings
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e44a909eb92f0d9dfa21980a918a2d370dcf427
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-define-and-use-custom-numeric-format-providers"></a>방법: 사용자 지정 숫자 형식 공급자 정의 및 사용
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 숫자 값의 문자열 표현 광범위 하 게 제어할 수 있게 합니다. 숫자 값의 형식을 사용자 지정하기 위한 다음과 같은 기능을 지원합니다.  
  
-   숫자를 해당 문자열 표현으로 변환하기 위한 미리 정의된 형식 집합을 제공하는 표준 숫자 형식 문자열입니다. 숫자와 같은 서식 지정 메서드에 사용할 수 있습니다 <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, 올려진는 `format` 매개 변수입니다. 자세한 내용은 참조 [표준 숫자 형식 문자열](../../../docs/standard/base-types/standard-numeric-format-strings.md)합니다.  
  
-   함께 결합되어 사용자 지정 숫자 형식 지정자를 정의할 수 있는 기호 집합을 제공하는 사용자 지정 숫자 형식 문자열입니다. 모든 숫자와 같은 서식 지정 메서드에 함께 사용할 수도 <xref:System.Decimal.ToString%28System.String%29?displayProperty=nameWithType>, 올려진는 `format` 매개 변수입니다. 자세한 내용은 참조 [사용자 지정 숫자 형식 문자열](../../../docs/standard/base-types/custom-numeric-format-strings.md)합니다.  
  
-   사용자 지정 <xref:System.Globalization.CultureInfo> 또는 <xref:System.Globalization.NumberFormatInfo> 기호를 정의 하 고 숫자 값의 문자열 표현을 표시에 사용 되는 패턴 서식을 지정 하는 개체입니다. 숫자와 같은 서식 지정 메서드에 사용할 수 있습니다 <xref:System.Int32.ToString%2A>, 올려진는 `provider` 매개 변수입니다. 일반적으로 `provider` culture 별 서식 지정 하려면 매개 변수를 사용 합니다.  
  
 응용 프로그램에서 형식이 지정된 계정 번호, ID 번호 또는 우편 번호를 표시해야 하는 경우와 같이 이 세 가지 방법이 부적절한 경우도 있습니다. [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 서식 지정 개체를 정의할 수 있습니다는 <xref:System.Globalization.CultureInfo> 또는 <xref:System.Globalization.NumberFormatInfo> 숫자 값을 형식 지정 방법을 결정 하는 개체입니다. 이 항목에서는 이러한 개체를 구현하기 위한 단계별 지침을 제공하고 전화 번호 형식을 지정하는 예제를 제공합니다.  
  
### <a name="to-define-a-custom-format-provider"></a>사용자 지정 형식 공급자를 정의하려면  
  
1.  구현 하는 클래스 정의 <xref:System.IFormatProvider> 및 <xref:System.ICustomFormatter> 인터페이스입니다.  
  
2.  <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> 메서드를 구현합니다. <xref:System.IFormatProvider.GetFormat%2A>콜백 메서드는 서식 지정 방법 (같은 <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드)를 실제로 담당 하는 개체를 검색 하기 위해 호출 합니다. 구현 하는 일반적인 <xref:System.IFormatProvider.GetFormat%2A> 다음 작업을 수행 합니다.  
  
    1.  결정 여부는 <xref:System.Type> 개체 메서드로 전달 된 매개 변수를 나타냅니다는 <xref:System.ICustomFormatter> 인터페이스.  
  
    2.  매개 변수가 나타내는 경우는 <xref:System.ICustomFormatter> 인터페이스를 <xref:System.IFormatProvider.GetFormat%2A> 구현 하는 개체를 반환 합니다.는 <xref:System.ICustomFormatter> 인터페이스를 사용자 지정 서식을 제공 해야 합니다. 일반적으로 사용자 지정 형식 지정 개체 자체가 반환됩니다.  
  
    3.  매개 변수를 나타내지 않는 경우는 <xref:System.ICustomFormatter> 인터페이스 <xref:System.IFormatProvider.GetFormat%2A> 반환 `null`합니다.  
  
3.  <xref:System.ICustomFormatter.Format%2A> 메서드를 구현합니다. 이 메서드는 <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드 및 숫자의 문자열 표현을 반환 합니다. 일반적으로 메서드를 구현하는 과정은 다음과 같습니다.  
  
    1.  필요에 따라 메서드를 검사 하 여 형식 지정 서비스를 제공 하기 위한 것인지 확인는 `provider` 매개 변수입니다. 둘 다를 구현 하는 개체의 서식을 지정 하기 위한 <xref:System.IFormatProvider> 및 <xref:System.ICustomFormatter>, 테스트 하 여는 `provider` 서식 현재 개체와 같은지 여부에 대 한 매개 변수입니다.  
  
    2.  형식 지정 개체가 사용자 지정 형식 지정자를 지원해야 하는지 여부를 결정합니다. 예를 들어 "N" 형식 지정자는 미국 전화 번호가 NANP 형식으로, "I" 형식 지정자는 ITU-T 권장 E.123 형식으로 출력되어야 함을 나타낼 수 있습니다. 형식 지정자가 사용된 경우 메서드에서 특정 형식 지정자를 처리해야 합니다. 메서드에 전달 되는 `format` 매개 변수입니다. 지정 자가 없는 경우 현재의 가치는 `format` 매개 변수는 <xref:System.String.Empty?displayProperty=nameWithType>합니다.  
  
    3.  숫자 값으로 메서드에 전달 된 검색의 `arg` 매개 변수입니다. 문자열 표현으로 변환하는 데 필요한 조작을 수행합니다.  
  
    4.  문자열 표현을 반환는 `arg` 매개 변수입니다.  
  
### <a name="to-use-a-custom-numeric-formatting-object"></a>사용자 지정 숫자 형식 지정 개체를 사용하려면  
  
1.  사용자 지정 형식 지정 클래스의 새 인스턴스를 만듭니다.  
  
2.  호출의 <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 서식 지정 메서드에 사용자 지정 형식 지정 개체에 서식 지정자를 전달 합니다 (또는 <xref:System.String.Empty?displayProperty=nameWithType>사용 되지 않는 경우,), 서식을 지정할 숫자 값입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 미국 전화 번호를 나타내는 숫자를 NANP 또는 E.123 형식으로 변환하는 `TelephoneFormatter`라는 사용자 지정 숫자 형식 공급자를 정의합니다. 메서드는 두 가지 형식 지정자 "N"(NANP 형식 출력)과 "I"(국제 E.123 형식 출력)를 처리합니다.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 사용자 지정 숫자 형식 공급자에만 사용할 수 있습니다는 <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드. 다른 숫자 서식 지정 메서드 오버 로드 (같은 `ToString`) 형식의 매개 변수가 있는 <xref:System.IFormatProvider> 모두 통과 <xref:System.IFormatProvider.GetFormat%2A?displayProperty=nameWithType> 구현은 <xref:System.Type> 를 나타내는 개체입니다는 <xref:System.Globalization.NumberFormatInfo> 유형입니다. 반환 하는 메서드, 예상 되는 <xref:System.Globalization.NumberFormatInfo> 개체입니다. 표시 되지 않는 경우는 사용자 지정 숫자 형식 공급자는 무시 되 고 <xref:System.Globalization.NumberFormatInfo> 개체가 현재 문화권은 그 위치에 사용 됩니다. 예제에서는 `TelephoneFormatter.GetFormat` 메서드가를 반환 하는 메서드 매개 변수를 검사 하 여 서식 지정 메서드에 부적절 하 게 전달 될 수 있는 가능성을 처리 `null` 이외의 다른 형식을 나타내는 경우 <xref:System.ICustomFormatter>합니다.  
  
 사용자 지정 숫자 형식 공급자의 형식 지정자 집합을 지 원하는 경우에 사용 되는 서식 항목의 형식 지정 자가 없는 제공 하는 경우 기본 동작을 제공 하는지 확인는 <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드를 호출 합니다. 예제에서는 "N"이 기본 형식 지정자입니다. 이렇게 하면 명시적 형식 지정자를 제공하여 숫자를 형식이 지정된 전화 번호로 변환할 수 있습니다. 다음 예제에서는 이러한 메서드 호출을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 그러나 형식 지정자가 없는 경우에도 변환을 수행할 수 있습니다. 다음 예제에서는 이러한 메서드 호출을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 기본 형식 지정 자가 없는 정의 된 경우 구현에서 <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> 메서드는 해당.NET을 제공할 수 있도록 서식 코드를 지원 하지 않습니다는 다음과 같은 코드를 포함 해야 합니다.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 이 예제의 경우 메서드를 구현 하는 <xref:System.ICustomFormatter.Format%2A?displayProperty=nameWithType> 에 대 한 콜백 메서드로 제공 하기 위한는 <xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=nameWithType> 메서드. 그러므로 메서드는 `formatProvider` 현재에 대 한 참조가 포함 되어 있는지 여부를 확인 하려면 매개 변수 `TelephoneFormatter` 개체입니다. 그러나 코드에서 메서드를 직접 호출할 수도 있습니다. 이 경우 사용할 수 있습니다는 `formatProvider` 매개 변수를 한 <xref:System.Globalization.CultureInfo> 또는 <xref:System.Globalization.NumberFormatInfo> culture 별 서식 지정 정보를 제공 하는 개체입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 Csc.exe 또는 vb.exe를 사용 하 여 명령줄에서 코드를 컴파일하십시오. 코드를 컴파일하려면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], 콘솔 응용 프로그램 프로젝트 템플릿을에 배치 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)
