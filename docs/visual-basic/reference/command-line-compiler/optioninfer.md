---
title: "/optioninfer | Microsoft Docs"
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
  - "/optioninfer"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-optioninfer compiler option [Visual Basic]"
  - "/optioninfer compiler option [Visual Basic]"
  - "optioninfer compiler option [Visual Basic]"
ms.assetid: f6c09db1-0553-464a-abe3-d4510c61d6ed
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /optioninfer
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

변수 선언에서 지역 형식 유추를 사용하도록 설정합니다.  
  
## 구문  
  
```  
/optioninfer[+ | -]  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`+`  &#124; `-`|선택 사항입니다.  지역 형식 유추를 사용하도록 설정하려면 `/optioninfer+`를 지정하고, 차단하려면 `/optioninfer-`를 지정합니다.  값을 지정하지 않은 `/optioninfer` 옵션은 `/optioninfer+`와 같습니다.  `/optioninfer` 스위치가 없을 때의 기본값도 `/optioninfer+`입니다.  기본값은 vbc.rsp 지시 파일에서 설정됩니다.|  
  
> [!NOTE]
>  `/noconfig` 옵션을 사용하여 vbc.rsp에 지정된 값 대신 컴파일러의 내부 기본값을 유지할 수 있습니다.  이 옵션에 대한 컴파일러 기본값은 `/optioninfer-`입니다.  
  
## 설명  
 소스 코드 파일에 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md)이 포함되어 있으면 해당 문이 `/optioninfer` 명령줄 컴파일러 설정을 재정의합니다.  
  
### Visual Studio IDE에서 \/optioninfer를 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 클릭합니다.  자세한 내용은 [NIB: Managing Project Properties with the Project Designer](http://msdn.microsoft.com/ko-kr/983f3c18-832f-4666-afec-74b716ff3e0e)을 참조하십시오.  
  
2.  **컴파일** 탭에서 **Option infer** 상자의 값을 수정합니다.  
  
## 예제  
 다음 코드에서는 지역 형식 유추를 사용하도록 설정한 상태로 `test.vb`를 컴파일합니다.  
  
```  
vbc /optioninfer+ test.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optionstrict](../../../visual-basic/reference/command-line-compiler/optionstrict.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [옵션 대화 상자, 프로젝트, VB 기본값](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)   
 [프로젝트 디자이너, 컴파일 페이지\(Visual Basic\)](/visual-studio/ide/reference/compile-page-project-designer-visual-basic)   
 [\/noconfig](../../../visual-basic/reference/command-line-compiler/noconfig.md)   
 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)