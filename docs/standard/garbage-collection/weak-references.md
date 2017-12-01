---
title: "약한 참조"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- weak references, short
- weak references, using
- weak references, long
- garbage collection, weak references
ms.assetid: 6a600fe5-3af3-4c64-82da-10a0a8e2d79b
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 906c23caa7065486bb094ad2475ed9e7e24b3d9c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="weak-references"></a>약한 참조
응용 프로그램의 코드가 해당 개체에 연결될 수 있는 반면 가비지 수집기는 응용 프로그램에서 사용 중인 개체를 수집할 수 없습니다. 응용 프로그램은 개체에 대한 강력한 참조를 가진다고 합니다.  
  
 Weak references는 응용 프로그램에서 개체에 계속 액세스할 수 있는 동안 가비지 수집기에서 해당 개체를 수집할 수 있도록 합니다. 강한 참조가 없을 경우 Weak references는 개체가 수집되기 전까지 임의의 시간 동안에만 유효합니다. Weak references를 사용하면 응용 프로그램은 여전히 개체에 대한 강한 참조를 유지할 수 있으며 이로 인해 개체가 수집되지 않도록 방지합니다. 그러나 강력한 참조를 다시 설정하기 전에 가비지 수집기가 먼저 개체에 연결될 위험이 항상 존재합니다.  
  
 Weak references는 많은 메모리를 사용하는 개체에 유용하지만 가비지 수집에서 회수될 경우 쉽게 다시 만들 수 있습니다.  
  
 사용자에 게 계층적 복잡 한 선택 옵션을 표시 하는 Windows Forms 응용 프로그램의 트리 뷰 한다고 가정 합니다. 기본 데이터가 크다면 사용자가 응용 프로그램에서 다른 작업을 수행하는 경우 트리를 메모리에 유지하는 것은 비효율적입니다.  
  
 사용자 응용 프로그램의 다른 부분으로 전환할 때 사용할 수 있습니다는 <xref:System.WeakReference> 트리에 대 한 약한 참조를 만들고 모든 강력한 참조를 제거 하는 클래스입니다. 사용자가 트리로 다시 전환할 때 응용 프로그램은 트리에 대한 강한 참조를 가지려고 하며 이 시도가 성공할 경우 트리를 다시 생성하지 않도록 방지합니다.  
  
 만들 개체를 사용 하 여 약한 참조를 설정 하려면 한 <xref:System.WeakReference> 개체의 인스턴스를 사용 하 여 추적 해야 합니다. 그런 다음 <xref:System.WeakReference.Target%2A> 속성을 해당 개체로 설정하고 해당 개체에 대한 원래 참조를 `null`로 설정합니다. 코드 예제를 참조 하세요. <xref:System.WeakReference> 클래스 라이브러리에서.  
  
## <a name="short-and-long-weak-references"></a>Short 및 Long Weak References  
 Short Weak Reference 또는 Long Weak References를 만들 수 있습니다.  
  
-   Short  
  
     가비지 수집에서 개체를 회수하는 경우 Short Weak Reference의 대상은 `null`이 됩니다. Weak Reference는 자체 관리되는 개체이며 다른 관리되는 개체와 마찬가지로 가비지 수집의 대상입니다.  짧은 약한 참조에 대 한 기본 생성자는 <xref:System.WeakReference>합니다.  
  
-   Long  
  
     개체의 긴 약한 참조를 유지 하는 <xref:System.Object.Finalize%2A> 메서드가 호출 되었습니다. 이렇게 하면 개체를 다시 만들 수 있지만 개체의 상태는 예측할 수 없게 됩니다. 긴 참조를 사용 하려면 지정 `true` 에 <xref:System.WeakReference> 생성자입니다.  
  
     개체의 형식에 없는 경우는 <xref:System.Object.Finalize%2A> 메서드, 짧은 약한 참조 기능이 적용 하 고 대상이 수집 될 때까지 실행 된 종료자 후 언제 든 지 발생할 수 있는 약한 참조는 유효 합니다.  
  
 강한 참조를 설정 하 고 개체를 다시 사용 하려면 캐스팅는 <xref:System.WeakReference.Target%2A> 속성의는 <xref:System.WeakReference> 개체의 형식입니다. 경우는 <xref:System.WeakReference.Target%2A> 속성에서 반환 `null`, 개체가 고 그러지 않으면 수집, 계속 응용 프로그램에 대 한 강한 참조를 재설정 했습니다 때문에 개체를 사용할 수 있습니다.  
  
## <a name="guidelines-for-using-weak-references"></a>Weak References를 사용하기 위한 지침  
 종료된 후에 개체의 상태를 예측할 수 없기 때문에 필요한 경우에만 Long Weak Referencs를 사용합니다.  
  
 포인터 자체는 이상일 수 있기 때문에 작은 개체에 Weak Referencs를 사용하지 않습니다.  
  
 메모리 관리 문제에 대한 자동 솔루션으로 Weak Referencs를 사용하지 않습니다. 대신, 응용 프로그램의 개체를 처리하기 위한 효과적인 캐싱 정책을 개발합니다.  
  
## <a name="see-also"></a>참고 항목  
 [가비지 수집](../../../docs/standard/garbage-collection/index.md)
