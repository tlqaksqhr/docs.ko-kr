---
title: "AddressOf 연산자 (Visual Basic) | Microsoft 문서"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
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
ms.openlocfilehash: 04a7c5be9b890faea561c28715093a271cf9eaa8
ms.lasthandoff: 03/13/2017

---
# <a name="addressof-operator-visual-basic"></a>AddressOf 연산자(Visual Basic)
특정 절차를 참조 하는 프로시저 대리자 인스턴스를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
AddressOf procedurename  
```  
  
## <a name="parts"></a>요소  
 `procedurename`  
 필수 요소. 새로 만든된 프로시저 대리자가 참조 하는 절차를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 `AddressOf` 연산자는 함수 대리자에 지정 된 함수를 가리키는 만듭니다 `procedurename`합니다. 지정 된 프로시저를 때 인스턴스 메서드는 함수 대리자는 인스턴스와 메서드를 가리킵니다. 그런 다음 함수 대리자가 호출 되 면 지정 된 인스턴스의 지정된 된 메서드 호출 됩니다.  
  
 `AddressOf` 는 대리자 생성자의 피연산자와 연산자를 사용할 수 있습니다 또는 컴파일러는 대리자의 형식을 결정 하는 컨텍스트에서 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 `AddressOf` 처리 하는 대리자를 지정 하는 연산자는 `Click` 단추의 이벤트입니다.  
  
 [!code-vb[VbVbalrDelegates #&8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `AddressOf` 연산자를 사용 하는 스레드에 대 한 시작 함수를 지정 합니다.  
  
 [!code-vb[VbVbalrDelegates #&9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>참고 항목  
 [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [대리자](../../../visual-basic/programming-guide/language-features/delegates/index.md)
