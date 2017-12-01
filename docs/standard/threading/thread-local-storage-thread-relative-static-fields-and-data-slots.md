---
title: "스레드 로컬 저장소: 스레드 상대 정적 필드 및 데이터 슬롯"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- threading [.NET Framework], local storage
- threading [.NET Framework], thread-relative static fields
- local thread storage
- TLS
ms.assetid: c633a4dc-a790-4ed1-96b5-f72bd968b284
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 39dd80d378171563f2aadadaa146278e8a417d32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="thread-local-storage-thread-relative-static-fields-and-data-slots"></a>스레드 로컬 저장소: 스레드 상대 정적 필드 및 데이터 슬롯
스레드 및 응용 프로그램 도메인에 고유한 관리 되는 스레드 로컬 저장소 (TLS) 데이터를 저장을 사용할 수 있습니다. .NET Framework에서 제공 하는 두 가지 방법으로 사용 하도록 관리 TLS: 스레드 상대 정적 필드 및 데이터 슬롯입니다.  
  
-   스레드 관련 정적 필드를 사용 하 여 (스레드 상대 `Shared` Visual Basic의 필드) 컴파일 타임에 정확한 요구 사항을 예상할 수 있는 경우. 스레드 관련 정적 필드는 최적의 성능을 제공 합니다. 또한 제공 컴파일 타임 형식 검사의 이점을 합니다.  
  
-   실제 요구 사항을 런타임에만 노출 될 수 있습니다 하는 경우 데이터 슬롯을 사용 합니다. 데이터 형식으로 저장 됩니다 및 데이터 슬롯은 느리고 스레드 상대 정적 필드 보다 사용 <xref:System.Object>이므로 사용 하기 전에 올바른 형식으로 캐스팅 해야 합니다.  
  
 관리 되지 않는 c + +를 사용 하 여 `TlsAlloc` 슬롯을 동적으로 할당 하 고 `__declspec(thread)` 변수 스레드 상대 저장소에 할당 되는 선언 하 합니다. 이 동작의 관리 되는 버전을 제공 하는 스레드 상대 정적 필드 및 데이터 슬롯입니다.  
  
 에 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], 사용할 수 있습니다는 <xref:System.Threading.ThreadLocal%601?displayProperty=nameWithType> 클래스는 개체가 처음 사용 하는 경우 지연 초기화 하는 스레드 로컬 개체를 만들 수 있습니다. 자세한 내용은 [초기화 지연](../../../docs/framework/performance/lazy-initialization.md)을 참조하세요.  
  
## <a name="uniqueness-of-data-in-managed-tls"></a>관리 되는 TLS에 있는 데이터의 고유성  
 스레드 상대 정적 필드 또는 데이터 슬롯을 사용 하는지 여부를 관리 되는 TLS에 있는 데이터는 스레드 및 응용 프로그램 도메인의 조합에 고유 합니다.  
  
-   응용 프로그램 도메인 내에서 스레드를 하나씩 두 스레드 슬롯 또는 동일한 필드를 사용 하는 경우에 다른 스레드에서 데이터를 수정할 수 없습니다.  
  
-   여러 응용 프로그램 도메인에서 동일한 필드 또는 슬롯을 액세스 하는 스레드를 각 응용 프로그램 도메인에서 별도 값을 유지 관리 됩니다.  
  
 예를 들어 스레드를 설정 하는 경우 다른 응용 프로그램 도메인을 입력 하 고 필드의 값을 검색 하는 스레드 상대 정적 필드의 값, 두 번째 응용 프로그램 도메인에서 검색 된 값이 첫 번째 응용 프로그램 도메인의 값에서과 다른 합니다. 두 번째 응용 프로그램 도메인의 필드에 대 한 새 값을 설정 필드 값의 첫 번째 응용 프로그램 도메인에 영향을 주지 않습니다.  
  
 마찬가지로, 스레드를 두 개의 서로 다른 응용 프로그램 도메인에서 동일한 이름의 데이터 슬롯을 가져오면 첫 번째 응용 프로그램 도메인에서 데이터는 두 번째 응용 프로그램 도메인에 있는 데이터의 독립적인 남아 있습니다.  
  
## <a name="thread-relative-static-fields"></a>스레드 관련 정적 필드  
 데이터의 일부는 스레드 및 응용 프로그램 도메인 조합에 고유한 항상 알고 있는 경우 적용 된 <xref:System.ThreadStaticAttribute> 특성을 정적 필드입니다. 다른 정적 필드를 사용할 때 처럼 필드를 사용 합니다. 필드의 데이터는 사용 하 여 각 스레드에 고유 합니다.  
  
 스레드 관련 정적 필드 데이터 슬롯의 경우 보다 더 나은 성능을 제공할 및 컴파일 타임 형식 검사의 이점이 있습니다.  
  
 주의 모든 클래스 생성자 코드 필드에 액세스 하는 첫 번째 컨텍스트에서 첫 번째 스레드에서 실행 됩니다. 모든 다른 스레드 또는 컨텍스트에서 동일한 응용 프로그램 도메인에서 필드로 초기화 됩니다 `null` (`Nothing` Visual basic에서)은 참조 형식 또는 값 있더라도 값 형식이 기본값으로 경우. 따라서 안됩니다 클래스 생성자 스레드 상대 정적 필드를 초기화 합니다. 대신, 스레드 상대 정적 필드를 초기화 하지 않도록 하 고에 초기화 된다고 가정 `null` (`Nothing`) 또는를 기본값으로 합니다.  
  
## <a name="data-slots"></a>데이터 슬롯  
 .NET Framework에서는 스레드 및 응용 프로그램 도메인의 조합에 고유한 동적 데이터 슬롯입니다. 두 가지 방법으로 데이터 슬롯의: 명명 된 슬롯 및 명명 되지 않은 슬롯입니다. 둘 다 사용 하 여 구현 되는 <xref:System.LocalDataStoreSlot> 구조입니다.  
  
-   명명된 된 데이터 슬롯을 만들려면 사용는 <xref:System.Threading.Thread.AllocateNamedDataSlot%2A?displayProperty=nameWithType> 또는 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType> 메서드. 전달 하 고 이름을 기존의 명명 된 슬롯에 대 한 참조를 가져오려면는 <xref:System.Threading.Thread.GetNamedDataSlot%2A> 메서드.  
  
-   명명 되지 않은 데이터 슬롯을 만들려면 사용은 <xref:System.Threading.Thread.AllocateDataSlot%2A?displayProperty=nameWithType> 메서드.  
  
 명명 된 슬롯과 명명 되지 않은 및 둘 다에 사용 된 <xref:System.Threading.Thread.SetData%2A?displayProperty=nameWithType> 및 <xref:System.Threading.Thread.GetData%2A?displayProperty=nameWithType> 설정 및 슬롯에 대 한 정보를 검색 하는 메서드. 이 해당를 현재 실행 중인 스레드에 대 한 데이터에만 적용 하는 정적 메서드입니다.  
  
 명명 된 슬롯에 해당 이름을 전달 하 여 필요할 때 슬롯을 검색할 수 없으므로 편리할 수 있습니다는 <xref:System.Threading.Thread.GetNamedDataSlot%2A> 명명 되지 않은 슬롯에 대 한 참조를 유지 하는 대신 메서드. 그러나 다른 구성 요소는 스레드 관련 저장소에 동일한 이름을 사용 하 여 스레드 구성 요소와 다른 구성 요소가 모두에서 코드를 실행 하는 경우 두 가지 구성 요소가 다른 사용자의 데이터 손상 될 수 있습니다. (이 시나리오에서는 두 구성 요소를 동일한 응용 프로그램 도메인에서 실행 되 고 있는지와 동일한 데이터를 공유 하도록 설계 되지 않은)  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ContextStaticAttribute>  
 <xref:System.Threading.Thread.GetNamedDataSlot%2A?displayProperty=nameWithType>  
 <xref:System.ThreadStaticAttribute>  
 <xref:System.Runtime.Remoting.Messaging.CallContext>  
 [스레딩](../../../docs/standard/threading/index.md)
