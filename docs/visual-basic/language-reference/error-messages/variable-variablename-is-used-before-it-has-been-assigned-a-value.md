---
title: 변수 &#39; &lt;variablename&gt;&#39; 값이 할당 되기 전에 사용 되었습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42104
- BC42104
helpviewer_keywords:
- BC42104
ms.assetid: 6909aa0b-b4a1-46f5-a18c-ba3e565c1dd8
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 201667c250e15bb9af73e64e2d8c924c1952d1be
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="variable-39ltvariablenamegt39-is-used-before-it-has-been-assigned-a-value"></a>변수 &#39; &lt;variablename&gt;&#39; 값이 할당 되기 전에 사용 되었습니다.
변수 '\<variablename >' 값이 할당 되기 전에 사용 되었습니다. 런타임에 null 참조 예외가 발생할 수 있습니다.  
  
 응용 프로그램에 코드 값을 할당 하기 전에 변수를 읽는 통해 하나 이상의 경로가 있습니다.  
  
 변수에 값이 할당되지 않으면 해당 데이터 형식에 대한 기본값을 유지합니다. 참조 데이터 형식에 대 한 해당 기본값은 [Nothing](../../../visual-basic/language-reference/nothing.md)합니다. 값이 `Nothing` 인 참조 변수를 읽으면 일부 환경에서 <xref:System.NullReferenceException> 이 발생할 수 있습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기 거 나 경고를 오류로 처리 하는 방법에 대 한 자세한 내용은 참조 하십시오. [Visual Basic에서 경고 구성](/visualstudio/ide/configuring-warnings-in-visual-basic)합니다.  
  
 **오류 ID:** b c 42104  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   제어 흐름 논리를 읽어온 문에 컨트롤이 전달 되기 전에 변수가 유효한 값이 있는지 확인 하십시오.  
  
-   변수 값이 올바른 값을 항상에 있는지를 보장 하기 위해 한 가지 방법은 해당 선언의 일부로 초기화 하는 것입니다. "초기화"를 참조 하십시오. [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)  
 [변수 선언](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [변수 문제 해결](../../../visual-basic/programming-guide/language-features/variables/troubleshooting-variables.md)
