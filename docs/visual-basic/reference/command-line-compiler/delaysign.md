---
title: "/delaysign | Microsoft Docs"
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
  - "delaysign compiler option [Visual Basic]"
  - "/delaysign compiler option [Visual Basic]"
  - "-delaysign compiler option [Visual Basic]"
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /delaysign
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

어셈블리를 완전히 서명할지, 아니면 부분적으로 서명할지를 지정합니다.  
  
## 구문  
  
```  
/delaysign[+ | -]  
```  
  
## 인수  
 `+` &#124; `-`  
 선택적 요소.  어셈블리에 완전히 서명하려면 `/delaysign-`를 사용하고  어셈블리에 공개 키를 배치하고 서명된 해시를 위한 공간을 예약하려면 `/delaysign+`를 사용합니다.  기본값은 `/delaysign-`입니다.  
  
## 설명  
 `/delaysign` 옵션은 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) 또는 [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)와 함께 사용할 경우에만 효과를 나타냅니다.  
  
 완전히 서명된 어셈블리를 요청하면 컴파일러가 매니페스트\(어셈블리 메타데이터\)가 포함된 파일을 해시한 후 해당 해시를 개인 키로 서명합니다.  결과로 생성되는 디지털 서명은 매니페스트가 포함된 파일에 저장됩니다.  어셈블리 서명이 연기되면 컴파일러가 서명을 계산하거나 저장하지 않습니다. 그러나 나중에 서명을 추가할 수 있도록 파일에 공간을 예약합니다.  
  
 예를 들어, 회사의 개발자는 `/delaysign+`를 사용하여 테스터가 전역 어셈블리 캐시에 등록하여 사용할 수 있는 서명되지 않은 테스트 버전 어셈블리를 배포할 수 있습니다.  어셈블리 작업이 완료되면 회사의 개인 키 담당자가 해당 어셈블리를 완전히 서명할 수 있습니다.  이렇게 작업을 분리하면 회사의 개인 키가 노출되는 것을 방지하면서 모든 개발자가 어셈블리 작업을 수행할 수 있습니다.  
  
 어셈블리에 서명하는 데 대한 자세한 내용은 [강력한 이름의 어셈블리 만들기 및 사용](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md)을 참조하십시오.  
  
### Visual Studio 통합 개발 환경에서 \/delaysign을 설정하려면  
  
1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.  자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.  
  
2.  **서명** 탭을 클릭합니다.  
  
3.  **서명만 연기** 상자에서 값을 설정합니다.  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [\/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)