---
title: "방법: 프로시저 만들기(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- Visual Basic code, reusing
- procedure declarations
- procedures [Visual Basic], about procedures
ms.assetid: 4f779247-0b50-47e8-9e5c-ab5cf39ac0d2
caps.latest.revision: "27"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 56a44918b7a1426d215cee0ff2981f5763432a48
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-procedure-visual-basic"></a>방법: 프로시저 만들기(Visual Basic)
선언문의 시작 사이 프로시저를 묶습니다 (`Sub` 또는 `Function`) 및 선언문의 끝 (`End Sub` 또는 `End Function`). 프로시저의 모든 코드이 문 사이 표시 됩니다.  
  
 프로시저의 시작 및 끝 문은 다른 프로시저 밖에 서 있어야 하므로 다른 프로시저를 포함할 수 없습니다.  
  
 서로 다른 위치에서 동일한 작업을 수행 하는 코드를 있는 경우 절차로 한 번 작업 쓰고 코드에서 다른 위치에서 호출 합니다.  
  
### <a name="to-create-a-procedure-that-does-not-return-a-value"></a>값을 반환 하지 않는 프로시저를 만들려면  
  
1.  다른 프로시저 밖에 서 사용 하 여 한 `Sub` 문 다음에 `End Sub` 문.  
  
2.  에 `Sub` 문을 수행는 `Sub` 키워드와 프로시저를 지정한 다음 매개 변수 목록을 괄호로 이름 합니다.  
  
3.  프로시저의 코드 문을 사이 `Sub` 및 `End Sub` 문.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>값을 반환 하는 프로시저를 만들려면  
  
1.  다른 프로시저 밖에 서 사용 하 여 한 `Function` 문 다음에 `End Function` 문.  
  
2.  에 `Function` 문을 수행는 `Function` 키워드와 프로시저를 지정한 다음 매개 변수 목록을 괄호로 이름 차례로 `As` 반환 값의 데이터 형식을 지정 하는 절.  
  
3.  프로시저의 코드 문을 사이 `Function` 및 `End Function` 문.  
  
4.  사용 하 여 한 `Return` 호출 코드에 값을 반환 하는 문입니다.  
  
### <a name="to-connect-your-new-procedure-with-the-old-repetitive-blocks-of-code"></a>오래 되 고 반복적인 코드 블록을 사용 하 여 새 프로시저를 연결 하려면  
  
1.  이전 코드에 액세스할 수 있는 위치에서 새 프로시저를 정의 하 고 있는지 확인 합니다.  
  
2.  이전 반복 코드 블록을 호출 하는 단일 문 반복적인 작업을 수행 하는 문을 바꿉니다는 `Sub` 또는 `Function` 프로시저입니다.  
  
3.  프로시저가 `Function` 값을 반환 하는, 하도록 하는 변수에 저장 하는 등의 반환된 값과 함께 동작을 수행 하는 호출 문에서 값이 손실 됩니다.  
  
## <a name="example"></a>예제  
 다음 `Function` 프로시저 가장 긴 면 또는 다른 두 변에 대 한 값을 지정 하는 직각 삼각형의 빗변을 계산 합니다.  
  
 [!code-vb[VbVbcnProcedures#1](./codesnippet/VisualBasic/how-to-create-a-procedure_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [절차](./index.md)  
 [Sub 프로시저](./sub-procedures.md)  
 [Function 프로시저](./function-procedures.md)  
 [속성 프로시저](./property-procedures.md)  
 [연산자 프로시저](./operator-procedures.md)  
 [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)  
 [재귀 프로시저](./recursive-procedures.md)  
 [프로시저 오버로딩](./procedure-overloading.md)  
 [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [개체 지향 프로그래밍](http://msdn.microsoft.com/library/1cf6e655-3f30-45f1-9a5d-4a88ca24a1c2)
