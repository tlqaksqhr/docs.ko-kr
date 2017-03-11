---
title: "/optionexplicit | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optionexplicit"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optionexplicit compiler option [Visual Basic]"
  - "optionexplicit compiler option [Visual Basic]"
  - "-optionexplicit compiler option [Visual Basic]"
ms.assetid: 5d296ab3-bafe-4c4d-9887-78f162ed86c7
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /optionexplicit
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

변수를 선언하지 않고 사용할 경우 컴파일러에서 오류를 보고합니다.  
  
## 구문  
  
```  
/optionexplicit[+ | -]  
```  
  
## 인수  
 `+` &#124; `-`  
 선택적 요소.  명시적인 변수 선언을 수행하도록 하려면 `/optionexplicit+`를 지정합니다.  `/optionexplicit+` 옵션은 기본값이며 `/optionexplicit`와 같습니다.  `/optionexplicit-` 옵션을 사용하면 변수를 암시적으로 선언할 수 있습니다.  
  
## 설명  
 소스 코드에 [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md) 문이 있으면 해당 문이 `/optionexplicit` 명령줄 컴파일러 설정을 재정의합니다.  
  
### Visual Studio IDE에서 \/optionexplicit를 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  **Option Explicit** 상자에서 값을 수정합니다.  
  
## 예제  
 다음 코드는 `/optionexplicit-`가 사용된 경우에 컴파일합니다.  
  
 [!code-vb[VbVbalrCompiler#5](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/optionexplicit_1.vb)]  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Explicit Statement](../../../visual-basic/language-reference/statements/option-explicit-statement.md)   
 [옵션 대화 상자, 프로젝트, VB 기본값](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)