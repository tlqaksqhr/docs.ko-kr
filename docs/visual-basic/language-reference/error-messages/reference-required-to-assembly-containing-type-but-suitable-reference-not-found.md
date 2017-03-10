---
title: "&#39;&lt;typename&gt;&#39; 형식을 포함하는 &#39;&lt;assemblyidentity&gt;&#39; 어셈블리에 대한 참조가 필요하지만 &#39;&lt;projectname1&gt;&#39; 프로젝트와 &#39;&lt;projectname2&gt;&#39; 프로젝트 간의 모호성으로 인해 적합한 참조를 찾을 수 없습니다. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30969"
  - "vbc30969"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30969"
ms.assetid: 1b29dbc5-8268-45fe-bfc2-b2070a5c845c
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &#39;&lt;typename&gt;&#39; 형식을 포함하는 &#39;&lt;assemblyidentity&gt;&#39; 어셈블리에 대한 참조가 필요하지만 &#39;&lt;projectname1&gt;&#39; 프로젝트와 &#39;&lt;projectname2&gt;&#39; 프로젝트 간의 모호성으로 인해 적합한 참조를 찾을 수 없습니다.
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

식은 프로젝트 외부에 정의된 클래스, 구조체, 인터페이스, 열거형 또는 대리자와 같은 형식을 사용합니다. 그러나 해당 형식을 정의하는 둘 이상의 어셈블리에 대한 프로젝트 참조가 있습니다.  
  
 인용된 프로젝트는 이름이 동일한 어셈블리를 생성합니다. 따라서 컴파일러에서 사용자가 액세스하려는 형식에 사용할 어셈블리를 확인할 수 없습니다.  
  
 다른 어셈블리에 정의된 형식에 액세스하려면 [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] 컴파일러에 해당 어셈블리에 대한 참조가 있어야 합니다. 이 참조는 프로젝트 간의 순환 참조를 발생시키지 않는 명확한 단일 참조여야 합니다.  
  
 **오류 ID:** BC30969  
  
### 이 오류를 해결하려면  
  
1.  참조할 프로젝트에 가장 적합한 어셈블리를 생성하는 프로젝트를 결정합니다. 이러한 결정을 위해 파일 접근성 및 업데이트 빈도 등의 조건을 사용할 수 있습니다.  
  
2.  프로젝트 속성에서 사용 중인 형식을 정의하는 어셈블리가 포함된 파일에 대한 참조를 추가합니다.  
  
## 참고 항목  
 [프로젝트의 참조 관리](/visual-studio/ide/managing-references-in-a-project)   
 [References to Declared Elements](../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [NIB 방법: 프로젝트 속성 및 구성 설정 수정](http://msdn.microsoft.com/ko-kr/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)   
 [끊어진 참조 문제 해결](/visual-studio/ide/troubleshooting-broken-references)