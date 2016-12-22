---
title: "Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found | Microsoft Docs"
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
  - "bc40056"
  - "vbc40056"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40056"
ms.assetid: b59f5754-444f-4378-9272-9678b437e84a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Namespace or type specified in the Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Imports '\<qualifiedelementname\>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.네임스페이스 또는 형식이 정의되어 있으며 적어도 하나의 public 멤버가 포함되는지 확인합니다.별칭 이름에 다른 별칭이 포함되지 않는지 확인합니다.  
  
 `Imports` 문은 찾을 수 없거나 `Public` 멤버를 정의하지 않는 포함하는 요소를 지정합니다.  
  
 *포함하는 요소*는 네임스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형일 수 있습니다.  포함하는 요소에는 변수와 같은 멤버, 프로시저 또는 다른 포함하는 요소가 포함됩니다.  
  
 가져오기의 목적은 코드에서 네임스페이스 또는 형식 멤버를 한정하지 않고 해당 멤버에 액세스할 수 있도록 하기 위한 것입니다.  프로젝트가 네임스페이스 또는 형식에 대한 참조를 추가해야 할 수도 있습니다.  자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)의 "포함하는 요소 가져오기"를 참조하십시오.  
  
 컴파일러에서 지정한 포함하는 요소를 찾을 수 없는 경우 해당 요소를 사용하는 참조를 확인할 수 없습니다.  요소를 찾았지만 해당 요소가 `Public` 멤버를 노출시키지 않는 경우 참조에 실패합니다.  두 가지 경우 모두 요소를 가져오는 의미가 없습니다.  
  
 포함하는 요소를 가져와 가져오기 별칭을 지정하는 경우 해당 가져오기 별칭을 사용하여 다른 요소를 가져올 수 없습니다.  다음 코드에서는 컴파일러 오류가 생성됩니다.  
  
 `Imports`   `winfrm`   `= System.Windows.Forms`  
  
 `' The following statement is`   `INVALID`   `because it reuses an import alias.`  
  
 `Imports behav =`   `winfrm`  `.Design.Behavior`  
  
 **오류 ID:** BC40056  
  
### 이 오류를 해결하려면  
  
1.  프로젝트에서 포함하는 요소에 액세스할 수 있는지 확인합니다.  
  
2.  포함하는 요소의 사양에 다른 가져오기로부터의 가져오기 별칭이 포함되지 않는지 확인합니다.  
  
3.  포함하는 요소가 적어도 하나의 `Public` 멤버를 노출시키는지 확인합니다.  
  
## 참고 항목  
 [Imports Statement \(.NET Namespace and Type\)](../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)   
 [Namespace Statement](../../../visual-basic/language-reference/statements/namespace-statement.md)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)