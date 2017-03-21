---
title: "Visual Basic 프로그램의 구조 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- conditional compilation, Visual Basic
- program structure, Visual Basic
- procedures, structure
- Visual Basic code, program structure
ms.assetid: ad0c6531-d762-4c77-a700-de16b07b6119
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 64aab045538461d86946c870fa428bf8ad4ec15e
ms.lasthandoff: 03/13/2017

---
# <a name="structure-of-a-visual-basic-program"></a>Visual Basic 프로그램의 구조
A [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램은 표준 구성 요소에서 빌드됩니다. A *솔루션* 하나 이상의 프로젝트를 구성 합니다. A *프로젝트* 어셈블리 하나 이상 포함할 수 있습니다. 각 *어셈블리* 는 하나 이상의 소스 파일에서 컴파일됩니다. A *소스 파일* 정 및 클래스, 구조체, 모듈 및 궁극적으로 모든 코드를 포함 하는 인터페이스의 구현을 제공 합니다.  
  
 이러한 구성 요소에 대 한 자세한 내용은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램의 경우 참조 [솔루션 및 프로젝트](https://docs.microsoft.com/visualstudio/ide/solutions-and-projects-in-visual-studio) 및 [어셈블리 및 전역 어셈블리 캐시](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)합니다.  
  
## <a name="file-level-programming-elements"></a>파일 수준 프로그래밍 요소  
 프로젝트 또는 파일을 시작 하 고 코드 편집기를 열고 일부 코드가 이미 있는 및 올바른 순서로 표시 됩니다. 모든 코드를 작성할 때는 다음 순서를 따라야 합니다.  
  
1.  `Option`문  
  
2.  `Imports`문  
  
3.  `Namespace`문 및 네임 스페이스 수준 요소  
  
 다른 순서로 명령문을 입력 하는 경우 컴파일 오류가 발생할 수 있습니다.  
  
 프로그램에는 조건부 컴파일 문에 포함할 수도 있습니다. 앞에 나온 일련의 문 함께 소스 파일에서 이러한 중간에 삽입할 수 있습니다.  
  
### <a name="option-statements"></a>Option 문  
 `Option`문 구문 및 논리 오류를 방지 하기 위해 노력 하는 후속 코드에 대 한 기본 규칙을 구성 합니다. [Option Explicit 문](../../../visual-basic/language-reference/statements/option-explicit-statement.md) 는 모든 변수 선언 되 고 철자가 디버깅 시간을 줄여주는 보장 합니다. [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md) 서로 다른 데이터 형식의 변수 사이 작업할 때 발생할 수 있는 논리 오류 및 데이터 손실을 최소화 하는 데 도움이 됩니다. [옵션 비교 문](../../../visual-basic/language-reference/statements/option-compare-statement.md) 서로 기반 방식으로 문자열 비교 지정 자신의 `Binary` 또는 `Text` 값입니다.  
  
### <a name="imports-statements"></a>Imports 문  
 포함할 수는 [Imports 문 (.NET Namespace 및 형식)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md) 프로젝트 외부에 정의 된 이름을 가져올 수 있습니다. `Imports` 문은 코드를 클래스와 기타 형식을 한정 하지 않고는 가져온된 네임 스페이스 내에 정의 된 참조를 허용 합니다. 만큼 사용할 수 `Imports` 문을 적절 하 게 합니다. 자세한 내용은 참조 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)합니다.  
  
### <a name="namespace-statements"></a>Namespace 문  
 네임 스페이스 도움말 구성 하 고 그룹화 하 고 액세스 하는 편의 위해 프로그래밍 요소를 분류 합니다. 사용의 [Namespace 문을](../../../visual-basic/language-reference/statements/namespace-statement.md) 특정 네임 스페이스 내에서 다음 문을 분류할 수 있습니다. 자세한 내용은 참조 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)합니다.  
  
### <a name="conditional-compilation-statements"></a>조건부 컴파일 문은  
 조건부 컴파일 문은 원본 파일에서 거의 모든 곳에 나타날 수 있습니다. 일부 코드를 포함 하거나 제외할 특정 조건에 따라 컴파일 타임에 발생 합니다. 사용할 수도 있습니다 이러한 응용 프로그램을 디버깅 하는 것에 대 한 조건부 코드 디버깅 모드 에서만 실행 되므로 합니다. 자세한 내용은 참조 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)합니다.  
  
## <a name="namespace-level-programming-elements"></a>Namespace 수준 프로그래밍 요소  
 클래스, 구조체 및 모듈에는 원본 파일의 모든 코드를 포함 합니다. 이들은 *네임 스페이스 수준* 요소 네임 스페이스 내에서 또는 소스 파일 수준에서 표시 될 수 있습니다. 다른 모든 프로그래밍 요소 선언이 포함 됩니다. 인터페이스 요소 서명을 정의 되지만 구현이 제공 하는 모듈 수준에도 나타납니다. 모듈 수준 요소에 대 한 자세한 내용은 다음을 참조 합니다.  
  
-   [Class 문](../../../visual-basic/language-reference/statements/class-statement.md)  
  
-   [Structure 문](../../../visual-basic/language-reference/statements/structure-statement.md)  
  
-   [Module 문](../../../visual-basic/language-reference/statements/module-statement.md)  
  
-   [Interface 문](../../../visual-basic/language-reference/statements/interface-statement.md)  
  
 네임 스페이스 수준에서 데이터 요소는 열거형 및 대리자입니다.  
  
## <a name="module-level-programming-elements"></a>모듈 수준 프로그래밍 요소  
 프로시저, 연산자, 속성 및 이벤트는 실행 코드 (실행 시 작업을 수행 하는 문)을 보유할 수 있는 유일한 프로그래밍 요소입니다. 이들은 *모듈 수준* 프로그램의 요소입니다. 프로시저 수준 요소에 대 한 자세한 내용은 다음을 참조 합니다.  
  
-   [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
-   [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
-   [Operator 문](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
-   [Property 문](../../../visual-basic/language-reference/statements/property-statement.md)  
  
-   [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)  
  
 모듈 수준에서 데이터 요소에는 변수, 상수, 열거형 및 대리자는입니다.  
  
## <a name="procedure-level-programming-elements"></a>프로시저 수준 프로그래밍 요소  
 내용 대부분 *프로시저 수준* 요소는 구성 하는 프로그램의 런타임 코드를 구성 합니다. 일부 절차의 모든 실행 코드 여야 합니다 (`Function`, `Sub`, `Operator`, `Get`, `Set`, `AddHandler`, `RemoveHandler`, `RaiseEvent`). 자세한 내용은 참조 [문을](../../../visual-basic/programming-guide/language-features/statements.md)합니다.  
  
 프로시저 수준에서 데이터 요소는 로컬 변수 및 상수 제한 됩니다.  
  
## <a name="the-main-procedure"></a>Main 프로시저  
 `Main` 절차는 응용 프로그램 로드 되었을 때 실행 하는 첫 번째 코드입니다. `Main`시작 지점 및 응용 프로그램에 대 한 전체 제어 하는 데 사용 합니다. 네 가지가 `Main`:  
  
-   `Sub Main()`  
  
-   `Sub Main(ByVal cmdArgs() As String)`  
  
-   `Function Main() As Integer`  
  
-   `Function Main(ByVal cmdArgs() As String) As Integer`  
  
 이 절차의 가장 일반적인 것은 `Sub Main()`합니다. 자세한 내용은 참조 [Visual Basic의 Main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Visual Basic의 main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)   
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [Visual Basic 제한 사항](../../../visual-basic/programming-guide/program-structure/limitations.md)
