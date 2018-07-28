---
title: Visual Basic에서 문화권이 문자열에 영향을 주는 방식
ms.date: 07/20/2015
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
ms.openlocfilehash: 41fd612695fbeacbc7b53cb9e5dbf67939e73482
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332602"
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>Visual Basic에서 문화권이 문자열에 영향을 주는 방식
이 도움말 페이지는 Visual Basic 문자열 변환과 비교를 수행 하려면 문화권 정보를 사용 하는 방법을 설명 합니다.  
  
## <a name="when-to-use-culture-specific-strings"></a>문화권 관련 문자열을 사용 하는 경우  
 일반적으로 제공 하는 모든 데이터에 대 한 문화권 관련 문자열을 사용 하 고, 사용자에 게 읽고 해야 고정 문화권 문자열을 사용 하 여 응용 프로그램의 내부 데이터에 대 한.  
  
 예를 들어, 응용 프로그램 사용자가 문자열로 날짜를 입력 하도록 요청 하면 예상 해야 합니다. 해당 문화권에 따라 문자열의 서식을 지정 하는 사용자 및 응용 프로그램 문자열을 적절 하 게 변환 해야 합니다. 응용 프로그램의 사용자 인터페이스에서 해당 날짜를 사용 하는 경우 사용자의 문화권에서 제공 되어야 합니다.  
  
 그러나 날짜 중앙 서버에 업로드 하는 응용 프로그램을 하는 경우 형식을 지정 해야 잠재적으로 서로 다른 날짜 형식 간에 혼동을 방지 하려면 하나의 특정 문화권에 따라 문자열입니다.  
  
## <a name="culture-sensitive-functions"></a>문화권 구분 함수  
 모든 Visual Basic 문자열 변환 함수 (제외 합니다 `Str` 및 `Val` 함수) 응용 프로그램의 culture 정보를 사용 하 여 변환 및 비교는 해당 응용 프로그램의 문화권에 맞게 되도록 사용자입니다.  
  
 성공적으로 다른 문화권 설정 사용 하 여 컴퓨터에서 실행 되는 응용 프로그램에서 문자열 변환 함수를 사용 하는 핵심은 함수는 특정 문화권 설정을 사용 하면와 현재 문화권 설정을 사용 하는 이해 하는 것입니다. 응용 프로그램의 문화권 설정에 기본적으로에서 상속 됨 운영 체제의 culture 설정을 확인 합니다. 자세한 내용은 <xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>, <xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>, <xref:Microsoft.VisualBasic.Strings.Format%2A>를 <xref:Microsoft.VisualBasic.Conversion.Hex%2A>, <xref:Microsoft.VisualBasic.Conversion.Oct%2A>, 및 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.  
  
 합니다 `Str` (숫자를 문자열로 변환) 및 `Val` 문자열 및 숫자 간에 변환 하는 경우 (변환 문자열을 숫자로) 함수에서는 응용 프로그램의 culture 정보를 넣지 마십시오. 대신, 마침표 (.)만 유효한 소수 구분 기호로 인식합니다. 이러한 함수의 문화권 인식에서 유사한 점은 다음과 같습니다.  
  
-   **현재 문화권을 사용 하는 변환입니다.** `CStr` 하 고 `Format` 함수는 문자열을 숫자로 변환할 하며 `CDbl` 및 `CInt` 함수는 문자열을 숫자로 변환 합니다.  
  
-   **특정 문화권을 사용 하는 변환입니다.** 각 숫자 개체에는 `ToString(IFormatProvider)` 문자열을 숫자로 변환 하는 메서드 및 `Parse(String, IFormatProvider)` 메서드는 문자열을 숫자로 변환 합니다. 예를 들어 합니다 `Double` 형식을 제공 합니다 <xref:System.Double.ToString%28System.IFormatProvider%29> 및 <xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29> 메서드.  
  
 자세한 내용은 <xref:Microsoft.VisualBasic.Conversion.Str%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Val%2A>를 참조하세요.  
  
## <a name="using-a-specific-culture"></a>특정 문화권을 사용 하 여  
 웹 서비스 (문자열로 서식이 지정 된) 날짜를 전송 하는 응용 프로그램을 개발 하는 경우를 가정해 보겠습니다. 이 경우 응용 프로그램에서는 문자열 변환에 대 한 특정 문화권을 사용 해야 합니다. 이유를 보여 주기 위해 날짜의를 사용 하 여 결과 고려해 보십시오. <xref:System.DateTime.ToString> 메서드: 응용 프로그램에서 해당 메서드를 사용 하 여 2005 년 7 월 4 일 날짜를 반환 합니다 "2005 년 7 월 4 일 오전 12시: 00" 미국 영어 (EN-US) 문화권을 사용 하 여 실행 하는 경우 반환 되지만 " 04.07.2005 00시: 00 "독일어 (DE-DE) 문화권을 사용 하 여 실행 하는 경우.  
  
 특정 문화권 형태로 문자열 변환을 수행 해야 하는 경우 사용 해야 합니다 `CultureInfo` 클래스에 기본 제공 되는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]합니다. 새로 만들 수 있습니다 `CultureInfo` 문화권의 이름을 전달 하 여 특정 문화권에 대 한 개체는 <xref:System.Globalization.CultureInfo.%23ctor%2A> 생성자입니다. 지원 되는 문화권 이름에 나열 됩니다는 <xref:System.Globalization.CultureInfo> 클래스 도움말 페이지입니다.  
  
 인스턴스를 가져올 수 있습니다 또는 합니다 *고정 문화권* 에서 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 속성입니다. 고정 문화권은 영어 문화권을 기반으로 하지만 일부의 차이점이 있습니다. 예를 들어, 고정 문화권 12 시간제를 대신 24 시간 시계를 지정합니다.  
  
 문화권의 문자열에 날짜를 변환, 전달 된 <xref:System.Globalization.CultureInfo> 날짜 개체의 개체 <xref:System.DateTime.ToString%28System.IFormatProvider%29> 메서드. 예를 들어, 다음 코드에서는 "2005-07-04 00시: 00" 응용 프로그램의 문화권 설정에 관계 없이 합니다.  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  날짜 리터럴은 항상 영어 culture에 따라 해석 됩니다.  
  
## <a name="comparing-strings"></a>문자열 비교  
 다음 두 가지 중요 한 경우 문자열 비교 해야 하는 위치:  
  
-   **사용자에 게 표시할 데이터를 정렬 합니다.** 문자열이 제대로 정렬 되므로 현재 문화권에 따라 작업을 사용 합니다.  
  
-   **두 응용 프로그램 내부 문자열 (일반적으로 보안을 위해) 정확히 일치 하는 경우를 결정 합니다.** 현재 문화권을 무시 하는 작업을 사용 합니다.  
  
 두 가지 유형의 Visual Basic을 사용한 비교를 수행할 수 있습니다 <xref:Microsoft.VisualBasic.Strings.StrComp%2A> 함수입니다. 선택적 지정 `Compare` 비교의 형식을 제어 하는 인수: `Text` 대부분의 입력 및 출력에 대 한 `Binary` 정확히 일치를 확인 합니다.  
  
 `StrComp` 정렬 순서를 기반으로 하는 두 비교 문자열 간의 관계를 나타내는 정수를 반환 합니다. 결과 대 한 양수 값을 첫 번째 문자열이 두 번째 문자열 보다 크면 임을 나타냅니다. 음수 결과 첫 번째 문자열은 작은 나타내고 0 문자열이 같은지를 나타냅니다.  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 사용할 수도 있습니다는 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 의 파트너는 `StrComp` 함수를 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드. 이것이 기본 string 클래스의 정적, 오버 로드 된 방법입니다. 다음 예제에서는이 메서드를 사용 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 비교를 수행 하는 방법 보다 세부적으로 제어에 대 한 추가 오버 로드를 사용할 수 있습니다는 <xref:System.String.Compare%2A> 메서드. 사용 하 여 합니다 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드를 사용할 수는 `comparisonType` 사용할 비교 형식을 지정 하는 인수입니다.  
  
|에 대 한 값 `comparisonType` 인수|비교 유형|사용 시기|  
|---|---|---|  
|`Ordinal`|문자열의 구성 요소 바이트에 따라 비교 합니다.|이 값을 비교할 때 사용 합니다: 대/소문자 구분 식별자, 보안 관련 설정 또는 기타 비 언어적 식별자 바이트 수를 정확 하 게 일치 해야 합니다.|  
|`OrdinalIgnoreCase`|문자열의 구성 요소 바이트에 따라 비교 합니다.<br /><br /> `OrdinalIgnoreCase` 두 문자 대/소문자만 다른 시기를 결정 하는 고정 문화권 정보를 사용 합니다.|이 값을 비교할 때 사용 합니다: 대/소문자 식별자, 보안 관련 설정 및 Windows에 저장 된 데이터입니다.|  
|`CurrentCulture` 또는 `CurrentCultureIgnoreCase`|현재 문화권의 문자열 해석에 따라 비교 합니다.|이러한 값을 비교할 때 사용할: 사용자, 대부분의 사용자 입력 및 언어적 해석 해야 하는 기타 데이터에 표시 되는 데이터입니다.|  
|`InvariantCulture` 또는 `InvariantCultureIgnoreCase`|고정 문화권에서 문자열 해석에 따라 비교 합니다.<br /><br /> 이 다른 합니다 `Ordinal` 및 `OrdinalIgnoreCase`고정 문화권은 허용 된 범위를 벗어나는 문자가 해당 고정 문자로 취급 하므로, 합니다.|고정된 정렬 순서가 필요한 비교 데이터를 유지 하거나 언어적으로 관련 된 데이터를 표시 하는 경우에 이러한 값을 사용 합니다.|  
  
### <a name="security-considerations"></a>보안 고려 사항  
 응용 프로그램에서 비교 또는 대/소문자 변경 작업의 결과에 따라 보안 결정 다음 작업을 사용 해야 합니다 <xref:System.String.Compare%2A?displayProperty=nameWithType> 메서드를 통과 `Ordinal` 또는 `OrdinalIgnoreCase` 에 대 한는 `comparisonType` 인수입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Globalization.CultureInfo>  
 [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [형식 변환 함수](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
