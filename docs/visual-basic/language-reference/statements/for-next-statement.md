---
title: "For...Next 문(Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Step"
  - "vb.Next"
  - "vb.To"
  - "vb.for"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "무한 루프"
  - "Next 키워드, For...Next 문"
  - "For 키워드[Visual Basic], For...Next 문"
  - "Step 키워드, For...Next 문"
  - "연산자 오버로드, For...Next 문"
  - "To 키워드, For...Next 문"
  - "무한 루프"
  - "루프, 무한"
  - "명령, 반복"
  - "Next 문, For...Next"
  - "For...Next 문"
  - "루프 구조, For...Next"
  - "루프, 무한"
  - "Exit 문, For...Next 문"
  - "For 문"
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
caps.latest.revision: 64
caps.handback.revision: 64
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# For...Next 문(Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

문의 그룹을 지정한 횟수만큼 반복합니다.  
  
## 구문  
  
```  
For counter [ As datatype ] = start To end [ Step step ]  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ counter ]  
```  
  
## 요소  
  
|파트|설명|  
|--------|--------|  
|`counter`|`For` 문에서 필수적 요소입니다.  숫자 변수이며  루프에 대한 제어 변수입니다.  자세한 내용은 이 항목의 뒤에 나오는 [카운터 인수](#BKMK_Counter)를 참조하십시오.|  
|`datatype`|선택 사항입니다.  `counter`의 데이터 형식입니다.  자세한 내용은 이 항목의 뒤에 나오는 [카운터 인수](#BKMK_Counter)를 참조하십시오.|  
|`start`|필수 요소.  숫자 식입니다.  `counter`의 초기 값입니다.|  
|`end`|필수 요소.  숫자 식입니다.  `counter`의 최종 값입니다.|  
|`step`|선택 사항입니다.  숫자 식입니다.  루프가 실행될 때마다 `counter`가 증가되는 정도입니다.|  
|`statements`|선택 사항입니다.  지정한 횟수만큼 실행되는 `For`와 `Next` 사이의 하나 이상의 문입니다.|  
|`Continue For`|선택 사항입니다.  제어를 다음 루프 반복으로 이동합니다.|  
|`Exit For`|선택 사항입니다.  `For` 루프의 외부로 제어를 이동합니다.|  
|`Next`|필수 요소.  `For` 루프의 정의를 끝냅니다.|  
  
> [!NOTE]
>  `To` 키워드가이 문에서 카운터의 범위를 지정 하는 데 사용 합니다.  이 키워드를 사용할 수도 있습니다는 [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) 및 배열 선언에서.  배열 선언에 대한 자세한 내용은 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)을 참조하십시오.  
  
## 간단한 예제  
 You use a `For`...`Next` 구조체는 문을 횟수 만큼 반복 하려면.  
  
 다음 예제에서는 `index` 변수 값을 1로 시작 하 고 종료 한 후의 값은 루프의 각 반복에 증가 `index` 5에 도달 합니다.  
  
 [!code-vb[VbVbalrStatements#111](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/for-next-statement_1.vb)]  
  
 다음 예제에서는 `number` 변수 2를 시작 하 고 종료 한 후의 값은 루프의 각 반복에서 0.25 줄어듭니다 `number` 0에 도달 합니다.  `Step` 인수를 `-.25` 값 0.25는 루프의 각 반복에 의해 줄어듭니다.  
  
 [!code-vb[VbVbalrStatements#112](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/for-next-statement_2.vb)]  
  
> [!TIP]
>  A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 또는 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) 때 미리 문은 루프의 실행 횟수 모르는 잘 작동 합니다.  그러나 루프 실행 횟수를 아는 경우에는 `For`...`Next` 루프가 더 유용합니다.  루프를 처음 입력할 때 반복 횟수를 결정합니다.  
  
## 루프 중첩  
 한 루프를 다른 루프 내에 배치하여 `For` 루프를 서로 중첩할 수 있습니다.  다음 예제에서는 단계 값이 다른 중첩된 `For`...`Next` 구조를 보여 줍니다.  외부 루프는 루프가 반복될 때마다 문자열을 생성합니다.  내부 루프는 루프가 반복될 때마다 루프 카운터를 감소시킵니다.  
  
 [!code-vb[VbVbalrStatements#113](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/for-next-statement_3.vb)]  
  
 루프를 중첩 하는 경우 각 루프에는 고유 해야 합니다 `counter` 변수입니다.  
  
 또한 다른 종류의 제어 구조를 서로 중첩할 수 있습니다.  자세한 내용은 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)을 참조하십시오.  
  
## 계속 해 서 exit  
 `Exit For` 문을 즉시 종료는 `For`...`Next` 다음에 오는 문에 루프 및 전송 컨트롤의 `Next` 문.  
  
 `Continue For` 문은 제어를 루프의 다음 반복으로 바로 이동합니다.  자세한 내용은 [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md)을 참조하십시오.  
  
 다음 예제에서는 `Continue For` 및 `Exit For` 문을 사용하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#115](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/for-next-statement_4.vb)]  
  
 `For`…`Next` 루프에 임의 수의 `Exit For` 문을 배치할 수 있습니다.  중첩된 `For`…`Next` 루프 내에 `Exit For`를 사용하면 Exit For는 가장 안쪽의 루프를 끝내고 중첩 수준이 그 다음으로 높은 루프에 제어를 전달합니다.  
  
 `Exit For`일부 조건을 확인 한 후에 자주 사용 됩니다 \(예를 들어,는 `If`...`Then`...`Else` 구조\).  다음 조건에 대해 `Exit For`를 사용할 수 있습니다.  
  
-   계속 반복은 불필요하며 불가능합니다.  잘못 된 값 이나 종료 요청과이 조건을 만들 수 있습니다.  
  
-   A `Try`...`Catch`...`Finally` 문은 예외를 catch 합니다.  `Finally` 블록 끝에 `Exit For`를 사용할 수 있습니다.  
  
-   대규모 또는 심지어 무한 여러 번 실행할 수 있는 루프는 무한 루프의 경우  이러한 조건을 감지한 경우 `Exit For`를 사용하여 루프를 이스케이프할 수 있습니다.  자세한 내용은 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)을 참조하십시오.  
  
## 기술 구현  
 `For`...`Next` 루프가 시작되면 Visual Basic에서 `start`, `end` 및 `step`을 계산합니다.  Visual Basic이 시간과 할당에 다음 이러한 값을 계산 `start` 에 `counter`.  하기 전에 문 블록을 실행, Visual Basic 비교 `counter` 에 `end`.  경우 `counter` 보다 이미 큰는 `end` 값 \(더 작은 경우 `step` 음수입니다\), `For` 루프가 종료 되 고 제어가 다음 문으로 전달 된 `Next` 문.  그렇지 않은 경우 문 블록이 실행 됩니다.  
  
 Visual Basic에서 `Next` 문을 만날 때마다 `step`을 기준으로 `counter`를 증가시키고 `For` 문으로 돌아옵니다.  다시 `counter`와 `end`를 비교하여 결과에 따라 블록을 다시 실행하거나 루프를 종료합니다.  `counter`가 `end`를 지나가거나 `Exit For` 문을 만날 때까지 이 프로세스는 계속됩니다.  
  
 루프를 중지할 때까지 하지 않는 `counter` 전달 된 `end`.  `counter`가 `end`와 같으면 루프가 계속됩니다.  블록 실행 여부를 결정하는 비교 연산은 `step`이 양수일 경우 `counter` \<\= `end`이고 `step`이 음수일 경우 `counter` \<\= `end`입니다.  
  
 값을 변경 하는 경우 `counter` 루프 안에 있는 동안, 코드를 읽고 디버깅 하기가 어려울 수 있습니다.  값을 변경 `start`, `end`, 또는 `step` 루프를 처음 입력 했을 때 결정 한 반복 값에 영향을 주지 않습니다.  
  
 루프를 중첩 한 경우 컴파일러에서 오류를 발견 하는 경우 알립니다의 `Next` 문 전에 외부 중첩 수준의 `Next` 문이 내부 수준의.  하지만 컴파일러는 `counter`를 모든 `Next` 문에 지정하는 경우에만 이러한 중복 오류를 감지할 수 있습니다.  
  
### 단계 인수  
 `step`의 값은 양수 또는 음수가 될 수 있습니다.  이 매개 변수는 다음 표에 따라 루프 처리를 결정:  
  
|**Step 값**|**루프가 실행되는 경우**|  
|----------------|---------------------|  
|양수 또는 0|`counter` \<\= `end`|  
|음수|`counter` \>\= `end`|  
  
 기본값은 `step` 1입니다.  
  
###  <a name="BKMK_Counter"></a> 카운터 인수  
 다음 표에서 여부 `counter` 는 전체 범위가 지정 되는 새 로컬 변수 정의 `For…Next` 루프.  이 결정 여부에 따라 다릅니다. `datatype` 존재 여부 및 `counter` 이미 정의 되어 있습니다.  
  
|`datatype` 가?|`counter` 이미 정의?|결과 \(여부 `counter` 는 전체 범위가 지정 되는 새 로컬 변수 정의 `For...Next` 루프\)|  
|-------------------|----------------------|-------------------------------------------------------------------|  
|아니요|예|아니오, 때문에 `counter` 이미 정의 되어 있습니다.  경우 범위를 `counter` 프로시저에 로컬 아닌 컴파일 타임 경고가 발생 합니다.|  
|아니요|아니요|예.  데이터 형식에서 유추 되는 `start`, `end`, 및 `step` 식.  형식 유추에 대 한 내용은 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|  
|예|예|예, 하지만 경우에만 기존 `counter` 변수가 프로시저 밖에 서 정의 됩니다.  변수를 별도 남아 있습니다.  경우 기존 범위 `counter` 변수인 프로시저에 로컬 컴파일 타임 오류가 발생 합니다.|  
|예|아니요|예.|  
  
 데이터 형식은 `counter` 는 다음 형식 중 하나 여야 합니다 반복 형식을 결정 합니다.  
  
-   `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single` 또는 `Double`입니다.  
  
-   [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md) 문을 사용하여 선언하는 열거형입니다.  
  
-   `Object`입니다.  
  
-   다음 연산자가 있는 형식 `T`이며, 여기서 `B`는 `Boolean` 식에 사용 가능한 형식입니다.  
  
     `Public Shared Operator >= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator <= (op1 As T, op2 As T) As B`  
  
     `Public Shared Operator - (op1 As T, op2 As T) As T`  
  
     `Public Shared Operator + (op1 As T, op2 As T) As T`  
  
 선택적으로 지정할 수 있습니다에서 `counter` 변수는 `Next` 문.  특히 중첩 된 경우이 구문은 프로그램의 가독성이 향상 됩니다 `For` 루프.  해당 표시 되는 변수를 지정 해야 `For` 문.  
  
 `start`, `end` 및 `step` 식은 `counter` 형식으로 확대 변환되는 모든 데이터 형식으로 계산될 수 있습니다.  사용자 정의 형식에 대해 사용 하는 경우 `counter`를 정의 할 수 있습니다는 `CType` 의 형식을 변환 하는 변환 연산자 `start`, `end`, 또는 `step` 형식으로 `counter`.  
  
## 예제  
 다음 예제에서는 제네릭 목록에서 모든 요소를 제거합니다.  대신에 [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)을 보여 주는 예제는 `For`...`Next` 내림차순으로 반복 되는 문입니다.  때문에이 기술을 사용 하는 예제는 `removeAt` 방법을 사용 하면 요소 제거 요소 후 낮은 인덱스 값을 가져야 합니다.  
  
 [!code-vb[VbVbalrStatements#114](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/for-next-statement_5.vb)]  
  
## 예제  
 다음 예제에서는 열거형을 사용 하 여 선언 된 반복은 [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).  
  
 [!code-vb[VbVbalrStatements#116](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/for-next-statement_6.vb)]  
  
## 예제  
 다음 예제에서는 문 매개 변수가 `+`, `-`, `>=` 및 `<=` 연산자에 대한 연산자 오버로드가 있는 클래스를 사용합니다.  
  
 [!code-vb[VbVbalrStatements#117](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/for-next-statement_7.vb)]  
  
## 참고 항목  
 <xref:System.Collections.Generic.List%601>   
 [Loop Structures](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)   
 [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md)   
 [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md)   
 [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)   
 [Exit Statement](../../../visual-basic/language-reference/statements/exit-statement.md)   
 [컬렉션](../Topic/Collections%20\(C%23%20and%20Visual%20Basic\).md)