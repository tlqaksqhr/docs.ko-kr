---
title: "/addmodule | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "/addmodule compiler option [Visual Basic]"
  - "addmodule compiler option [Visual Basic]"
  - "-addmodule compiler option [Visual Basic]"
ms.assetid: fb4b89d4-4926-4f20-868d-427fa28497b2
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /addmodule
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컴파일러가 지정된 파일의 모든 형식 정보를 현재 컴파일 중인 프로젝트에서 사용할 수 있도록 만듭니다.  
  
## 구문  
  
```  
/addmodule:fileList  
```  
  
## 인수  
 `fileList`  
 필수 요소.  메타데이터는 포함되고 어셈블리 매니페스트는 포함되지 않은 파일을 쉼표로 구분한 목록입니다.  파일 이름에 공백이 들어 있는 경우 해당 이름을 따옴표\(" "\)로 묶어야 합니다.  
  
## 설명  
 `fileList` 매개 변수로 나열된 파일은 `/target:module` 옵션을 사용하거나 다른 컴파일러의 `/target:module`에 해당하는 옵션을 사용하여 만들어야 합니다.  
  
 `/addmodule`로 추가한 모든 모듈은 런타임에 출력 파일과 동일한 디렉터리에 있어야 합니다.  즉, 컴파일 타임에는 모든 디렉터리에 모듈을 지정할 수 있지만 런타임에는 모듈이 응용 프로그램 디렉터리에 있어야 합니다.  그렇지 않으면 <xref:System.TypeLoadException> 오류가 발생합니다.  
  
 `/addmodule`과 함께 `/target:module` 이외의 [\/target](../../../visual-basic/reference/command-line-compiler/target.md) 옵션을 암시적 또는 명시적으로 지정하면 `/addmodule`로 전달되는 파일이 프로젝트 어셈블리의 일부가 됩니다.  어셈블리는 `/addmodule`을 사용하여 추가한 파일이 하나 이상 포함된 출력 파일을 실행하는 데 필요합니다.  
  
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)를 사용하여 어셈블리를 포함하는 파일에서 메타데이터를 가져올 수 있습니다.  
  
> [!NOTE]
>  `/addmodule` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 모듈을 만듭니다.  
  
 [!code-vb[VbVbalrCompiler#47](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_1.vb)]  
  
 다음 코드에서는 모듈의 형식을 가져옵니다.  
  
 [!code-vb[VbVbalrCompiler#48](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/addmodule_2.vb)]  
  
 `t1` 을 실행하면 `802`가 출력됩니다.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)