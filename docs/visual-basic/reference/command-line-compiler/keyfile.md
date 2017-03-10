---
title: "/keyfile | Microsoft Docs"
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
  - "/keyfile compiler option [Visual Basic]"
  - "keyfile compiler option [Visual Basic]"
  - "-keyfile compiler option [Visual Basic]"
ms.assetid: ffa82a4b-517a-4c6c-9889-5bae7b534bb8
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# /keyfile
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

어셈블리에 강력한 이름을 제공하기 위해 키 또는 키 쌍을 포함하는 파일을 지정합니다.  
  
## 구문  
  
```  
/keyfile:file  
```  
  
## 인수  
 `file`  
 필수 요소.  키를 가지고 있는 파일입니다.  파일 이름에 공백이 포함되어 있으면 이름을 따옴표\(" "\)로 묶습니다.  
  
## 설명  
 컴파일러는 공개 키를 어셈블리 매니페스트에 삽입한 다음 개인 키를 사용하여 최종 어셈블리에 서명합니다.  키 파일을 생성하려면 명령줄에 `sn -k file`을 입력하십시오.  자세한 내용은 [Sn.exe\(강력한 이름 도구\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)를 참조하십시오.  
  
 `/target:module`을 사용하여 컴파일하면 키 파일의 이름이 해당 모듈에 저장되고, [\/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)을 사용하여 어셈블리를 컴파일할 때 만들어지는 어셈블리에서 이 정보를 사용할 수 있습니다.  
  
 [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)를 사용하여 컴파일러에 암호화 정보를 전달할 수도 있습니다.  어셈블리에 부분적으로 서명하려면 [\/delaysign](../../../visual-basic/reference/command-line-compiler/delaysign.md)을 사용하십시오.  
  
 MSIL\(Microsoft Intermediate Language\) 모듈의 소스 코드에서 이 옵션을 사용자 지정 특성\(<xref:System.Reflection.AssemblyKeyFileAttribute>\)으로 지정할 수도 있습니다.  
  
 명령줄 옵션 또는 사용자 지정 특성을 통해 동일한 컴파일에 `/keyfile`과 [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)가 모두 지정된 경우 컴파일러에서는 키 컨테이너를 먼저 시도합니다.  키 컨테이너에서 성공하면 어셈블리는 키 컨테이너의 정보로 서명됩니다.  컴파일러에서 키 컨테이너를 찾지 못하면 `/keyfile`에 지정된 파일을 사용합니다.  키 파일이 성공적으로 컴파일되면 이 키 파일의 정보로 어셈블리가 서명되고 다음에 컴파일할 때 키 컨테이너를 사용할 수 있도록 키 정보가 키 컨테이너에 설치됩니다\(`sn -i`와 유사\).  
  
 키 파일에는 공개 키만 포함될 수 있습니다.  
  
 어셈블리에 서명하는 데 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)을 참조하십시오.  
  
> [!NOTE]
>  `/keyfile` 옵션은 [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)] 개발 환경에서는 사용할 수 없고 명령줄에서 컴파일하는 경우에만 사용할 수 있습니다.  
  
## 예제  
 다음 코드에서는 소스 파일 `Input.vb`를 컴파일하고 키 파일을 지정합니다.  
  
```  
vbc /keyfile:myfile.sn input.vb  
```  
  
## 참고 항목  
 [어셈블리 및 전역 어셈블리 캐시](../Topic/Assemblies%20and%20the%20Global%20Assembly%20Cache%20\(C%23%20and%20Visual%20Basic\).md)   
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/reference](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)