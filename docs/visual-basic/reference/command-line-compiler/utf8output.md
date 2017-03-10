---
title: "/utf8output (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-utf8output compiler option [Visual Basic]"
  - "utf8output compiler option [Visual Basic]"
  - "/utf8output compiler option [Visual Basic]"
ms.assetid: 8ab36b1e-027a-49ac-85b4-f48997d9e4d6
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /utf8output (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

UTF\-8 인코딩을 사용하여 컴파일러 출력을 표시합니다.  
  
## 구문  
  
```  
/utf8output[+ | -]  
```  
  
## 인수  
 `+` &#124; `-`  
 선택적 요소.  이 옵션의 기본값은 `/utf8output-`로 이 경우 컴파일러 출력에 UTF\-8 인코딩을 사용하지 않습니다.  `/utf8output`을 지정하는 것은 `/utf8output+`를 지정하는 것과 같습니다.  
  
## 설명  
 일부 국가별 구성에서는컴파일러 출력이 콘솔에 올바르게 표시되지 않을 수 있습니다.  이러한 구성에서는 `/utf8output`을 사용하여 컴파일러 출력을 파일로 리디렉션합니다.  
  
> [!NOTE]
>  `/utf8output` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드는 `In.vb`를 컴파일하고 컴파일러에게 UTF\-8 인코딩을 사용하여 출력을 표시하도록 지시합니다.  
  
```  
vbc /utf8output in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)