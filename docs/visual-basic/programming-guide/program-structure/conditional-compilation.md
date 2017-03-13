---
title: "Conditional Compilation in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conditional compilation, about conditional compilation"
  - "compilation, conditional"
ms.assetid: 9c35e55e-7eee-44fb-a586-dad1f1884848
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Conditional Compilation in Visual Basic
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

*조건부 컴파일*에서는 프로그램의 특정 코드 블록이 선택적으로 컴파일되고 나머지 코드 부분은 무시됩니다.  
  
 예를 들어 동일한 프로그래밍 작업을 서로 다른 방식으로 수행하여 각각의 속도를 비교하는 디버깅 문을 작성하는 경우, 또는 특정 응용 프로그램을 여러 언어로 지역화하는 경우가 있습니다.  조건부 컴파일 문은 런타임에서가 아니라 컴파일 타임에 실행되도록 만들어졌습니다.  
  
 `#If...Then...#Else` 지시문을 사용하여 조건부로 컴파일할 코드 블록을 나타냅니다.  예를 들어, 동일한 소스 코드를 사용하여 프랑스어 및 독일어 버전의 동일한 응용 프로그램을 만들려면 미리 정의된 상수 `FrenchVersion`과 `GermanVersion`을 사용하여 플랫폼별 코드 세그먼트를 `#If...Then` 문에 포함합니다.  다음 예제는 그 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrConditionalComp#5](../../../visual-basic/language-reference/directives/codesnippet/VisualBasic/conditional-compilation_1.vb)]  
  
 컴파일 타임에 `FrenchVersion` 조건부 컴파일 상수 값을 `True`로 설정하면 프랑스어 버전의 조건부 코드가 컴파일되고  `GermanVersion` 상수 값을 `True`로 설정하면 독일어 버전이 컴파일됩니다.  `True`로 설정된 상수 값이 없으면 마지막 `Else` 블록의 코드가 실행됩니다.  
  
> [!NOTE]
>  코드가 현재 분기의 일부가 아닌 경우에는 코드를 편집하고 조건부 컴파일 지시문을 사용할 때 자동 완성이 작동하지 않습니다.  
  
## 조건부 컴파일 상수 선언  
 조건부 컴파일 상수는 다음 세 가지 방법을 사용하여 설정할 수 있습니다.  
  
-   **프로젝트 디자이너**에서 설정  
  
-   명령줄 컴파일러를 사용하는 경우 명령줄에서 설정  
  
-   코드에서 설정  
  
 조건부 컴파일 상수는 특별한 범위를 가지며 일반 코드로는 액세스할 수 없습니다.  조건부 컴파일 상수는 설정 방법에 따라 범위가 달라집니다.  다음 표에서는 위의 세 가지 방법을 사용하여 선언한 상수의 범위를 설명합니다.  
  
|||  
|-|-|  
|상수 설정 방법|상수의 범위|  
|**프로젝트 디자이너**|프로젝트의 모든 파일에서 사용할 수 있습니다.|  
|명령줄|명령줄 컴파일러로 전달된 모든 파일에서 사용할 수 있습니다.|  
|`#Const` 문\(코드\)|문이 선언된 파일에서만 사용할 수 있습니다.|  
  
||  
|-|  
|프로젝트 디자이너에서 상수를 설정하려면|  
|-   실행 파일을 만들기 전에 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)에서 설명하는 단계에 따라 **프로젝트 디자이너**에서 상수를 설정합니다.|  
  
||  
|-|  
|명령줄에서 상수를 설정하려면|  
|-   다음 예제와 같이 **\/d** 스위치를 사용하여 조건부 컴파일 상수를 입력합니다.<br />     `vbc MyProj.vb /d:conFrenchVersion=–1:conANSI=0`<br />     **\/d** 스위치와 첫 번째 상수 사이에는 공백을 두지 않습니다.  자세한 내용은 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)을 참조하십시오.<br />     명령줄 선언은 **프로젝트 디자이너**에 입력된 선언을 재정의하지만 해당 선언을 지우지는 않습니다.  **프로젝트 디자이너**에 설정된 인수는 다음에 컴파일할 때도 유효합니다.<br />     코드에 상수를 쓰는 경우 상수를 선언한 전체 모듈이 범위가 되므로 위치에 대해서는 엄격한 규칙이 없습니다.|  
  
||  
|-|  
|코드에서 상수를 설정하려면|  
|-   상수가 사용되는 모듈의 선언 블록에 상수를 놓습니다.  이렇게 하면 코드가 정리되어 이해하기 쉬워집니다.|  
  
## 관련 항목  
  
|||  
|-|-|  
|제목|설명|  
|[프로그램 구조 및 코드 규칙](../../../visual-basic/programming-guide/program-structure/program-structure-and-code-conventions.md)|쉽게 이해하고 관리할 수 있는 코드를 작성하는 방법에 대해 설명합니다.|  
  
## 참조  
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md)  
  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
  
 [\/define](../../../visual-basic/reference/command-line-compiler/define.md)