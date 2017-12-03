---
title: "데이터 계약 사용"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataContractAttribute class
- WCF, data
- data contracts [WCF]
ms.assetid: a3ae7b21-c15c-4c05-abd8-f483bcbf31af
caps.latest.revision: "38"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: acbe1fc52cec011863dea8f3ae81492e3661cd97
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="using-data-contracts"></a>데이터 계약 사용
*데이터 계약* 은 서비스와 클라이언트 사이에서 교환할 데이터를 추상적으로 설명한 공식 계약입니다. 즉, 클라이언트와 서비스가 같은 형식을 공유하지 않고 같은 데이터 계약만 공유해도 통신이 가능합니다. 데이터 계약에서는 각 매개 변수 또는 반환 형식에 대해 교환을 위해 serialize(XML로 변환)해야 할 데이터를 세밀하게 정의합니다.  
  
## <a name="data-contract-basics"></a>데이터 계약 기본 사항  
 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 에서는 기본적으로 데이터 계약 serializer라는 serialization 엔진을 사용하여 데이터를 serialize 및 deserialize(XML로 변환 및 변환 해제)합니다. 정수 및 문자열과 같은 모든 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 기본 형식 외에도 <xref:System.DateTime> 및 <xref:System.Xml.XmlElement>와 같이 기본 형식으로 취급되는 일부 형식을 별도의 준비 없이 serialize할 수 있으며 기본 데이터 계약이 있는 것으로 간주할 수 있습니다. [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 형식에도 기존 데이터 계약이 있는 것이 많습니다. 모든 serialize 가능 형식의 목록은 [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)을 참조하십시오.  
  
 새로 만든 복합 형식을 serialize하려면 데이터 계약이 정의되어 있어야 합니다. 기본적으로 <xref:System.Runtime.Serialization.DataContractSerializer> 는 데이터 계약을 유추하고 모든 공개 형식을 serialize합니다. 이 경우 형식의 모든 공개 읽기/쓰기 속성과 필드가 serialize됩니다. <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>를 사용하여 멤버의 serialization을 취소할 수 있습니다. 또한 <xref:System.Runtime.Serialization.DataContractAttribute> 및 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 사용하여 데이터 계약을 명시적으로 만들 수도 있습니다. 보통은 형식에 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하면 됩니다. 이 특성을 클래스, 구조 및 열거에 적용할 수 있습니다. 그런 다음 데이터 계약 형식의 각 멤버에 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 적용하여 *데이터 멤버*이며 serialize되어야 한다는 것을 나타내야 합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Serializable 형식](../../../../docs/framework/wcf/feature-details/serializable-types.md)합니다.  
  
### <a name="example"></a>예제  
 다음 예제에서는 <xref:System.ServiceModel.ServiceContractAttribute> 및 <xref:System.ServiceModel.OperationContractAttribute> 특성이 명시적으로 적용된 서비스 계약(인터페이스)을 보여 줍니다. 이 예제는 기본 형식에는 데이터 계약이 필요 없지만 복합 형식에는 필요하다는 것을 보여 줍니다.  
  
 [!code-csharp[C_DataContract#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#1)]
 [!code-vb[C_DataContract#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#1)]  
  
 다음 예제에서는 클래스 및 해당 멤버에 `MyTypes.PurchaseOrder` 및 <xref:System.Runtime.Serialization.DataContractAttribute> 특성을 적용하여 <xref:System.Runtime.Serialization.DataMemberAttribute> 형식의 데이터 계약을 만드는 방법을 보여 줍니다.  
  
 [!code-csharp[C_DataContract#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#2)]
 [!code-vb[C_DataContract#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#2)]  
  
### <a name="notes"></a>참고  
 다음 참고 사항에서는 데이터 계약을 만들 때 고려해야 할 항목을 소개합니다.  
  
-   <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> 특성은 표시되지 않은 형식으로 사용한 경우에만 적용됩니다. 여기에는 <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.SerializableAttribute>, <xref:System.Runtime.Serialization.CollectionDataContractAttribute>또는 <xref:System.Runtime.Serialization.EnumMemberAttribute> 특성 중 하나로 표시되지 않은 형식이나 다른 방법(예: <xref:System.Xml.Serialization.IXmlSerializable>)으로 serialize할 수 있는 것으로 표시된 형식이 포함됩니다.  
  
-   필드 및 속성에 <xref:System.Runtime.Serialization.DataMemberAttribute> 특성을 적용할 수 있습니다.  
  
-   멤버 액세스 가능성 수준(internal, private, protected 또는 public)은 데이터 계약에 어떤 방식으로도 영향을 주지 않습니다.  
  
-   <xref:System.Runtime.Serialization.DataMemberAttribute> 특성은 정적 멤버에 적용하면 무시됩니다.  
  
-   serialization을 수행하는 동안 속성 데이터 멤버에 대해 property-get 코드를 호출하여 serialize할 속성의 값을 가져옵니다.  
  
-   deserialize를 수행하는 동안 초기화되지 않은 개체가 형식에서 생성자를 호출하지 않고 먼저 만들어집니다. 그러면 모든 데이터 멤버가 deserialize됩니다.  
  
-   deserialization을 수행하는 동안 속성 데이터 멤버에 대해 property-set 코드를 호출하여 deserialize할 값으로 속성을 설정합니다.  
  
-   유효한 데이터 계약에서는 모든 데이터 멤버를 serialize할 수 있어야 합니다. 모든 serialize 가능 형식의 목록은 [Types Supported by the Data Contract Serializer](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)을 참조하십시오.  
  
     제네릭 형식은 비제네릭 형식과 완전히 같은 방식으로 처리됩니다. 제네릭 매개 변수에 대한 특수 요구 사항은 없습니다. 다음 형식을 예로 들 수 있습니다.  
  
 [!code-csharp[C_DataContract#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#3)]
 [!code-vb[C_DataContract#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#3)]  
  
 제네릭 형식 매개 변수(`T`)에 사용된 형식이 serialize 가능한지 여부에 관계없이 이 형식은 serialize할 수 있습니다. 모든 데이터 멤버를 serialize할 수 있어야 하기 때문에 다음 코드에 표시된 것과 같이 제네릭 형식 매개 변수도 serialize할 수 있는 경우에만 다음 형식을 serialize할 수 있습니다.  
  
 [!code-csharp[C_DataContract#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#4)]
 [!code-vb[C_DataContract#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#4)]  
  
 데이터 계약을 정의하는 WCF 서비스의 전체 코드 샘플을 보려면 [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) 샘플을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.Serialization.DataMemberAttribute>  
 <xref:System.Runtime.Serialization.DataContractAttribute>  
 [Serializable 형식](../../../../docs/framework/wcf/feature-details/serializable-types.md)  
 [데이터 계약 이름](../../../../docs/framework/wcf/feature-details/data-contract-names.md)  
 [데이터 계약 동등성](../../../../docs/framework/wcf/feature-details/data-contract-equivalence.md)  
 [데이터 멤버 순서](../../../../docs/framework/wcf/feature-details/data-member-order.md)  
 [데이터 계약 알려진된 형식](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)  
 [이후 버전과 호환 데이터 계약](../../../../docs/framework/wcf/feature-details/forward-compatible-data-contracts.md)  
 [데이터 계약 버전 관리](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [버전 독립적 Serialization 콜백](../../../../docs/framework/wcf/feature-details/version-tolerant-serialization-callbacks.md)  
 [데이터 멤버 기본값](../../../../docs/framework/wcf/feature-details/data-member-default-values.md)  
 [데이터 계약 Serializer에서 지 원하는 형식](../../../../docs/framework/wcf/feature-details/types-supported-by-the-data-contract-serializer.md)  
 [방법: 클래스 또는 구조체에 대 한 기본 데이터 계약 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
