---
title: "COM 래퍼 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "COM 호출 가능 래퍼"
  - "COM interop, COM 래퍼"
  - "COM 래퍼"
  - "COM, 래퍼"
  - "비관리 코드와의 상호 운용, COM 래퍼"
  - "래퍼 클래스"
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# COM 래퍼
COM은 다음과 같은 몇 가지 중요한 측면에서 .NET Framework 개체 모델과 다릅니다.  
  
-   COM 개체의 클라이언트는 COM 개체의 수명을 관리해야 하고 공용 언어 런타임은 환경에서의 개체 수명을 관리합니다.  
  
-   COM 개체의 클라이언트는 서비스를 제공하는 인터페이스를 요청하고 다시 인터페이스 포인터를 반환하여 해당 서비스를 사용할 수 있는지 여부를 확인합니다.  .NET 개체의 클라이언트는 리플렉션을 사용하여 개체의 기능에 대한 설명을 얻을 수 있습니다.  
  
-   NET 개체는 .NET Framework 실행 환경에서 관리하는 메모리에 상주합니다.  실행 환경에서는 성능상의 이유로 메모리의 개체를 이리 저리 이동할 수 있으며 이동하는 개체에 대한 모든 참조를 업데이트할 수 있습니다.  개체에 대한 포인터를 획득하는 관리되지 않는 클라이언트는 동일한 위치를 유지하기 위해 개체에 의존합니다.  이러한 클라이언트에는 위치가 고정되지 않은 개체를 처리하기 위한 메커니즘이 없습니다.  
  
 이러한 차이점을 극복하기 위해 런타임은 래퍼 클래스를 제공하여 관리되는 클라이언트와 관리되지 않는 클라이언트 둘 다 해당하는 각 환경 내에서 개체를 호출하는 것으로 간주되게 합니다.  관리되는 클라이언트가 COM 개체에 대한 메서드를 호출할 때마다 런타임은 [RCW](../../../docs/framework/interop/runtime-callable-wrapper.md)를 만듭니다.  RCW는 특히 관리되는 참조 메커니즘과 관리되지 않는 참조 메커니즘 간의 차이점을 추출합니다.  또한 런타임에서는 [CCW](../../../docs/framework/interop/com-callable-wrapper.md)를 만들어 프로세스를 반대로 만듭니다. 즉, COM 클라이언트가 .NET 개체에서 아무런 문제 없이 원만하게 메서드를 호출할 수 있습니다.  다음 그림과 같이 호출 코드에 따라 런타임에서 만드는 래퍼 클래스가 결정됩니다.  
  
 ![COM 래퍼 개요](../../../docs/framework/interop/media/bidirectional.gif "bidirectional")  
COM 래퍼 개요  
  
 대부분의 경우 런타임에서 생성하는 표준 RCW 또는 CCW는 COM과 .NET Framework 간의 경계를 지나 호출하기 위한 적절한 마샬링을 제공합니다.  사용자 지정 특성을 사용하면 런타임에서 관리 코드와 비관리 코드를 나타내는 방법을 선택적으로 조정할 수 있습니다.  
  
## 참고 항목  
 [Advanced COM Interoperability](http://msdn.microsoft.com/ko-kr/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [RCW](../../../docs/framework/interop/runtime-callable-wrapper.md)   
 [CCW](../../../docs/framework/interop/com-callable-wrapper.md)   
 [Customizing Standard Wrappers](http://msdn.microsoft.com/ko-kr/c40d089b-6a3c-41b5-a20d-d760c215e49d)   
 [How to: Customize Runtime Callable Wrappers](http://msdn.microsoft.com/ko-kr/4a4bb3da-4d60-4517-99f2-78d46a681732)