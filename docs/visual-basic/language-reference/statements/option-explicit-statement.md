---
title: "Option Explicit Statement (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Explicit"
  - "vb.OptionExplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "declaring variables, explicit"
  - "forced variable declaration in Option Explicit statement"
  - "Explicit keyword"
  - "explicit variable declaration"
  - "Option Explicit statement"
ms.assetid: e82ac1ad-2cd3-49b2-b985-8bcf016f3fcc
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# Option Explicit Statement (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

파일에 있는 모든 변수를 명시적으로 강제 선언하거나 변수의 암시적 선언을 허용합니다.  
  
## 구문  
  
```  
Option Explicit { On | Off }  
```  
  
## 요소  
 `On`  
 선택적 요소.  `Option Explicit` 검사를 설정합니다.  `On` 또는 `Off`가 지정되지 않은 경우 기본값은 `On`입니다.  
  
 `Off`  
 선택적 요소.  `Option Explicit` 검사를 해제합니다.  
  
## 설명  
 파일에 `Option Explicit On` 또는 `Option Explicit`이 나타나는 경우 `Dim` 또는 `ReDim` 문을 사용하여 모든 변수를 명시적으로 선언해야 합니다.  선언되지 않은 변수 이름을 사용하는 경우 컴파일 타임에 오류가 발생합니다.  `Option Explicit Off` 문을 사용하면 변수를 암시적으로 선언할 수 있습니다.  
  
 이 요소를 사용하는 경우 `Option Explicit` 문은 파일에서 원본 코드 문의 제일 앞에 와야 합니다.  
  
> [!NOTE]
>  일반적으로 `Option Explicit`를 `Off`로 설정하는 것은 좋지 않습니다.  하나 이상의 위치에서 변수 이름을 잘못 입력하면 프로그램이 실행될 때 예상하지 않은 결과가 나타날 수 있습니다.  
  
## Option Explicit 문이 없는 경우  
 소스 코드에 `Option Explicit` 문이 없으면 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)의 **Option Explicit** 설정이 사용됩니다.  명령줄 컴파일러가 사용된 경우 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션이 사용됩니다.  
  
#### IDE에서 Option Explicit을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  **Option Explicit** 상자에서 값을 설정합니다.  
  
 새 프로젝트를 만들면 **컴파일** 탭의 **Option Explicit** 설정이 **VB 기본값** 대화 상자에서 **Option Explicit** 설정으로 설정됩니다.  **VB 기본값** 대화 상자에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭합니다.  **옵션** 대화 상자에서 **프로젝트 및 솔루션**을 확장한 다음 **VB 기본값**을 클릭합니다.  **VB 기본값**의 최초 기본 설정은 `On`입니다.  
  
#### 명령줄에서 Option Explicit을 설정하려면  
  
-   **vbc** 명령에 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md) 컴파일러 옵션을 포함합니다.  
  
## 예제  
 다음 예제에서는 `Option Explicit` 문을 사용하여 모든 변수를 명시적으로 강제 선언합니다.  선언되지 않은 변수를 사용하는 경우 컴파일 타임 오류가 발생합니다.  
  
 [!code-vb[VbVbalrStatements#47](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-explicit-statement_1.vb)]  
  
 [!code-vb[VbVbalrStatements#48](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/option-explicit-statement_2.vb)]  
  
## 참고 항목  
 [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md)   
 [ReDim Statement](../../../visual-basic/language-reference/statements/redim-statement.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [옵션 대화 상자, 프로젝트, VB 기본값](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)