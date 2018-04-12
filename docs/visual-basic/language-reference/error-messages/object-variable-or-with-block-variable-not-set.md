---
title: Object 변수 또는 With 블록 변수가 설정되지 않았습니다.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID91
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 9e1f587e194acf744b6ec9b8f1bede3acef7b753
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="object-variable-or-with-block-variable-not-set"></a>Object 변수 또는 With 블록 변수가 설정되지 않았습니다.
잘못 된 개체 변수가 참조 하 고 있습니다.   여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.  
  
-   변수는 형식을 지정 하지 않고 선언 되었습니다. 변수는 형식을 지정 하지 않고 선언 된 경우 입력 기본값으로 `Object`합니다.  
  
     선언 된 변수는 예를 들어 `Dim x` 형식의 것 `Object;` 선언 된 변수는 `Dim x As String` 형식의 것 `String`합니다.  
  
    > [!TIP]
    >  `Option Strict` 문이 암시적 형식 지정을 허용 하지 않는 한 `Object` 유형입니다. 형식을 생략 하면 컴파일 타임 오류가 발생 합니다. 참조 [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.  
  
-   으로 설정 되어 있는 개체를 참조 하려고 합니다.`Nothing`  
  
     입니다.  
  
-   요소를 올바르게 선언 되지 않은 배열 변수에 액세스 하려고 합니다.  
  
     로 배열을 선언 하는 예를 들어 `products() As String` 은 배열의 요소를 참조 하려고 하면 오류를 발생 `products(3) = "Widget"`합니다. 배열에 요소가 고 개체로 처리 됩니다.  
  
-   내에서 코드 액세스 하려고 한 `With...End With` 블록 초기화 되기 전에 차단 합니다.   A `With...End With` 블록을 실행 하 여 초기화 해야는 `With` 문 진입점입니다.  
  
> [!NOTE]
>  이전 버전의 Visual Basic 또는 VBA에서이 오류도 트리거된 사용 하지 않고 값을 변수에 할당 하 여는 `Set` 키워드 (`x = "name"` 대신 `Set x = "name"`). `Set` 키워드는 더 이상 Visual Basic.net에서 유효 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1.  설정 `Option Strict` 를 `On` 파일의 시작 부분에 다음 코드를 추가 하 여:  
  
```vb  
Option Strict On  
```  

     When you run the project, a compiler error will appear in the **Error List** for any variable that was specified without a type.  
  
2.  사용 하도록 설정 하려면 `Option Strict`, 형식 없이 지정 된 모든 변수의 코드 검색 (`Dim x` 대신 `Dim x As String`) 원하는 형식 선언에 추가 합니다.  
  
3.  에 설정 된 개체 변수에 참조 되지 있는지 확인 `Nothing`합니다.  키워드에 대 한 코드 검색 `Nothing`, 개체도 설정 하도록 코드를 수정 하 고 `Nothing` 참조 한 후 될 때까지 합니다.  
  
4.  모든 배열 변수에 액세스 하기 전에 치수가 설정 되어 있는지 확인 합니다. 배열의 처음 만들 때 차원을 할당 하거나 (`Dim x(5) As String` 대신 `Dim x() As String`), 사용 또는 `ReDim` 키워드를 처음으로 액세스 하기 전에 배열의 차수를 설정 합니다.  
  
5.  있는지 확인 프로그램 `With` 블록을 실행 하 여 초기화 된 `With` 문 진입점입니다.  
  
## <a name="see-also"></a>참고 항목  
 [개체 변수 선언](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)  
 [ReDim 문](../../../visual-basic/language-reference/statements/redim-statement.md)  
 [With...End With 문](../../../visual-basic/language-reference/statements/with-end-with-statement.md)
