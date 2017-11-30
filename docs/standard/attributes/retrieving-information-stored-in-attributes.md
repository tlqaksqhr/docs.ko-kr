---
title: "특성에 저장된 정보 검색"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- retrieving attributes
- multiple attribute instances
- attributes [.NET Framework], retrieving
ms.assetid: 37dfe4e3-7da0-48b6-a3d9-398981524e1c
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9d3fd9a5a49d65b37d2cdb5107e9c516a6df5847
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="retrieving-information-stored-in-attributes"></a>특성에 저장된 정보 검색
사용자 지정 특성을 검색 하는 것은 간단 합니다. 먼저, 검색 하려는 특성의 인스턴스를 선언 합니다. 그런 다음 사용 하는 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType> 메서드를 검색 하려는 특성의 값을 새 특성을 초기화 합니다. 새 특성의 초기화 된 단순히 속성을 사용 하 여 값을 가져옵니다.  
  
> [!IMPORTANT]
>  이 항목에서는 실행 컨텍스트에 로드 된 코드에 대 한 특성을 검색 하는 방법을 설명 합니다. 리플렉션 전용 컨텍스트에 로드 된 코드에 대 한 특성을 검색 하려면 사용 해야 합니다는 <xref:System.Reflection.CustomAttributeData> 클래스에 표시 된 대로 [하는 방법: 리플렉션 컨텍스트에 로드 어셈블리](../../../docs/framework/reflection-and-codedom/how-to-load-assemblies-into-the-reflection-only-context.md)합니다.  
  
 이 섹션에서는 특성을 검색 하려면 다음과 같은 방법으로 설명 합니다.  
  
-   [특성의 단일 인스턴스 검색](#cpconretrievingsingleinstanceofattribute)  
  
-   [동일한 범위에 적용 되는 특성의 여러 인스턴스 검색](#cpconretrievingmultipleinstancesofattributeappliedtosamescope)  
  
-   [서로 다른 범위에 적용 되는 특성의 여러 인스턴스 검색](#cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes)  
  
<a name="cpconretrievingsingleinstanceofattribute"></a>   
## <a name="retrieving-a-single-instance-of-an-attribute"></a>특성의 단일 인스턴스 검색  
 다음 예제에서는 `DeveloperAttribute` (이전 섹션에서 설명)에 적용 되는 `MainApp` 클래스 수준에는 클래스입니다. `GetAttribute` 메서드 **GetCustomAttribute** 에 저장 된 값을 검색 `DeveloperAttribute` 콘솔에이 표시 하기 전에 클래스 수준에 있습니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#18)]
 [!code-csharp[Conceptual.Attributes.Usage#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#18)]
 [!code-vb[Conceptual.Attributes.Usage#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#18)]  
  
 이 프로그램 실행 하면 다음 텍스트를 표시 합니다.  
  
```  
The Name Attribute is: Joan Smith.  
The Level Attribute is: 42.  
The Reviewed Attribute is: True.  
```  
  
 특성이 없으면는 **GetCustomAttribute** 메서드 초기화 `MyAttribute` 를 null 값입니다. 이 예제에서는 검사 `MyAttribute` 이러한 인스턴스에 대 한 특성이 없는 경우에 사용자에 게 알리는 합니다. 경우는 `DeveloperAttribute` 사전에 클래스 범위를 콘솔에 다음 메시지가 표시 됩니다.  
  
```  
The attribute was not found.   
```  
  
 이 예에서는 특성 정의 현재 네임 스페이스에 있다고 가정 합니다. 특성 정의가 있는 현재 네임 스페이스에 없는 경우 네임 스페이스를 가져올 해야 합니다.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtosamescope"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-the-same-scope"></a>동일한 범위에 적용 되는 특성의 여러 인스턴스 검색  
 이전 예에서 검사 하는 클래스 및 찾을 특성에 전달 됩니다 <xref:System.Attribute.GetCustomAttribute%2A>합니다. 해당 코드에는 특성의 한 인스턴스는 클래스 수준에서 적용 하는 경우만 잘 작동 합니다. 그러나 특성의 여러 인스턴스는 동일한 클래스 수준에서 적용 되는 경우, 고 **GetCustomAttribute** 메서드는 모든 정보를 검색 하지 않습니다. 동일한 특성의 여러 인스턴스는 동일한 범위에 적용 하는 경우에 사용할 수 있습니다 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType> 특성의 모든 인스턴스를 배열에 배치할 수 있습니다. 예를 들어 두 인스턴스의 `DeveloperAttribute` 동일한 클래스의 클래스 수준에서 적용 되는 `GetAttribute` 두 특성 모두에 있는 정보를 표시 하는 메서드를 수정할 수 있습니다. 동일한 수준에 여러 특성을 적용 하려면 기억 특성으로 정의 되어야 합니다는 **AllowMultiple** 속성이로 설정 **true** 에 <xref:System.AttributeUsageAttribute>합니다.  
  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 **GetCustomAttributes** 의 모든 인스턴스를 참조 하는 배열을 만드는 메서드를 `DeveloperAttribute` 모든 클래스를 제공 합니다. 그러면 모든 특성의 값은 콘솔에 표시 됩니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#19](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#19)]
 [!code-csharp[Conceptual.Attributes.Usage#19](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#19)]
 [!code-vb[Conceptual.Attributes.Usage#19](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#19)]  
  
 특성이 발견 되 면이 코드 사용자를 게 알립니다. 두 인스턴스 모두에 정보가 포함 되는 그렇지 않은 경우 `DeveloperAttribute` 표시 됩니다.  
  
<a name="cpconretrievingmultipleinstancesofattributeappliedtodifferentscopes"></a>   
## <a name="retrieving-multiple-instances-of-an-attribute-applied-to-different-scopes"></a>서로 다른 범위에 적용 되는 특성의 여러 인스턴스 검색  
 <xref:System.Attribute.GetCustomAttributes%2A> 및 <xref:System.Attribute.GetCustomAttribute%2A> 메서드 전체 클래스를 검색 하지 않으며 해당 클래스에 특성의 모든 인스턴스를 반환 합니다. 대신, 이러한 지정 된 메서드 또는 멤버를 하나만 한 번에 검색 합니다. 모든 멤버에 적용 된 동일한 특성을 가진 클래스 있고 해당 멤버에 적용 된 모든 특성의 값을 검색 하려는 경우를 제공 해야 모든 메서드나 멤버 개별적으로 **GetCustomAttributes** 및  **GetCustomAttribute**합니다.  
  
 다음 코드 예제에서는 매개 변수로 클래스를 사용 하 고 검색는 `DeveloperAttribute` (정의 된 이전에)와 해당 클래스의 모든 개별 메서드에서 클래스 수준에 있습니다.  
  
 [!code-cpp[Conceptual.Attributes.Usage#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.attributes.usage/cpp/source3.cpp#20)]
 [!code-csharp[Conceptual.Attributes.Usage#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.attributes.usage/cs/source3.cs#20)]
 [!code-vb[Conceptual.Attributes.Usage#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.attributes.usage/vb/source3.vb#20)]  
  
 인스턴스가 없으면는 `DeveloperAttribute` 메서드 수준 또는 클래스 수준에서 발견 되는 `GetAttribute` 특성이 없습니다. 발견 된 사용자에 게 알리는 메서드와 메서드 또는 특성을 포함 하지 않는 클래스의 이름을 표시 합니다. 특성을 찾을 경우는 `Name`, `Level`, 및 `Reviewed` 필드가 콘솔에 표시 됩니다.  
  
 멤버를 사용할 수는 <xref:System.Type> 클래스 전달 된 클래스의 개별 메서드 및 멤버를 가져올 수 있습니다. 이 예에서는 먼저 쿼리는 **형식** 클래스 수준에 대 한 특성 정보를 가져올 개체입니다. 사용 하 여 다음으로, <xref:System.Type.GetMethods%2A?displayProperty=nameWithType> 모든 메서드의 배열로 인스턴스를 배치 하려면 <xref:System.Reflection.MemberInfo?displayProperty=nameWithType> 메서드 수준의 특성 정보를 검색 하기 위해 개체입니다. 사용할 수도 있습니다는 <xref:System.Type.GetProperties%2A?displayProperty=nameWithType> 속성 수준에서 특성에 대 한 확인 하는 메서드 또는 <xref:System.Type.GetConstructors%2A?displayProperty=nameWithType> 생성자 수준에 특성에 대 한 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Type?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttribute%2A?displayProperty=nameWithType>  
 <xref:System.Attribute.GetCustomAttributes%2A?displayProperty=nameWithType>  
 [특성](../../../docs/standard/attributes/index.md)
