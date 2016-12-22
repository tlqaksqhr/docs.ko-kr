---
title: "기본 클래스 &#39;&lt;classname&gt;&#39;을(를) 포함하는 &#39;&lt;assemblyname&gt;&#39; 어셈블리에 대한 참조가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30007"
  - "vbc30007"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30007"
ms.assetid: 5f34cf47-6c6e-4954-bd8e-d6b020b75fb7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 기본 클래스 &#39;&lt;classname&gt;&#39;을(를) 포함하는 &#39;&lt;assemblyname&gt;&#39; 어셈블리에 대한 참조가 필요합니다.
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

기본 클래스 '\<classname\>'을\(를\) 포함하는 '\<assemblyname\>' 어셈블리에 대한 참조가 필요합니다. 하나를 프로젝트에 추가합니다.  
  
 클래스는 프로젝트에서 직접 참조하지 않는 어셈블리 또는 DLL\(동적 연결 라이브러리\)에서 정의됩니다. 둘 이상이 DLL 또는 어셈블리에서 클래스가 정의된 경우 모호성을 방지하기 위해 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 컴파일러에 참조가 필요합니다.  
  
 **오류 ID:** BC30007  
  
### 이 오류를 해결하려면  
  
-   참조되지 않은 DLL 또는 어셈블리 이름을 프로젝트 참조에 포함합니다.  
  
## 참고 항목  
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [프로젝트의 참조 관리](/visual-studio/ide/managing-references-in-a-project)   
 [끊어진 참조 문제 해결](/visual-studio/ide/troubleshooting-broken-references)