---
title: "복사 및 고정 | Microsoft Docs"
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
  - "복사, interop 마샬링"
  - "interop 마샬링, 복사"
  - "interop 마샬링, 고정"
  - "고정, interop 마샬링"
ms.assetid: 0059f576-e460-4e70-b257-668870e420b8
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 8
---
# 복사 및 고정
데이터를 마샬링할 때 interop 마샬러에서는 마샬링되는 데이터를 복사하거나 고정할 수 있습니다.  데이터를 복사하는 것은 한 메모리 위치에 있는 데이터의 복사본을 다른 메모리 위치에 놓는 것입니다.  다음 그림에서는 관리되는 메모리에서 관리되지 않는 메모리로 값 형식을 복사할 때와 참조로 전달되는 형식을 복사할 때의 차이점을 보여 줍니다.  
  
 ![값 및 참조로 전달되는 값 형식](../../../docs/framework/interop/media/interopmarshalcopy.gif "interopmarshalcopy")  
값 및 참조로 전달되는 값 형식  
  
 값으로 전달되는 메서드 인수는 비관리 코드로 마샬링될 때 스택에 값으로 마샬링됩니다.  복사 프로세스는 직접적입니다.  참조로 전달되는 인수는 스택에 포인터로 전달됩니다.  참조 형식은 값 및 참조로 전달될 수도 있습니다.  다음 그림에서 보여 주는 것처럼, 값으로 전달되는 참조 형식은 복사되거나 고정됩니다.  
  
 ![COM interop](../../../docs/framework/interop/media/interopmarshalpin.gif "interopmarshalpin")  
값 및 참조로 전달되는 참조 형식  
  
 임시 고정은 현재 메모리 위치에 있는 데이터를 잠금으로써 공용 언어 런타임의 가비지 수집기에서 다시 할당하지 못하도록 하는 것입니다.  마샬러에서는 데이터를 고정함으로써 복사할 때의 오버헤드를 줄이고 성능을 향상시킵니다.  마샬링 프로세스 동안 데이터를 복사할지 고정할지 여부는 해당 데이터의 형식에 따라 결정됩니다.  고정 작업은 <xref:System.String> 등의 개체애 대한 마샬링 중에 자동으로 수행되지만, <xref:System.Runtime.InteropServices.GCHandle> 클래스를 사용하여 수동으로 메모리를 고정할 수도 있습니다.  
  
## Formatted Blittable 클래스  
 formatted [Blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) 클래스의 레이아웃은 고정되어 있으며\(formatted\), 이 클래스는 관리되는 메모리와 관리되지 않는 메모리에서 공통되는 데이터 표현을 가집니다.  이러한 형식을 마샬링해야 하는 경우에는 힙에 있는 개체에 대한 참조가 호출 수신자에게 직접 전달됩니다.  호출 수신자는 포인터로 참조되는 메모리 위치의 내용을 변경할 수 있습니다.  
  
> [!NOTE]
>  호출 수신자는 매개 변수가 Out 또는 In\/Out으로 표시된 경우 메모리 내용을 변경할 수 있습니다.  반면, 매개 변수가 In으로 마샬링되도록 설정된 경우\(formatted blittable 형식의 기본값\)에는 호출 수신자가 내용을 변경하지 않아야 합니다.  In 개체를 수정하면 동일한 클래스를 형식 라이브러리로 내보내서 아파트 간 호출을 실행하는 데 사용할 경우 문제가 발생합니다.  
  
## 비 Blittable Formatted 클래스  
 formatted [비 Blittable](../../../docs/framework/interop/blittable-and-non-blittable-types.md) 클래스의 레이아웃은 고정되어 있지만\(formatted\), 이 클래스의 데이터 표현은 관리되는 메모리와 관리되지 않는 메모리에서 서로 다릅니다.  다음과 같은 경우에는 데이터를 변환해야 할 수 있습니다.  
  
-   비 blittable 클래스를 값으로 마샬링하는 경우 호출 수신자는 해당 데이터 구조체의 복사본에 대한 포인터를 받습니다.  
  
-   비 blittable 클래스를 참조로 마샬링하는 경우 호출 수신자는 해당 데이터 구조체의 복사본에 대한 포인터에 대한 포인터를 받습니다.  
  
-   <xref:System.Runtime.InteropServices.InAttribute> 특성이 설정된 경우 이 복사본은 항상 해당 인스턴스의 상태를 사용하여 초기화되며 필요할 때 마샬링됩니다.  
  
-   <xref:System.Runtime.InteropServices.OutAttribute> 특성이 설정된 경우에는 반환될 때 항상 상태가 해당 인스턴스로 다시 복사되며 필요할 때 마샬링됩니다.  
  
-   **InAttribute**와 **OutAttribute**가 모두 설정된 경우에는 두 개의 복사본이 모두 필요합니다.  한 특성이 생략되면 마샬러에서는 둘 중 한 복사본을 제거함으로써 최적화할 수 있습니다.  
  
## 참조 형식  
 참조 형식은 값 또는 참조로 전달될 수 있습니다.  값으로 전달될 때는 해당 형식에 대한 포인터가 스택에 전달됩니다.  참조로 전달될 때는 해당 형식에 대한 포인터에 대한 포인터가 스택에 전달됩니다.  
  
 참조 형식에는 다음의 조건부 동작이 있습니다.  
  
-   참조 형식이 값으로 전달되고 비 blittable 형식의 멤버를 포함하는 경우 해당 형식은 두 번 변환됩니다.  
  
    -   인수가 관리되지 않는 쪽에 전달될 때  
  
    -   호출에서 반환될 때  
  
     불필요한 복사 및 변환을 방지하기 위해 이러한 형식은 In 매개 변수로 마샬링됩니다.  호출 수신자가 변경한 내용을 호출자가 볼 수 있도록 하려면 인수에 **InAttribute** 및 **OutAttribute** 특성을 명시적으로 적용해야 합니다.  
  
-   참조 형식이 값으로 전달되고 blittable 형식의 멤버만 포함하는 경우에는 마샬링하는 동안 해당 형식을 고정할 수 있으며 호출 수신자가 해당 형식의 멤버에 대해 변경한 내용을 호출자가 볼 수 있습니다.  이 동작이 필요하면 **InAttribute** 및 **OutAttribute**를 명시적으로 적용합니다.  interop 마샬러에서는 기본적으로 형식 라이브러리에 방향 정보를 In으로 내보내지만 이러한 방향 특성이 없으면 방향 정보를 내보내지 않으므로 COM의 아파트 간 마샬링과 관련된 문제가 발생할 수 있습니다.  
  
-   참조 형식이 참조로 전달되는 경우에는 기본적으로 In\/Out으로 마샬링됩니다.  
  
## System.String 및 System.Text.StringBuilder  
 데이터를 비관리 코드에 값 또는 참조로 마샬링할 때 마샬러에서는 대개 데이터를 보조 버퍼로 복사하고 가능하면 복사하는 동안 문자 집합을 변환하며, 해당 버퍼에 대한 참조를 호출 수신자에게 전달합니다.  참조가 **SysAllocString**을 사용하여 할당된 **BSTR**이 아니면 해당 참조는 항상 **CoTaskMemAlloc**을 사용하여 할당됩니다.  
  
 둘 중 한 문자열 형식을 유니코드 문자열 등의 값으로 마샬링할 때 마샬러에서는 최적화를 위해 해당 문자열을 새 버퍼로 복사하는 대신 내부 유니코드 버퍼에 있는 관리되는 문자열에 대한 직접 참조를 호출 수신자에게 전달합니다.  
  
> [!CAUTION]
>  문자열을 값으로 전달할 때 호출 수신자는 마샬러가 전달한 참조를 변경하지 말아야 합니다.  관리되는 힙을 손상시킬 수 있기 때문입니다.  
  
 <xref:System.String?displayProperty=fullName>을 참조로 전달할 때 마샬러에서는 호출을 실행하기 전에 해당 문자열의 내용을 보조 버퍼로 복사합니다.  그런 다음 호출에서 반환할 때 버퍼의 내용을 새 문자열로 복사합니다.  이 방법을 사용하면 변경할 수 없는 관리되는 문자열이 변경되지 않은 상태로 있게 됩니다.  
  
 <xref:System.Text.StringBuilder?displayProperty=fullName>를 값으로 전달할 때 마샬러에서는 **StringBuilder**의 내부 버퍼에 대한 참조를 호출자에게 직접 전달합니다.  호출자와 호출 수신자는 버퍼 크기에 동의해야 합니다.  호출 수신자는 적절한 길이의 **StringBuilder**를 만들어야 합니다.  또한 호출 수신자는 해당 버퍼가 오버런되지 않도록 필요한 예방 조치를 취해야 합니다.  값으로 전달되는 참조 형식은 기본적으로 In 매개 변수로 전달된다는 규칙이 **StringBuilder**에는 적용되지 않습니다.  StringBuilder는 항상 In\/Out으로 전달됩니다.  
  
## 참고 항목  
 [기본 마샬링 동작](../../../docs/framework/interop/default-marshaling-behavior.md)   
 [Memory Management with the Interop Marshaler](http://msdn.microsoft.com/ko-kr/417206ce-ee3e-4619-9529-0c0b686c7bee)   
 [Directional Attributes](http://msdn.microsoft.com/ko-kr/241ac5b5-928e-4969-8f58-1dbc048f9ea2)   
 [Interop 마샬링](../../../docs/framework/interop/interop-marshaling.md)