---
title: "/optioncompare | Microsoft Docs"
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
  - "/optioncompare"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "optioncompare compiler option [Visual Basic]"
  - "-optioncompare compiler option [Visual Basic]"
  - "/optioncompare compiler option [Visual Basic]"
ms.assetid: 7237b766-b44d-4cc5-9a3c-885348a7d9e4
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /optioncompare
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

문자열 비교 방법을 지정합니다.  
  
## 구문  
  
```  
/optioncompare:{binary | text}  
```  
  
## 설명  
 `/optioncompare`는 두 가지 형식으로 지정할 수 있습니다. 즉, 이진 문자열 비교에는 `/optioncompare:binary`를 사용하고 텍스트 문자열 비교에는 `/optioncompare:text`를 사용합니다.  기본적으로 컴파일러에서는 `/optioncompare:binary`를 사용합니다.  
  
 Microsoft Windows에서는 사용 중인 코드 페이지에 따라 이진 정렬 순서가 결정됩니다.  일반적인 이진 정렬 순서는 다음과 같습니다.  
  
 `A < B < E < Z < a < b < e < z < À < Ê < Ø < à < ê < ø`  
  
 텍스트 기반 문자열 비교는 시스템의 로캘에 지정된 대\/소문자를 구분하지 않는 텍스트 정렬 순서를 기반으로 합니다.  일반적인 텍스트 정렬 순서는 다음과 같습니다.  
  
 `(A = a) < (À = à) < (B=b) < (E=e) < (Ê = ê) < (Z=z) < (Ø = ø)`  
  
### Visual Studio IDE에서 \/optioncompare를 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  **Option Compare** 상자의 값을 수정합니다.  
  
### \/optioncompare를 프로그래밍 방식으로 설정하려면  
  
-   자세한 내용은 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)를 참조하십시오.  
  
## 예제  
 다음 코드에서는 P`rojFile.vb`를 컴파일하고 이진 문자열 비교를 사용합니다.  
  
```  
vbc /optioncompare:binary projFile.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Compare Statement](../../../visual-basic/language-reference/statements/option-compare-statement.md)   
 [옵션 대화 상자, 프로젝트, VB 기본값](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)