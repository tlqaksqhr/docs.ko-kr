---
title: Visual Basic의 문자열 조작 메서드 유형
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], manipulating [Visual Basic]
- string manipulation
ms.assetid: 905055cd-7f50-48fb-9eed-b0995af1dc1f
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3677c8a23e956716af4357fe79041fc96f4014f2
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="types-of-string-manipulation-methods-in-visual-basic"></a>Visual Basic의 문자열 조작 메서드 유형
분석 및 나 문자열을 조작 하는 여러 가지가 있습니다. 일부 메서드는 Visual Basic 언어의 일부 이며 다른 사용자에 내재 된는 `String` 클래스입니다.  
  
## <a name="visual-basic-language-and-the-net-framework"></a>Visual Basic 언어와.NET Framework  
 Visual Basic 메서드 언어의 기본 기능으로 사용 됩니다. 코드에서 자격 증명 없이 사용할 수 있습니다. 다음 예제에서는 Visual Basic 문자열 조작 명령의 일반적인 사용을 보여 줍니다.  
  
 [!code-vb[VbVbalrStrings#44](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_1.vb)]  
  
 이 예제는 `Mid` 함수에서 직접 연산을 수행 `aString` 값을 할당 하 고 `bString`합니다.  
  
 Visual Basic 문자열 조작 메서드 목록에 대 한 참조 [문자열 조작 요약](../../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)합니다.  
  
### <a name="shared-methods-and-instance-methods"></a>공유 메서드와 인스턴스 메서드  
 방법을 사용 하 여 문자열을 조작할 수도 있습니다는 `String` 클래스입니다. 메서드의 두 가지 `String`: *공유* 메서드 및 *인스턴스* 메서드.  
  
#### <a name="shared-methods"></a>공유 메서드  
 발생 하는 방법은 공유 메서드는 `String` 클래스 자체와 작동 하도록 해당 클래스의 인스턴스를 필요로 하지 않습니다. 이러한 메서드는 클래스의 이름으로 정규화 할 수 있습니다 (`String`)의 인스턴스 대신는 `String` 클래스입니다. 예를 들어:  
  
 [!code-vb[VbVbalrStrings#45](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_2.vb)]  
  
 앞의 예제에는 <xref:System.String.Copy%2A?displayProperty=nameWithType> 메서드는 정적 메서드는 식에 대해 동작 하는 것은 되며 결과 값을 할당 `bString`합니다.  
  
#### <a name="instance-methods"></a>인스턴스 메서드  
 인스턴스 메서드와 달리,의 특정 인스턴스에서 형태소 분석 `String` 및 인스턴스 이름으로 한정 되어야 합니다. 예를 들어:  
  
 [!code-vb[VbVbalrStrings#46](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/types-of-string-manipulation-methods_3.vb)]  
  
 이 예제는 <xref:System.String.Substring%2A?displayProperty=nameWithType> 메서드는 인스턴스 메서드 `String` (즉, `aString`). 에 작업을 수행할 `aString` 해당 값을 할당 하 고 `bString`합니다.  
  
 자세한 내용은 참조에 대 한 설명서는 <xref:System.String> 클래스입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 문자열 소개](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
