---
title: "x:XData 내장 XAML 형식"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: "17"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec46d0363e5b10d3bd3bd3f9c8f4d3694abc1c8d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData 내장 XAML 형식
XAML 프로덕션 내에서 XML 데이터 아일랜드를 배치할을 수 있습니다. 내에서 XML 요소 `x:XData` 기본 XAML 네임 스페이스의 일부 인지 XAML 네임 스페이스 마치 XAML 프로세서에서 처리 되지 해야 합니다. `x:XData`임의의 올바른 형식의 XML을 포함할 수 있습니다.  
  
## <a name="xaml-object-element-usage"></a>XAML 개체 요소 사용  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>XAML 값  
  
|||  
|-|-|  
|`elementDataRoot`|포함 된 데이터 아일랜드의 단일 루트 요소입니다. 대부분의 최종 소비자에 대 한 단일 루트 하지 않은 XML이 잘못 되었습니다. 간주 됩니다. 특히 하나의 루트는 나중에 필요한 경우는 `x:XData` WPF 또는 데이터 바인딩에 대 한 XML 원본을 사용 하는 다른 많은 기술에 대 한 XML 데이터 소스로 제공 됩니다.|  
|`[elementData]`|선택 사항입니다. XML 데이터를 나타내는 XML입니다. 원하는 수의 요소는 요소 데이터로 포함 될 수 있으며 다른 요소에 중첩 된 요소가 포함 될 수 있는 그러나 XML의 일반적인 규칙이 적용 됩니다.|  
  
## <a name="remarks"></a>설명  
 내에서 XML 요소는 `x:XData` 모든 가능한 네임 스페이스 및 접두사 포함 된 XMLDOM 데이터 내에서 개체 다시 선언할 수 있습니다.  
  
 XML 데이터에 프로그래밍 방식 액세스 및 `x:XData` 내장 XAML 형식을 확장할 수를 통해.NET Framework XAML 서비스는 <xref:System.Windows.Markup.XData> 클래스입니다.  
  
## <a name="wpf-usage-notes"></a>WPF 사용 정보  
 `x:XData` 의 자식 개체로 개체는 <xref:System.Windows.Data.XmlDataProvider>, 또는 또는의 자식 개체는 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 속성 (XAML에서이 일반적으로 표시 된 속성 요소 구문으로).  
  
 일반적으로 데이터 (빈 문자열로 설정)를 새 기본 XML 네임 스페이스는 데이터 아일랜드 내에서 기본 XML 네임 스페이스로 재정의 해야 합니다. 간단한 데이터 아일랜드 때문에이 방법이 간편는 <xref:System.Windows.Data.Binding.XPath%2A> 참조 하 고 데이터에 바인딩 사용 되는 식 접두사 포함을 피할 수 있습니다. 더 복잡 한 데이터 아일랜드 데이터에 대 한 여러 개의 접두사를 정의 하 고 루트에 XML 네임 스페이스에 대 한 특정 접두사를 사용 될 수 있습니다. 이 경우 모든 <xref:System.Windows.Data.Binding.XPath%2A> 식 참조는 적절 한 네임 스페이스 매핑 접두사를 포함 해야 합니다. 자세한 내용은 [데이터 바인딩 개요](../../../docs/framework/wpf/data/data-binding-overview.md)를 참조하세요.  
  
 기술적으로 `x:XData` 유형의 속성의 내용으로 사용할 수 <xref:System.Xml.Serialization.IXmlSerializable>합니다. 그러나 <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> 주로 사용 되는 구현입니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Windows.Data.XmlDataProvider>  
 [데이터 바인딩 개요](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Binding 태그 확장](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
