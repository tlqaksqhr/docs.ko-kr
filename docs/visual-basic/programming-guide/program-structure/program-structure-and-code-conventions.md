---
title: "프로그램 구조 및 코드 규칙(Visual Basic) | Microsoft Docs"
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
  - "코딩 규칙"
  - "Visual Basic 코드, 코딩 규칙"
  - "코딩 규칙, Visual Basic"
  - "프로그램, 구조"
  - "프로그램 구조"
  - "명명 규칙, Visual Basic"
  - "모범 사례, 코딩 규칙"
  - "규칙, Visual Basic 코딩"
  - "Visual Basic 코드"
  - "프로그래밍, Visual Basic 코딩 규칙"
ms.assetid: dd9be76f-6944-4e78-ad72-0b6084a3fc13
caps.latest.revision: 21
caps.handback.revision: 21
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 프로그램 구조 및 코드 규칙(Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 단원에서는 일반적인 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램 구조를 소개하고, 간단한 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램인 "Hello, World"를 제공하며, [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드 규칙에 대해 설명합니다.  코드 규칙은 프로그램의 논리가 아니라 물리적 구조 및 모양에 중점을 둔 제안 사항입니다.  코드 규칙을 따르면 코드를 읽고 이해하며 관리하기가 쉬워집니다.  코드 규칙에 포함되는 사항은 다음과 같습니다.  
  
-   코드에 레이블을 지정하고 주석을 표시하는 표준화된 형식  
  
-   코드의 공백, 형식 지정 및 들여쓰기에 대한 지침  
  
-   개체, 변수 및 프로시저에 대한 명명 규칙  
  
 다음 항목에서는 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램에 대한 프로그래밍 지침을 제공하고 올바른 사용 예제를 보여 줍니다.  
  
## 단원 내용  
 [Structure of a Visual Basic Program](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램을 구성하는 요소에 대해 간략하게 설명합니다.  
  
 [Main Procedure in Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)  
 응용 프로그램의 시작 위치를 나타내며 해당 응용 프로그램을 전체적으로 제어하는 데 사용되는 프로시저에 대해 설명합니다.  
  
 [References and the Imports Statement](../../../visual-basic/programming-guide/program-structure/references-and-the-imports-statement.md)  
 다른 어셈블리에 있는 개체를 참조하는 방법에 대해 설명합니다.  
  
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)  
 어셈블리 내에서 네임스페이스가 개체를 구성하는 방식에 대해 설명합니다.  
  
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)  
 프로시저, 상수, 변수, 인수 및 개체에 대한 일반적인 명명 규칙에 대해 설명합니다.  
  
 [Visual Basic Coding Conventions](../../../visual-basic/programming-guide/program-structure/coding-conventions.md)  
 이 설명서에서는 샘플을 개발하는 데 사용되는 지침에 대해 살펴 봅니다.  
  
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)  
 특정 코드 블록만 선택적으로 컴파일하고 컴파일러에서 다른 코드 블록을 무시하도록 하는 방법에 대해 설명합니다.  
  
 [방법: 코드에서 문 분리 및 결합](../Topic/How%20to:%20Break%20and%20Combine%20Statements%20in%20Code%20\(Visual%20Basic\).md)  
 긴 문을 여러 줄로 나누는 방법과 여러 개의 짧은 문을 한 줄로 결합하는 방법을 보여 줍니다.  
  
 [How to: Collapse and Hide Sections of Code](../../../visual-basic/programming-guide/program-structure/how-to-collapse-and-hide-sections-of-code.md)  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 코드 편집기에서 코드 섹션을 축소하고 숨기는 방법을 보여 줍니다.  
  
 [How to: Label Statements](../../../visual-basic/programming-guide/program-structure/how-to-label-statements.md)  
 `On Error Goto`와 같은 문에서 사용하기 위한 식별 코드 줄을 표시하는 방법을 보여 줍니다.  
  
 [Special Characters in Code](../../../visual-basic/programming-guide/program-structure/special-characters-in-code.md)  
 숫자나 영문자가 아닌 문자의 사용 방법 및 위치를 보여 줍니다.  
  
 [Comments in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 코드에 설명용 주석을 추가하는 방법에 대해 설명합니다.  
  
 [Keywords as Element Names in Code](../../../visual-basic/programming-guide/program-structure/keywords-as-element-names-in-code.md)  
 대괄호\(`[]`\)를 사용하여 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 키워드이기도 한 변수 이름을 구분하는 방법에 대해 설명합니다.  
  
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 프로그램의 요소를 참조하는 여러 가지 방법에 대해 설명합니다.  
  
 [Visual Basic Limitations](../../../visual-basic/programming-guide/program-structure/limitations.md)  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에서 코드를 작성할 때의 알려진 제한 사항을 제거하는 방법에 대해 설명합니다.  
  
## 관련 단원  
 [Typographic and Code Conventions](../../../visual-basic/language-reference/typographic-and-code-conventions.md)  
 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]에 대한 표준 코딩 규칙을 제공합니다.  
  
 [코드 작성](/visual-studio/ide/writing-code-in-the-code-and-text-editor)  
 코드를 더 쉽게 작성 및 관리할 수 있도록 하는 기능에 대해 설명합니다.