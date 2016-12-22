---
title: "/bugreport | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "-bugreport compiler option [Visual Basic]"
  - "bugreport compiler option [Visual Basic]"
  - "/bugreport compiler option [Visual Basic]"
ms.assetid: e4325406-8dbd-4b48-b311-9ee0799e48bb
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /bugreport
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

버그 보고에 사용할 수 있는 파일을 만듭니다.  
  
## 구문  
  
```  
/bugreport:file  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`file`|필수 요소.  버그 보고서를 포함할 파일의 이름입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.|  
  
## 설명  
 `file`에 추가되는 정보는 다음과 같습니다.  
  
-   컴파일에 사용된 모든 소스 코드 파일의 복사본  
  
-   컴파일에 사용된 컴파일러 옵션 목록  
  
-   컴파일러, 공용 언어 런타임 및 운영 체제의 버전 정보  
  
-   컴파일러 출력\(있는 경우\)  
  
-   화면에 표시되는 문제에 대한 설명  
  
-   화면에 표시되는 문제의 해결 방법에 대한 설명  
  
 모든 소스 코드 파일의 복사본은 `file`에 포함되므로 오류 가능성이 있는 코드 오류를 가능한 가장 짧은 프로그램으로 재현할 수도 있습니다.  
  
> [!IMPORTANT]
>  `/bugreport` 옵션은 중요한 정보가 들어 있는 파일을 생성합니다.  이러한 정보에는 현재 시간, 컴파일러 버전, [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] 버전, OS 버전, 사용자 이름, 컴파일러 실행 시 사용되는 명령줄 인수, 모든 소스 코드, 참조되는 모든 어셈블리의 이진 형식 등이 포함됩니다.  [!INCLUDE[vstecasp](../../../visual-basic/developing-apps/programming/drives-directories-files/includes/vstecasp_md.md)] 응용 프로그램의 서버측 컴파일을 위한 Web.config 파일에서 명령줄 옵션을 지정하여 이 옵션에 액세스할 수 있습니다.  이 옵션에 액세스하지 못하도록 하려면 서버에서 사용자가 컴파일하지 못하도록 Machine.config 파일을 수정하십시오.  
  
 이 옵션을 `/errorreport:prompt`, `/errorreport:queue` 또는 `/errorreport:send`와 함께 사용하는 경우, 응용 프로그램에서 내부 컴파일러 오류가 발생하면 `file`의 정보가 Microsoft Corporation으로 전송됩니다.  이 정보는 Microsoft 엔지니어가 오류의 원인을 파악하는 데 도움이 되며, 다음 릴리스에서 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]의 기능을 향상시키는 데 도움이 될 수도 있습니다.  기본적으로는 Microsoft로 아무런 정보도 전송되지 않습니다.  그러나 기본적으로 사용하도록 설정된 `/errorreport:queue`를 사용하여 응용 프로그램을 컴파일하는 경우 응용 프로그램에서 해당 오류 보고서를 수집합니다.  그런 다음 컴퓨터 관리자가 로그인하면 오류 보고 시스템에 팝업 창이 표시되며 관리자는 이 창을 통해 로그온 이후 발생한 모든 오류 보고서를 Microsoft에 보낼 수 있습니다.  
  
> [!NOTE]
>  `/bugreport` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `T2.vb`를 컴파일하고 모든 버그 보고 정보를 `Problem.txt` 파일에 저장합니다.  
  
```  
vbc /bugreport:problem.txt t2.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [\/errorreport](../../../visual-basic/reference/command-line-compiler/errorreport.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [securityPolicy에 대한 trustLevel 요소\(ASP.NET 설정 스키마\)](http://msdn.microsoft.com/ko-kr/729ab04c-03da-4ee5-86b1-be9d08a09369)