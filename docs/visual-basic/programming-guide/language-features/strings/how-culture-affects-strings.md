---
title: "문화권 Visual Basic의 문자열에 미치는 영향 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- locale, effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: 20
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 63228a40897b29d0324be73ca1a17bcb19af2a16
ms.lasthandoff: 03/13/2017

---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Visual Basic에서 문화권이 문자열에 영향을 주는 방식
이 도움말 페이지에 설명 방식을 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문화권 문자열 변환과 비교를 수행 하는 정보를 사용 합니다.  
  
## <a name="when-to-use-culture-specific-strings"></a>문화권 관련 문자열을 사용 하는 경우  
 일반적으로에 게 표시 하는 모든 데이터에 대 한 문화권 관련 문자열을 사용 하 고, 사용자에 게 읽고 해야 응용 프로그램의 내부 데이터에 대 한 고정 문화권 문자열을 사용 합니다.  
  
 예를 들어, 응용 프로그램 사용자가 날짜를 문자열로 입력을 요청 하는 경우 해당 문화권에 따라 문자열의 서식을 지정 하려면 사용자가 예상 해야 하 고 응용 프로그램은 문자열을 적절 하 게 변환 해야 합니다. 응용 프로그램의 사용자 인터페이스에서 해당 날짜를 사용 하는 경우 사용자의 culture에 제공 되어야 합니다.  
  
 그러나 날짜 중앙 서버에 업로드 하는 응용 프로그램을 하는 경우 형식을 지정 해야 여러 가지 날짜 형식 사이의 혼동을 방지 하기 위해 하나의 특정 문화권에 따라 문자열입니다.  
  
## <a name="culture-sensitive-functions"></a>문화권 구분 기능  
 모든는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 문자열 변환 함수 (제외 하 고는 `Str` 및 `Val` 함수) 응용 프로그램의 culture 정보를 사용 하 여 변환과 비교가 응용 프로그램의 사용자의 문화권에 대 한 적절 하 게 되도록 합니다.  
  
 키를 성공적으로 문자열 변환 함수를 사용 하 여 다른 culture 설정 사용 하 여 컴퓨터에서 실행 되는 응용 프로그램에서 현재 문화권 설정을 사용 하 고 함수를 사용 하 여 특정 문화권 설정을 이해 하는 것입니다. 응용 프로그램의 culture 설정, 기본적으로에서 상속 된다는 것 운영 체제의 culture 설정을 확인 합니다. 자세한 내용은 참조 <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>, <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, 및 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md).</xref:Microsoft.VisualBasic.Conversion.Oct%2A> </xref:Microsoft.VisualBasic.Conversion.Hex%2A> </xref:Microsoft.VisualBasic.Strings.Format%2A> </xref:Microsoft.VisualBasic.Strings.ChrW%2A> </xref:Microsoft.VisualBasic.Strings.Chr%2A> </xref:Microsoft.VisualBasic.Strings.AscW%2A> </xref:Microsoft.VisualBasic.Strings.Asc%2A>  
  
 `Str` (숫자를 문자열로 변환) 및 `Val` 문자열 및 숫자를 변환할 때 (변환 문자열을 숫자로) 함수는 응용 프로그램의 culture 정보를 사용 하지 않습니다. 대신, 마침표 (.)만 유효한 소수 구분 기호로 인식합니다. 이러한 함수의 문화권 인식 유사한 점은 다음과 같습니다.  
  
-   **현재 문화권을 사용 하는 변환입니다.** `CStr` 및 `Format` 함수는 숫자를 문자열로 변환 및 `CDbl` 및 `CInt` 함수는 문자열을 숫자로 변환 합니다.  
  
-   **특정 문화권을 사용 하는 변환입니다.** 각 숫자 개체에는 `ToString(IFormatProvider)` 숫자를 문자열로 변환 하는 메서드 및 `Parse(String, IFormatProvider)` 문자열을 숫자로 변환 하는 메서드입니다. 예를 들어는 `Double` 형식은 제공는 <xref:System.Double.ToString%28System.IFormatProvider%29>및 <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>메서드.</xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> </xref:System.Double.ToString%28System.IFormatProvider%29>  
  
 자세한 내용은 <xref:Microsoft.VisualBasic.Conversion.Str%2A>및 <xref:Microsoft.VisualBasic.Conversion.Val%2A>.</xref:Microsoft.VisualBasic.Conversion.Val%2A> </xref:Microsoft.VisualBasic.Conversion.Str%2A> 를 참조 하십시오.  
  
## <a name="using-a-specific-culture"></a>특정 문화권을 사용 하 여  
 날짜 (문자열 형식)는 웹 서비스에 전송 하는 응용 프로그램를 개발 하는 경우를 가정해 보겠습니다. 이 경우 응용 프로그램 문자열 변환에 대 한 특정 문화권을 사용 해야 합니다. 그 이유를 보여 주기 위해 날짜의를 사용 하 여 결과 고려해 보십시오. <xref:System.DateTime.ToString>메서드: 응용 프로그램에서 해당 메서드를 사용 하 여 2005 년 7 월 4 일 날짜를 반환 "2005 년 7 월 4 일 오전 12시: 00" 미국 영어 (EN-US) culture로 실행 하면 반환 되지만 "04.07.2005 00시: 00" 독일어 (DE) culture로 실행 하면.</xref:System.DateTime.ToString>  
  
 특정 문화권 형식으로 문자열 변환을 수행 해야 할 때 사용 해야는 `CultureInfo` 에 기본 제공 되는 클래스는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]합니다. 새를 만들 수 있습니다 `CultureInfo` 문화권의 이름을 전달 하 여 특정 문화권에 대 한 개체는 <xref:System.Globalization.CultureInfo.%23ctor%2A>생성자.</xref:System.Globalization.CultureInfo.%23ctor%2A> 에 지원 되는 문화권 이름이 나열 되는 <xref:System.Globalization.CultureInfo>클래스 도움말 페이지.</xref:System.Globalization.CultureInfo>  
  
 인스턴스를 가져올 수 또는 *고정 문화권* 에서 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName>속성.</xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=fullName> 고정 문화권은 영어 culture를 기반으로 하지만 일부의 차이점이 있습니다. 예를 들어, 고정 문화권 12 시간제 대신 24 시간 형식을 지정합니다.  
  
 문화권의 문자열에 날짜를 변환, 전달 된 <xref:System.Globalization.CultureInfo>날짜 개체의 개체 <xref:System.DateTime.ToString%28System.IFormatProvider%29>메서드.</xref:System.DateTime.ToString%28System.IFormatProvider%29> </xref:System.Globalization.CultureInfo> 예를 들어 다음 코드 표시 "07/04/2005 00시: 00" 응용 프로그램의 문화권 설정에 관계 없이 합니다.  
  
 [!code-vb[VbVbalrConcepts #&1;](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  날짜 리터럴은 영어 culture에 따라 항상 해석 됩니다.  
  
## <a name="comparing-strings"></a>문자열 비교  
 다음 두 가지 중요 한 경우 문자열 비교 해야 하는 위치:  
  
-   **사용자에 게 표시할 데이터를 정렬 합니다.** 문자열이 적절 하 게 정렬 되도록 현재 문화권에 따라 작업을 사용 합니다.  
  
-   **두 응용 프로그램 내부 문자열 (일반적으로 보안을 위해) 정확 하 게 일치 하는 경우를 결정 합니다.** 현재 문화권을 무시 하는 작업을 사용 합니다.  
  
 두 가지 유형의 비교 하는 작업을 수행할 수는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] <xref:Microsoft.VisualBasic.Strings.StrComp%2A>함수.</xref:Microsoft.VisualBasic.Strings.StrComp%2A> 선택적 지정 `Compare` 비교 유형을 제어 하는 인수: `Text` 대부분의 입력 및 출력에 대 한 `Binary` 정확히 일치 하는 결정 합니다.  
  
 `StrComp` 함수는 정렬 순서를 기반으로 하는 두 비교 문자열 간의 관계를 나타내는 정수를 반환 합니다. 결과 대 한 양수 값을 첫 번째 문자열이 두 번째 문자열 보다 큰 임을 나타냅니다. 음수 결과 첫 번째 문자열이 작다는 것을 나타내고&0;은 문자열이 같은지를 나타냅니다.  
  
 [!code-vb[VbVbalrStrings #&22;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 사용할 수도 있습니다는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] 의 파트너는 `StrComp` 함수는 <xref:System.String.Compare%2A?displayProperty=fullName>메서드.</xref:System.String.Compare%2A?displayProperty=fullName> 이 기본 string 클래스의 정적, 오버 로드 된 메서드입니다. 다음 예제에서는이 메서드를 사용 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStrings #&48;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 비교를 수행 하는 방법을 보다 세부적으로 제어에 대 한 추가 오버 로드를 사용할 수 있습니다는 <xref:System.String.Compare%2A>메서드.</xref:System.String.Compare%2A> 와 <xref:System.String.Compare%2A?displayProperty=fullName>사용할 수는 `comparisonType` 인수를 사용 하 여 비교 형식을 지정 합니다.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
|에 대 한 값 `comparisonType` 인수|비교의 유형|사용 시기|  
|---|---|---|  
|`Ordinal`|문자열의 구성 요소 (바이트)에 따라 비교 합니다.|이 값을 비교할 때 사용 하 여: 대/소문자 구분 식별자, 보안 관련 설정 또는 다른 비 언어적 식별자 바이트 정확히 일치 해야 합니다.|  
|`OrdinalIgnoreCase`|문자열의 구성 요소 (바이트)에 따라 비교 합니다.<br /><br /> `OrdinalIgnoreCase`고정 문화권 정보를 사용 하 여 두 문자를 대/소문자만 다 시기를 결정 합니다.|이 값을 비교할 때 사용 하 여: 대/소문자 구분 식별자, 보안 관련 설정 및 Windows에 저장 된 데이터입니다.|  
|`CurrentCulture` 또는 `CurrentCultureIgnoreCase`|현재 문화권에서 해석 된 문자열에 따라 비교 합니다.|이러한 값을 비교할 때 사용 하 여: 사용자, 대부분의 사용자 입력 언어 해석이 필요한 기타 데이터에 표시 되는 데이터입니다.|  
|`InvariantCulture` 또는 `InvariantCultureIgnoreCase`|고정 문화권에 해석 된 문자열에 따라 비교 합니다.<br /><br /> 이와 `Ordinal` 및 `OrdinalIgnoreCase`고정 문화권 해당 고정 문자로 취급 하는 허용 되는 범위를 벗어난 문자 때문에 있습니다.|고정된 된 정렬 순서가 필요한 비교 데이터를 유지 하거나 언어적으로 관련 된 데이터를 표시 하는 경우에 이러한 값을 사용 합니다.|  
  
### <a name="security-considerations"></a>보안 고려 사항  
 비교 또는 대/소문자 변경 작업의 결과에 따라 보안 결정을 수행 하는 응용 프로그램이 다음 작업을 사용 해야는 <xref:System.String.Compare%2A?displayProperty=fullName>메서드와 패스 `Ordinal` 또는 `OrdinalIgnoreCase` 에 대 한는 `comparisonType` 인수.</xref:System.String.Compare%2A?displayProperty=fullName>  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Globalization.CultureInfo></xref:System.Globalization.CultureInfo>   
 [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)   
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
