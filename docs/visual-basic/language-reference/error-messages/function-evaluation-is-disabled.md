---
title: "이전 함수 실행 시간이 초과 되었으므로 함수를 실행할 수 없습니다 | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
dev_langs:
- VB
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: 7
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
ms.openlocfilehash: b861b5c6c151c5d3aeec2810c7f2a228f22fdf6e
ms.lasthandoff: 03/13/2017

---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>이전 함수 실행 시간이 초과되었으므로 함수를 실행할 수 없습니다.
이전 함수 실행 시간이 초과 되었으므로 함수 실행 비활성화 됩니다. 함수 실행을 다시 활성화 하려면 다시 단계별로 실행 하거나 디버깅을 다시 시작 합니다.  
  
 Visual Studio 디버거는 프로시저 호출을 지정 하는 식이 되지만 또 다른 평가 시간이 초과 되었습니다.  
  
 무한 루프를 포함 하는 시간 제한 초과로 프로시저 호출에 대 한 가능한 원인 또는 *무한 루프*합니다. 자세한 내용은 참조 [에 대 한... 다음 문](../../../visual-basic/language-reference/statements/for-next-statement.md)합니다.  
  
 무한 루프의 특수 한 경우는 *재귀*합니다. 자세한 내용은 참조 [재귀 프로시저](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)합니다.  
  
 **오류 ID:** BC30957  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  가능 하면 이전 함수 실행 무슨 일 및 시간 제한 초과로 원인을 확인 합니다. 그렇지 않은 경우이 오류가 다시 발생할 수 있습니다.  
  
2.  디버거를 다시 실행 하거나 종료 하 고 디버깅을 다시 시작 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio의 디버깅](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)   
 [디버거로 코드 탐색](https://docs.microsoft.com/visualstudio/debugger/navigating-through-code-with-the-debugger)
