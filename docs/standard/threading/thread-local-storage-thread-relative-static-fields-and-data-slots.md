---
title: "Thread Local Storage: Thread-Relative Static Fields and Data Slots | Microsoft Docs"
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
  - "threading [.NET Framework], local storage"
  - "threading [.NET Framework], thread-relative static fields"
  - "local thread storage"
  - "TLS"
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Thread Local Storage: Thread-Relative Static Fields and Data Slots
관리되는 TLS\(스레드 로컬 저장소\)를 사용하여 스레드와 응용 프로그램 도메인에 고유한 데이터를 저장할 수 있습니다.  .NET Framework에서는 스레드 상대 정적 필드와 데이터 슬롯이라는 두 가지 방법으로 TLS를 사용할 수 있습니다.  
  
-   컴파일 타임에 정확한 요구 사항을 예상할 수 있으면 스레드 상대 정적 필드\(Visual Basic에서는 `Shared` 필드\)를 사용합니다.  스레드 상대 정적 필드를 사용하면 최상의 성능이 제공될 뿐 아니라  컴파일 타임에 형식을 검사할 수도 있습니다.  
  
-   런타임에만 실제 요구 사항을 알 수 있으면 데이터 슬롯을 사용합니다.  데이터 슬롯은 스레드 상대 정적 필드보다 느리고 사용하기 어렵습니다. 또한 데이터가 <xref:System.Object> 형식으로 저장되므로 데이터를 사용하기 전에 올바른 형식으로 캐스팅해야 합니다.  
  
 관리되지 않는 C\+\+에서 `TlsAlloc`을 사용하여 슬롯을 동적으로 할당하고 `__declspec(thread)`을 사용하여 변수를 스레드 상대 저장소에 할당하도록 선언할 수 있습니다.  스레드 상대 정적 필드와 데이터 슬롯은 이러한 동작의 관리되는 버전을 제공합니다.  
  
 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 <xref:System.Threading.ThreadLocal%601?displayProperty=fullName> 클래스를 사용하여 개체가 처음 사용될 때 천천히 초기화되는 스레드 지역 개체를 만들 수 있습니다.  자세한 내용은 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)을 참조하십시오.  
  
## 관리되는 TLS에 있는 데이터의 고유성  
 스레드 상대 정적 필드를 사용하든지 아니면 데이터 슬롯을 사용하든지 간에 관리되는 TLS에 있는 데이터는 스레드와 응용 프로그램 도메인의 조합에 고유합니다.  
  
-   응용 프로그램 도메인 내에서 두 스레드가 동일한 필드나 슬롯을 사용하는 경우에도 한 스레드가 다른 스레드의 데이터를 수정할 수는 없습니다.  
  
-   스레드가 여러 응용 프로그램 도메인에 있는 동일한 필드나 슬롯에 액세스하면 각 응용 프로그램 도메인에 별도의 값이 유지됩니다.  
  
 예를 들어, 스레드가 스레드 상대 정적 필드의 값을 설정하고 다른 응용 프로그램 도메인에 들어간 다음 필드 값을 검색하면 두 번째 응용 프로그램 도메인에서 검색된 값이 첫 번째 응용 프로그램 도메인에서 검색된 값과 다릅니다.  두 번째 응용 프로그램 도메인의 필드 값을 새로 설정해도 첫 번째 응용 프로그램 도메인의 필드 값에는 아무런 영향이 없습니다.  
  
 마찬가지로 스레드가 두 개의 서로 다른 응용 프로그램 도메인에서 동일한 이름의 데이터 슬롯을 가져오면 첫 번째 응용 프로그램 도메인의 데이터는 두 번째 응용 프로그램 도메인의 데이터와 독립적으로 유지됩니다.  
  
## 스레드 상대 정적 필드  
 데이터가 항상 스레드와 응용 프로그램 도메인의 조합에 고유하다는 것을 알고 있는 경우 정적 필드에 <xref:System.ThreadStaticAttribute> 특성을 적용합니다.  그러면 이 필드를 다른 모든 정적 필드와 마찬가지로 사용할 수 있습니다.  이 필드의 데이터는 자신을 사용하는 각 스레드에 고유합니다.  
  
 스레드 상대 정적 필드를 사용하면 데이터 슬롯의 경우보다 성능이 향상되며 컴파일 타임 형식 검사를 수행할 수도 있습니다.  
  
 모든 클래스 생성자 코드는 해당 필드에 액세스하는 첫 번째 컨텍스트의 첫 번째 스레드에서 실행되어야 합니다.  동일한 응용 프로그램 도메인에 있는 다른 모든 스레드나 컨텍스트에서 이러한 필드는 참조 형식인 경우 `null`\(Visual Basic에서는 `Nothing`\)로 초기화되고 값 형식인 경우 기본값으로 초기화됩니다.  따라서 클래스 생성자를 사용하여 스레드 상대 정적 필드를 초기화하면 안 됩니다.  대신 스레드 상대 정적 필드를 초기화하지 않고 스레드 상대 정적 필드가 `null`\(`Nothing`\)이나 해당 기본값으로 초기화된다고 가정해야 합니다.  
  
## 데이터 슬롯  
 .NET Framework에서는 스레드와 응용 프로그램 도메인의 조합에 고유한 동적 데이터 슬롯을 제공합니다.  데이터 슬롯에는 명명된 슬롯과 명명되지 않은 슬롯이라는 두 가지 유형이 있습니다.  두 유형 모두 <xref:System.LocalDataStoreSlot> 구조체를 사용하여 구현됩니다.  
  
-   명명된 데이트 슬롯을 만들려면 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=fullName> 또는 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=fullName> 메서드를 사용합니다.  기존의 명명된 슬롯에 대한 참조를 가져오려면 해당 이름을 <xref:System.Threading.Thread.GetNamedDataSlot%2A> 메서드에 전달합니다.  
  
-   명명되지 않은 데이트 슬롯을 만들려면 <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=fullName> 메서드를 사용합니다.  
  
 명명된 슬롯과 명명되지 않은 슬롯 모두 <xref:System.Threading.Thread.SetData%2A?displayProperty=fullName> 및 <xref:System.Threading.Thread.GetData%2A?displayProperty=fullName> 메서드를 사용하여 슬롯 정보를 설정하고 검색합니다.  이러한 메서드는 현재 자신들을 실행하고 있는 스레드의 데이터에 대한 작업을 항상 수행하는 정적 메서드입니다.  
  
 명명된 슬롯은 명명되지 않은 슬롯에 대한 참조를 유지하는 대신 필요할 때 해당 이름을 <xref:System.Threading.Thread.GetNamedDataSlot%2A> 메서드를 전달하여 검색할 수 있기 때문에 편리할 수 있습니다.  그러나 다른 구성 요소에서 스레드 상대 저장소에 대해 같은 이름을 사용하고 스레드가 이 구성 요소에서도 코드를 실행하는 경우 두 구성 요소가 서로의 데이터를 손상시킬 수 있습니다. 이 시나리오에서는 두 구성 요소가 동일한 응용 프로그램 도메인에서 실행되고 있지만 동일한 데이터를 공유하도록 설계되지 않은 것으로 가정합니다.  
  
## 참고 항목  
 <xref:System.ContextStaticAttribute>   
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=fullName>   
 <xref:System.ThreadStaticAttribute>   
 <xref:System.Runtime.Remoting.Messaging.CallContext>   
 [Threading](../../../docs/standard/threading/index.md)