---
title: 스택 공간이 부족합니다(Visual Basic).
ms.date: 07/20/2015
f1_keywords:
- vbrID28
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
ms.openlocfilehash: e39be5913fe877cf7b3396e4f13f4440288cb8f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593287"
---
# <a name="out-of-stack-space-visual-basic"></a>스택 공간이 부족합니다(Visual Basic).
스택은 실행 프로그램의 요청으로 동적으로 증가 하 고 감소 하는 메모리의 작업 영역입니다. 해당 한도 초과 했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  프로시저 너무 깊게 중첩 되지 않은 것을 확인 합니다.  
  
2.  재귀 프로시저 올바르게 종료 되었는지 확인 합니다.  
  
3.  지역 변수 공간이 사용 가능한 것 보다 모듈 수준에서 일부 변수를 선언 해 봅니다. 또한 변수를 선언할 수 모든 절차에서 정적 앞는 `Property`, `Sub`, 또는 `Function` 키워드를 함께 `Static`합니다. 또는 사용할 수는 `Static` 문을 프로시저 내에서 개별 정적 변수를 선언 합니다.  
  
4.  고정 길이 문자열 가변 길이 문자열과 보다 더 많은 스택 공간을 사용 하 여 다양 한 길이의 문자열로 고정 길이 문자열의 일부를 재정의 합니다. 또한 스택 공간이 없으면 걸리는 모듈 수준에서 문자열을 정의할 수 있습니다.  
  
5.  개수를 검사할 중첩 `DoEvents` 함수 호출을 사용 하 여는 `Calls` 스택에 활성화 되어 있는 프로시저 보기로 대화 상자.  
  
6.  이미 스택에 이벤트 프로시저를 호출 하는 이벤트를 트리거하여 "이벤트 cascade"이 발생 하지 있는지 확인 합니다. 이벤트 cascade는 종료 되지 않았습니다. 재귀 프로시저 호출과 유사 하지만 호출 코드에서 명시적으로 호출 하지 않고 Visual Basic 있으므로 덜 명확 합니다. 사용 하 여는 `Calls` 스택에 활성화 되어 있는 프로시저 보기로 대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 창](/visualstudio/debugger/memory-windows)
