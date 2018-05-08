---
title: '방법: Visual Basic에서 개체 변수 선언 및 개체 변수에 개체 할당'
ms.date: 07/20/2015
helpviewer_keywords:
- object variables [Visual Basic], declaring
- declaring object variables [Visual Basic]
ms.assetid: 2fa77dde-1fb2-439a-80d4-3e9787649fad
ms.openlocfilehash: 1f38c90f0571b3fc73c4c89812092cdada936d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-an-object-variable-and-assign-an-object-to-it-in-visual-basic"></a>방법: Visual Basic에서 개체 변수 선언 및 개체 변수에 개체 할당
형식의 변수를 선언한는 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md) 지정 하 여 `As Object` 에 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)합니다. 등호 뒤에 개체를 배치 하 여 이러한 변수를 개체를 할당 (`=`) 대입문 이나 초기화 절에서.  
  
## <a name="example"></a>예제  
 다음 예제에서는 선언는 `Object` 변수와 현재 인스턴스를 할당 합니다.  
  
```  
      Dim thisObject As Object  
thisObject = "This is an Object"  
```  
  
 선언 및 할당 변수 선언의 일부로 초기화 하 여 결합할 수 있습니다. 다음 예제에서는 앞의 예제와 같습니다.  
  
```  
Dim thisObject As Object= "This is an Object"  
```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
-   <xref:System> 네임스페이스에 대한 참조  
  
-   클래스, 구조체 또는 모듈을 작성할는 `Dim` 문.  
  
-   할당 문을 배치 하는 프로시저입니다.  
  
## <a name="see-also"></a>참고 항목  
 [변수 선언](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)  
 [개체 변수](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)  
 [개체 변수 선언](../../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [Object 데이터 형식](../../../../visual-basic/language-reference/data-types/object-data-type.md)  
 [Dim 문](../../../../visual-basic/language-reference/statements/dim-statement.md)  
 [지역 형식 유추](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
