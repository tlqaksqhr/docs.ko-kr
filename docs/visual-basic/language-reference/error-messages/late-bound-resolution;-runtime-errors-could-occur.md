---
title: "Late bound resolution; runtime errors could occur | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42017"
  - "BC42017"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42017"
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# Late bound resolution; runtime errors could occur
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

개체는 [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md)으로 선언된 변수에 개체가 할당됩니다.  
  
 변수를 `Object`로 선언하면 컴파일러에서 *런타임에 바인딩*을 수행해야 하기 때문에 런타임에 추가 연산이 발생합니다.  이렇게 되면 응용 프로그램이 런타임 오류에 노출될 수도 있습니다.  예를 들어 `Object` 변수에 <xref:System.Windows.Forms.Form>을 할당하고 <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName> 속성에 액세스하면 <xref:System.Windows.Forms.Form> 클래스가 `NameTable` 속성을 노출하지 않으므로 런타임에서 <xref:System.MemberAccessException>을 throw합니다.  
  
 변수를 특정 형식으로 선언하면 컴파일러는 컴파일 타임에 *초기 바인딩*을 수행할 수 있습니다.  그러면 성능이 향상되고 특정 형식의 멤버에 대한 액세스를 제어할 수 있으며 코드를 보다 쉽게 읽을 수 있습니다.  
  
 기본적으로 이 메시지는 경고입니다.  경고를 숨기거나 경고를 오류로 처리하는 방법은 [Visual Basic에서 경고 구성](/visual-studio/ide/configuring-warnings-in-visual-basic)을 참조하십시오.  
  
 **오류 ID:** BC33024  
  
### 이 오류를 해결하려면  
  
-   가능한 경우 변수를 특정 형식으로 선언합니다.  
  
## 참고 항목  
 [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)