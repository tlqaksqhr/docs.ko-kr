---
title: "방법: 사용자 지정 숫자 형식 공급자 정의 및 사용 | Microsoft Docs"
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
  - "사용자 지정 형식 문자열"
  - "사용자 지정 숫자 형식 문자열"
  - "날짜 및 시간 데이터 표시"
  - "형식 공급자[.NET Framework]"
  - "서식 지정[.NET Framework], 숫자"
  - "숫자 형식 지정[.NET Framework]"
  - "숫자[.NET Framework], 사용자 지정 숫자 형식 문자열"
  - "숫자 형식 문자열[.NET Framework]"
ms.assetid: a281bfbf-6596-45ed-a2d6-3782d535ada2
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# 방법: 사용자 지정 숫자 형식 공급자 정의 및 사용
[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 숫자 값의 문자열 표현을 다양한 방식으로 제어할 수 있습니다.  숫자 값 형식을 사용자 지정하는 데 사용할 수 있는 기능은 다음과 같습니다.  
  
-   숫자를 문자열 표현으로 변환하는 데 사용되는 미리 정의된 형식 집합을 제공하는 표준 숫자 형식 문자열.  `format` 매개 변수가 있는 <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName> 등의 숫자 서식 지정 메서드에 이러한 문자열을 사용할 수 있습니다.  자세한 내용은 [표준 숫자 형식 문자열](../../../docs/standard/base-types/standard-numeric-format-strings.md)를 참조하십시오.  
  
-   사용자 지정 숫자 서식 지정자를 정의하기 위해 조합할 수 있는 기호 집합을 제공하는 사용자 지정 숫자 형식 문자열.  이러한 문자열은 `format` 매개 변수가 있는 <xref:System.Decimal.ToString%28System.String%29?displayProperty=fullName> 등의 숫자 서식 지정 메서드에도 사용할 수 있습니다.  자세한 내용은 [사용자 지정 숫자 형식 문자열](../../../docs/standard/base-types/custom-numeric-format-strings.md)를 참조하십시오.  
  
-   숫자 값의 문자열 표현을 표시하는 데 사용되는 기호 및 형식 패턴을 정의하는 사용자 지정 <xref:System.Globalization.CultureInfo> 또는 <xref:System.Globalization.NumberFormatInfo> 개체.  `provider` 매개 변수가 있는 <xref:System.Int32.ToString%2A> 등의 숫자 서식 지정 메서드에 이러한 개체를 사용할 수 있습니다.  대개 `provider` 매개 변수는 문화권별 형식을 지정하는 데 사용됩니다.  
  
 응용 프로그램에서 서식이 지정된 계좌 번호, ID 번호 또는 우편 번호를 표시해야 하는 등의 일부 경우에는 이 세 가지 기술이 적합하지 않습니다.  또한 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]에서는 <xref:System.Globalization.CultureInfo> 개체도, <xref:System.Globalization.NumberFormatInfo> 개체도 아닌 서식 지정 개체를 정의하여 숫자 값의 서식 지정 방식을 결정할 수 있습니다.  이 항목에서는 이러한 개체를 구현하기 위한 단계별 지침과 전화 번호 형식을 지정하는 예제를 제공합니다.  
  
### 사용자 지정 형식 공급자를 정의하려면  
  
1.  <xref:System.IFormatProvider> 및 <xref:System.ICustomFormatter> 인터페이스를 구현하는 클래스를 정의합니다.  
  
2.  <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName> 메서드를 구현합니다.  <xref:System.IFormatProvider.GetFormat%2A>은 [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> 메서드와 같은 서식 지정 메서드가 실제로 사용자 지정 서식 지정을 수행하는 개체를 검색하기 위해 호출하는 콜백 메서드입니다.  일반적으로 <xref:System.IFormatProvider.GetFormat%2A>을 구현하면 다음 작업이 수행됩니다.  
  
    1.  메서드 매개 변수로 전달되는 <xref:System.Type> 개체가 <xref:System.ICustomFormatter> 인터페이스를 나타내는지 여부를 확인합니다.  
  
    2.  매개 변수가 <xref:System.ICustomFormatter> 인터페이스를 나타내는 경우 <xref:System.IFormatProvider.GetFormat%2A>은 사용자 지정 서식 지정을 수행하는 <xref:System.ICustomFormatter> 인터페이스를 구현하는 개체를 반환합니다.  일반적으로 사용자 지정 서식 지정 개체는 자기 자신을 반환합니다.  
  
    3.  매개 변수가 <xref:System.ICustomFormatter> 인터페이스를 나타내지 않으면 <xref:System.IFormatProvider.GetFormat%2A>은 `null`을 반환합니다.  
  
3.  <xref:System.ICustomFormatter.Format%2A> 메서드를 구현합니다.  이 메서드는 [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> 메서드에서 호출되며 숫자의 문자열 표현을 반환합니다.  이 메서드를 구현할 때는 대개 다음 작업이 수행됩니다.  
  
    1.  선택적으로 `provider` 매개 변수를 확인하여 이 메서드가 서식 지정 서비스를 제공하기 위한 것인지를 확인합니다.  <xref:System.IFormatProvider> 및 <xref:System.ICustomFormatter>를 모두 구현하는 서식 지정 개체의 경우 여기에는 현재 서식 지정 개체와 같은지 확인하기 위해 `provider` 매개 변수를 테스트하는 작업이 포함됩니다.  
  
    2.  서식 지정 개체가 사용자 지정 서식 지정자를 지원하는지 여부를 확인합니다. \(예를 들어, "N" 형식 지정자는 미국 전화 번호가 NANP 형식으로 출력 되어야 하 고 "I" 지정자는 Itu\-t 권장 E.123 형식으로 출력을 나타낼 수 있습니다.\) 서식 지정자를 사용하는 경우 이 메서드가 특정 서식 지정자를 처리해야 합니다.  서식 지정자는 `format` 매개 변수에서 메서드로 전달됩니다.  지정자가 없으면 `format` 매개 변수의 값은 <xref:System.String.Empty?displayProperty=fullName>가 됩니다.  
  
    3.  `arg` 매개 변수로 메서드에 전달된 숫자 값을 검색합니다.  적절히 조작하여 숫자 값을 문자열 표현으로 변환합니다.  
  
    4.  `arg` 매개 변수의 문자열 표현을 반환합니다.  
  
### 사용자 지정 숫자 서식 지정 개체를 사용하려면  
  
1.  사용자 지정 서식 지정 클래스의 새 인스턴스를 만듭니다.  
  
2.  [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> 서식 지정 메서드를 호출하여 사용자 지정 서식 지정 개체, 서식 지정자\(지정자를 사용하지 않는 경우 <xref:System.String.Empty?displayProperty=fullName>\) 및 형식을 지정할 숫자 값을 전달합니다.  
  
## 예제  
 다음 예제에서는 미국 전화 번호를 NANP 또는 E.123 형식으로 나타내는 숫자로 변환하는 `TelephoneFormatter` 라는 사용자 지정 숫자 형식 공급자를 정의합니다.  이 메서드는 두 서식 지정자, 즉 NANP 형식을 출력하는 "N"과 국제 E.123 형식을 출력하는 "I"를 처리합니다.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#1)]
 [!code-vb[Formatting.HowTo.NumericValue#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#1)]  
  
 사용자 지정 숫자 형식 공급자는 [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> 메서드에서만 사용할 수 있습니다.  형식이 <xref:System.IFormatProvider>인 매개 변수가 있는 `ToString` 등의 다른 숫자 서식 지정 메서드 오버로드는 모두 <xref:System.IFormatProvider.GetFormat%2A?displayProperty=fullName> 구현에 <xref:System.Globalization.NumberFormatInfo> 형식을 나타내는 <xref:System.Type> 개체를 전달합니다.  이러한 오버로드를 사용하는 경우 메서드는 <xref:System.Globalization.NumberFormatInfo> 개체를 반환해야 합니다.  그렇지 않으면 사용자 지정 숫자 형식 공급자는 무시되고 현재 문화권의 <xref:System.Globalization.NumberFormatInfo> 개체가 대신 사용됩니다.  예제에서 `TelephoneFormatter.GetFormat` 메서드는 메서드 매개 변수를 확인하고 매개 변수가 <xref:System.ICustomFormatter> 이외의 형식을 나타내는 경우 `null`을 반환하여 매개 변수가 숫자 서식 지정 메서드로 잘못 전달되지 않도록 처리합니다.  
  
 사용자 지정 숫자 형식 공급자가 서식 지정자 집합을 지원하는 경우, [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> 메서드 호출에 사용된 형식 항목에 서식 지정자가 제공되지 않으면 기본 동작을 제공해야 합니다.  이 예제에서는 "N"이 기본 서식 지정자입니다.  이렇게 하면 명시적인 서식 지정자를 제공하여 숫자를 서식이 지정된 전화 번호로 변환할 수 있습니다.  다음 예제에서는 이와 같은 메서드 호출을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#2)]
 [!code-vb[Formatting.HowTo.NumericValue#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#2)]  
  
 그러나 서식 지정자가 없는 경우에도 변환을 수행할 수 있습니다.  다음 예제에서는 이와 같은 메서드 호출을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.NumericValue#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.NumericValue/cs/Telephone1.cs#3)]
 [!code-vb[Formatting.HowTo.NumericValue#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.NumericValue/vb/Telephone1.vb#3)]  
  
 기본 서식 지정자가 정의되어 있지 않으면 .NET Framework에서 코드가 지원하지 않는 서식 지정을 제공하도록 <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName> 메서드 구현에 다음과 같은 코드를 포함해야 합니다.  
  
 [!code-csharp[System.ICustomFormatter.Format#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.ICustomFormatter.Format/cs/format.cs#1)]
 [!code-vb[System.ICustomFormatter.Format#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.ICustomFormatter.Format/vb/Format.vb#1)]  
  
 이 예제의 경우 <xref:System.ICustomFormatter.Format%2A?displayProperty=fullName>을 구현하는 메서드는 [String.Format\(IFormatProvider, String, Object\<xref:System.String.Format%28System.IFormatProvider%2CSystem.String%2CSystem.Object%5B%5D%29?displayProperty=fullName> 메서드의 콜백 메서드 역할을 합니다.  그러므로 이 메서드는 현재 `TelephoneFormatter` 개체에 대한 참조가 포함되어 있는지 `formatProvider` 매개 변수를 확인합니다.  그러나 이 메서드를 코드에서 직접 호출할 수도 있습니다.  이 경우에는 `formatProvider` 매개 변수를 사용하여 문화권별 서식 지정 정보를 제공하는 <xref:System.Globalization.CultureInfo> 또는 <xref:System.Globalization.NumberFormatInfo> 개체를 제공할 수 있습니다.  
  
## 코드 컴파일  
 csc.exe 또는 vb.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)