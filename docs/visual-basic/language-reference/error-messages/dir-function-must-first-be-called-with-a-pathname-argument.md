---
title: "&#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbrDIR_IllegalCall"
dev_langs: 
  - "VB"
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 7
---
# &#39;Dir&#39; function must first be called with a &#39;PathName&#39; argument
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`Dir` 함수를 처음 호출할 때 `PathName` 인수를 사용하지 않았습니다.  `Dir`를 처음 호출할 때에는 `PathName`이 필요하지만 다음 `Dir` 호출에서는 그 다음 항목을 검색하기 위해 매개 변수를 사용할 필요가 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  함수 호출에 `PathName` 인수를 사용합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>