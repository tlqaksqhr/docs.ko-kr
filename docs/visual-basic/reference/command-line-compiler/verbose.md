---
title: "/verbose | Microsoft Docs"
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
  - "verbose compiler option [Visual Basic]"
  - "-verbose compiler option [Visual Basic]"
  - "/verbose compiler option [Visual Basic]"
ms.assetid: d1aec0c1-0261-421d-9adc-5b13756100be
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /verbose
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러가 자세한 상태 정보와 오류 메시지를 출력합니다.  
  
## 구문  
  
```  
/verbose[+ | -]  
```  
  
## 인수  
 `+` &#124; `-`  
 선택적 요소.  `/verbose`를 지정할 때와 `/verbose+`를 지정할 때의 결과는 같습니다. 즉, 컴파일러가 자세한 메시지를 출력합니다.  이 옵션의 기본값은 `/verbose-`입니다.  
  
## 설명  
 `/verbose` 옵션은 컴파일러에서 생성한 총 오류 수에 대한 정보를 표시하고, 모듈에서 어떤 어셈블리를 로드하고 있는지 보고하고, 현재 컴파일 중인 파일을 표시합니다.  
  
> [!NOTE]
>  `/verbose` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 `In.vb`를 컴파일하고 자세한 상태 정보를 표시하도록 컴파일러에 지시합니다.  
  
```  
vbc /verbose in.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)