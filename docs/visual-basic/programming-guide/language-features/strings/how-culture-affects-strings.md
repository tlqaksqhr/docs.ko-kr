---
title: "How Culture Affects Strings in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "locale, effect on strings"
  - "strings [Visual Basic], locale dependence"
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How Culture Affects Strings in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 도움말 페이지에서는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 문화권 정보를 사용하여 문자열 변환과 비교를 수행하는 방법에 대해 설명합니다.  
  
## 문화권 관련 문자열을 사용하는 경우  
 일반적으로 사용자에게 제공하고 사용자로부터 읽어오는 모든 데이터에는 문화권 관련 문자열을 사용하고, 응용 프로그램의 내부 데이터에는 문화권 고정 문자열을 사용해야 합니다.  
  
 예를 들어, 응용 프로그램에서 사용자가 날짜를 문자열로 입력해야 하는 경우 사용자는 자신의 문화권에 따라 문자열 형식을 지정해야 하며 응용 프로그램에서는 이 문자열을 적절히 변환해야 합니다.  응용 프로그램에서 이 날짜를 자체 사용자 인터페이스로 나타내는 경우에는 날짜가 해당 사용자의 문화권으로 제공되어야 합니다.  
  
 그러나 응용 프로그램에서 날짜를 중앙 서버에 업로드하는 경우에는 여러 가지 날짜 형식 간의 혼동이 없도록 한 가지 특정 문화권에 따라 문자열 형식을 지정해야 합니다.  
  
## 문화권의 영향을 받는 함수  
 `Str` 및 `Val` 함수를 제외한 모든 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문자열 변환 함수에서는 응용 프로그램의 문화권 정보를 사용하여 변환과 비교가 응용 프로그램 사용자의 문화권에 맞게 수행되도록 합니다.  
  
 여러 가지 문화권이 설정되어 있는 컴퓨터에서 실행되는 응용 프로그램에서 문자열 변환 함수를 제대로 사용하기 위해서는 특정 문화권 설정을 사용하는 함수와 현재 문화권 설정을 사용하는 함수를 파악하는 것이 중요합니다.  응용 프로그램의 문화권 설정은 기본적으로 운영 체제의 문화권 설정에서 상속됩니다.  자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A> 및 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)를 참조하십시오.  
  
 `Str`\(숫자를 문자열로 변환\) 함수와 `Val`\(문자열을 숫자로 변환\) 함수에서는 문자열과 숫자 간을 변환할 때 응용 프로그램의 문화권 정보를 사용하지 않습니다.  마침표\(.\)만이 유효한 소수 구분 기호로 인식됩니다.  이 두 함수에서 문화권을 인식하는 유사한 점은 다음과 같습니다.  
  
-   **현재 문화권을 사용하는 변환.** `CStr` 함수와 `Format` 함수는 숫자를 문자열로 변환하고, `CDbl` 함수와 `CInt` 함수는 문자열을 숫자로 변환합니다.  
  
-   **특정 문화권을 사용하는 변환.** 각 숫자 개체에는 숫자를 문자열로 변환하는 `ToString(IFormatProvider)` 메서드와 문자열을 숫자로 변환하는 `Parse(String, IFormatProvider)` 메서드가 있습니다.  예를 들어, `Double` 형식은 <xref:System.Double.ToString%28System.IFormatProvider%29> 및 <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> 메서드를 제공합니다.  
  
 자세한 내용은 <xref:Microsoft.VisualBasic.Conversion.Str%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Val%2A>을 참조하십시오.  
  
## 특정 문화권 사용  
 문자열로 형식이 지정된 날짜를 웹 서비스로 보내는 응용 프로그램을 개발하는 경우를 가정합니다.  이 경우 응용 프로그램에서는 문자열 변환에 특정 문화권을 사용해야 합니다.  날짜의 <xref:System.DateTime.ToString> 메서드 사용 결과를 검토해 보면 그 이유를 알 수 있습니다. 응용 프로그램에서 이 메서드를 사용하여 2005년 7월 4일 날짜의 형식을 지정하는 경우 영어\(미국\)\(en\-US\) 문화권으로 실행될 때는 "7\/4\/2005 12:00:00 AM"이 반환되지만 독일어\(de\-DE\) 문화권으로 실행될 때는 "04.07.2005 00:00:00"이 반환됩니다.  
  
 특정 문화권 형식으로 문자열 변환을 수행해야 할 경우에는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]에 기본적으로 제공되는 `CultureInfo` 클래스를 사용해야 합니다.  문화권 이름을 <xref:System.Globalization.CultureInfo.%23ctor%2A> 생성자에 전달하여 특정 문화권에 대한 새 `CultureInfo` 개체를 만들 수 있습니다.  지원되는 문화권 이름은 <xref:System.Globalization.CultureInfo> 클래스 도움말 페이지에 나열되어 있습니다.  
  
 또는 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> 속성에서 *고정 문화권*의 인스턴스를 가져올 수 있습니다.  고정 문화권은 영어 문화권을 기준으로 하지만 몇 가지 차이점이 있습니다.  예를 들어 고정 문화권에서는 12시간 형식 대신 24시간 형식이 지정됩니다.  
  
 날짜를 문화권의 문자열로 변환하려면 <xref:System.Globalization.CultureInfo> 개체를 날짜 개체의 <xref:System.DateTime.ToString%28System.IFormatProvider%29> 메서드에 전달합니다.  예를 들어, 다음 코드에서는 응용 프로그램의 문화권 설정에 관계없이 "07\/04\/2005 00:00:00"이 표시됩니다.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/visualbasic/how-culture-affects-stri_1.vb)]  
  
> [!NOTE]
>  날짜 리터럴은 항상 영어 문화권에 따라 해석됩니다.  
  
## 문자열 비교  
 문자열을 비교해야 하는 중요한 상황은 다음 두 가지가 있습니다.  
  
-   **사용자에게 표시할 데이터 정렬.** 문자열이 제대로 정렬되도록 현재 문화권 기반의 작업을 사용합니다.  
  
-   **두 개의 응용 프로그램 내부 문자열이 정확하게 일치하는지 여부 확인\(일반적으로 보안 목적상\)** 현재 문화권을 무시하는 작업을 사용합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] <xref:Microsoft.VisualBasic.Strings.StrComp%2A> 함수를 사용하여 두 가지 비교를 수행할 수 있습니다.  선택적 `Compare` 인수를 지정하여 비교 형식을 제어합니다. 대부분의 입출력에는 `Text`를 사용하고, 정확한 일치를 확인하려면 `Binary`를 사용합니다.  
  
 `StrComp` 함수는 정렬 순서를 기반으로 하는 두 비교 문자열 간의 관계를 나타내는 정수를 반환합니다.  양수 결과 값은 첫째 문자열이 둘째 문자열보다 크다는 것을 나타냅니다.  음수 결과 값은 첫째 문자열이 작다는 것을 나타내고 0은 두 문자열이 같음을 나타냅니다.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-culture-affects-stri_2.vb)]  
  
 또한 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)]에서는 `StrComp` 함수에 해당하는 <xref:System.String.Compare%2A?displayProperty=fullName> 메서드를 사용할 수 있습니다.  이것은 기본 문자열 클래스의 오버로드된 정적 메서드입니다.  다음 예제에서는 이 메서드가 사용되는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/visualbasic/how-culture-affects-stri_3.vb)]  
  
 비교를 수행하는 방법을 보다 세밀하게 제어하려는 경우 <xref:System.String.Compare%2A> 메서드의 추가 오버로드를 사용할 수 있습니다.  <xref:System.String.Compare%2A?displayProperty=fullName> 메서드에는 `comparisonType` 인수를 사용하여 수행할 비교 형식을 지정할 수 있습니다.  
  
||||  
|-|-|-|  
|`comparisonType` 인수의 값|비교 형식|용도|  
|`Ordinal`|문자열의 구성 요소 바이트를 기반으로 하는 비교|대\/소문자를 구분하는 식별자, 보안 관련 설정 또는 바이트가 정확하게 일치해야 하는 그 밖의 비언어 식별자를 비교할 때 이 값을 사용합니다.|  
|`OrdinalIgnoreCase`|문자열의 구성 요소 바이트를 기반으로 하는 비교<br /><br /> `OrdinalIgnoreCase`에서는 고정 문화권 정보를 사용하여 두 개의 문자가 대\/소문자만 다른 경우를 확인합니다.|대\/소문자를 구분하지 않는 식별자, 보안 관련 설정 및 Windows에 저장된 데이터를 비교할 때 이 값을 사용합니다.|  
|`CurrentCulture`또는 `CurrentCultureIgnoreCase`|현재 문화권으로 해석된 문자열을 기반으로 하는 비교|사용자에게 표시되는 데이터, 대부분의 사용자 입력 및 언어 해석이 필요한 그 밖의 데이터를 비교할 때 이러한 값을 사용합니다.|  
|`InvariantCulture`또는 `InvariantCultureIgnoreCase`|고정 문화권으로 해석된 문자열을 기반으로 하는 비교<br /><br /> 이 경우 고정 문화권은 허용 범위 밖의 문자를 동일한 고정 문자로 처리하므로 `Ordinal` 및 `OrdinalIgnoreCase`와는 다릅니다.|지속되는 데이터를 비교하거나 고정된 정렬 순서가 필요한 언어적으로 관련된 데이터를 표시할 때만 이러한 값을 사용합니다.|  
  
### 보안 고려 사항  
 응용 프로그램에서 비교 또는 대\/소문자 변경 작업의 결과에 따라 보안을 결정하는 경우 작업에 <xref:System.String.Compare%2A?displayProperty=fullName> 메서드를 사용하고 `comparisonType` 인수에 `Ordinal` 또는 `OrdinalIgnoreCase`를 전달해야 합니다.  
  
## 참고 항목  
 <xref:System.Globalization.CultureInfo>   
 [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [Type Conversion Functions](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)