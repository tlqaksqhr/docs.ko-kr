---
title: "수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedure arguments
- arguments [Visual Basic], nonmodifiable
- Visual Basic code, procedures
- arguments [Visual Basic], modifiable
ms.assetid: 87b2df69-e1f7-4657-9caf-b3f48d693428
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab108d064f5c6740f80328a9b6db4785334550ca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="differences-between-modifiable-and-nonmodifiable-arguments-visual-basic"></a>수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점(Visual Basic)
프로시저를 호출 하는 경우 일반적으로에 하나 이상의 인수를 전달 합니다. 각 인수는 기본 프로그래밍 요소에 해당합니다. 기본 요소와 인수 자체 수정 가능 하거나 수정할 수 있습니다.  
  
## <a name="modifiable-and-nonmodifiable-elements"></a>수정할 수 있는 인수와 수정할 수 없는 요소  
 프로그래밍 요소는 일 수 있습니다는 *수정할 수 있는 요소*, 변경, 해당 값을 사용할 수 있는 또는 *수정할 수 없는 요소*에 고정된 값이 있는 만들어진 후 합니다.  
  
 다음 표에서 수정할 수 있는 인수와 수정할 수 없는 프로그래밍 요소를 나열합니다.  
  
|수정할 수 있는 요소|수정할 수 없는 요소|  
|-------------------------|----------------------------|  
|지역 변수 (프로시저 내에 선언 됨), 읽기 전용 제외 개체 변수를 포함 하 여|읽기 전용 변수, 필드 및 속성|  
|읽기 전용 제외 필드 (모듈, 클래스 및 구조체의 멤버 변수)|상수 및 리터럴|  
|읽기 전용 제외 속성|열거형 멤버|  
|배열 요소|식 (해당 요소를 수정할 수 있는 경우에)|  
  
## <a name="modifiable-and-nonmodifiable-arguments"></a>수정할 수 있는 인수와 인수  
 A *수정할 수 있는 인수* 는 수정할 수 없는 내부 요소를 포함 된 인수입니다. 호출 코드에서 언제 든 지 새 값을 저장할 수는 인수를 전달 하는 경우 및 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), 절차의 코드 호출 코드에서 기본 요소를 수정할 수 있습니다.  
  
 A *수정할 수 없는 인수* 는 수정할 수 없는 내부 요소 또는 전달 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다. 수정 가능한 요소인 것 이며 경우에 프로시저에서 호출 코드에서 해당 요소를 수정할 수 없습니다. 수정할 수 없는 요소는 호출 코드 자체 수정할 수 없습니다.  
  
 호출된 된 프로시저 수정 호출 코드에서 해당 요소에는 영향을 주지 있지만 수정할 수 없는 인수의 자체 로컬 복사본을 수정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)  
 [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)  
 [인수를 값으로 전달할 때와 참조로 전달할 때의 차이점](./differences-between-passing-an-argument-by-value-and-by-reference.md)  
 [방법: 프로시저 인수의 값 변경](./how-to-change-the-value-of-a-procedure-argument.md)  
 [방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)  
 [방법: 인수가 값으로 전달되도록 설정](./how-to-force-an-argument-to-be-passed-by-value.md)  
 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)  
 [값 형식과 참조 형식](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
