---
title: "/vbruntime | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbruntime"
  - "/vbruntime"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "vbruntime compiler option [Visual Basic]"
  - "-vbruntime compiler option [Visual Basic]"
  - "/vbruntime compiler option [Visual Basic]"
ms.assetid: 1aa0239e-511a-4c29-957d-fd72877b350a
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /vbruntime
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

컴파일러가 Visual Basic 런타임 라이브러리에 대한 참조 없이 또는 특정 런타임 라이브러리에 대한 참조를 통해 컴파일하도록 지정합니다.  
  
## 구문  
  
```  
/vbruntime:{ - | + | * | path }  
```  
  
## 인수  
 \-  
 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일합니다.  
  
 \+  
 기본 Visual Basic 런타임 라이브러리에 대한 참조를 사용하여 컴파일합니다.  
  
 \*  
 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하고 Visual Basic 런타임 라이브러리의 핵심 기능을 어셈블리에 포함합니다.  
  
 `path`  
 지정된 라이브러리\(DLL\)에 대한 참조를 사용하여 컴파일합니다.  
  
## 설명  
 `/vbruntime` 컴파일러 옵션을 사용하여 컴파일러가 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하도록 지정할 수 있습니다.  Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하는 경우 오류 또는 경고가 Visual Basic 런타임 도우미에 대한 호출을 생성하는 코드 또는 언어 구문에 기록됩니다.  *Visual Basic 런타임 도우미*는 특정 언어 의미 체계를 실행하기 위해 런타임에 호출되는 Microsoft.VisualBasic.dll에 정의된 함수입니다.  
  
 `/vbruntime+` 옵션을 사용하면 `/vbruntime` 스위치가 지정되지 않았을 때 발생하는 동작과 동일한 동작이 실행됩니다.  `/vbruntime+` 옵션을 사용하여 이전 `/vbruntime` 스위치를 재정의할 수 있습니다.  
  
 대부분의 개체에는 `My` 형식을 사용 하는 경우 사용할 수 있습니다에서 `/vbruntime-` 또는 `vbruntime:``path` 옵션.  
  
## Visual Basic 런타임 핵심 기능 임베드  
 `/vbruntime*` 옵션을 사용하면 런타임 라이브러리에 대한 참조 없이 컴파일할 수 있습니다.  대신, 사용자 어셈블리에 Visual Basic 런타임 라이브러리의 핵심 기능이 포함됩니다.  Visual Basic런타임포함 되지 않은 플랫폼에서응용 프로그램을 실행 하는 경우이 옵션을 사용할 수 있습니다.  
  
 다음 런타임 멤버가 포함되었습니다.  
  
-   <xref:Microsoft.VisualBasic.CompilerServices.Conversions> 클래스  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.Char%29> 메서드  
  
-   <xref:Microsoft.VisualBasic.Strings.AscW%28System.String%29> 메서드  
  
-   <xref:Microsoft.VisualBasic.Strings.ChrW%28System.Int32%29> 메서드  
  
-   <xref:Microsoft.VisualBasic.Constants.vbBack> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCr> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbCrLf> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbFormFeed> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbLf> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNewLine> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullChar> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbNullString> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbTab> 상수  
  
-   <xref:Microsoft.VisualBasic.Constants.vbVerticalTab> 상수  
  
-   일부 개체에는 `My` 형식  
  
 `/vbruntime*`을 사용하여 컴파일하고 코드가 핵심 기능이 포함되지 않은 Visual Basic 런타임 라이브러리의 멤버를 참조할 경우 컴파일러는 멤버를 사용할 수 없다는 오류를 반환합니다.  
  
## 지정된 라이브러리 참조  
 `path` 인수를 사용하여 기본 Visual Basic 런타임 라이브러리 대신 사용자 지정 런타임 라이브러리에 대한 참조를 사용하여 컴파일할 수 있습니다.  
  
 `path` 인수의 값이 DLL에 대한 정규화된 경로인 경우 컴파일러는 해당 파일을 런타임 라이브러리로 사용합니다.  `path` 인수의 값이 DLL에 대한 정규화된 경로가 아닌 경우 Visual Basic 컴파일러는 먼저 현재 폴더에서 식별된 DLL을 검색합니다.  그런 다음 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md) 컴파일러 옵션을 사용하여 지정한 경로를 검색합니다.  `/sdkpath` 컴파일러 옵션을 사용하지 않으면 컴파일러는 .NET Framework 폴더\(`%systemroot%\Microsoft.NET\Framework\versionNumber`\)에서 식별된 DLL을 검색합니다.  
  
## 예제  
 다음 예제에서는 `/vbruntime` 옵션을 사용하여 사용자 지정 라이브러리에 대한 참조를 통해 컴파일하는 방법을 보여 줍니다.  
  
```  
vbc /vbruntime:C:\VBLibraries\CustomVBLibrary.dll  
```  
  
## 참고 항목  
 [Visual Basic Core – New compilation mode in Visual Studio 2010 SP1](http://blogs.msdn.com/b/vbteam/archive/2011/01/10/vb-core-new-compilation-mode-in-visual-studio-2010-sp1.aspx)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/sdkpath](../../../visual-basic/reference/command-line-compiler/sdkpath.md)