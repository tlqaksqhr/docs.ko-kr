---
title: "방법: (Visual Basic) 코드에서 문 분리 및 결합 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb._
dev_langs:
- VB
helpviewer_keywords:
- colons (:)
- line continuation
- _ line-continuation character
- ': line separator character'
- Visual Basic code, line breaks in
- Visual Basic code, line breaks
- Visual Basic code, line continuation
- long lines of code
- line terminator
- line-continuation sequence
- underscores, in code
- statements [Visual Basic], line continuation in
- line breaks, in code
- line-continuation character
- Visual Basic code, line continuation in
- statements [Visual Basic], line breaks in
ms.assetid: dea01dad-a8ac-484a-bb3a-8c45a1b1eccc
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 840036a91f430f72e0258b8be466770f2855a58f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-break-and-combine-statements-in-code-visual-basic"></a>방법: 코드에서 문 분리 및 결합(Visual Basic)
코드를 작성할 때 코드 편집기에서 가로로 스크롤하면 볼 수 있는 긴 문을 시간에 만들 수 있습니다. 방식에 영향을 주지 않지만 코드를 실행, 하기 어렵습니다 사용자나 다른 사람이 모니터에 표시 된 대로 코드를 읽는 합니다. 이러한 경우 긴 문은 여러 줄으로 분리를 고려해 야 합니다.  
  
### <a name="to-break-a-single-statement-into-multiple-lines"></a>단일 문에 여러 줄으로 중단 하려면  
  
-   밑줄 줄 연속 문자를 사용 하 여 (`_`), 줄을 지점입니다. 밑줄 바로 앞에는 공백이 오고 바로 뒤에는 줄 종결자(캐리지 리턴)가 와야 합니다.  
  
    > [!NOTE]
    >  경우에 따라 줄 연속 문자를 생략 하면 Visual Basic 컴파일러는 암시적으로 문을 계속 코드의 다음 줄에 있습니다. 줄 연속 문자를 생략할 수 있는 구문 요소 목록은 "암시적 줄 연속 문자"의 참조 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.  
  
     다음 예제에서는 문이 마지막 줄을 제외한 모든 줄 연속 문자로 네 줄으로 분리 합니다.  
  
     [!code-vb[VbVbcnConventions #&20;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_1.vb)]  
  
     이 시퀀스를 사용 하 여 하면 온라인 및 때 인쇄 코드를 쉽게 읽을 수 있습니다.  
  
     줄 연속 문자에는 줄에서 마지막 문자 여야 합니다. 같은 줄에 언제나 그렇듯 쓸 수 없습니다.  
  
     줄 연속 문자입니다; 사용할 수 있는 대 한 몇 가지 제한 사항이 예를 들어 중간 인수 이름에 사용할 수 없습니다. 줄 연속 문자를 인수 목록을 분리할 수 있지만 개별 인수 이름에는 그대로 유지 해야 합니다.  
  
     줄 연속 문자를 사용 하 여 메모를 계속할 수 없습니다. 컴파일러의 특별 한 의미에 대 한 주석 문자를 검사 하지 않습니다. 주석이 여러 행에 대 한 반복 주석 기호 (`'`) 각 줄에 있습니다.  
  
 일반적으로 각 문을 별도 줄에는 권장된 방법 이지만 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 같은 줄에 여러 개의 문을 배치할 수 있습니다.  
  
### <a name="to-place-multiple-statements-on-the-same-line"></a>여러 개의 문을 같은 줄에 배치 하려면  
  
-   각 문을 콜론 (`:`) 다음 예제와 같이 합니다.  
  
     [!code-vb[VbVbcnConventions #&10;](../../../visual-basic/programming-guide/language-features/codesnippet/VisualBasic/how-to-break-and-combine-statements-in-code_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [문](../../../visual-basic/programming-guide/language-features/statements.md)
