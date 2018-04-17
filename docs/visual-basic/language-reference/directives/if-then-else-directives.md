---
title: '#다음과 같은 경우... Then... #Else 지시문'
ms.date: 04/11/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.#EndIf
- '#End If'
- '#Then'
- '#ElseIf'
- vb.#ElseIf
- vb.#Else
- vb.#If
helpviewer_keywords:
- Visual Basic code, compiling
- '#If directive [Visual Basic]'
- conditional compilation [Visual Basic], directives
- '#End if directive [Visual Basic]'
- selective compiling
- else directive (#else)
- '#Else directive [Visual Basic]'
ms.assetid: 10bba104-e3fd-451b-b672-faa472530502
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 884c7ed6f0a346f2d35f01006cea23e47907d13f
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ifthenelse-directives"></a>#If...Then...#Else 지시문
Visual Basic 코드의 선택 된 블록을 조건부로 컴파일합니다.  
  
## <a name="syntax"></a>구문  
  
```  
#If expression Then  
   statements  
[ #ElseIf expression Then  
   [ statements ]  
...  
#ElseIf expression Then  
   [ statements ] ]  
[ #Else  
   [ statements ] ]  
#End If  
```  
  
## <a name="parts"></a>요소  
 `expression`  
 에 필요한 `#If` 및 `#ElseIf` 문, 선택적 다른 곳입니다. 조건부 컴파일러 상수, 리터럴 및 연산자 계산 되는 하나 이상의 구성 하는 모든 식, `True` 또는 `False`합니다.  
  
 `statements`  
 에 필요한 `#If` 문 블록에서는 선택적 다른 곳입니다. Visual Basic 프로그램 줄 또는 컴파일러 지시문과 관련 된 식은로 평가 되 면 컴파일되는 `True`합니다.  
  
 `#End If`  
 종료는 `#If` 문 블록입니다.  
  
## <a name="remarks"></a>설명  
 동작은 화면에는 `#If...Then...#Else` 지시문 동일 하 게의 표시는 `If...Then...Else` 문. 그러나는 `#If...Then...#Else` 지시문은 컴파일러에 의해 컴파일되는 내용을 반면 평가 `If...Then...Else` 문 실행 시 조건을 평가 합니다.  
  
 조건부 컴파일 여러 플랫폼에 대해 동일한 프로그램을 컴파일하는 데 주로 사용 됩니다. 방지 하기 위해 사용 되는 실행 파일에 표시 되는 코드를 디버깅 합니다. 조건부 컴파일 타임에 제외 된 코드에서에서 완전히 생략 최종 실행 파일 때문에 크기 또는 성능에 영향을 주지 않습니다.  
  
 모든 평가 결과 상관 없이 모든 식을 사용 하 여 평가 됩니다 `Option Compare Binary`합니다. `Option Compare` 문은 식에 영향을 주지 않습니다 `#If` 및 `#ElseIf` 문.  
  
> [!NOTE]
>  한 줄 형식이 없으므로 `#If`, `#Else`, `#ElseIf`, 및 `#End If` 지시문 존재 합니다. 다른 코드 지시문와 같은 줄에 나타날 수 있습니다. 

조건부 컴파일 블록 내에서 문을 완료 논리 문 이어야 합니다. 예를 들어 함수의 특성만 조건에 따라 컴파일할 수 없습니다 하지만 조건에 따라 특성 함께 함수를 선언할 수 있습니다.

```vb
   #If DEBUG Then
   <WebMethod()>
   Public Function SomeFunction() As String
   #Else
   <WebMethod(CacheDuration:=86400)>
   Public Function SomeFunction() As String
   #End If
```

## <a name="example"></a>예제
 사용 하 여이 예제는 `#If...Then...#Else` 구문을 특정 문의 컴파일 여부를 결정 합니다.  
  
 [!code-vb[VbVbalrConditionalComp#1](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/if-then-else-directives_1.vb)]  
  
## <a name="see-also"></a>참고 항목  
[#Const 지시문](../../../visual-basic/language-reference/directives/const-directive.md)  
[If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)  
[조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)   
<xref:System.Diagnostics.ConditionalAttribute?displayProperty=nameWithType>   


