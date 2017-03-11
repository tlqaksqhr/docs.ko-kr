---
title: "Special Characters in Code (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.)"
  - "vb.("
  - "vb.colon"
  - "vb.!"
  - "vb.."
  - "vb.:"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "special characters, in code"
  - "parentheses, using in code"
  - "colons (:)"
  - "period character in code"
  - "dot operator (.)"
  - "dictionary access operator"
  - "concatenation operators, special characters in code"
  - "concatenation operators, vs. addition operator"
  - "! operator"
  - "separators, using in code"
  - "operators [Visual Basic], dictionary access"
  - ": separator character"
  - "member access operator"
  - "addition operator"
  - "operators [Visual Basic], member access"
  - ". operator"
  - "exclamation points"
  - "separators"
  - "exclamation point operator (!)"
  - "Visual Basic code, special characters"
ms.assetid: 310dce0c-45b5-4e0d-83e9-32df258d2a3e
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Special Characters in Code (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

간혹 알파벳 또는 숫자가 아닌 문자인 특수 문자를 코드에 사용해야 할 수 있습니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 문자 집합의 문장 부호와 특수 문자는 프로그램 텍스트 구성에서 컴파일러 또는 컴파일된 프로그램이 수행한 작업의 정의에 이르기까지 다양한 용도로 사용됩니다.  이러한 특수 문자는 수행할 작업을 지정하지 않습니다.  
  
## 괄호  
 `Sub` 또는 `Function` 등의 프로시저를 정의할 때는 괄호를 사용합니다.  모든 프로시저 인수 목록은 괄호로 묶어야 합니다.  특히 복잡한 식에서 연산자 우선 순위의 기본 순서를 무시하려는 경우 변수 또는 인수를 논리 그룹에 삽입할 때 괄호를 사용할 수도 있습니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#11](../../../visual-basic/programming-guide/language-features/codesnippet/visualbasic/special-characters-in-code_1.vb)]  
  
 앞의 코드에서 `d` 값은 8.225로 `e` 값은 "3"으로 실행합니다.  `d` 계산은 `/` 다음에 `+`를 연산하는 기본 우선 순위를 사용하며 `d = b + (c / a)`와 같습니다.  `e` 계산에 있는 괄호는 기본 우선 순위를 무시합니다.  
  
## 구분 기호  
 구분 기호는 이 이름에서 알 수 있듯이 코드를 여러 섹션으로 구분합니다.  [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 콜론\(`:`\)을 구분 문자로 사용합니다.  구분 기호를 사용하면 별도의 줄이 아니라 한 줄에 여러 개의 문을 포함할 수 있어  공간을 절약하고 코드를 쉽게 읽을 수 있습니다.  다음 예제에서는 콜론으로 구분된 세 개의 문을 보여 줍니다.  
  
 [!code-vb[VbVbcnConventions#12](../../../visual-basic/programming-guide/language-features/codesnippet/visualbasic/special-characters-in-code_2.vb)]  
  
 자세한 내용은 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)을 참조하십시오.  
  
 콜론\(`:`\) 문자를 사용하여 문 레이블을 식별할 수도 있습니다.  자세한 내용은 [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)을 참조하십시오.  
  
## 연결 연산  
 문자열을 서로 *연결*하는 경우에는 `&` 연산자를 사용합니다.  이 연산자를 숫자 값을 서로 더하는 `+` 연산자와 혼동하지 마십시오.  숫자 값에 대해 연산을 수행할 때 `+` 연산자를 사용하여 연결하면 잘못된 결과가 발생할 수 있습니다.  다음 예제에서는 이 작업을 보여 줍니다.  
  
 [!code-vb[VbVbcnConventions#13](../../../visual-basic/programming-guide/language-features/codesnippet/visualbasic/special-characters-in-code_3.vb)]  
  
 앞의 코드에서 `resultA` 값은 21.01로 `resultB` 값은 "10.0111"로 실행합니다.  
  
## 멤버 액세스 연산자  
 형식 멤버에 액세스하려면 형식 이름과 멤버 이름 사이에 점\(`.`\) 또는 느낌표\(`!`\) 연산자를 사용합니다.  
  
### 점\(.\) Operator  
 클래스, 구조체, 인터페이스 또는 열거형에서는 `.` 연산자를 멤버 액세스 연산자로 사용합니다.  멤버는 필드, 속성, 이벤트 또는 메서드일 수 있습니다.  다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbcnConventions#14](../../../visual-basic/programming-guide/language-features/codesnippet/visualbasic/special-characters-in-code_4.vb)]  
  
### 느낌표\(\!\) Operator  
 클래스나 인터페이스에서는 `!` 연산자를 사전 액세스 연산자로 사용합니다.  클래스나 인터페이스는 단일 `String` 인수를 허용하는 기본 속성을 가져야 합니다.  `!` 연산자 바로 뒤의 식별자는 기본 속성에 문자열로 전달되는 인수 값이 됩니다.  다음 예제에서는 이 작업을 보여 줍니다.  
  
 [!code-vb[VbVbcnConventions#15](../../../visual-basic/programming-guide/language-features/codesnippet/visualbasic/special-characters-in-code_5.vb)]  
  
 `MsgBox`의 출력 세 줄은 모두 값 `32856`을 표시합니다.  첫째 줄에서는 `index` 속성에 대한 일반적인 액세스를 사용하고 둘째 줄에서는 `index`가 `hasDefault` 클래스의 기본 속성이라는 사실을 이용하며 셋째 줄에서는 클래스에 대한 사전 액세스를 사용합니다.  
  
 `!` 연산자의 두 번째 피연산자는 큰따옴표\(`" "`\)로 묶지 않은 유효한 Visual Basic 식별자여야 합니다.  즉, 문자열 리터럴이나 문자열 변수를 사용할 수 없습니다.  `MsgBox` 호출의 마지막 줄을 다음과 같이 변경하면 `"X"`가 문자열 리터럴로 묶여 오류가 발생합니다.  
  
 `"Dictionary access returns " & hD!"X")`  
  
> [!NOTE]
>  기본 컬렉션에 대한 참조는 명시적이어야 합니다.  특히, 런타임에 바인딩되는 변수에 대해서는 `!` 연산자를 사용할 수 없습니다.  
  
 `!` 문자는 `Single` 형식 문자로도 사용될 수 있습니다.  
  
## 참고 항목  
 [프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)   
 [Type Characters](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)