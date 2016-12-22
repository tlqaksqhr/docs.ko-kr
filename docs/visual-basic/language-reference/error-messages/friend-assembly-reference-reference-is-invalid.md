---
title: "Friend assembly reference &lt;reference&gt; is invalid | Microsoft Docs"
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
  - "vbc31535"
  - "bc31535"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31535"
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Friend assembly reference &lt;reference&gt; is invalid
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Friend 어셈블리 참조 \<reference\>이\(가\) 잘못되었습니다.강력한 이름의 서명된 어셈블리에는 InternalsVisibleTo 선언에 공개 키를 지정해야 합니다.  
  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에 전달한 어셈블리 이름이 강력한 이름의 어셈블리를 나타내지만 `PublicKey` 특성을 포함하지 않습니다.  
  
 **오류 ID:** BC31535  
  
### 이 오류를 해결하려면  
  
1.  강력한 이름의 Friend 어셈블리의 공개 키를 확인한 후  <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성 생성자에 전달하는 어셈블리 이름의 일부로 `PublicKey` 특성을 사용하여 이 공개 키를 포함합니다.  
  
## 참고 항목  
 <xref:System.Reflection.AssemblyName>   
 [Friend 어셈블리](../Topic/Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)   
 [방법: 서명된 Friend 어셈블리 만들기](../Topic/How%20to:%20Create%20Signed%20Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)