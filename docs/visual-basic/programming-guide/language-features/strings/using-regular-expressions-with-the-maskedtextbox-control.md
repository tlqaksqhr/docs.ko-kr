---
title: "Using Regular Expressions with the MaskedTextBox Control in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "strings [Visual Basic], regular expressions"
  - "strings [Visual Basic], masked edit"
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Using Regular Expressions with the MaskedTextBox Control in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 예제에서는 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤을 사용하여 간단한 정규식을 변환하는 방법을 보여 줍니다.  
  
## 마스킹 언어 설명  
 표준 <xref:System.Windows.Forms.MaskedTextBox> 마스킹 언어는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 6.0의 `Masked Edit` 컨트롤에서 사용하는 마스킹 언어를 기반으로 하며 해당 플랫폼에서 마이그레이션하는 사용자는 이러한 마스킹 언어에 익숙해야 합니다.  
  
 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤의 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성은 사용할 입력 마스크를 지정합니다.  마스크는 다음 표에 나열된 하나 이상의 마스킹 요소로 구성된 문자열이어야 합니다.  
  
|마스킹 요소|설명|정규식 요소|  
|------------|--------|------------|  
|0|0에서 9 사이의 한 자리 수입니다.  필수적 항목입니다.|\\d|  
|9|숫자 또는 공백이며  선택적 항목입니다.|\[ \\d\]?|  
|\#|숫자 또는 공백이며  선택적 항목입니다.  마스크에서 이 위치가 비어 있으면 공백으로 렌더링됩니다.  더하기\(\+\) 및 빼기\(\-\) 기호를 사용할 수 있습니다.|\[ \\d\+\-\]?|  
|L|ASCII 문자이며  필수적 항목입니다.|\[a\-zA\-Z\]|  
|?|ASCII 문자이며  선택적 항목입니다.|\[a\-zA\-Z\]?|  
|&|Character  필수적 항목입니다.|\[\\p{Ll}\\p{Lu}\\p{Lt}\\p{Lm}\\p{Lo}\]|  
|C|Character  선택적 항목입니다.|\[\\p{Ll}\\p{Lu}\\p{Lt}\\p{Lm}\\p{Lo}\]?|  
|A|영숫자이며  선택적 항목입니다.|\\W|  
|.|Culture에 따른 소수 자리 표시자입니다.|사용할 수 없음|  
|,|Culture에 따른 1000 단위 자리 표시자입니다.|사용할 수 없음|  
|:|Culture에 따른 시간 구분 기호입니다.|사용할 수 없음|  
|\/|Culture에 따른 날짜 구분 기호입니다.|사용할 수 없음|  
|$|Culture에 따른 통화 기호입니다.|사용할 수 없음|  
|\<|다음에 나오는 모든 문자를 소문자로 변환합니다.|사용할 수 없음|  
|\>|뒤에 오는 문자를 모두 대문자로 변환합니다.|사용할 수 없음|  
|&#124;|이전의 위로 시프트 또는 아래로 시프트를 실행 취소합니다.|사용할 수 없음|  
|\\|마스크 문자를 이스케이프하여 리터럴로 전환합니다. 이때   "\\\\" 는 백슬래시에 대한 이스케이프 시퀀스입니다.|\\|  
|다른 모든 문자|리터럴이며  마스크가 아닌 모든 요소는 <xref:System.Windows.Forms.MaskedTextBox> 내에 그대로 나타납니다.|다른 모든 문자|  
  
 기본적으로 소수점\(.\), 1000 단위 구분\(,\), 시간\(:\), 날짜\(\/\) 및 통화 기호\($\)는 응용 프로그램의 culture에 정의된 대로 이들 기호가 표시됩니다.  <xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A> 속성을 사용하여 이들 기호를 다른 culture에 대한 기호로 표시할 수 있습니다.  
  
## 정규식 및 마스크  
 사용자 입력의 유효성을 검사하는 데 정규식 및 마스크를 사용할 수 있지만 정규식과 마스크는 서로 완전히 다릅니다.  정규식은 마스크보다 더 복잡한 패턴으로 표현할 수 있는 반면 마스크는 동일한 정보를 더 간결하게 culture에 맞는 관련 형식으로 표현할 수 있습니다.  
  
 다음 표에서는 네 가지 정규식과 이에 해당하는 마스크를 비교하여 보여 줍니다.  
  
|정규식|마스크|참고|  
|---------|---------|--------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|마스크에서 `/` 문자는 논리적 날짜 구분 기호이며 응용 프로그램의 현재 culture에 맞는 날짜 구분 기호로 사용자에게 표시됩니다.|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|미국식 날짜\(일, 월 약어 및 연도\) 표기 형식에서 세 문자로 된 월 약어의 첫 문자는 대문자로, 나머지 두 문자는 소문자로 입력합니다.|  
|`(\(\d{3}\)-)?  \d{3}-d{4}`|`(999)-000-0000`|미국 전화 번호로 지역 번호는 선택 사항입니다.  지역 번호를 입력하지 않으려면 공백을 입력하거나 첫 번째 0이 나타나는 마스크의 위치에 직접 마우스 포인터를 놓을 수 있습니다.|  
|`$\d{6}.00`|`$999,999.00`|0\-999999 범위의 통화 값입니다.  통화, 1000 단위 구분 및 소수점 문자는 런타임에 해당 문화권의 통화, 1000 단위 구분 및 소수점 문자로 대체됩니다.|  
  
## 참고 항목  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>   
 <xref:System.Windows.Forms.MaskedTextBox>   
 [Validating Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)   
 [MaskedTextBox 컨트롤](../Topic/MaskedTextBox%20Control%20\(Windows%20Forms\).md)