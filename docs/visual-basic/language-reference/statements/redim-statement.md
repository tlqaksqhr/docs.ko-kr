---
title: "ReDim Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ReDim"
  - "vb.Preserve"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "fixed-length strings, declaring"
  - "ReDim statement, syntax"
  - "dynamic arrays, ReDim statement"
  - "arrays [Visual Basic], reallocating"
  - "arrays [Visual Basic], reinitializing"
  - "arrays [Visual Basic], dimensions"
  - "scalars, and arrays"
  - "scalars"
  - "declarations, dynamic arrays"
  - "variables [Visual Basic], scalar"
  - "ReDim statement"
  - "data types [Visual Basic], assigning"
  - "As keyword, in ReDim statement"
  - "To keyword, ReDim statement"
  - "arrays [Visual Basic], declaring"
  - "Preserve keyword, ReDim statement"
  - "storage, allocating"
  - "arrays [Visual Basic], and scalars"
  - "declaration statements"
  - "scalar variables"
ms.assetid: ad1c5e07-dcd7-4ae1-a79e-ad3f2dcc2083
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# ReDim Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

배열 변수의 저장 공간을 다시 할당합니다.  
  
## 구문  
  
```  
ReDim [ Preserve ] name(boundlist) [ ,  name(boundlist) [, ... ] ]  
```  
  
## 요소  
  
|용어|정의|  
|--------|--------|  
|`Preserve`|선택 사항입니다.  마지막 차원의 크기만 변경한 경우 기존 배열의 데이터를 유지하기 위해 사용되는 한정자입니다.|  
|`name`|필수.  배열 변수의 이름입니다.  [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하세요.|  
|`boundlist`|필수.  다시 정의된 배열의 각 차원에 대한 범위 목록입니다.|  
  
## 설명  
 `ReDim` 문을 사용하여 이미 선언된 배열의 차원 중 하나 이상의 크기를 변경할 수 있습니다.  큰 배열이 있고 요소가 더 이상 필요하지 않은 경우 `ReDim`은 배열 크기를 줄여서 메모리를 확보할 수 있습니다.  반면에 배열에 요소가 더 필요한 경우 `ReDim`은 요소를 추가할 수 있습니다.  
  
 `ReDim` 문은 배열에만 사용할 수 있으며  스칼라\(단일 값만 포함된 변수\), 컬렉션 또는 구조체에서는 유효하지 않습니다.  변수를 `Array` 형식으로 선언하는 경우 `ReDim` 문에는 새 배열을 만들 수 있는 충분한 형식 정보가 없습니다.  
  
 `ReDim`은 프로시저 수준에서만 사용할 수 있습니다.  따라서 변수의 선언 컨텍스트는 프로시저여야 하며, 소스 파일, 네임스페이스, 인터페이스, 클래스, 구조체, 모듈 또는 블록일 수 없습니다.  자세한 내용은 [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md)을 참조하세요.  
  
## 규칙  
  
-   **여러 변수.** 동일한 선언문에서 여러 배열 변수의 크기를 조정하고 각 변수의 `name` 및 `boundlist` 부분을 지정할 수 있습니다.  여러 변수는 쉼표로 구분됩니다.  
  
-   **배열 범위.** `boundlist`의 각 항목은 해당 차원의 하한과 상한을 지정할 수 있습니다.  하한은 항상 0\(영\)입니다.  상한은 해당 차원에 가능한 최대 인덱스 값이며 차원의 길이\(상한에 1을 더한 값\)는 아닙니다.  각 차원의 인덱스는 0부터 상한 값까지 다양할 수 있습니다.  
  
     `boundlist`의 차원 수는 배열의 원래 차원 수\(차수\)와 일치해야 합니다.  
  
-   **데이터 형식.** `ReDim` 문은 배열 변수나 배열 요소의 데이터 형식을 변경할 수 없습니다.  
  
-   **초기화.** `ReDim` 문은 배열 요소에 대한 새로운 초기화 값을 제공할 수 없습니다.  
  
-   **차수.** `ReDim` 문은 배열의 차수\(차원 수\)를 변경할 수 없습니다.  
  
-   **Preserve를 사용한 크기 조정.** `Preserve`를 사용하는 경우 배열의 마지막 차원만 크기를 조정할 수 있습니다.  다른 모든 차원의 경우에는 기존 배열의 범위를 지정해야 합니다.  
  
     예를 들어 배열에 차원이 하나만 있는 경우 해당 차원의 크기를 조정해도 배열의 모든 내용을 보존할 수 있습니다. 마지막이자 유일한 차원을 변경하기 때문입니다.  그러나 배열에 둘 이상의 차원이 있는 경우에는 `Preserve`를 사용하여 마지막 차원의 크기만 변경할 수 있습니다.  
  
-   **속성.** 값의 배열이 포함된 속성에 대해 `ReDim`을 사용할 수 있습니다.  
  
## 동작  
  
-   **배열 대체.** `ReDim`은 기존 배열을 해제하고 동일한 차수로 새 배열을 만듭니다.  새 배열은 배열 변수에서 해제된 배열을 대체합니다.  
  
-   **Preserve를 사용하지 않는 초기화.** `Preserve`를 지정하지 않는 경우 `ReDim`은 데이터 형식의 기본값을 사용하여 새 배열의 요소를 초기화합니다.  
  
-   **Preserve를 사용하는 초기화.** `Preserve`를 지정하는 경우 Visual Basic에서는 기존 배열의 요소를 새 배열에 복사합니다.  
  
## 예제  
 다음 예제에서는 배열의 기존 데이터를 손실하지 않고 동적 배열의 마지막 차원 크기를 늘린 다음 데이터를 부분적으로 손실하며 크기를 줄입니다.  마지막으로 크기를 원래 값으로 다시 줄이고 모든 배열 요소를 다시 초기화합니다.  
  
 [!code-vb[VbVbalrStatements#52](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/redim-statement_1.vb)]  
  
 `Dim` 문은 차원이 세 개인 새 배열을 만듭니다.  각 차원은 범위 10으로 선언되므로 각 차원의 배열 인덱스는 0에서 10까지의 범위일 수 있습니다.  다음 설명에서는 세 개의 차원이 계층, 행 및 열로 지칭됩니다.  
  
 첫 번째 `ReDim`은 `intArray` 변수의 기존 배열을 대체하는 새 배열을 만듭니다.  `ReDim`은 기존 배열의 모든 요소를 새 배열에 복사합니다.  또한 모든 계층에 있는 각 행의 끝에 열 10개를 더 추가하고 이러한 새 열의 요소를 0\(배열의 요소 형식인 `Integer`의 기본값\)으로 초기화합니다.  
  
 두 번째 `ReDim`은 새 배열을 하나 더 만들고 적합한 모든 요소를 복사합니다.  그러나 5개의 열이 각 계층에 있는 각 행의 끝에서 손실됩니다.  이는 해당 열의 사용을 마친 경우 문제가 되지 않습니다.  큰 배열의 크기를 줄이면 더 이상 필요하지 않은 메모리를 확보할 수 있습니다.  
  
 세 번째 `ReDim`은 새 배열을 하나 더 만들고 각 계층에 있는 각 행의 끝에서 5개의 열을 제거합니다.  이번에는 기존 요소를 복사하지 않습니다.  이 문은 배열을 원래 크기로 되돌립니다.  이 문은 `Preserve` 한정자를 포함하지 않기 때문에 모든 배열 요소를 원래 기본값으로 설정합니다.  
  
 추가 예제는 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)을 참조하세요.  
  
## 참고 항목  
 <xref:System.IndexOutOfRangeException>   
 [Const Statement](../../../visual-basic/language-reference/statements/const-statement.md)   
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [Erase Statement](../../../visual-basic/language-reference/statements/erase-statement.md)   
 [Nothing](../../../visual-basic/language-reference/nothing.md)   
 [배열](../../../visual-basic/programming-guide/language-features/arrays/index.md)