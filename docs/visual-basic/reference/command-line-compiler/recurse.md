---
title: "/recurse | Microsoft Docs"
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
  - "/recurse compiler option [Visual Basic]"
  - "-recurse compiler option [Visual Basic]"
  - "recurse compiler option [Visual Basic]"
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# /recurse
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

지정한 디렉터리 또는 프로젝트 디렉터리의 모든 자식 디렉터리에 있는 소스 코드 파일을 컴파일합니다.  
  
## 구문  
  
```  
/recurse:[dir\]file  
```  
  
## 인수  
 `dir`  
 선택적 요소.  검색을 시작할 디렉터리입니다.  이 옵션을 지정하지 않으면 프로젝트 디렉터리에서 검색을 시작합니다.  
  
 `file`  
 필수 요소.  검색할 파일입니다.  와일드카드 문자를 사용할 수 있습니다.  
  
## 설명  
 `/recurse`를 사용하지 않고 파일 이름에 와일드카드를 사용하여 프로젝트 디렉터리에서 일치하는 모든 파일을 컴파일할 수 있습니다.  출력 파일의 이름이 지정되어 있지 않으면 컴파일러는 첫 번째로 처리한 입력 파일을 출력 파일의 이름으로 사용합니다.  이것은 대개 컴파일된 파일 목록을 사전순으로 표시할 때 처음으로 나오는 파일입니다.  따라서 `/out` 옵션을 사용하여 출력 파일을 지정하는 것이 좋습니다.  
  
> [!NOTE]
>  `/recurse` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 현재 디렉터리의 모든 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 파일을 컴파일합니다.  
  
```  
vbc *.vb  
```  
  
 다음 코드에서는 `Test\ABC` 디렉터리와 이 디렉터리의 모든 하위 디렉터리에 있는 모든 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 파일을 컴파일하여 `Test.ABC.dll`을 생성합니다.  
  
```  
vbc /target:library /out:Test.ABC.dll /recurse:Test\ABC\*.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/out](../../../visual-basic/reference/command-line-compiler/out.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)