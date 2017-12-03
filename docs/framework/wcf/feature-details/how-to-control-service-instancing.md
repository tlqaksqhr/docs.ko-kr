---
title: "방법: 서비스 인스턴스 만들기 제어"
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
ms.assetid: e0b12b34-8004-443a-a46d-83a5c00f2601
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 61c7dd84b802d116721170080bb55a0be1ef1dfc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-control-service-instancing"></a>방법: 서비스 인스턴스 만들기 제어
서비스의 인스턴스 모드를 설정하면 <xref:System.ServiceModel.InstanceContext?displayProperty=nameWithType>(및 연결된 사용자 정의 서비스 개체)가 만들어지는 시기를 지정할 수 있습니다. 가능한 모드에 대해서는 <xref:System.ServiceModel.InstanceContextMode> 열거형을 참조하세요. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]동작 참조 [구성 하 고 런타임 동작을 확장](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)합니다. 작업 예제를 보려면 [동작](../../../../docs/framework/wcf/samples/behaviors.md)합니다.  
  
### <a name="to-control-the-service-instance-lifetime-using-code"></a>코드를 사용하여 서비스 인스턴스 수명을 제어하려면  
  
1.  서비스 클래스에 <xref:System.ServiceModel.ServiceBehaviorAttribute>를 적용합니다.  
  
2.  <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 속성을 <xref:System.ServiceModel.InstanceContextMode.PerCall>, <xref:System.ServiceModel.InstanceContextMode.PerSession> 또는 <xref:System.ServiceModel.InstanceContextMode.Single> 값 중 하나로 설정합니다.  
  
     [!code-csharp[C_ControlServiceInstancing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#1)]
     [!code-vb[C_ControlServiceInstancing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#1)]  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A> 특성의 <xref:System.ServiceModel.ServiceBehaviorAttribute> 속성을 <xref:System.ServiceModel.InstanceContextMode.PerCall>로 설정합니다.  
  
 [!code-csharp[c_ControlServiceInstancing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_controlserviceinstancing/cs/source.cs#2)]
 [!code-vb[c_ControlServiceInstancing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_controlserviceinstancing/vb/source.vb#2)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.ServiceBehaviorAttribute>  
 <xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>  
 <xref:System.ServiceModel.InstanceContextMode>  
 [서비스: 동작 샘플](http://msdn.microsoft.com/en-us/4e3c6513-a7ff-4b35-8dcf-b5506c6f39a7)
