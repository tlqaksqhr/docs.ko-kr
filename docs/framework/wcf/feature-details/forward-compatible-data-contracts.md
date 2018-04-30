---
title: 이후 버전과 호환되는 데이터 계약
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data contracts [WCF], forward compatibility
ms.assetid: 413c9044-26f8-4ecb-968c-18495ea52cd9
caps.latest.revision: 21
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 554176d2b6ac0c1d5cbe817721c55d06f88457cc
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="forward-compatible-data-contracts"></a>이후 버전과 호환되는 데이터 계약
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 데이터 계약 시스템의 특징은 시간에 따라 변경되지 않는 방법으로 계약을 개발할 수 있다는 점입니다. 즉, 이전 버전의 데이터 계약을 가진 클라이언트가 새 버전의 동일한 데이터 계약을 가진 서비스와 통신할 수 있거나, 새 버전의 데이터 계약을 가진 클라이언트가 이전 버전의 동일한 데이터 계약과 통신할 수 있습니다. 자세한 내용은 참조 [모범 사례: 데이터 계약 버전 관리](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)합니다.  
  
 새 버전의 기존 데이터 계약을 작성하는 경우 필요한 기준에 따라 대부분의 버전 관리 기능을 적용할 수 있습니다. 그러나 버전 관리 기능, *라운드트립*, 제대로 작동 하려면 첫 번째 버전의 형식으로 빌드해야 합니다.  
  
## <a name="round-tripping"></a>라운드트립  
 라운드트립은 데이터를 새 버전에서 기존 버전으로 전달한 후 다시 새 버전의 데이터 계약으로 전달할 때 발생합니다. 라운드트립을 사용해도 데이터는 손실되지 않습니다. 라운드트립을 사용하면 데이터 계약 버전 관리 모델에서 지원하는 이후 모든 변경 사항에 대해 이후 버전과 호환되는 형식으로 만들 수 있습니다.  
  
 특정 형식의 라운드트립을 사용하려면 형식이 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현해야 합니다. 인터페이스에는 속성 중 하나인 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A>가 포함되어 있습니다(<xref:System.Runtime.Serialization.ExtensionDataObject> 형식 반환). 속성은 현재 버전에서는 알 수 없는 이후 버전 데이터 계약의 모든 데이터를 저장합니다.  
  
### <a name="example"></a>예제  
 다음 데이터 계약은 이후 변경 사항에 대해 이후 버전과 호환되지 않습니다.  
  
 [!code-csharp[C_DataContract#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#7)]
 [!code-vb[C_DataContract#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#7)]  
  
 예를 들어, "phoneNumber"라는 새 데이터 멤버와 같은 이후 변경 사항과 호환되는 형식을 만들려면 <xref:System.Runtime.Serialization.IExtensibleDataObject> 인터페이스를 구현합니다.  
  
 [!code-csharp[C_DataContract#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#8)]
 [!code-vb[C_DataContract#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#8)]  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 인프라에서 원래 데이터 계약의 일부가 아닌 데이터가 있는 경우 해당 데이터는 속성에 저장되어 보관됩니다. 임시 저장소를 제외한 다른 방법으로는 처리되지 않습니다. 개체가 최초 위치로 다시 돌아오는 경우, 원래 데이터(알 수 없는 데이터)도 반환됩니다. 따라서 데이터가 손실 없이 원래 끝점 간을 라운드트립합니다. 그러나 원래 끝점에서 데이터를 처리해야 하는 경우 예상했던 작업은 수행되지 않고 해당 끝점은 변경 사항을 감지하고 적용해야 합니다.  
  
 <xref:System.Runtime.Serialization.ExtensionDataObject> 형식에는 public 메서드 또는 속성이 없습니다. 따라서 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> 속성 내에 저장된 데이터에 직접 액세스할 수 없습니다.  
  
 라운드트립 기능은 `ignoreExtensionDataObject` 생성자에서 `true`를 <xref:System.Runtime.Serialization.DataContractSerializer>로 설정하거나 <xref:System.ServiceModel.ServiceBehaviorAttribute.IgnoreExtensionDataObject%2A>에서 `true` 속성을 <xref:System.ServiceModel.ServiceBehaviorAttribute>로 설정하여 해제할 수 있습니다. 이 기능을 해제하면 deserializer가 <xref:System.Runtime.Serialization.IExtensibleDataObject.ExtensionData%2A> 속성을 채우지 않고, serializer가 속성의 콘텐츠를 내보내지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Runtime.Serialization.IExtensibleDataObject>  
 <xref:System.Runtime.Serialization.ExtensionDataObject>  
 [데이터 계약 버전 관리](../../../../docs/framework/wcf/feature-details/data-contract-versioning.md)  
 [모범 사례: 데이터 계약 버전 관리](../../../../docs/framework/wcf/best-practices-data-contract-versioning.md)
