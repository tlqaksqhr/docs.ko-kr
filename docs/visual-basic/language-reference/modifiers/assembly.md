---
title: "Assembly (Visual Basic) | Microsoft Docs"
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
  - "vb.Assembly"
  - "vb.AssemblyAttribute"
  - "Assembly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Assembly modifier"
  - "Assembly keyword"
  - "attribute blocks, Assembly keyword"
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Assembly (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

소스 파일의 시작 부분에 있는 특성이 전체 어셈블리에 적용되도록 지정합니다.  
  
## 설명  
 특성은 클래스나 속성 같은 개별 프로그래밍 요소에 속하는 경우가 많습니다.  특성을 적용하려면 특성 블록을 꺾쇠 괄호\(`< >`\)로 묶어 선언문에 직접 연결합니다.  
  
 특성이 바로 다음에 이어지는 요소만이 아닌 전체 어셈블리에도 해당되는 경우에는 특성 블록을 소스 파일의 시작 부분에 놓고 `Assembly` 키워드를 사용하여 해당 특성을 식별합니다.  현재 어셈블리 모듈에만 적용되는 경우에는 [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md) 키워드를 사용합니다.  
  
 특성을 AssemblyInfo.vb 파일의 어셈블리에 적용할 수도 있습니다. 이런 경우에는 기본 소스 코드 파일에서 특성 블록을 사용하지 않아도 됩니다.  
  
## 참고 항목  
 [Module \<keyword\>](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [특성](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)