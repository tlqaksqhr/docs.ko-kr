---
title: "&#39;&lt;typename&gt;&#39; is a delegate type | Microsoft Docs"
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
  - "bc32008"
  - "vbc32008"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32008"
ms.assetid: dc6abba0-a9ad-450f-8899-87265bc84abc
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; is a delegate type
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

'\<typename\>'은\(는\) 대리자 형식입니다.대리자 구문에서는 하나의 AddressOf 식만 인수 목록으로 사용할 수 있습니다.종종 대리자 구문 대신 AddressOf 식을 사용할 수 있습니다.  
  
 대리자 클래스 인스턴스를 만드는 `New` 절에서는 대리자 생성자에 잘못된 인수 목록을 제공합니다.  
  
 새 대리자 인스턴스를 만들 때는 `AddressOf` 식을 하나만 사용할 수 있습니다.  
  
 대리자 생성자에 인수를 제공하지 않거나, 둘 이상의 인수를 제공하거나, 올바른 `AddressOf` 식이 아닌 단일 인수를 전달하는 경우 이 오류가 발생할 수 있습니다.  
  
 **오류 ID:** BC32008  
  
### 이 오류를 해결하려면  
  
-   `New` 절의 대리자 클래스에 대한 인수 목록에서 `AddressOf` 식을 하나만 사용하십시오.  
  
## 참고 항목  
 [New Operator](../../../visual-basic/language-reference/operators/new-operator.md)   
 [AddressOf Operator](../../../visual-basic/language-reference/operators/addressof-operator.md)   
 [Delegates](../../../visual-basic/programming-guide/language-features/delegates/delegates.md)   
 [How to: Invoke a Delegate Method](../../../visual-basic/programming-guide/language-features/delegates/how-to-invoke-a-delegate-method.md)