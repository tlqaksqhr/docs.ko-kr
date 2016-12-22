---
title: "Structure of a Visual Basic Program | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "conditional compilation, Visual Basic"
  - "program structure, Visual Basic"
  - "procedures, structure"
  - "Visual Basic code, program structure"
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Structure of a Visual Basic Program
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

[!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램은 표준 빌딩 블록에서 빌드됩니다.  *솔루션*은 하나 이상의 프로젝트로 구성됩니다.  따라서 *프로젝트*는 하나 이상의 어셈블리를 포함할 수 있습니다.  각 *어셈블리*는 하나 이상의 소스 파일에서 컴파일됩니다.  *소스 파일*은 사용자의 모든 코드를 포함하는 클래스, 구조체, 모듈 및 인터페이스의 정의와 구현을 제공합니다.  
  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램의 이러한 빌딩 블록에 대한 자세한 내용은 [솔루션 및 프로젝트](/visual-studio/ide/solutions-and-projects-in-visual-studio) 및 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
## 파일 수준 프로그래밍 요소  
 프로젝트나 파일을 시작하고 코드 편집기를 열면 일부 코드가 이미 적절한 위치에 올바른 순서로 표시되어 있습니다.  다음 순서를 따라 코드를 작성해야 합니다.  
  
1.  `Option` 문  
  
2.  `Imports` 문  
  
3.  `Namespace` 문 및 네임스페이스 수준 요소  
  
 위와 다른 순서로 문을 입력하면 오류가 발생할 수 있습니다.  
  
 프로그램은 조건부 컴파일 문을 포함할 수도 있습니다.  이러한 조건부 컴파일 문을 위에 나온 시퀀스의 문과 함께 소스 파일에서 사용할 수 있습니다.  
  
### Option 문  
 `Option` 문을 사용하면 그 다음 코드에 대해 기본 규칙을 구성하여 구문 오류와 논리 오류가 발생하지 않도록 합니다.  [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md)을 사용하면 모든 변수를 제대로 선언하고 변수의 철자를 올바르게 유지하여 디버깅 시간을 줄일 수 있습니다.  [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)을 사용하면 서로 다른 데이터 형식의 변수 사이에서 작업할 때 발생할 수 있는 논리 오류와 데이터 손실을 최소화할 수 있습니다.  [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)은 문자열의 `Binary` 또는 `Text` 값에 따라 문자열을 비교하는 방법을 지정합니다.  
  
### Imports 문  
 프로젝트 외부에서 정의된 이름을 가져올 수 있는 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)을 포함할 수 있습니다.  `Imports` 문을 사용하면 가져온 네임스페이스 내에서 정의된 클래스 및 기타 형식을 한정하지 않고도 코드에서 참조할 수 있습니다.  적절한 범위 내에서 가능한 한 많은 수의 `Imports` 문을 사용할 수 있습니다.  자세한 내용은 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)를 참조하십시오.  
  
### Namespace 문  
 네임스페이스를 사용하면 그룹화 및 액세스에 용이하도록 프로그래밍 요소를 구성하고 분류할 수 있습니다.  [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)을 사용하여 특정 네임스페이스 내에서 다음 문을 분류할 수 있습니다.  자세한 내용은 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)를 참조하십시오.  
  
### 조건부 컴파일 문  
 조건부 컴파일 문은 소스 파일 내의 거의 모든 위치에 사용할 수 있습니다.  조건부 컴파일 문을 사용하면 특정 조건에 따라 코드의 일부가 컴파일 타임에 포함되거나 제외됩니다.  조건부 코드는 디버깅 모드에서만 실행되므로 응용 프로그램을 디버깅할 때에도 이 문을 사용할 수 있습니다.  자세한 내용은 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)를 참조하십시오.  
  
## 네임스페이스 수준 프로그래밍 요소  
 클래스, 구조체 및 모듈에는 소스 파일의 모든 코드가 포함되어 있습니다.  또한 이들은 *네임스페이스 수준* 요소이므로 네임스페이스 내부에 또는 소스 파일 수준으로 표시될 수 있습니다.  클래스, 구조체 및 모듈은 다른 모든 프로그래밍 요소의 선언을 저장합니다.  요소 시그니처를 정의하지만 구현을 제공하지는 않는 인터페이스는 모듈 수준으로도 표시됩니다.  모듈 수준 요소에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [Class Statement](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure Statement](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 네임스페이스 수준의 데이터 요소에는 열거형과 대리자가 있습니다.  
  
## 모듈 수준 프로그래밍 요소  
 프로시저, 연산자, 속성 및 이벤트는 실행 코드\(런타임에 작업을 수행하는 문\)를 저장할 수 있는 유일한 프로그래밍 요소입니다.  이들은 프로그램의 *모듈 수준* 요소입니다.  프로시저 수준 요소에 대한 자세한 내용은 다음을 참조하십시오.  
  
-   [Function Statement](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub Statement](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 모듈 수준 데이터 요소로는 변수, 상수, 열거형, 대리자 등이 있습니다.  
  
## 프로시저 수준 프로그래밍 요소  
 *프로시저 수준* 요소의 내용 중 대부분은 프로그램의 런타임 코드를 구성하는 실행문입니다.  모든 실행 코드는 일부 프로시저\(`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`\) 안에 있어야 합니다.  자세한 내용은 [Statements](../../../visual-basic/programming-guide/language-features/statements.md)을 참조하십시오.  
  
 프로시저 수준의 데이터 요소는 지역 변수와 상수로 제한됩니다.  
  
## Main 프로시저  
 `Main` 프로시저는 응용 프로그램을 로드했을 떼 실행할 첫 번째 코드입니다.  `Main`은 응용 프로그램의 시작 위치를 나타내며 해당 응용 프로그램을 전체적으로 제어하는 데 사용됩니다.  `Main`은 네 가지 형태로 사용됩니다.  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 이러한 프로시저 중에서 가장 일반적인 것은 `Sub Main()`입니다.  자세한 내용은 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)를 참조하십시오.  
  
## 참고 항목  
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/ko-kr/9d030b60-e148-4366-a462-69532f02294c)   
 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)