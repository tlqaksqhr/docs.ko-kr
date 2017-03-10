---
title: "/optimize | Microsoft Docs"
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
  - "optimize compiler option [Visual Basic]"
  - "/optimize compiler option [Visual Basic]"
  - "optimization, enabling"
  - "-optimize compiler option [Visual Basic]"
ms.assetid: fcba4a97-3622-4b87-a891-0f77deab4998
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# /optimize
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

컴파일러 최적화를 사용하거나 사용하지 않습니다.  
  
## 구문  
  
```  
/optimize[ + | - ]  
```  
  
## 인수  
  
|||  
|-|-|  
|용어|정의|  
|`+`  &#124; `-`|선택적 요소.  `/optimize-` 옵션은 컴파일러 최적화를 사용하지 않고,  `/optimize+` 옵션은 최적화를 사용합니다.  기본적으로는 최적화가 사용되지 않습니다.|  
  
## 설명  
 컴파일러 최적화는 출력 파일을 작고 빠르고 효율적이 되도록 만듭니다.  그러나 최적화로 인해 출력 파일에서 코드가 다시 정렬되기 때문에 `/optimize+`는 디버깅을 어렵게 만들 수 있습니다.  
  
 같은 어셈블리에 대해 `/target:module`을 통해 생성된 모든 모듈에서는 어셈블리와 동일한 `/optimize` 설정을 사용해야 합니다.  자세한 내용은 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)를 참조하십시오.  
  
 `/optimize` 옵션과 `/debug` 옵션을 함께 사용할 수 있습니다.  
  
||  
|-|  
|Visual Studio 통합 개발 환경에서 \/optimize를 설정하려면|  
|1.  **솔루션 탐색기**에서 프로젝트를 선택합니다.  **프로젝트** 메뉴에서 **속성**을 선택합니다.<br />     자세한 내용은 [Introduction to the Project Designer](http://msdn.microsoft.com/ko-kr/898dd854-c98d-430c-ba1b-a913ce3c73d7)를 참조하십시오.<br />2.  **컴파일** 탭을 클릭합니다.<br />3.  **고급** 단추를 클릭합니다.<br />4.  **최적화 사용** 확인란을 수정합니다.|  
  
## 예제  
 다음 코드에서는 `T2.vb`를 컴파일하고 컴파일러 최적화 기능을 활성화합니다.  
  
```  
vbc t2.vb /optimize  
```  
  
## 참고 항목  
 [Visual Basic Command\-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/debug](../../../visual-basic/reference/command-line-compiler/debug.md)   
 [샘플 컴파일 명령줄](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)