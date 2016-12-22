---
title: "/highentropyva (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "highentropyva compiler option (Visual Basic)"
  - "/highentropyva compiler option (Visual Basic)"
ms.assetid: ff25f20a-6ca2-467b-9e52-5cf439f5028e
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /highentropyva (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

나타냅니다 64 비트 실행 파일 또는 실행 파일 표시 됩니다 여부를  [\/platform:anycpu](../../../visual-basic/reference/command-line-compiler/platform.md) 컴파일러 옵션을 지 원하는 높은 엔트로피 주소 공간 레이아웃 불규칙화 \(ASLR\).  
  
## 구문  
  
```  
/highentropyva[+ | -]  
```  
  
## 인수  
 `+` &#124; `-`  
 선택적 요소.  옵션은 기본적으로 꺼져 있고 지정할 경우 `/highentropyva-`.  지정 하는 경우에 옵션입니다 `/highentropyva` 또는 `/highentropyva+`.  
  
## 설명  
 이 옵션을 지정 하면 커널 ASLR의 일부로 프로세스의 주소 공간 레이아웃을 임의 때 호환 되는 버전의 Windows 커널 높은 수준의 엔트로피를 사용할 수 있습니다.  커널은 높은 수준의 엔트로피를 사용 하는 경우 스택 및 힙 메모리 영역에 더 많은 주소를 할당할 수 있습니다.  따라서 특정 메모리 영역의 위치를 추측 하기 더 어렵습니다.  
  
 옵션에는 대상 실행 파일 및 모듈을 켜져 있으면 종속 되는 해당 모듈이 64 비트 프로세스로 실행 하는 경우는 4 기가바이트 \(GB\) 보다 큰 포인터 값을 처리할 수 있어야 합니다.  
  
 ASLR에 대 한 자세한 내용은 참조 하십시오. [소프트웨어 취약점을 완화](http://go.microsoft.com/fwlink/?LinkId=226234).  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)