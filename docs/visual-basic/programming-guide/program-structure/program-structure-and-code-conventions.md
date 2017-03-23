---
title: "프로그램 구조 및 코드 규칙 (Visual Basic) | Microsoft 문서"
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
- coding conventions
- Visual Basic code, coding conventions
- coding conventions, Visual Basic
- programs, structure
- program structure
- naming conventions, Visual Basic
- best practices, coding conventions
- conventions, Visual Basic coding
- Visual Basic code
- programming, Visual Basic coding conventions
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: cd25d99d74bf1e4d416c9da63758f6ad04027258
ms.lasthandoff: 03/13/2017

---
# <a name="program-structure-and-code-conventions-visual-basic"></a>프로그램 구조 및 코드 규칙(Visual Basic)
이 섹션에서는 일반적인 소개 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램 구조, 간단한 제공 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] "Hello, World" 프로그램을 설명 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드 규칙입니다. 코드 규칙은 프로그램의 논리에 없는 있지만 물리적 구조 및 모양에 초점을 두는 제안 사항입니다. 그 뒤에 쉽게 코드를 읽고, 이해 하 고, 유지 관리 합니다. 코드 규칙 중 일부 포함할 수 있습니다.  
  
-   하 고 코드를 주석 처리 하기 위한 표준화 된 형식입니다.  
  
-   간격, 서식 및 코드 들여쓰기에 대 한 지침입니다.  
  
-   개체, 변수 및 프로시저에 대 한 명명 규칙입니다.  
  
 다음 항목은 일련의 프로그래밍에 대 한 지침을 제공 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 올바른 사용의 예도 함께 프로그램입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [Visual Basic 프로그램의 구조](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 구성 하는 요소에 간략하게는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.  
  
 [Visual Basic의 main 프로시저](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 역할의 시작을 가리키고 전체적으로 응용 프로그램에 대 한 제어 하는 절차를 설명 합니다.  
  
 [참조 및 Imports 문](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 다른 어셈블리의 개체를 참조 하는 방법에 설명 합니다.  
  
 [Visual Basic의 네임 스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 네임 스페이스 어셈블리 내에서 개체를 구성 하는 방법에 대해 설명 합니다.  
  
 [Visual Basic 명명 규칙](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 프로시저, 상수, 변수, 인수 및 개체 명명에 대 한 일반적인 지침을 포함 합니다.  
  
 [Visual Basic 코딩 규칙](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 이 설명서의 예제를 개발에 사용 되는 지침을 검토 합니다.  
  
 [조건부 컴파일](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 다른 사용자를 무시 하도록 컴파일러에 지시 하는 동안 특정 코드 블록을 선택적으로 컴파일하는 방법을 설명 합니다.  
  
 [방법: 코드에서 문 분리 및 결합](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)  
 긴 문은 여러 줄으로 나누고 짧은 문을 한 줄에 결합 하는 방법을 보여 줍니다.  
  
 [방법: 코드 섹션 축소 및 숨기기](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 코드 섹션 축소 및 숨기기 하는 방법을 보여 줍니다는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드 편집기입니다.  
  
 [방법: Label 문](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 사용 하기 위해 문으로 같은 식별 하는 코드 줄을 표시 하는 방법을 보여 줍니다. `On Error Goto`합니다.  
  
 [코드의 특수 문자](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 위치와 방법을 보여 줍니다. 숫자가 아닌 및 알파벳이 아닌 문자를 사용 하도록 합니다.  
  
 [코드 주석](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 코드에 설명을 추가 하는 방법에 설명 합니다.  
  
 [코드에서 요소 이름으로 사용되는 키워드](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 대괄호를 사용 하는 방법에 설명 (`[]`) 되는 변수 이름을 구분 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 키워드입니다.  
  
 [Me, My, MyBase 및 MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 요소를 참조 하는 다양 한 방법에 설명 된 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램입니다.  
  
 [Visual Basic 제한 사항](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 내에서 코딩 알려진된 제한 사항 제거에 설명 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [글꼴 표시 및 코드 규칙](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 에 대 한 표준 코딩 규칙을 제공 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]합니다.  
  
 [코드 작성](https://docs.microsoft.com/visualstudio/ide/writing-code-in-the-code-and-text-editor)  
 쉽게 작성 하 고 코드를 관리 하는 기능에 설명 합니다.
