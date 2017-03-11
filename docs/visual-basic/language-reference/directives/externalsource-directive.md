---
title: "#ExternalSource Directive | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "#Externalsource"
  - "#ExternalSource"
  - "vb.ExternalSource"
  - "Externalsource"
  - "vb.#ExternalSource"
  - "ExternalSource"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ExternalSource directive (#ExternalSource)"
  - "#ExternalSource directive"
ms.assetid: 243bc6a2-34c3-4eeb-a776-9fd2bf988149
caps.latest.revision: 160
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 160
---
# #ExternalSource Directive
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

소스 코드의 특정 줄과 소스 외부에 있는 텍스트 간의 매핑을 나타냅니다.  
  
## 구문  
  
```  
#ExternalSource( StringLiteral , IntLiteral )  
    [ LogicalLine+ ]  
#End ExternalSource  
```  
  
## 요소  
 `StringLiteral`  
 외부 소스의 경로입니다.  
  
 `IntLiteral`  
 외부 소스의 첫째 줄에 대한 줄 번호입니다.  
  
 `LogicalLine`  
 오류가 발생한 외부 소스 줄입니다.  
  
 `#End ExternalSource`  
 `#ExternalSource` 블록을 종료합니다.  
  
## 설명  
 이 지시문은 컴파일러와 디버거에서만 사용됩니다.  
  
 소스 파일에 소스 파일 안의 특정 코드 줄과 소스 외부에 있는 텍스트 간의 매핑을 나타내는 외부 소스 지시문이 포함될 수 있습니다\(예: .aspx 파일\).  컴파일하는 동안 지정된 소스 코드에서 오류가 발생하면 외부 소스에서 발생한 오류로 식별됩니다.  
  
 외부 소스 지시문은 컴파일에는 영향을 주지 않으며 중첩될 수 없습니다.  이러한 지시문은 응용 프로그램에서 내부적으로 사용하기 위한 것입니다.  
  
## 참고 항목  
 [Conditional Compilation](../../../visual-basic/programming-guide/program-structure/conditional-compilation.md)