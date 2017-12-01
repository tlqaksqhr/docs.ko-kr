---
title: "방법: 웹 사용자에게 지역화된 날짜 및 시간 정보 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- formatting [.NET Framework], dates
- parsing strings [.NET Framework], date and time strings
- localization [.NET Framework], date and time displays
- formatting [.NET Framework], localized data
- displaying date and time data
- localized date displays [.NET Framework]
ms.assetid: 377fe93c-32be-421a-a30a-be639a46ede8
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 21493e0e0c9e42cf5efc42d86c8f126fbae9b392
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-localized-date-and-time-information-to-web-users"></a>방법: 웹 사용자에게 지역화된 날짜 및 시간 정보 표시
구문 분석 하 고 날짜 및 시간 값의 형식을 지정 하는 작업 (이 가장 자주 웹 서버 로컬 문화권의 형식) 기본 형식에 의존 하지 않아야 웹 페이지는 전 세계 어디서 나 표시 될 수 있습니다, 때문에 사용자와 상호 작용할 때. 대신, 사용자가 입력 한 문자열 시간과 날짜를 처리 하는 Web forms에는 사용자의 기본 culture를 사용 하 여 문자열 구문 분석 해야 합니다. 마찬가지로, 날짜 및 시간 데이터는 사용자의 culture에 맞는 형식으로의 사용자에 게 표시 됩니다. 이 항목에서는 프로젝션의 형식을 제어하는 방법을 보여 줍니다.  
  
### <a name="to-parse-date-and-time-strings-input-by-the-user"></a>사용자가 입력 문자열을 날짜 및 시간 구문 분석  
  
1.  문자열 배열에서 반환 되는지 확인은 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 속성이 채워집니다. 그렇지 않을 경우 6 단계를 진행 합니다.  
  
2.  문자열 배열에서 반환 하는 경우는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 채워집니다, 그 첫 번째 요소를 검색 합니다. 첫 번째 요소는 사용자의 기본 또는 기본 언어와 지역을 나타냅니다.  
  
3.  인스턴스화하는 <xref:System.Globalization.CultureInfo> 사용자를 나타내는 개체를 호출 하 여 문화권의 기본 설정의 <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> 생성자입니다.  
  
4.  중 하나를 호출는 `TryParse` 또는 `Parse` 의 메서드는 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 종류를 변환 하십시오. 오버 로드를 사용 하 여는 `TryParse` 또는 `Parse` 사용 하 여 메서드는 `provider` 매개 변수를 다음 중 하나를 전달 합니다.  
  
    -   <xref:System.Globalization.CultureInfo> 3 단계에서 만든 개체입니다.  
  
    -   <xref:System.Globalization.DateTimeFormatInfo> 에서 반환 되는 개체는 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> 의 속성은 <xref:System.Globalization.CultureInfo> 3 단계에서 만든 개체입니다.  
  
5.  변환에 실패 하는 경우 2 단계까지 반복 문자열 배열에 나머지 각 요소에 대해 4에서 반환 되는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성입니다.  
  
6.  변환에 실패 하면 여전히 또는 문자열 배열에서 반환 하는 경우는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 비어 있으면 반환 하는 고정 문화권을 사용 하 여 문자열을 구문 분석은 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 속성입니다.  
  
### <a name="to-parse-the-local-date-and-time-of-the-users-request"></a>로컬 날짜 및 시간 사용자의 요청을 구문 분석 하려면  
  
1.  추가 <xref:System.Web.UI.WebControls.HiddenField> 컨트롤을 웹 폼입니다.  
  
2.  처리 하는 JavaScript 함수를 만들기는 `onClick` 의 이벤트는 `Submit` 현재 날짜 및 시간과 현지 표준 시간대 오프셋을 utc (협정 세계시)에서 작성 하 여 단추는 <xref:System.Web.UI.WebControls.HiddenField.Value%2A> 속성. 문자열의 두 가지 구성 요소를 구분 하는 구분 기호 (예: 세미콜론)를 사용 합니다.  
  
3.  Web form을 사용 하 여 <xref:System.Web.UI.Control.PreRender> 스크립트의 텍스트를 전달 하 여 HTML에 함수를 삽입 하는 이벤트 출력 스트림에 <xref:System.Web.UI.ClientScriptManager.RegisterClientScriptBlock%28System.Type%2CSystem.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType> 메서드.  
  
4.  이벤트 처리기를 연결는 `Submit` 단추의 `onClick` JavaScript 함수의 이름을 제공 하 여 이벤트는 `OnClientClick` 특성에는 `Submit` 단추입니다.  
  
5.  에 대 한 처리기를 만들기는 `Submit` 단추의 <xref:System.Web.UI.WebControls.Button.Click> 이벤트입니다.  
  
6.  이벤트 처리기에서 문자열 배열을 반환 여부를 확인는 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 속성이 채워집니다. 없는 경우에 14 단계를 계속 합니다.  
  
7.  문자열 배열에서 반환 하는 경우는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 채워집니다, 그 첫 번째 요소를 검색 합니다. 첫 번째 요소는 사용자의 기본 또는 기본 언어와 지역을 나타냅니다.  
  
8.  인스턴스화하는 <xref:System.Globalization.CultureInfo> 사용자를 나타내는 개체를 호출 하 여 문화권의 기본 설정의 <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> 생성자입니다.  
  
9. 에 할당 된 문자열을 전달는 <xref:System.Web.UI.WebControls.HiddenField.Value%2A> 속성을는 <xref:System.String.Split%2A> 메서드를 별도 배열 요소에 사용자의 로컬 날짜 및 시간의 문자열 표현 및 사용자의 현지 시간 표준 시간대 오프셋의 문자열 표현을 저장 합니다.  
  
10. 호출의 <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> 또는 <xref:System.DateTime.TryParse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%2CSystem.DateTime%40%29?displayProperty=nameWithType> 날짜와 시간을 사용자의 요청을 변환 하는 메서드는 <xref:System.DateTime> 값입니다. 사용 하 여 메서드 오버 로드를 사용 하 여 한 `provider` 매개 변수를 다음 중 하나를 전달 합니다.  
  
    -   <xref:System.Globalization.CultureInfo> 8 단계에서 만든 개체입니다.  
  
    -   <xref:System.Globalization.DateTimeFormatInfo> 에서 반환 되는 개체는 <xref:System.Globalization.CultureInfo.DateTimeFormat%2A> 의 속성은 <xref:System.Globalization.CultureInfo> 8 단계에서 만든 개체입니다.  
  
11. 10 단계에서 구문 분석 작업이 실패 하면 13 단계로 이동 합니다. 그렇지 않으면 호출에서 <xref:System.UInt32.Parse%28System.String%29?displayProperty=nameWithType> 메서드를 사용자의 표준 시간대 오프셋의 문자열 표현을 정수로 변환 합니다.  
  
12. 인스턴스화하는 <xref:System.DateTimeOffset> 호출 하 여 사용자의 현지 시간을 나타내는 <xref:System.DateTimeOffset.%23ctor%28System.DateTime%2CSystem.TimeSpan%29?displayProperty=nameWithType> 생성자입니다.  
  
13. 10 단계에서 변환에 실패 하는 경우에서 반환 된 문자열 배열에 나머지 각 요소에 대 한 12 7 단계를 반복는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성입니다.  
  
14. 변환에 실패 하면 여전히 또는 문자열 배열에서 반환 하는 경우는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 비어 있으면 반환 하는 고정 문화권을 사용 하 여 문자열을 구문 분석은 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 속성입니다. 그런 다음 7-12 단계를 반복 합니다.  
  
 결과는 <xref:System.DateTimeOffset> 웹 페이지의 사용자의 현지 시간을 나타내는 개체입니다. 해당 하는 UTC를 호출 하 여 확인할 수 있습니다는 <xref:System.DateTimeOffset.ToUniversalTime%2A> 메서드. 확인할 수도 있습니다는 날짜 및 시간 웹 서버에서 호출 하 여는 <xref:System.TimeZoneInfo.ConvertTime%28System.DateTimeOffset%2CSystem.TimeZoneInfo%29?displayProperty=nameWithType> 메서드 및 값을 전달 <xref:System.TimeZoneInfo.Local%2A?displayProperty=nameWithType> 시간을 변환 하는 표준 시간대로 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 HTML 소스와 사용자를 날짜 및 시간 값을 입력 하도록 요청 하는 ASP.NET Web form에 대 한 코드를 포함 합니다. 클라이언트 쪽 스크립트는 또한 숨겨진된 필드에 UTC에서 로컬 날짜 및 시간을 사용자의 요청 및 사용자의 표준 시간대 오프셋에 대 한 정보를 씁니다. 이 정보는 사용자 입력을 표시 하는 웹 페이지를 반환 하는 서버에 의해 구문 분석 합니다. 사용자의 요청 사용자의 현지 시간, 시간을 사용 하 여 서버 및 UTC 시간과 날짜에도 표시 됩니다.  
  
 [!code-aspx-csharp[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/cs/GetDateInfo.aspx#1)]
 [!code-aspx-vb[Formatting.HowTo.ParseDateInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseDateInput/vb/GetDateInfo.aspx#1)]
  
 JavaScript를 호출 하는 클라이언트 쪽 스크립트 `toLocaleString` 메서드. 이 서버에 성공적으로 구문 분석할 수 있는 사용자의 로캘의 서식 지정 규칙을 따르는 문자열을 생성 합니다.  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 속성에 포함 된 문화권 이름에서 입력 됩니다 `Accept-Language` HTTP 요청에 포함 된 헤더입니다. 그러나 포함 하지 않는 브라우저 `Accept-Language` 헤더의 요청 및 사용자에 헤더를 완전히 않을 수도 있습니다. 이렇게 하면 사용자 입력을 구문 분석할 때 대체 문화권을 보유 해야 합니다. 일반적으로 대체 문화권은 고정 문화권에서 반환 된 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>합니다. 사용자가 제공할 수도 Internet Explorer 문화권 이름으로는 문화권 이름은 유효 하지 않게 될 가능성을 만드는 텍스트 상자에 입력 하 합니다. 이렇게 하면 인스턴스화할 때 예외 처리를 사용 하는 것이 중요 한 <xref:System.Globalization.CultureInfo> 개체입니다.  
  
 Internet Explorer에서 제출 하는 HTTP 요청에서 검색할 때의 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 배열 사용자 기본 설정 순서에 채워집니다. 배열의 첫 번째 요소에는 사용자의 기본 문화권/지역의 이름을 포함합니다. 배열에는 추가 항목이 포함 된 경우 Internet Explorer 임의로 할당 품질 지정자에서 문화권 이름을 세미콜론으로 구분 합니다. FR-FR 문화권에 대 한 항목 형식을 가질 수 예를 들어 `fr-FR;q=0.7`합니다.  
  
 예제에서는 <xref:System.Globalization.CultureInfo.%23ctor%2A> 생성자와 해당 `useUserOverride` 매개 변수 설정 `false` 새로 만들려면 <xref:System.Globalization.CultureInfo> 개체입니다. 이렇게 하면, 문화권 이름이 서버에서 기본 문화권 이름을 새 <xref:System.Globalization.CultureInfo> 클래스 생성자가 만든 개체는 문화권의 기본 설정을 포함 하 고 서버를 사용 하 여 재정의 설정을 반영 하지 않습니다  **국가별 및 언어 옵션** 응용 프로그램입니다. 서버에서 재정의 된 설정의 값 사용자의 시스템에 있는 사용자의 입력에 반영 되지 않습니다.  
  
 이 예제에서는 날짜 및 시간 (숨겨진된 필드에 저장 된 사용자가 하나의 입력)의 두 문자열 표현을 구문 분석을 하기 때문에 정의 <xref:System.Globalization.CultureInfo> 사전에 필요할 수 있는 개체입니다. 배열을 만들 <xref:System.Globalization.CultureInfo> 가 반환 하는 요소 개수 보다 1 씩 증가 하는 개체는 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 속성입니다. 그런 다음는 <xref:System.Globalization.CultureInfo> 각 언어/지역 문자열에 대 한 개체를 인스턴스화하고는 <xref:System.Globalization.CultureInfo> 을 나타내는 개체 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>합니다.  
  
 코드 중 하나를 호출할 수는 <xref:System.DateTime.Parse%2A> 또는 <xref:System.DateTime.TryParse%2A> 날짜의 문자열 표현을 사용자의 변환 하는 데 필요한 시간 메서드는 <xref:System.DateTime> 값입니다. Parse 메서드를 반복된 호출 하는 단일 구문 분석 작업에 대 한 필요할 수 있습니다. 결과적으로 <xref:System.DateTime.TryParse%2A> 메서드는 반환 하기 때문에 더 나은 `false` 구문 분석 작업이 실패 하는 경우. 반면에 의해 throw 될 수 있는 반복 된 예외를 처리는 <xref:System.DateTime.Parse%2A> 웹 응용 프로그램에는 매우 많은 비용이 소요 될 수 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 만들기는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 코드 숨김 없이 웹 페이지입니다. 그런 다음 모든 기존 코드를 웹 페이지에는 예를 복사 합니다. [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 페이지는 다음과 같은 컨트롤을 포함 해야 합니다.  
  
-   A <xref:System.Web.UI.WebControls.Label> 컨트롤을 코드에서 참조 되지 않습니다. 설정의 <xref:System.Web.UI.WebControls.TextBox.Text%2A> 속성을 "숫자를 입력 하십시오:".  
  
-   `DateString`이라는 <xref:System.Web.UI.WebControls.TextBox> 컨트롤  
  
-   `OKButton`이라는 <xref:System.Web.UI.WebControls.Button> 컨트롤 설정의 <xref:System.Web.UI.WebControls.Button.Text%2A> 속성을 "OK"입니다.  
  
-   `DateInfo`이라는 <xref:System.Web.UI.WebControls.HiddenField> 컨트롤  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 사용자 스크립트를 HTML 스트림에 삽입 되지 않도록 하려면 사용자 입력 되지 에코 해야 할지 직접 서버 응답에서. 대신, 사용 하 여 암호화 되어야는 <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [Standard Date and Time Format Strings](../../../docs/standard/base-types/standard-date-and-time-format-strings.md)  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)  
 [날짜 및 시간 문자열 구문 분석](../../../docs/standard/base-types/parsing-datetime.md)
