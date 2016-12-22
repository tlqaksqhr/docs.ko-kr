---
title: "A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39; | Microsoft Docs"
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
  - "vbc40059"
  - "bc40059"
helpviewer_keywords: 
  - "VBC40059"
  - "BC40059"
ms.assetid: 520e39cb-8ab6-46f5-aa00-08afd51b4b7c
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# A reference was created to embedded interop assembly &#39;&lt;assembly1&gt;&#39; because of an indirect reference to that assembly from assembly &#39;&lt;assembly2&gt;&#39;
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

포함된 interop 어셈블리 '\<assembly1\>'에 대한 참조는 해당 어셈블리에 대한 '\<assembly2\>' 어셈블리의 간접 참조로 인해 만들어졌습니다.두 어셈블리 중 하나에서 'Interop 형식 포함' 속성을 변경하십시오.  
  
 `Embed Interop Types` 속성이 `True`로 설정된 어셈블리\(assembly1\)에 대한 참조를 추가했습니다.  이 경우 컴파일러는 해당 어셈블리의 interop 형식 정보를 포함하게 됩니다.  그러나 참조되는 다른 어셈블리\(assembly2\)에서도 이 어셈블리\(assembly1\)를 참조하고 `Embed Interop Types` 속성이 `False`로 설정되어 있기 때문에 컴파일러는 해당 어셈블리\(assembly1\)의 interop 형식 정보를 포함할 수 없습니다.  
  
> [!NOTE]
>  어셈블리 참조에서 `Embed Interop Types` 속성을 `True`로 설정하는 것은 명령줄 컴파일러의 `/link` 옵션을 사용하여 어셈블리를 참조하는 것과 같습니다.  
  
 **오류 ID:** BC40059  
  
### 이 경고를 처리하려면  
  
-   두 어셈블리의 interop 형식 정보를 포함하려면 에 대한 모든 참조에서 `Embed Interop Types` 속성을 `True`로 설정합니다.  
  
-   이 경고를 제거하려면 assembly1의 `Embed Interop Types` 속성을 `False`로 설정하면 됩니다.  이 경우 interop 형식 정보는 PIA\(주 interop 어셈블리\)에서 제공됩니다.  
  
## 참고 항목  
 [\/link](../../../visual-basic/reference/command-line-compiler/link.md)   
 [Programming with Primary Interop Assemblies](http://msdn.microsoft.com/ko-kr/306fa1d6-0703-4004-9e93-d0a57f1be81e)