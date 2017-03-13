---
title: "Visual Basic의 변수 선언 | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "변수[Visual Basic], 선언"
  - "멤버 변수, 선언"
  - "Dim 문, 변수 선언"
  - "변수 선언"
  - "변수[Visual Basic], 범위"
  - "변수[Visual Basic], 데이터 형식"
  - "데이터 형식[Visual Basic], 변수 선언"
  - "수명, 변수"
  - "변수[Visual Basic], 수명"
  - "액세스 수준, 변수"
  - "범위, 선언문"
  - "변수[Visual Basic], 액세스 수준"
  - "지역 변수, 선언"
  - "변수, 변수"
ms.assetid: d8f10226-92b1-480f-9f53-df377b2d7e15
caps.latest.revision: 31
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 31
---
# Visual Basic의 변수 선언
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변수의 이름과 특징을 지정하려면 변수를 선언합니다.  변수에 대한 선언문은 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)입니다.  선언문의 위치와 내용에 따라 변수의 특징이 결정됩니다.  
  
 변수 명명 규칙 및 고려 사항에 대한 자세한 내용은 [Declared Element Names](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)을 참조하십시오.  
  
## 선언 수준  
  
### 지역 및 멤버 변수  
 *지역 변수*는 프로시저 내에서 선언되는 변수이지만  *멤버 변수*는 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 형식의 멤버입니다. 이 변수는 모듈 수준, 즉 클래스, 구조체 또는 모듈 내에서 선언되지만 해당 클래스, 구조체 또는 모듈의 내부 프로시저 내에서는 선언할 수 없습니다.  
  
### 공유 및 인스턴스 변수  
 클래스 또는 구조체에서 멤버 변수의 범주는 해당 변수의 공유 여부에 따라 달라집니다.  [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) 키워드로 선언된 변수는 *공유 변수*이며 단일 복사본의 형태로 클래스나 구조체의 모든 인스턴스 사이에서 공유됩니다.  
  
 이 이외의 변수는 *인스턴스 변수*이며 클래스나 구조체의 각 인스턴스에 대해 해당 변수의 개별 복사본이 만들어집니다.  인스턴스 변수 복사본이 지정 된 클래스 또는 구조체에서 만들어진 인스턴스에서만 사용 가능 합니다.  인스턴스 변수는 클래스 또는 구조체의 다른 모든 인스턴스의 복사본 으로부터 독립적입니다.  
  
## 데이터 형식 선언  
 선언문에 [As](../../../../visual-basic/language-reference/statements/as-clause.md) 절을 사용하면 선언하는 변수의 데이터 형식이나 개체 형식을 정의할 수 있습니다.  변수에 대해 다음과 같은 형식을 지정할 수 있습니다.  
  
-   `Boolean`, `Long` 또는 `Decimal` 등의 기본 데이터 형식  
  
-   배열 또는 구조체와 같은 복합 데이터 형식  
  
-   응용 프로그램이나 다른 응용 프로그램에서 정의된 개체 형식 또는 클래스  
  
-   <xref:System.Windows.Forms.Label> 또는 <xref:System.Windows.Forms.TextBox>와 같은 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] 클래스  
  
-   인터페이스 형식\(예: <xref:System.IComparable> 또는 <xref:System.IDisposable>\)  
  
 데이터 형식을 반복하지 않고도 하나의 문에서 여러 개의 변수를 선언할 수 있습니다.  다음 문에서 변수 `i`, `j` 및 `k`는 `Integer` 형식으로 선언되고, 변수 `l` 및 `m`은 `Long` 형식으로 선언되며, 변수 `x` 및 `y`는 `Single` 형식으로 선언됩니다.  
  
```  
Dim i, j, k As Integer  
' All three variables in the preceding statement are declared as Integer.  
Dim l, m As Long, x, y As Single  
' In the preceding statement, l and m are Long, x and y are Single.  
```  
  
 데이터 형식에 대한 자세한 내용은 [데이터 형식](../../../../visual-basic/programming-guide/language-features/data-types/index.md)을 참조하십시오.  개체에 대한 자세한 내용은 [Objects and Classes](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) 및 [구성 요소를 사용한 프로그래밍](../Topic/Programming%20with%20Components.md)을 참조하십시오.  
  
## 지역 형식 유추  
 *형식 유추*는 `As` 절 없이 선언된 지역 변수의 데이터 형식을 결정하는 데 사용됩니다.  컴파일러는 초기화 식의 형식에서 변수 형식을 유추합니다.  이를 통해 형식을 명시적으로 선언하지 않고 변수를 선언할 수 있습니다.  다음 코드 예제에서 `num1`과 `num2`는 모두 정수로 강력하게 형식화되어 있습니다.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/variable-declaration_1.vb)]  
  
 지역 형식 유추를 사용하려면 `Option Infer`를 `On`으로 설정해야 합니다.  자세한 내용은 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md) 및 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)을 참조하십시오.  
  
## 선언 된 변수의 특징  
 변수의 *수명*은 변수를 사용할 수 있는 기간입니다.  일반적으로 변수는 해당 변수를 선언하는 프로시저 또는 클래스 등의 요소가 존재하는 동안에만 존재합니다.  변수의 수명을 포함 하는 요소를 넘어 존재 해야 한다면 선언에 특별 한 아무것도 할 필요가 없습니다.  변수가 해당 변수를 포함하는 요소보다 오래 존재해야 하는 경우 `Dim` 문에 `Static` 또는 `Shared` 키워드를 포함하면 됩니다.  자세한 내용은 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)을 참조하십시오.  
  
 변수의 *범위*는 이름을 한정하지 않고 해당 변수를 참조할 수 있는 모든 코드 집합으로,  변수가 선언된 위치에 따라 달라집니다.  변수가 선언된 영역에 있는 코드는 변수의 이름을 한정하지 않고도 해당 변수를 사용할 수 있습니다.  자세한 내용은 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)을 참조하십시오.  
  
 변수의 *액세스 수준*은 변수에 액세스할 수 있는 권한이 있는 코드의 범위로,  `Dim` 문에서 사용하는 액세스 한정자\([Public](../../../../visual-basic/language-reference/modifiers/public.md) 또는 [Private](../../../../visual-basic/language-reference/modifiers/private.md)\)에 의해 결정됩니다.  자세한 내용은 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조하십시오.  
  
## 참고 항목  
 [How to: Create a New Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-create-a-new-variable.md)   
 [How to: Move Data Into and Out of a Variable](../../../../visual-basic/programming-guide/language-features/variables/how-to-move-data-into-and-out-of-a-variable.md)   
 [Data Types](../../../../visual-basic/language-reference/data-types/data-type-summary.md)   
 [Protected](../../../../visual-basic/language-reference/modifiers/protected.md)   
 [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)   
 [Static](../../../../visual-basic/language-reference/modifiers/static.md)   
 [Declared Element Characteristics](../../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-characteristics.md)   
 [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Option Infer Statement](../../../../visual-basic/language-reference/statements/option-infer-statement.md)