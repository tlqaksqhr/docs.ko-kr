---
title: "특성에 저장된 정보 검색 | Microsoft Docs"
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
  - "특성[.NET Framework], 검색"
  - "여러 특성 인스턴스"
  - "특성 검색"
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: 12
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 12
---
# 특성에 저장된 정보 검색
사용자 지정 특성은 간단하게 검색할 수 있습니다.  먼저 검색할 특성의 인스턴스를 선언합니다.  그런 다음 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName> 메서드를 사용하여 검색하려는 특성의 값으로 새로운 특성을 초기화합니다.  새로운 특성을 초기화한 다음에는 해당 속성을 사용하여 값을 가져오기만 하면 됩니다.  
  
> [!IMPORTANT]
>  이 항목에서는 실행 컨텍스트에 로드된 코드의 특성을 검색하는 방법을 설명합니다.  리플렉션 전용 컨텍스트에 로드된 코드의 특성을 검색하려면 [방법: 리플렉션 전용 컨텍스트에 어셈블리 로드](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)에서 볼 수 있듯이 <xref:System.Reflection.CustomAttributeData> 클래스를 사용해야 합니다.  
  
 이 단원에서는 다음과 같은 특성 검색 방법을 설명합니다.  
  
-   [특성의 단일 인스턴스 검색](#cpconretrievingsingleinstanceofattribute)  
  
-   [동일한 범위에 적용된 특성의 여러 인스턴스 검색](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [서로 다른 범위에 적용된 특성의 여러 인스턴스 검색](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## 특성의 단일 인스턴스 검색  
 다음 예제에서는 앞 단원에서 설명한 `DeveloperAttribute`가 클래스 수준의 `MainApp` 클래스에 적용됩니다.  `GetAttribute` 메서드는 **GetCustomAttribute**를 사용하여 클래스 수준의 `DeveloperAttribute`에 저장된 값을 검색한 다음 이 값을 콘솔에 표시합니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 이 프로그램을 실행하면 다음과 같은 텍스트가 표시됩니다.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 해당 특성이 없으면 **GetCustomAttribute** 메서드는 `MyAttribute`를 Null 값으로 초기화합니다.  이 예제에서는 `MyAttribute`에 이러한 인스턴스가 있는지 확인하고 특성이 없는 경우 사용자에게 알립니다.  클래스 범위에서 `DeveloperAttribute`가 없는 경우 다음과 같은 메시지가 콘솔에 표시됩니다.  
  
```  
The attribute was not found.   
```  
  
 이 예제에서는 특성 정의가 현재 네임스페이스에 있는 것으로 간주합니다.  특성 정의가 현재 네임스페이스에 없으면 특성 정의가 있는 네임스페이스를 가져와야 합니다.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## 동일한 범위에 적용된 특성의 여러 인스턴스 검색  
 앞의 예제에서 검사할 클래스와 찾을 특성은 <xref:System.Attribute.GetCustomAttribute%2A>에 전달됩니다.  이 코드는 클래스 수준에서 특성의 인스턴스가 하나만 적용된 경우에 제대로 작동합니다.  하지만 동일한 클래스 수준에서 특성의 인스턴스가 여러 개 적용된 경우에는 **GetCustomAttribute** 메서드가 모든 정보를 검색하지는 않습니다.  동일한 범위에 동일한 특성의 인스턴스가 여러 개 적용된 경우 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>를 사용하여 특성의 모든 인스턴스를 배열에 놓을 수 있습니다.  예를 들어, `DeveloperAttribute`의 인스턴스 두 개가 동일한 클래스의 클래스 수준에 적용된 경우, `GetAttribute` 메서드를 수정하여 두 특성 모두에서 발견된 정보를 표시할 수 있습니다.  동일한 수준에 여러 특성을 적용하려면 특성을 정의할 때 <xref:System.AttributeUsageAttribute>에서 **AllowMultiple** 속성을 **true**로 설정해야 합니다.  
  
 다음 코드 예제에서는 **GetCustomAttributes** 메서드를 사용하여 지정된 클래스에서 `DeveloperAttribute`의 모든 인스턴스를 참조하는 배열을 만드는 방법을 보여 줍니다.  이렇게 하면 모든 특성의 값이 콘솔에 표시됩니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 특성이 없으면 이 코드는 사용자에게 경고를 표시합니다.  특성이 있으면 `DeveloperAttribute`의 두 인스턴스에 들어 있는 정보가 모두 표시됩니다.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## 서로 다른 범위에 적용된 특성의 여러 인스턴스 검색  
 <xref:System.Attribute.GetCustomAttributes%2A> 및 <xref:System.Attribute.GetCustomAttribute%2A> 메서드는 전체 클래스를 검색하여 해당 클래스에 있는 특성의 모든 인스턴스를 반환하지는 않습니다.  대신에 지정된 메서드 또는 멤버를 한 번에 하나씩 검색합니다.  동일한 특성이 모든 멤버에 적용된 클래스가 있는 경우 해당 멤버에 적용된 모든 특성에서 값을 검색하려면 **GetCustomAttributes** 및 **GetCustomAttribute**에 모든 메서드 또는 멤버를 개별적으로 지정해야 합니다.  
  
 다음 코드 예제에서는 클래스를 매개 변수로 사용하고 앞에서 정의한 `DeveloperAttribute` 를 클래스 수준과 해당 클래스의 모든 개별 메서드에서 검색합니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 메서드 수준 또는 클래스 수준에서 `DeveloperAttribute`의 인스턴스가 없으면 `GetAttribute` 메서드는 특성이 없음을 사용자에게 알리고 특성이 없는 메서드 또는 클래스의 이름을 표시합니다.  특성이 있으면 `Name`, `Level` 및 `Reviewed` 필드가 콘솔에 표시됩니다.  
  
 <xref:System.Type> 클래스의 멤버를 사용하면 전달된 클래스의 개별 메서드 및 멤버를 가져올 수 있습니다.  이 예제에서는 먼저 **Type** 개체를 쿼리하여 클래스 수준의 특성 정보를 가져옵니다.  그런 다음 <xref:System.Type.GetMethods%2A?displayProperty=fullName>를 사용하여 모든 메서드의 인스턴스를 <xref:System.Reflection.MemberInfo?displayProperty=fullName> 개체의 배열에 놓아 메서드 수준의 특성 정보를 검색합니다.  또한 <xref:System.Type.GetProperties%2A?displayProperty=fullName> 메서드를 사용하여 속성 수준의 특성을 확인하거나 <xref:System.Type.GetConstructors%2A?displayProperty=fullName> 메서드를 사용하여 생성자 수준의 특성을 확인할 수도 있습니다.  
  
## 참고 항목  
 <xref:System.Type?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=fullName>   
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=fullName>   
 [특성](../../../docs/standard/attributes/index.md)