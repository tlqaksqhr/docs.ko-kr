---
title: "/optionstrict | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/optionstrict"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-optionstrict compiler option [Visual Basic]"
  - "optionstrict compiler option [Visual Basic]"
  - "/optionstrict compiler option [Visual Basic]"
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /optionstrict
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

엄격한 형식 의미 확인을 수행하여 암시적인 형식 변환을 제한합니다.  
  
## 구문  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## 인수  
 `+` &#124; `-`  
 선택적 요소.  `/optionstrict+` 옵션은 암시적 형식 변환을 제한합니다.  이 옵션의 기본값은 `/optionstrict-`이며  `/optionstrict+` 옵션은 `/optionstrict`와 동일합니다.  관대한 형식 의미 체계에 두 옵션을 모두 사용할 수 있습니다.  
  
 `custom`  
 필수 요소.  엄격한 언어 의미를 준수하지 않을 경우 경고합니다.  
  
## 설명  
 `/optionstrict+`가 적용되면 형식 확대 변환만 암시적으로 수행할 수 있습니다.  Integer 형식 개체에 `Decimal` 형식 개체를 할당하는 경우와 같은 암시적인 형식 축소 변환은 오류로 보고됩니다.  
  
 암시적 형식 축소 변환에 대한 경고를 생성하려면 `/optionstrict:custom`을 사용합니다.  특정 경고를 무시하려면 `/nowarn:numberlist`를 사용하고 특정 경고를 오류로 처리하려면 `/warnaserror:numberlist`를 사용합니다.  
  
### Visual Studio IDE에서 \/optionstrict를 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 클릭합니다. 자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **컴파일** 탭을 클릭합니다.  
  
3.  **Option Strict** 상자의 값을 수정합니다.  
  
### \/optionstrict를 프로그래밍 방식으로 설정하려면  
  
-   자세한 내용은 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)를 참조하십시오.  
  
## 예제  
 다음 코드에서는 엄격한 형식 의미 체계를 사용하여 `Test.vb`를 컴파일합니다.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)   
 [\/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [옵션 대화 상자, 프로젝트, VB 기본값](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)