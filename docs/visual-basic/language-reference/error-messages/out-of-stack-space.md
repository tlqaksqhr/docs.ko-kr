---
title: "스택 공간이 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID28
dev_langs:
- VB
ms.assetid: bfcd792b-ac29-4158-81fc-ea0c13f4ffa2
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 6343767da28ea4e02f9443006b222640755f7882
ms.lasthandoff: 03/13/2017

---
# <a name="out-of-stack-space-visual-basic"></a>스택 공간이 부족합니다(Visual Basic).
실행 중인 프로그램의 요구와 동적으로 확장 및 축소 하는 메모리의 작업 영역 않습니다. 제한은 초과 했습니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  프로시저 너무 많이 중첩 되지 않은 것을 확인 합니다.  
  
2.  재귀 프로시저 올바르게 종료 해야 합니다.  
  
3.  지역 변수 공간이 사용 가능한 것 보다 모듈 수준에서 일부 변수를 선언 해 봅니다. 또한 변수를 선언할 수 모든 절차에서 정적 앞는 `Property`, `Sub`, 또는 `Function` 키워드를 함께 `Static`합니다. 또는 사용할 수는 `Static` 문을 프로시저 내에서 개별 정적 변수를 선언 합니다.  
  
4.  고정 길이 문자열 가변 길이 문자열 보다 더 많은 스택 공간을 사용 하 여 다양 한 길이의 문자열로 고정 길이 문자열의 일부를 재정의 합니다. 또한 모듈 수준 스택 공간이 없는 필요 위치에서 문자열을 정의할 수 있습니다.  
  
5.  수를 확인 하십시오 중첩 `DoEvents` 를 사용 하 여 함수 호출의 `Calls` 스택에 활성화 되어 있는 프로시저 보기 대화 상자입니다.  
  
6.  이미 스택에 이벤트 프로시저를 호출 하는 이벤트를 트리거하여 "이벤트 캐스케이딩"이 발생 하지 있는지 확인 합니다. 이벤트 캐스케이딩은 종료 되지 않은 재귀 프로시저 호출과 유사 하지만 덜 확실 한 하 여 호출 되므로 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드에서 명시적으로 호출 하는 대신 합니다. 사용 된 `Calls`스택에 활성화 되어 있는 프로시저 보기 대화 상자입니다.  
  
## <a name="see-also"></a>참고 항목  
 [메모리 창](https://docs.microsoft.com/visualstudio/debugger/memory-windows)
