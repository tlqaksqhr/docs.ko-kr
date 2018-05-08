---
title: Visual Basic에서 MaskedTextBox 컨트롤과 함께 정규식 사용
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: afc19ccf476317e8c30a1cc6964c64f1a59a0ff8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>Visual Basic에서 MaskedTextBox 컨트롤과 함께 정규식 사용
단순 정규식 작업을 변환 하는 방법을 보여 주는이 예제는 <xref:System.Windows.Forms.MaskedTextBox> 제어 합니다.  
  
## <a name="description-of-the-masking-language"></a>마스킹 언어 설명  
 표준 <xref:System.Windows.Forms.MaskedTextBox> 기반 마스킹 언어에서 사용 된 것으로는 `Masked Edit` Visual Basic 6.0에서 제어 하 고 해당 플랫폼에서 마이그레이션하는 사용자에 잘 알고 있어야 합니다.  
  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 의 속성은 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤 입력된 마스크를 사용 하 여 지정 합니다. / / 마스크에는 하나 이상의 다음 표에서 마스킹 요소로 구성 된 문자열 이어야 합니다.  
  
|요소를 마스킹|설명|정규식 요소|  
|---------------------|-----------------|--------------------------------|  
|0|0에서 9 사이의 임의의 단일 숫자입니다. 항목이 필요 합니다.|\d|  
|9|숫자 또는 공백이 있습니다. 선택적 항목입니다.|[\d]?|  
|#|숫자 또는 공백이 있습니다. 선택적 항목입니다. 이 위치에 정보를 마스크에 입력 하지 않으면 공간으로 렌더링 됩니다. 더하기 (+) 및 빼기 (-) 기호를 사용할 수 있습니다.|[\d+-]?|  
|L|ASCII 문자입니다. 항목이 필요 합니다.|[a-zA-Z]|  
|?|ASCII 문자입니다. 선택적 항목입니다.|[a-zA-Z]?|  
|&|문자. 항목이 필요 합니다.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|문자. 선택적 항목입니다.|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]?|  
|A|영숫자입니다. 선택적 항목입니다.|\W|  
|이어야 합니다.|10 진수 자리 표시자 culture에 따른입니다.|사용할 수 없습니다.|  
|,|Culture에 따른 천 단위 자리 표시자입니다.|사용할 수 없습니다.|  
|:|문화권에 적합 한 시간 구분 기호입니다.|사용할 수 없습니다.|  
|/|Culture에 따른 날짜 구분 기호입니다.|사용할 수 없습니다.|  
|$|Culture에 따른 통화 기호입니다.|사용할 수 없습니다.|  
|\<|모든 뒤에 있는 문자를 소문자로 변환 합니다.|사용할 수 없습니다.|  
|>|모든 뒤에 있는 문자를 대문자로 변환 합니다.|사용할 수 없습니다.|  
|&#124;|이전 shift를 실행 취소 또는 아래쪽으로 이동 합니다.|사용할 수 없습니다.|  
|\|클래스는 리터럴으로 변환 마스크 문자를 이스케이프 합니다. "\\\\" 백슬래시 이스케이프 시퀀스입니다.|\|  
|다른 모든 문자입니다.|리터럴입니다. 모든 비 마스크 요소가 내에 그대로 표시 되는 <xref:System.Windows.Forms.MaskedTextBox>합니다.|다른 모든 문자입니다.|  
  
 소수점 (.), 1/1000 (,), (:) 시간, 날짜 (/) 및 ($) 통화 기호 기본 응용 프로그램의 culture에 정의 된 대로 해당 기호를 표시 하도록 합니다. 다른 문화권에 대 한 기호를 사용 하 여 표시 되도록 할 수 있습니다는 <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> 속성입니다.  
  
## <a name="regular-expressions-and-masks"></a>정규식과 마스크  
 사용자를 사용할 수 있지만 정규식과 마스크 사용자 입력 유효성 검사를 완전히 동일 하지 않습니다. 정규식 마스크 보다 더 복잡 한 패턴을 표현할 수 있지만 더 간결 하 관련 형식으로 마스크에서 동일한 정보를 표현할 수 있습니다.  
  
 다음 표에서 각각에 대해 4 개의 정규식과 해당 하는 마스크를 비교 합니다.  
  
|정규식|마스크|노트|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|`/` 마스크의 문자에에서는 논리 날짜 구분 기호 이며 사용자에 게 응용 프로그램의 현재 문화권에 적합 한 날짜 구분 기호로 표시 됩니다.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|날짜 (예: 일, 월의 약어 및 연도) 미국 형식 뒤에 두 문자는 소문자 초기 대문자로 표시 되는 세 자리 월의 약어입니다.|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|미국 전화 번호, 지역 번호 선택 사항입니다. 사용자는 선택적 문자 입력을 원하지 않는, 그녀 공백을 입력 하거나 첫 번째 0이 나타나는 마스크에서 위치에 직접 마우스 포인터를 놓습니다.|  
|`$\d{6}.00`|`$999,999.00`|범위 0-999999에에서 통화 값입니다. 통화, 1/1000, 및 10 진수 문자는 해당 문화권별 형식으로 실시간으로 대체 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [Visual Basic의 문자열 유효성 검사](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)  
 [MaskedTextBox 컨트롤](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
