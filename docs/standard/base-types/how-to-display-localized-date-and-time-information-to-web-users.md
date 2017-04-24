---
title: "방법: 웹 사용자에게 지역화된 날짜 및 시간 정보 표시 | Microsoft Docs"
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
  - "날짜 및 시간 데이터 표시"
  - "서식 지정[.NET Framework], 날짜"
  - "서식 지정[.NET Framework], 지역화된 데이터"
  - "지역화[.NET Framework], 날짜 및 시간 표시"
  - "지역화된 날짜 표시[.NET Framework]"
  - "문자열 구문 분석[.NET Framework], 날짜 및 시간 문자열"
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 웹 사용자에게 지역화된 날짜 및 시간 정보 표시
웹 페이지는 세계 어디서나 표시될 수 있기 때문에 날짜 및 시간 값을 구문 분석하고 형식을 지정하는 작업에서는 사용자와 상호 작용할 때 기본 형식\(대개 웹 서버의 현지 문화권 형식\)을 사용해서는 안 됩니다.  대신 사용자가 입력한 날짜 및 시간 문자열을 처리하는 Web Forms에서는 사용자의 기본 설정 문화권을 사용하여 문자열을 구문 분석해야 합니다.  마찬가지로 날짜 및 시간 데이터는 사용자 문화권에 맞는 형식으로 사용자에게 표시되어야 합니다.  이 항목에서는 이를 수행하는 방법에 대해 설명합니다.  
  
### 사용자가 입력한 날짜 및 시간 문자열을 구문 분석하려면  
  
1.  <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 속성이 반환하는 문자열 배열이 채워져 있는지 확인합니다.  배열이 채워져 있지 않으면 6단계로 이동합니다.  
  
2.  <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 반환하는 문자열 배열이 채워져 있으면 배열의 첫 번째 요소를 검색합니다.  첫 번째 요소는 사용자의 기본\(기본 설정\) 언어 및 지역을 나타냅니다.  
  
3.  <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName> 생성자를 호출하여 사용자의 기본 설정 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체를 인스턴스화합니다.  
  
4.  <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 형식의 `TryParse` 또는 `Parse` 메서드를 호출하여 변환을 시도합니다.  `TryParse` 또는 `Parse` 메서드의 오버로드를 `provider` 매개 변수와 함께 사용하고 다음 중 하나를 전달합니다.  
  
    -   3단계에서 만든 <xref:System.Globalization.CultureInfo> 개체  
  
    -   3단계에서 만든 <xref:System.Globalization.CultureInfo> 개체의 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> 속성에서 반환되는 <xref:System.Globalization.DateTimeFormatInfo> 개체  
  
5.  변환이 실패하면 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성에서 반환되는 문자열 배열에 있는 나머지 각 요소에 대해 2단계에서 4단계를 반복합니다.  
  
6.  그래도 변환이 실패하거나 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성에서 반환하는 문자열 배열이 비어 있으면 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> 속성에서 반환하는 고정 문화권을 사용하여 문자열을 구문 분석합니다.  
  
### 사용자 요청의 현지 날짜 및 시간을 구문 분석하려면  
  
1.  Web Form에 <xref:System.Web.UI.WebControls.HiddenField> 컨트롤을 추가합니다.  
  
2.  현재 날짜 및 시간과 UTC\(협정 세계시\)에 대한 현지 표준 시간대의 오프셋을 <xref:System.Web.UI.WebControls.HiddenField.Value%2A> 속성에 쓰는 방법으로 `Submit` 단추의 `onClick` 이벤트를 처리하는 JavaScript 함수를 만듭니다.  세미콜론 등의 구분 기호를 사용하여 문자열의 두 구성 요소를 구분합니다.  
  
3.  Web Form의 <xref:System.Web.UI.Control.PreRender> 이벤트를 사용하여 스크립트 텍스트를 <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=fullName> 메서드에 전달함으로써 함수를 HTML 출력 스트림에 삽입합니다.  
  
4.  JavaScript 함수의 이름을 `Submit` 단추의 `OnClientClick` 특성에 제공하여 이벤트 처리기를 `Submit` 단추의 `onClick` 이벤트에 연결합니다.  
  
5.  `Submit` 단추의 <xref:System.Web.UI.WebControls.Button.Click> 이벤트에 대한 처리기를 만듭니다.  
  
6.  이벤트 처리기에서 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 속성이 반환하는 문자열 배열이 채워져 있는지 확인합니다.  배열이 채워져 있지 않으면 14단계로 이동합니다.  
  
7.  <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 반환하는 문자열 배열이 채워져 있으면 배열의 첫 번째 요소를 검색합니다.  첫 번째 요소는 사용자의 기본\(기본 설정\) 언어 및 지역을 나타냅니다.  
  
8.  <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName> 생성자를 호출하여 사용자의 기본 설정 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체를 인스턴스화합니다.  
  
9. <xref:System.Web.UI.WebControls.HiddenField.Value%2A> 속성에 할당된 문자열을 <xref:System.String.Split%2A> 메서드로 전달하여 사용자의 현지 날짜 및 시간에 대한 문자열 표현과 사용자의 현지 표준 시간대 오프셋에 대한 문자열 표현을 각각 별도의 배열 요소에 저장합니다.  
  
10. <xref:System.DateTime.Parse%2A?displayProperty=fullName> 또는 <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=fullName> 메서드를 호출하여 사용자 요청의 날짜 및 시간을 <xref:System.DateTime> 값으로 변환합니다.  메서드의 오버로드를 `provider` 매개 변수와 함께 사용하고 다음 중 하나를 전달합니다.  
  
    -   8단계에서 만든 <xref:System.Globalization.CultureInfo> 개체  
  
    -   8단계에서 만든 <xref:System.Globalization.CultureInfo> 개체의 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> 속성에서 반환되는 <xref:System.Globalization.DateTimeFormatInfo> 개체  
  
11. 10단계의 구문 분석 작업이 실패하면 13단계로 이동하고,  그렇지 않으면 <xref:System.UInt32.Parse%28System.String%29?displayProperty=fullName> 메서드를 호출하여 사용자 표준 시간대 오프셋의 문자열 표현을 정수로 변환합니다.  
  
12. <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=fullName> 생성자를 호출하여 사용자의 현지 시간을 나타내는 <xref:System.DateTimeOffset>을 인스턴스화합니다.  
  
13. 10단계의 변환이 실패하면 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성에서 반환되는 문자열 배열에 있는 나머지 각 요소에 대해 7단계에서 12단계를 반복합니다.  
  
14. 그래도 변환이 실패하거나 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성에서 반환하는 문자열 배열이 비어 있으면 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> 속성에서 반환하는 고정 문화권을 사용하여 문자열을 구문 분석합니다.  그런 다음 7단계부터 12단계까지 반복합니다.  
  
 그러면 웹 페이지 사용자의 현지 시간을 나타내는 <xref:System.DateTimeOffset> 개체가 생성됩니다.  여기서 <xref:System.DateTimeOffset.ToUniversalTime%2A> 메서드를 호출하여 해당 UTC를 확인할 수 있습니다.  또한 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=fullName> 메서드를 호출하고 <xref:System.TimeZoneInfo.Local%2A?displayProperty=fullName>의 값을 시간을 변환할 표준 시간대로 전달하여 웹 서버에서 해당하는 날짜 및 시간을 확인할 수도 있습니다.  
  
## 예제  
 다음 예제에는 사용자에게 날짜 및 시간 값을 입력하라는 메시지를 표시하는 ASP.NET Web Form의 HTML 소스 및 코드가 모두 포함되어 있습니다.  또한 클라이언트 쪽 스크립트는 사용자 요청의 현지 날짜 및 시간과 UTC에 대한 사용자 표준 시간대의 오프셋을 숨겨진 필드에 씁니다.  이 정보는 서버에서 구문 분석되며 서버에서는 사용자 입력을 표시하는 웹 페이지를 반환합니다.  또한 사용자의 현지 시간, 서버의 시간 및 UTC를 사용하여 사용자 요청의 날짜 및 시간이 표시됩니다.  
  
 <!-- TODO: review snippet reference [!code-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]  -->
 <!-- TODO: review snippet reference [!code-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]  -->  
  
 클라이언트 쪽 스크립트에서는 JavaScript `toLocaleString` 메서드를 호출합니다.  그러면 사용자 로캘의 서식 지정 규칙을 따르는 문자열이 생성되며, 이 문자열은 서버에서 성공적으로 구문 분석될 가능성이 더 높습니다.  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 속성은 HTTP 요청에 포함된 `Accept-Language` 헤더에 들어 있는 문화권 이름에서 채워집니다.  그러나 모든 브라우저의 요청에 `Accept-Language` 헤더가 들어 있는 것은 아니며 사용자가 헤더를 완전히 표시하지 않을 수도 있습니다.  그러므로 사용자 입력을 구문 분석할 때는 대체\(fallback\) 문화권이 있어야 합니다.  일반적으로 대체\(fallback\) 문화권은 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>에서 반환하는 고정 문화권입니다.  사용자는 텍스트 상자에 문화권 이름을 입력하여 Internet Explorer에 대해 문화권 이름을 제공할 수도 있지만, 이렇게 하면 문화권 이름이 유효하지 않게 될 수도 있습니다.  그러므로 <xref:System.Globalization.CultureInfo> 개체를 인스턴스화할 때는 예외 처리를 사용해야 합니다.  
  
 Internet Explorer에서 전송한 HTTP 요청에서 검색되는 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 배열은 사용자가 기본 설정한 순서대로 채워집니다.  배열의 첫 번째 요소에는 사용자의 기본 문화권\/지역 이름이 포함됩니다.  배열에 항목이 추가로 포함된 경우에는 Internet Explorer에서 이러한 항목에 품질 지정자를 임의로 할당합니다. 품질 지정자는 세미콜론을 사용하여 문화권 이름과 구분됩니다.  예를 들어 fr\-FR 문화권에 대한 항목은 `fr-FR;q=0.7` 형식일 수 있습니다.  
  
 이 예제에서는 `useUserOverride` 매개 변수를 `false`로 설정하고 <xref:System.Globalization.CultureInfo.%23ctor%2A> 생성자를 호출하여 새 <xref:System.Globalization.CultureInfo> 개체를 만듭니다.  이렇게 하면 문화권 이름이 서버의 기본 문화권 이름인 경우 클래스 생성자에서 만드는 새 <xref:System.Globalization.CultureInfo> 개체에 문화권의 기본 설정이 포함되고 서버의 **국가 및 언어 옵션**을 사용하여 재정의한 모든 설정이 반영되지 않습니다.  서버에서 재정의된 설정 값은 사용자 시스템에 없거나 사용자 입력에 반영되지 않습니다.  
  
 이 예제에서는 날짜 및 시간의 두 문자열 표현\(사용자의 입력과 숨겨진 필드에 저장된 입력\)을 구문 분석하므로 사전에 필요할 수 있는 <xref:System.Globalization.CultureInfo> 개체를 정의합니다.  즉, <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 속성에서 반환하는 요소의 수보다 큰 <xref:System.Globalization.CultureInfo> 개체의 배열이 만들어집니다.  그런 다음 각 언어\/지역 문자열에 대해 <xref:System.Globalization.CultureInfo> 개체가 인스턴스화되며 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>를 나타내는 <xref:System.Globalization.CultureInfo> 개체도 인스턴스화됩니다.  
  
 코드에서 <xref:System.DateTime.Parse%2A> 또는 <xref:System.DateTime.TryParse%2A> 메서드를 호출하여 사용자의 날짜 및 시간 문자열 표현을 <xref:System.DateTime> 값으로 변환할 수 있습니다.  한 번의 구문 분석 작업을 위해 구문 분석 메서드를 반복해서 호출해야 할 수 있습니다.  그러므로 구문 분석 작업이 실패하면 `false`를 반환하는 <xref:System.DateTime.TryParse%2A> 메서드를 사용하는 것이 보다 효과적입니다.  반면 <xref:System.DateTime.Parse%2A> 메서드에서 throw할 수 있는 반복적인 예외를 처리하는 작업은 웹 응용 프로그램의 경우 매우 많은 비용이 소요될 수 있습니다.  
  
## 코드 컴파일  
 코드를 컴파일하려면 코드를 숨기지 않고 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 페이지를 만듭니다.  그런 다음 모든 기존 코드 대신 이 항목의 예제를 웹 페이지에 복사합니다.  그러면 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 페이지에 다음 컨트롤이 포함됩니다.  
  
-   코드에서 참조되지 않는 <xref:System.Web.UI.WebControls.Label> 컨트롤.  <xref:System.Web.UI.WebControls.TextBox.Text%2A> 속성을 "Enter a Number:"로 설정합니다.  
  
-   `DateString`이라는 <xref:System.Web.UI.WebControls.TextBox> 컨트롤  
  
-   `OKButton`이라는 <xref:System.Web.UI.WebControls.Button> 컨트롤.  <xref:System.Web.UI.WebControls.Button.Text%2A> 속성을 "OK"로 설정합니다.  
  
-   `DateInfo`라는 <xref:System.Web.UI.WebControls.HiddenField> 컨트롤  
  
## .NET Framework 보안  
 사용자가 HTML 스트림에 스크립트를 삽입하지 못하게 하려면 사용자 입력을 서버 응답에서 직접 다시 에코해서는 안 됩니다.  이 경우에는 <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=fullName> 메서드를 사용하여 입력을 인코딩해야 합니다.  
  
## 참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [표준 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)   
 [사용자 지정 날짜 및 시간 형식 문자열](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)   
 [날짜 및 시간 문자열 구문 분석](../../../docs/standard/base-types/parsing-datetime.md)