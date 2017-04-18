---
title: "방법: 이벤트 속성을 사용하여 여러 이벤트 처리 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "이벤트 처리[.NET Framework], 여러 가지 이벤트"
  - "이벤트 속성[.NET Framework]"
  - "이벤트[.NET Framework], 여러 가지"
  - "여러 이벤트[.NET Framework]"
ms.assetid: 30047cba-e2fd-41c6-b9ca-2ad7a49003db
caps.latest.revision: 16
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 15
---
# 방법: 이벤트 속성을 사용하여 여러 이벤트 처리
이벤트 속성을 사용하려면 이벤트를 발생시키는 클래스에서 이벤트 속성을 정의한 다음 이벤트를 처리하는 클래스에서 이벤트 속성의 대리자를 설정합니다.  클래스에서 여러 이벤트 속성을 구현하려면 클래스가 각 이벤트에 대해 정의된 대리자를 내부적으로 저장 및 유지 관리해야 합니다.  일반적인 방법은 이벤트 키로 인덱싱된 대리자 컬렉션을 구현하는 것입니다.  
  
 각 이벤트에 대한 대리자를 저장하려면 <xref:System.ComponentModel.EventHandlerList> 클래스를 사용하거나 고유한 컬렉션을 구현하면 됩니다.  컬렉션 클래스는 이벤트 키에 따라 이벤트 처리기 대리자를 설정, 액세스 및 검색하는 메서드를 제공해야 합니다.  예를 들어 <xref:System.Collections.Hashtable> 클래스를 사용하거나 <xref:System.Collections.DictionaryBase> 클래스에서 사용자 지정 클래스를 파생시킬 수 있습니다.  대리자 컬렉션의 구현 세부 정보는 클래스 외부에 노출할 필요가 없습니다.  
  
 클래스 내의 각 이벤트 속성은 add 접근자 메서드 및 remove 접근자 메서드를 정의합니다.  이벤트 속성에 대한 add 접근자는 대리자 컬렉션에 입력 대리자 인스턴스를 추가합니다.  이벤트 속성에 대한 remove 접근자는 대리자 컬렉션에서 입력 대리자 인스턴스를 제거합니다.  이벤트 속성 접근자는 이벤트 속성의 미리 정의된 키를 사용하여 대리자 컬렉션에서 인스턴스를 추가 및 제거합니다.  
  
### 이벤트 속성을 사용하여 여러 이벤트 처리하려면  
  
1.  이벤트를 발생시키는 클래스 내에서 대리자 컬렉션을 정의합니다.  
  
2.  각 이벤트에 대한 키를 정의합니다.  
  
3.  이벤트를 발생시키는 클래스에서 이벤트 속성을 정의합니다.  
  
4.  대리자 컬렉션을 사용하여 이벤트 속성에 대한 add 및 remove 접근자 메서드를 구현합니다.  
  
5.  public 이벤트 속성을 사용하여 이벤트를 처리하는 클래스에서 이벤트 처리기 대리자를 추가 및 제거합니다.  
  
## 예제  
 다음 C\# 예제에서는 <xref:System.ComponentModel.EventHandlerList>를 사용하여 각 이벤트의 대리자를 저장하는 이벤트 속성 `MouseDown` 및 `MouseUp`을 구현합니다.  이벤트 속성 구문의 키워드는 굵은 글꼴로 표시됩니다.  
  
> [!NOTE]
>  [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)]에서는 이벤트 속성이 지원되지 않습니다.  
  
 [!code-cpp[Conceptual.Events.Other#31](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.events.other/cpp/example3.cpp#31)]
 [!code-csharp[Conceptual.Events.Other#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.events.other/cs/example3.cs#31)]
 [!code-vb[Conceptual.Events.Other#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.events.other/vb/example3.vb#31)]  
  
## 참고 항목  
 <xref:System.ComponentModel.EventHandlerList?displayProperty=fullName>   
 [이벤트](../../../docs/standard/events/index.md)   
 [System.Web.UI.Control.Events](frlrfSystemWebUIControlClassEventsTopic)   
 [How to: Declare Custom Events To Conserve Memory](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Conserve%20Memory%20\(Visual%20Basic\).md)