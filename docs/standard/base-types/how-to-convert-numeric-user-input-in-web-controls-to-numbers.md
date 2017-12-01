---
title: "방법: 사용자가 웹 컨트롤에 입력한 숫자를 숫자로 변환"
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
- parsing strings [.NET Framework], numeric strings
- converting numeric user input to number
- numbers [.NET Framework], converting numeric user input to number
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 92e28e3b303a7523b9da69b7eb283e0261fc681c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-numeric-user-input-in-web-controls-to-numbers"></a>방법: 사용자가 웹 컨트롤에 입력한 숫자를 숫자로 변환
사용자가 숫자 데이터를 입력할 수는 웹 페이지는 전 세계 어디서 나 표시 될 수 있으므로 <xref:System.Web.UI.WebControls.TextBox> 거의 무제한 형식 중에서 제어 합니다. 결과적으로, 것이 로캘 및 웹 페이지의 사용자의 문화권을 결정 하는 매우 중요 합니다. 사용자 입력을 구문 분석할 때 사용자의 로캘 및 문화권에 의해 정의 된 서식 지정 규칙을 적용할 수 있습니다.  
  
### <a name="to-convert-numeric-input-from-a-web-textbox-control-to-a-number"></a>웹 TextBox 컨트롤에서 입력을 숫자로 변환 하려면  
  
1.  문자열 배열에서 반환 되는지 확인은 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 속성이 채워집니다. 그렇지 않을 경우 6 단계를 진행 합니다.  
  
2.  문자열 배열에서 반환 하는 경우는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 채워집니다, 그 첫 번째 요소를 검색 합니다. 첫 번째 요소는 사용자의 기본 또는 기본 언어와 지역을 나타냅니다.  
  
3.  인스턴스화하는 <xref:System.Globalization.CultureInfo> 사용자를 나타내는 개체를 호출 하 여 문화권의 기본 설정의 <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> 생성자입니다.  
  
4.  호출 된 `TryParse` 또는 `Parse` 사용자 변환할 숫자 형식의 메서드 입력을 합니다. 오버 로드를 사용 하 여는 `TryParse` 또는 `Parse` 사용 하 여 메서드는 `provider` 매개 변수를 다음 중 하나를 전달 합니다.  
  
    -   <xref:System.Globalization.CultureInfo> 3 단계에서 만든 개체입니다.  
  
    -   <xref:System.Globalization.NumberFormatInfo> 에서 반환 되는 개체는 <xref:System.Globalization.CultureInfo.NumberFormat%2A> 의 속성은 <xref:System.Globalization.CultureInfo> 3 단계에서 만든 개체입니다.  
  
5.  변환에 실패 하는 경우 2 단계까지 반복 문자열 배열에 나머지 각 요소에 대해 4에서 반환 되는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성입니다.  
  
6.  변환에 실패 하면 여전히 또는 문자열 배열에서 반환 하는 경우는 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 비어 있으면 반환 하는 고정 문화권을 사용 하 여 문자열을 구문 분석은 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 속성입니다.  
  
## <a name="example"></a>예제  
 다음 예제는 전체 코드 숨김 페이지에 숫자 값을 입력 하 라는 웹 폼에 대 한 <xref:System.Web.UI.WebControls.TextBox> 제어 하 고을 숫자로 변환 합니다. 해당 숫자를 두 배로 증가 하 고 원래 입력에서 동일한 서식 규칙을 사용 하 여 표시 합니다.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 속성에 포함 된 문화권 이름에서 입력 됩니다 `Accept-Language` HTTP 요청에 포함 된 헤더입니다. 그러나 포함 하지 않는 브라우저 `Accept-Language` 헤더의 요청 및 사용자에 헤더를 완전히 않을 수도 있습니다. 이렇게 하면 사용자 입력을 구문 분석할 때 대체 문화권을 보유 해야 합니다. 일반적으로 대체 문화권은 고정 문화권에서 반환 된 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>합니다. 사용자가 제공할 수도 Internet Explorer 문화권 이름으로는 문화권 이름은 유효 하지 않게 될 가능성을 만드는 텍스트 상자에 입력 하 합니다. 이렇게 하면 인스턴스화할 때 예외 처리를 사용 하는 것이 중요 한 <xref:System.Globalization.CultureInfo> 개체입니다.  
  
 Internet Explorer에서 제출 하는 HTTP 요청에서 검색할 때의 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=nameWithType> 배열 사용자 기본 설정 순서에 채워집니다. 배열의 첫 번째 요소에는 사용자의 기본 문화권/지역의 이름을 포함합니다. 배열에는 추가 항목이 포함 된 경우 Internet Explorer 임의로 할당 품질 지정자에서 문화권 이름을 세미콜론으로 구분 합니다. FR-FR 문화권에 대 한 항목 형식을 가질 수 예를 들어 `fr-FR;q=0.7`합니다.  
  
 예제에서는 <xref:System.Globalization.CultureInfo.%23ctor%2A> 생성자와 해당 `useUserOverride` 매개 변수 설정 `false` 새로 만들려면 <xref:System.Globalization.CultureInfo> 개체입니다. 이렇게 하면, 문화권 이름이 서버에서 기본 문화권 이름을 새 <xref:System.Globalization.CultureInfo> 클래스 생성자가 만든 개체는 문화권의 기본 설정을 포함 하 고 서버를 사용 하 여 재정의 설정을 반영 하지 않습니다  **국가별 및 언어 옵션** 응용 프로그램입니다. 서버에서 재정의 된 설정의 값 사용자의 시스템에 있는 사용자의 입력에 반영 되지 않습니다.  
  
 코드 중 하나를 호출할 수는 `Parse` 또는 `TryParse` 메서드는 사용자의 입력 하는 숫자 형식으로 변환 됩니다. Parse 메서드를 반복된 호출 하는 단일 구문 분석 작업에 대 한 필요할 수 있습니다. 결과적으로 `TryParse` 메서드는 반환 하기 때문에 더 나은, `false` 구문 분석 작업이 실패 하는 경우. 반면에 의해 throw 될 수 있는 반복 된 예외를 처리는 `Parse` 웹 응용 프로그램에는 매우 많은 비용이 소요 될 수 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 코드를 컴파일하려면 복사에 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 코드 숨김 페이지 모든 기존 코드를 대체 하도록 합니다. [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 페이지는 다음과 같은 컨트롤을 포함 해야 합니다.  
  
-   A <xref:System.Web.UI.WebControls.Label> 컨트롤을 코드에서 참조 되지 않습니다. 설정의 <xref:System.Web.UI.WebControls.TextBox.Text%2A> 속성을 "숫자를 입력 하십시오:".  
  
-   `NumericString`이라는 <xref:System.Web.UI.WebControls.TextBox> 컨트롤  
  
-   `OKButton`이라는 <xref:System.Web.UI.WebControls.Button> 컨트롤 설정의 <xref:System.Web.UI.WebControls.Button.Text%2A> 속성을 "OK"입니다.  
  
 클래스의 이름을 변경 `NumericUserInput` 에서 정의 된 클래스의 이름에는 `Inherits` 특성에는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지의 `Page` 지시문입니다. 이름을 변경는 `NumericInput` 개체에 정의 된 이름에 대 한 참조는 `id` 특성에는 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지의 `form` 태그입니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 사용자 스크립트를 HTML 스트림에 삽입 되지 않도록 하려면 사용자 입력 되지 에코 해야 할지 직접 서버 응답에서. 대신, 사용 하 여 암호화 되어야는 <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=nameWithType> 메서드.  
  
## <a name="see-also"></a>참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)  
 [숫자 문자열 구문 분석](../../../docs/standard/base-types/parsing-numeric.md)
