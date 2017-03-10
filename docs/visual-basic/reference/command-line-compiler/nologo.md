---
title: "/nologo (Visual Basic) | Microsoft Docs"
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
  - "-nologo compiler option [Visual Basic]"
  - "banners, suppressing startup"
  - "nologo compiler option [Visual Basic]"
  - "/nologo compiler option [Visual Basic]"
ms.assetid: 25ef54b6-d676-4639-a2d2-a747a158bc07
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /nologo (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일 중에 저작권 배너와 알림 메시지가 표시되지 않도록 합니다.  
  
## 구문  
  
```  
/nologo  
```  
  
## 설명  
 `/nologo`를 지정하면 컴파일러가 저작권 배너를 표시하지 않습니다.  기본적으로 `/nologo`는 설정되어 있지 않습니다.  
  
> [!NOTE]
>  `/nologo` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드는 `T2.vb`를 컴파일하고 저작권 배너를 표시하지 않습니다.  
  
```  
vbc /nologo t2.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)