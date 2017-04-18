---
title: "Weak References | Microsoft Docs"
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
  - "weak references, short"
  - "weak references, using"
  - "weak references, long"
  - "garbage collection, weak references"
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# Weak References
가비지 수집기는 응용 프로그램에서 사용하고 있는 개체를 수집할 수 없으며 응용 프로그램의 코드에서는 해당 개체에 액세스할 수 있습니다.  이 응용 프로그램을 가리켜 개체에 대한 강한 참조를 갖고 있다고 합니다.  
  
 약한 참조의 경우 가비지 수집기에서 해당 개체를 수집할 수 있으며 응용 프로그램에서도 해당 개체에 계속 액세스할 수 있습니다.  약한 참조는 강한 참조가 없을 때 개체가 수집되기 전까지의 임의의 시간 동안만 유효합니다.  약한 참조를 사용할 때 응용 프로그램에서 해당 개체에 대한 강한 참조를 얻을 수 있습니다. 이 경우 해당 개체는 수집할 수 없습니다.  그러나 강한 참조가 다시 설정되기 전에 가비지 수집기가 먼저 개체에 액세스할 위험은 항상 있습니다.  
  
 많은 양의 메모리를 사용하지만 가비지 수집을 통해 회수될 경우 쉽게 다시 만들 수 있는 개체에는 약한 참조가 유용합니다.  
  
 예를 들어, Windows Forms 응용 프로그램의 트리 뷰에 사용자가 선택할 수 있는 옵션이 복잡한 계층 구조로 표시된다고 가정합니다.  내부 데이터가 크면 사용자가 응용 프로그램에서 다른 작업을 수행하고 있을 때 트리를 메모리에 보관하는 것이 효율적이지 않습니다.  
  
 사용자가 응용 프로그램의 다른 부분으로 전환할 때 <xref:System.WeakReference> 클래스를 사용하여 트리에 대한 약한 참조를 만들고 강한 참조는 모두 삭제할 수 있습니다.  사용자가 다시 트리로 돌아오면 응용 프로그램에서는 트리에 대한 강한 참조를 얻으려고 하며 이에 성공하면 트리가 다시 생성되지 않게 됩니다.  
  
 개체에 대한 약한 참조를 설정하려면 추적할 개체의 인스턴스를 사용하여 <xref:System.WeakReference>를 만듭니다.  그런 다음<xref:System.WeakReference.Target%2A> 속성을 해당 개체로 설정하고 해당 개체 참조를 `null`로 설정합니다.  코드 예제를 보려면 클래스 라이브러리의 <xref:System.WeakReference>를 참조하십시오.  
  
## 짧은 약한 참조 및 긴 약한 참조  
 짧은 약한 참조나 긴 약한 참조를 만들 수 있습니다.  
  
-   Short  
  
     짧은 약한 참조의 대상은 해당 개체가 가비지 수집을 통해 회수될 때 `null`이 됩니다.  약한 참조 자체는 관리되는 개체이므로 다른 모든 관리되는 개체와 마찬가지로 가비지 수집될 수 있습니다.  짧은 약한 참조는 <xref:System.WeakReference>의 기본 생성자입니다.  
  
-   Long  
  
     긴 약한 참조는 해당 개체의 <xref:System.Object.Finalize%2A> 메서드가 호출된 후에도 유지됩니다.  따라서 개체를 다시 만들 수 있지만 개체의 상태는 예측할 수 없는 상태로 유지됩니다.  긴 참조를 사용하려면 <xref:System.WeakReference> 생성자에서 `true`를 지정합니다.  
  
     개체 형식에 <xref:System.Object.Finalize%2A> 메서드가 없으면 짧은 약한 참조 기능이 적용되며 약한 참조는 대상이 수집되기 전까지만 유효합니다. 가비지 수집은 종료자가 실행된 후 언제든지 수행될 수 있습니다.  
  
 강한 참조를 설정하고 개체를 다시 사용하려면 <xref:System.WeakReference>의 <xref:System.WeakReference.Target%2A> 속성을 해당 개체의 형식으로 캐스팅합니다.  개체가 수집되었으면 <xref:System.WeakReference.Target%2A> 속성이 `null`을 반환하며, 그렇지 않으면 응용 프로그램에서 개체에 대한 강한 참조를 다시 얻었으므로 개체를 계속 사용할 수 있습니다.  
  
## 약한 참조 사용 지침  
 긴 약한 참조는 개체가 종료된 후 개체의 상태를 예측할 수 없어서 필요한 경우에만 사용합니다.  
  
 개체 크기가 작을 때는 포인터 크기가 그와 같거나 그보다 클 수 있으므로 약한 참조를 사용하지 않는 것이 좋습니다.  
  
 메모리 관리 문제를 자동으로 해결하기 위한 수단으로 약한 참조를 사용하지 않는 것이 좋습니다.  대신 응용 프로그램의 개체를 처리하기 위한 효과적인 캐싱 정책을 개발하십시오.  
  
## 참고 항목  
 [Garbage Collection](../../../docs/standard/garbage-collection/index.md)