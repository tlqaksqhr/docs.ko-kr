---
title: "방법: 그레고리오력이 아닌 달력의 날짜 표시 | Microsoft Docs"
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
  - "서식 지정[.NET Framework], 날짜"
  - "날짜[.NET Framework], 서식"
  - "달력[.NET Framework], 날짜 표시"
  - "날짜 및 시간 데이터 표시"
ms.assetid: ed324eff-4aff-4a76-b6c0-04e6c0d8f5a9
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# 방법: 그레고리오력이 아닌 달력의 날짜 표시
<xref:System.DateTime> 및 <xref:System.DateTimeOffset> 형식은 그레고리오력을 기본 달력으로 사용합니다.  즉, 날짜 및 시간 값의 `ToString` 메서드를 호출하면 해당 날짜 및 시간이 다른 달력을 사용하여 만들어진 경우에도 날짜 및 시간의 문자열 표현이 그레고리오력에 표시됩니다.  이에 대한 예는 다음 예제에 나와 있는데, 여기서는 두 가지 다른 방법을 사용하여 페르시아력의 날짜 및 시간 값을 만들지만 <xref:System.DateTime.ToString%2A> 메서드를 호출할 때는 해당 날짜 및 시간 값이 그레고리오력에 표시됩니다.  이 예제에는 특정 달력에서 날짜를 표시하기 위해 자주 사용되는 잘못된 기술이 반영되어 있습니다.  
  
 [!code-csharp[Formatting.HowTo.Calendar#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#1)]
 [!code-vb[Formatting.HowTo.Calendar#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#1)]  
  
 두 가지 서로 다른 기술을 사용하여 특정 달력에 날짜를 표시할 수 있습니다.  첫 번째 기술의 경우 사용하는 달력이 특정 문화권의 기본 달력이어야 하지만  두 번째 기술의 경우에는 어떤 달력에나 사용할 수 있습니다.  
  
### 문화권의 기본 달력에 대해 날짜를 표시하려면  
  
1.  사용할 달력을 나타내는 <xref:System.Globalization.Calendar> 클래스에서 파생된 달력 개체를 인스턴스화합니다.  
  
2.  해당 형식을 사용하여 날짜를 표시할 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체를 인스턴스화합니다.  
  
3.  <xref:System.Array.Exists%2A?displayProperty=fullName> 메서드를 호출하여 달력 개체가 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName> 속성에서 반환되는 배열의 멤버인지 확인합니다.  이는 해당 달력이 <xref:System.Globalization.CultureInfo> 개체의 기본 달력이 될 수 있음을 나타냅니다.  개체가 배열의 멤버가 아니면 "달력에서 날짜를 표시하려면" 단원의 지침을 따릅니다.  
  
4.  달력 개체를 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName> 속성에서 반환하는 <xref:System.Globalization.DateTimeFormatInfo> 개체의 <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A> 속성에 할당합니다.  
  
    > [!NOTE]
    >  <xref:System.Globalization.CultureInfo> 클래스에는 <xref:System.Globalization.CultureInfo.Calendar%2A> 속성도 포함되어 있습니다.  그러나 이 속성은 읽기 전용 상수이므로 <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName> 속성에 할당되는 새 기본 달력을 반영하도록 변경되지 않습니다.  
  
5.  <xref:System.DateTime.ToString%2A> 또는 <xref:System.DateTime.ToString%2A> 메서드를 호출하고 이전 단계에서 해당 기본 달력을 수정한 <xref:System.Globalization.CultureInfo> 개체를 이 메서드에 전달합니다.  
  
### 달력에 날짜를 표시하려면  
  
1.  사용할 달력을 나타내는 <xref:System.Globalization.Calendar> 클래스에서 파생된 달력 개체를 인스턴스화합니다.  
  
2.  날짜 및 시간 값의 문자열 표현에 표시될 날짜 및 시간 요소를 결정합니다.  
  
3.  표시할 각 날짜 및 시간 요소에 대해 달력 개체의 `Get`… 메서드를 호출합니다.  사용할 수 있는 메서드는 다음과 같습니다.  
  
    -   적절한 달력에 연도를 표시하기 위한 <xref:System.Globalization.Calendar.GetYear%2A>  
  
    -   적절한 달력에 달을 표시하기 위한 <xref:System.Globalization.Calendar.GetMonth%2A>  
  
    -   적절한 달력에 해당 달의 일 수를 표시하기 위한 <xref:System.Globalization.Calendar.GetDayOfMonth%2A>  
  
    -   적절한 달력에 시간을 표시하기 위한 <xref:System.Globalization.Calendar.GetHour%2A>  
  
    -   적절한 달력에 분을 표시하기 위한 <xref:System.Globalization.Calendar.GetMinute%2A>  
  
    -   적절한 달력에 초를 표시하기 위한 <xref:System.Globalization.Calendar.GetSecond%2A>  
  
    -   적절한 달력에 밀리초를 표시하기 위한 <xref:System.Globalization.Calendar.GetMilliseconds%2A>  
  
## 예제  
 이 예제에서는 두 가지 다른 달력을 사용하여 날짜를 표시합니다.  즉, ar\-JO 문화권에 대해 회교식 달력을 기본 달력으로 정의한 후에 날짜를 표시하며, 동시에 페르시아력을 사용하여 날짜를 표시합니다. 페르시아력은 fa\-IR 문화권에서 선택적 달력으로 지원되지 않습니다.  
  
 [!code-csharp[Formatting.HowTo.Calendar#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Calendar/cs/Calendar1.cs#2)]
 [!code-vb[Formatting.HowTo.Calendar#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Calendar/vb/Calendar1.vb#2)]  
  
 각 <xref:System.Globalization.CultureInfo> 개체는 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A> 속성으로 나타내는 하나 이상의 달력을 지원할 수 있습니다.  이러한 달력 중 하나가 해당 문화권의 기본 달력으로 지정되어 읽기 전용 <xref:System.Globalization.CultureInfo.Calendar%2A?displayProperty=fullName> 속성에서 반환됩니다.  그리고 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=fullName> 속성에서 반환되는 <xref:System.Globalization.DateTimeFormatInfo.Calendar%2A?displayProperty=fullName> 속성에 선택적 달력 중 다른 하나를 나타내는 <xref:System.Globalization.Calendar> 개체를 할당하여 해당 달력을 기본 달력으로 지정할 수도 있습니다.  그러나 <xref:System.Globalization.PersianCalendar> 클래스로 표시되는 페르시아력 등의 일부 달력은 모든 문화권에 대해 선택적 달력으로 사용할 수 없습니다.  
  
 이 예제에서는 재사용 가능한 달력 유틸리티 클래스인 `CalendarUtility`를 정의하여 특정 달력으로 날짜의 문자열 표현을 생성하는 대부분의 세부 작업을 처리합니다.  `CalendarUtility` 클래스에는 다음과 같은 멤버가 있습니다.  
  
-   해당 단일 매개 변수가 <xref:System.Globalization.Calendar> 개체\(날짜를 표시할 개체\)인 매개 변수화된 생성자.  이 생성자는 클래스의 전용 필드에 할당됩니다.  
  
-   `CalendarUtility` 개체가 표시하는 달력이 매개 변수로 메서드에 전달되는 <xref:System.Globalization.CultureInfo> 개체에서 지원되는지 여부를 나타내는 부울 값을 반환하는 private 메서드인 `CalendarExists`.  이 메서드는 <xref:System.Array.Exists%2A?displayProperty=fullName> 메서드에 대한 호출을 래핑하며 이 메서드로 <xref:System.Globalization.CultureInfo.OptionalCalendars%2A?displayProperty=fullName> 배열을 전달합니다.  
  
-   매개 변수로 <xref:System.Array.Exists%2A?displayProperty=fullName> 메서드에 전달되는 <xref:System.Predicate%601> 대리자에게 할당되는 private 메서드인 `HasSameName`.  배열의 각 멤버는 메서드가 `true`를 반환할 때까지 메서드에 전달됩니다.  이 메서드는 선택적 달력의 이름이 `CalendarUtility` 개체로 표현되는 달력의 이름과 같은지 확인합니다.  
  
-   두 매개 변수, 즉 `CalendarUtility` 개체가 나타내는 달력에 표시할 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 값과 해당 서식 지정 규칙을 사용할 문화권이 전달되는 오버로드된 public 메서드인 `DisplayDate`.  날짜의 문자열 표현을 반환할 때의 메서드 동작은 해당 서식 지정 규칙을 사용할 문화권에서 대상 달력을 지원하는지 여부에 따라 달라집니다.  
  
 이 예제에서 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 값을 만드는 데 어떤 달력을 사용했든 관계없이 해당 값은 일반적으로 그레고리오력 날짜로 표시됩니다.  이는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 형식에는 달력 정보가 유지되지 않기 때문입니다.  이러한 형식은 내부적으로 0001년 1월 1일 자정 이후 경과한 눈금 수로 표시되며  해당 숫자를 해석하는 방식은 달력에 따라 다릅니다.  대부분의 문화권에서는 그레고리오력이 기본 달력입니다.  
  
## 코드 컴파일  
 이 예제는 System.Core.dll을 참조해야 합니다.  
  
 csc.exe 또는 vb.exe를 사용하여 명령줄에서 코드를 컴파일합니다.  [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]에서 코드를 컴파일하려면 콘솔 응용 프로젝트 템플릿에 코드를 삽입합니다.  
  
## 참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)