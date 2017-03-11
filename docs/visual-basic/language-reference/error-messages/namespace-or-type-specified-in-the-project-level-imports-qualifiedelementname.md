---
title: "Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40057"
  - "bc40057"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40057"
ms.assetid: 4ae3506e-2ebe-4ff3-995d-14ac60db5e9f
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Namespace or type specified in the project-level Imports &#39;&lt;qualifiedelementname&gt;&#39; doesn&#39;t contain any public member or cannot be found
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

프로젝트 수준의 Imports '\<qualifiedelementname\>'에 지정된 네임스페이스 또는 형식에 public 멤버가 없거나 해당 네임스페이스 또는 형식을 찾을 수 없습니다.네임스페이스 또는 형식이 정의되어 있으며 적어도 하나의 public 멤버가 포함되는지 확인합니다.별칭 이름에 다른 별칭이 포함되지 않는지 확인합니다.  
  
 프로젝트의 가져오기 속성은 찾을 수 없거나 `Public` 멤버를 정의하지 않는 포함하는 요소를 지정합니다.  
  
 *포함하는 요소*는 네임스페이스, 클래스, 구조체, 모듈, 인터페이스 또는 열거형일 수 있습니다.  포함하는 요소에는 변수와 같은 멤버, 프로시저 또는 다른 포함하는 요소가 포함됩니다.  
  
 가져오기의 목적은 코드에서 네임스페이스 또는 형식 멤버를 한정하지 않고 해당 멤버에 액세스할 수 있도록 하기 위한 것입니다.  프로젝트가 네임스페이스 또는 형식에 대한 참조를 추가해야 할 수도 있습니다.  자세한 내용은 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)의 "포함하는 요소 가져오기"를 참조하십시오.  
  
 컴파일러에서 지정한 포함하는 요소를 찾을 수 없는 경우 해당 요소를 사용하는 참조를 확인할 수 없습니다.  요소를 찾았지만 해당 요소가 `Public` 멤버를 노출시키지 않는 경우 참조에 실패합니다.  두 가지 경우 모두 요소를 가져오는 의미가 없습니다.  
  
 가져올 요소를 지정하려면 **프로젝트 디자이너**를 사용합니다.  **참조** 페이지의 **가져온 네임스페이스** 섹션을 사용합니다.  **솔루션 탐색기**에서 **My Project** 아이콘을 두 번 클릭하여 **프로젝트 디자이너**를 열 수 있습니다.  
  
 **오류 ID:** BC40057  
  
### 이 오류를 해결하려면  
  
1.  **프로젝트 디자이너**를 열고 **참조** 페이지로 전환합니다.  
  
2.  **가져온 네임스페이스** 섹션에서, 포함하는 요소를 프로젝트에서 액세스할 수 있는지 확인합니다.  
  
3.  포함하는 요소가 적어도 하나의 `Public` 멤버를 노출시키는지 확인합니다.  
  
## 참고 항목  
 [참조 페이지, 프로젝트 디자이너\(Visual Basic\)](/visual-studio/ide/reference/references-page-project-designer-visual-basic)   
 [방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [Public](../../../visual-basic/language-reference/modifiers/public.md)   
 [Visual Basic의 네임스페이스](../../../visual-basic/programming-guide/program-structure/namespaces.md)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)