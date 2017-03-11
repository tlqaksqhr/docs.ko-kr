---
title: "/moduleassemblyname | Microsoft Docs"
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
  - "moduleassemblyname compiler option [Visual Basic]"
  - "/moduleassemblyname compiler option [Visual Basic]"
  - "-moduleassemblyname compiler option [Visual Basic]"
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /moduleassemblyname
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 모듈이 속하게 될 어셈블리의 이름을 지정합니다.  
  
## 구문  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`assembly_name`|이 모듈이 속하게 될 어셈블리의 이름입니다.|  
  
## 설명  
 `/target:module` 옵션이 지정된 경우에만 컴파일러가 `/moduleassemblyname` 옵션을 처리합니다.  따라서 컴파일러가 모듈을 만듭니다.  컴파일러에서 생성된 모듈은 `/moduleassemblyname` 옵션으로 지정된 어셈블리에 대해서만 유효합니다.  모듈을 다른 어셈블리에 놓는 경우 런타임 오류가 발생합니다.  
  
 다음과 같은 경우에만 `/moduleassemblyname` 옵션이 필요합니다.  
  
-   모듈의 데이터 형식이 참조된 어셈블리의 `Friend` 형식에 액세스해야 하는 경우  
  
-   참조된 어셈블리에서 모듈을 빌드할 어셈블리에 대해 friend 어셈블리 액세스를 허용한 경우  
  
 모듈을 만드는 방법에 대한 자세한 내용은 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)을 참조하십시오.  friend 어셈블리에 대한 자세한 내용은 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)를 참조하십시오.  
  
> [!NOTE]
>  `/moduleassemblyname` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령 프롬프트에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 참고 항목  
 [방법: 다중 파일 어셈블리 빌드](../Topic/How%20to:%20Build%20a%20Multifile%20Assembly.md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [\/main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)