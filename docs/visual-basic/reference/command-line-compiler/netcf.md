---
title: "/netcf | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "/netcf"
  - "netcf"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-netcf compiler option [Visual Basic]"
  - "netcf compiler option [Visual Basic]"
  - "/netcf compiler option [Visual Basic]"
ms.assetid: db7cfa59-c315-401c-a59b-0daf355343d6
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# /netcf
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러 대상을 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]로 설정합니다.  
  
## 구문  
  
```  
/netcf  
```  
  
## 설명  
 `/netcf` 옵션을 사용하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러의 대상이 전체 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]가 아니라 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]가 됩니다.  이때 전체 [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]에서만 제공되는 언어 기능은 사용할 수 없습니다.  
  
 `/netcf` 옵션은 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)와 함께 사용할 수 있습니다.  `/netcf`를 지정할 때 사용할 수 없는 언어 기능은 `/sdkpath`의 대상 파일에서 제공되지 않는 언어 기능과 같습니다.  
  
> [!NOTE]
>  `/netcf` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  `/netcf` 옵션은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 장치 프로젝트가 로드되는 경우 설정됩니다.  
  
 `/netcf` 옵션을 사용하면 다음과 같은 언어 기능이 변경됩니다.  
  
-   프로그램 실행을 종료하는 [End \<keyword\> Statement](../../../visual-basic/language-reference/statements/end-keyword-statement.md) 키워드를 사용할 수 없습니다.  다음 프로그램은 `/netcf` 없이 컴파일되고 실행되지만, `/netcf`를 사용하면 컴파일 타임에 오류가 발생합니다.  
  
     [!code-vb[VbVbalrCompiler#34](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_1.vb)]  
  
-   모든 형식에서 런타임에 바인딩을 사용할 수 없습니다.  런타임에 바인딩 시나리오가 발견되면 컴파일 타임 오류가 생성됩니다.  다음 프로그램은 `/netcf` 없이 컴파일되고 실행되지만, `/netcf`를 사용하면 컴파일 타임에 오류가 발생합니다.  
  
     [!code-vb[VbVbalrCompiler#35](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_2.vb)]  
  
-   [Auto](../../../visual-basic/language-reference/modifiers/auto.md), [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md) 및 [Unicode](../../../visual-basic/language-reference/modifiers/unicode.md) 한정자를 사용할 수 없습니다.  [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) 문의 구문도 `Declare Sub|Function name Lib "library" [Alias "alias"] [([arglist])]`로 수정됩니다.  다음 코드에서는 컴파일할 때 `/netcf`를 사용한 결과를 보여 줍니다.  
  
     [!code-vb[VbVbalrCompiler#36](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/netcf_3.vb)]  
  
-   [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 제거된 Visual Basic 6.0 키워드를 사용하면 `/netcf`를 사용할 때 다른 오류가 생성됩니다.  이 경우 다음 키워드에 대한 오류 메시지가 영향을 받습니다.  
  
    -   `Open`  
  
    -   `Close`  
  
    -   `Put`  
  
    -   `Print`  
  
    -   `Write`  
  
    -   `Input`  
  
    -   `Lock`  
  
    -   `Unlock`  
  
    -   `Seek`  
  
    -   `Width`  
  
    -   `Name`  
  
    -   `FreeFile`  
  
    -   `EOF`  
  
    -   `Loc`  
  
    -   `LOF`  
  
    -   `Line`  
  
## 예제  
 다음 코드에서는 C 드라이브의 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] 기본 설치 디렉터리에 있는 Mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 사용하여 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]로 `Myfile.vb`를 컴파일합니다.  일반적으로 최신 버전의 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]를 사용합니다.  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)