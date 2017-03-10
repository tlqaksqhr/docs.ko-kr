---
title: "/keycontainer | Microsoft Docs"
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
  - "-keycontainer compiler option [Visual Basic]"
  - "keycontainer compiler option [Visual Basic]"
  - "/keycontainer compiler option [Visual Basic]"
ms.assetid: 6a9bc861-1752-4db1-9f64-b5252f0482cc
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# /keycontainer
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

어셈블리에 강력한 이름을 제공하기 위해 키 쌍에 대한 키 컨테이너 이름을 지정합니다.  
  
## 구문  
  
```  
/keycontainer:container  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`container`|필수 요소.  키를 가지고 있는 컨테이너 파일입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(""\)로 묶습니다.|  
  
## 설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입하고 개인 키를 사용하여 최종 어셈블리에 서명하는 방식으로 공유할 수 있는 구성 요소를 만듭니다.  키 파일을 생성하려면 명령줄에 `sn -k` `file`을 입력하십시오.  `-i` 옵션을 사용하면 키 쌍이 컨테이너에 설치됩니다.  자세한 내용은 [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)를 참조하십시오.  
  
 `/target:module`을 사용하여 컴파일하면 키 파일의 이름이 해당 모듈에 저장되고, [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)을 사용하여 어셈블리를 컴파일할 때 만들어지는 어셈블리에서 이 정보를 사용할 수 있습니다.  
  
 MSIL\(Microsoft Intermediate Language\) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성\(<xref:System.Reflection.AssemblyKeyNameAttribute>\)으로 지정할 수도 있습니다.  
  
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)을 사용하여 컴파일러에 암호화 정보를 전달할 수도 있습니다.  어셈블리에 부분적으로 서명하려면 [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용하십시오.  
  
 어셈블리에 서명하는 데 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)을 참조하십시오.  
  
> [!NOTE]
>  `/keycontainer` 옵션은 Visual Studio 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 소스 파일 `Input.vb`를 컴파일하고 키 컨테이너를 지정합니다.  
  
```  
vbc /keycontainer:key1 input.vb  
```  
  
## 참고 항목  
 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)