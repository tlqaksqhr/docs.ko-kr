---
title: "/sdkpath | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "sdkpath"
  - "/sdkpath"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "-sdkpath compiler option [Visual Basic]"
  - "/sdkpath compiler option [Visual Basic]"
  - "sdkpath compiler option [Visual Basic]"
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /sdkpath
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Mscorlib.dll 및 Microsoft.VisualBasic.dll의 위치를 지정합니다.  
  
## 구문  
  
```  
/sdkpath:path  
```  
  
## 인수  
 `path`  
 컴파일에 사용할 Mscorlib.dll 및 Microsoft.VisualBasic.dll 버전이 들어 있는 디렉터리입니다.  이 경로는 로드될 때까지 확인되지 않습니다.  디렉터리 이름에 공백이 있으면 해당 이름을 따옴표\(" "\)로 묶습니다.  
  
## 설명  
 이 옵션을 지정하면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러는 기본 위치가 아닌 위치에서 Mscorlib.dll 및 Microsoft.VisualBasic.dll 파일을 로드합니다.  `/sdkpath` 옵션은 [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)와 함께 사용할 수 있습니다.  [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]에서는 이러한 지원 라이브러리의 다른 버전을 사용하여 장치에 없는 형식 및 언어 기능을 사용하지 못하도록 합니다.  
  
> [!NOTE]
>  `/sdkpath` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  `/sdkpath` 옵션은 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 장치 프로젝트가 로드되는 경우 설정됩니다.  
  
 `/vbruntime` 컴파일러 옵션을 사용하여 컴파일러가 Visual Basic 런타임 라이브러리에 대한 참조 없이 컴파일하도록 지정할 수 있습니다.  자세한 내용은 [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)를 참조하십시오.  
  
## 예제  
 다음 코드에서는 C 드라이브의 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)] 기본 설치 디렉터리에 있는 Mscorlib.dll 및 Microsoft.VisualBasic.dll 버전을 사용하여 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]로 `Myfile.vb`를 컴파일합니다.  일반적으로 최신 버전의 [!INCLUDE[Compact](../../../visual-basic/reference/command-line-compiler/includes/compact-md.md)]를 사용합니다.  
  
```  
vbc /netcf /sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)   
 [\/vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)