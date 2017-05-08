---
title: "방법: 사용자가 웹 컨트롤에 입력한 숫자를 숫자로 변환 | Microsoft Docs"
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
  - "숫자 사용자 입력을 숫자로 변환"
  - "서식 지정[.NET Framework], 숫자"
  - "숫자 형식 지정[.NET Framework]"
  - "숫자[.NET Framework], 숫자 사용자 입력을 숫자로 변환"
  - "숫자 형식 문자열[.NET Framework]"
  - "문자열 구문 분석[.NET Framework], 숫자 문자열"
ms.assetid: f27ddfb8-7479-4b79-8879-02a3bd8402d4
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 방법: 사용자가 웹 컨트롤에 입력한 숫자를 숫자로 변환
웹 페이지는 세계 어디서나 표시될 수 있기 때문에 사용자가 <xref:System.Web.UI.WebControls.TextBox> 컨트롤에 숫자 데이터를 입력할 수 있는 형식에는 거의 제한이 없습니다.  그러므로 웹 페이지 사용자의 로캘 및 문화권을 확인하는 일은 매우 중요합니다.  사용자 입력을 구문 분석할 때는 사용자의 로캘 및 문화권에 의해 정의되는 서식 지정 규칙을 적용할 수 있습니다.  
  
### 웹 TextBox 컨트롤에 입력한 숫자를 숫자로 변환하려면  
  
1.  <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 속성이 반환하는 문자열 배열이 채워져 있는지 확인합니다.  배열이 채워져 있지 않으면 6단계로 이동합니다.  
  
2.  <xref:System.Web.HttpRequest.UserLanguages%2A> 속성이 반환하는 문자열 배열이 채워져 있으면 배열의 첫 번째 요소를 검색합니다.  첫 번째 요소는 사용자의 기본\(기본 설정\) 언어 및 지역을 나타냅니다.  
  
3.  <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=fullName> 생성자를 호출하여 사용자의 기본 설정 문화권을 나타내는 <xref:System.Globalization.CultureInfo> 개체를 인스턴스화합니다.  
  
4.  사용자 입력을 변환할 대상 숫자 형식의 `TryParse` 또는 `Parse` 메서드를 호출합니다.  `TryParse` 또는 `Parse` 메서드의 오버로드를 `provider` 매개 변수와 함께 사용하고 다음 중 하나를 전달합니다.  
  
    -   3단계에서 만든 <xref:System.Globalization.CultureInfo> 개체  
  
    -   3단계에서 만든 <xref:System.Globalization.CultureInfo> 개체의 <xref:System.Globalization.CultureInfo.NumberFormat%2A> 속성에서 반환되는 <xref:System.Globalization.NumberFormatInfo> 개체  
  
5.  변환이 실패하면 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성에서 반환되는 문자열 배열에 있는 나머지 각 요소에 대해 2단계에서 4단계를 반복합니다.  
  
6.  그래도 변환이 실패하거나 <xref:System.Web.HttpRequest.UserLanguages%2A> 속성에서 반환하는 문자열 배열이 비어 있으면 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> 속성에서 반환하는 고정 문화권을 사용하여 문자열을 구문 분석합니다.  
  
## 예제  
 다음 예제는 사용자에게 <xref:System.Web.UI.WebControls.TextBox> 컨트롤에 숫자 값을 입력하도록 하고 해당 값을 숫자로 변환하는 Web Form의 전체 코드 숨김 페이지입니다.  사용자가 입력한 숫자 값은 원래 입력 값과 같은 서식 지정 규칙을 사용하여 두 배로 늘어나 표시됩니다.  
  
 [!code-csharp[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/cs/NumericUserInput1.aspx.cs#1)]
 [!code-vb[Formatting.HowTo.ParseNumericInput#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.ParseNumericInput/vb/NumericUserInput1.aspx.vb#1)]  
  
 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 속성은 HTTP 요청에 포함된 `Accept-Language` 헤더에 들어 있는 문화권 이름에서 채워집니다.  그러나 모든 브라우저의 요청에 `Accept-Language` 헤더가 들어 있는 것은 아니며 사용자가 헤더를 완전히 표시하지 않을 수도 있습니다.  그러므로 사용자 입력을 구문 분석할 때는 대체\(fallback\) 문화권이 있어야 합니다.  일반적으로 대체\(fallback\) 문화권은 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>에서 반환하는 고정 문화권입니다.  사용자는 텍스트 상자에 문화권 이름을 입력하여 Internet Explorer에 대해 문화권 이름을 제공할 수도 있지만, 이렇게 하면 문화권 이름이 유효하지 않게 될 수도 있습니다.  그러므로 <xref:System.Globalization.CultureInfo> 개체를 인스턴스화할 때는 예외 처리를 사용해야 합니다.  
  
 Internet Explorer에서 전송한 HTTP 요청에서 검색되는 <xref:System.Web.HttpRequest.UserLanguages%2A?displayProperty=fullName> 배열은 사용자가 기본 설정한 순서대로 채워집니다.  배열의 첫 번째 요소에는 사용자의 기본 문화권\/지역 이름이 포함됩니다.  배열에 항목이 추가로 포함된 경우에는 Internet Explorer에서 이러한 항목에 품질 지정자를 임의로 할당합니다. 품질 지정자는 세미콜론을 사용하여 문화권 이름과 구분됩니다.  예를 들어 fr\-FR 문화권에 대한 항목은 `fr-FR;q=0.7` 형식일 수 있습니다.  
  
 이 예제에서는 `useUserOverride` 매개 변수를 `false`로 설정하고 <xref:System.Globalization.CultureInfo.%23ctor%2A> 생성자를 호출하여 새 <xref:System.Globalization.CultureInfo> 개체를 만듭니다.  이렇게 하면 문화권 이름이 서버의 기본 문화권 이름인 경우 클래스 생성자에서 만드는 새 <xref:System.Globalization.CultureInfo> 개체에 문화권의 기본 설정이 포함되고 서버의 **국가 및 언어 옵션**을 사용하여 재정의한 모든 설정이 반영되지 않습니다.  서버에서 재정의된 설정 값은 사용자 시스템에 없거나 사용자 입력에 반영되지 않습니다.  
  
 코드에서 사용자 입력을 변환할 대상 숫자 형식의 `Parse` 또는 `TryParse` 메서드를 호출할 수 있습니다.  한 번의 구문 분석 작업을 위해 구문 분석 메서드를 반복해서 호출해야 할 수 있습니다.  그러므로 구문 분석 작업이 실패하면 `false`를 반환하는 `TryParse` 메서드를 사용하는 것이 보다 효과적입니다.  반면 `Parse` 메서드에서 throw할 수 있는 반복적인 예외를 처리하는 작업은 웹 응용 프로그램의 경우 매우 많은 비용이 소요될 수 있습니다.  
  
## 코드 컴파일  
 코드를 컴파일하려면 모든 기존 코드를 대체하도록 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 코드 숨김 페이지에 복사합니다.  그러면 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 웹 페이지에 다음 컨트롤이 포함됩니다.  
  
-   코드에서 참조되지 않는 <xref:System.Web.UI.WebControls.Label> 컨트롤.  <xref:System.Web.UI.WebControls.TextBox.Text%2A> 속성을 "Enter a Number:"로 설정합니다.  
  
-   `NumericString`이라는 <xref:System.Web.UI.WebControls.TextBox> 컨트롤  
  
-   `OKButton`이라는 <xref:System.Web.UI.WebControls.Button> 컨트롤.  <xref:System.Web.UI.WebControls.Button.Text%2A> 속성을 "OK"로 설정합니다.  
  
 클래스의 이름을 `NumericUserInput`에서 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지 `Page` 지시문의 `Inherits` 특성에서 정의되는 클래스의 이름으로 변경합니다.  `NumericInput` 개체 참조의 이름을 [!INCLUDE[vstecasp](../../../includes/vstecasp-md.md)] 페이지 `form` 태그의 `id` 특성에서 정의되는 이름으로 변경합니다.  
  
## .NET Framework 보안  
 사용자가 HTML 스트림에 스크립트를 삽입하지 못하게 하려면 사용자 입력을 서버 응답에서 직접 다시 에코해서는 안 됩니다.  이 경우에는 <xref:System.Web.HttpServerUtility.HtmlEncode%2A?displayProperty=fullName> 메서드를 사용하여 입력을 인코딩해야 합니다.  
  
## 참고 항목  
 [서식 지정 작업 수행](../../../docs/standard/base-types/performing-formatting-operations.md)   
 [숫자 문자열 구문 분석](../../../docs/standard/base-types/parsing-numeric.md)