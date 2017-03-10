---
title: "/quiet | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/quiet"
  - "quiet"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-quiet compiler option [Visual Basic]"
  - "/quiet compiler option [Visual Basic]"
  - "quiet compiler option [Visual Basic]"
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# /quiet
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러가 구문 관련 오류 및 경고 코드를 표시하지 않도록 합니다.  
  
## 구문  
  
```  
/quiet  
```  
  
## 설명  
 기본적으로 `/quiet`는 아무런 효과가 없습니다.  컴파일러가 구문 관련 오류나 경고를 보고할 경우 소스 코드의 행도 출력합니다.  컴파일러 출력을 구문 분석하는 응용 프로그램에서는 컴파일러가 진단 텍스트만 출력하는 것이 더 편리할 수 있습니다.  
  
 다음 예제에서 `Module1`은 `/quiet` 없이 컴파일할 때 소스 코드를 포함하는 오류를 출력합니다.  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 출력  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 `/quiet`를 사용하여 컴파일하면 컴파일러가 다음 정보만 출력합니다.  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  `/quiet` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드는 `T2.vb`를 컴파일하고 구문 관련 컴파일러 진단에 대한 코드를 표시하지 않습니다.  
  
```  
vbc /quiet t2.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)