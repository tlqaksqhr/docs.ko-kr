---
title: "방법: ChannelFactory 사용"
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
ms.assetid: d48f01b5-582b-4c8b-b547-8adddae7e371
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 644160f11bd743a0c1d598cc01b3e365adea5c56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-channelfactory"></a>방법: ChannelFactory 사용
제네릭 <xref:System.ServiceModel.ChannelFactory%601> 클래스는 둘 이상의 채널을 만드는 데 사용할 수 있는 채널 팩터리를 만들어야 하는 고급 시나리오에서 사용됩니다.  
  
### <a name="to-create-and-use-the-channelfactory-class"></a>ChannelFactory 클래스를 만들고 사용하려면  
  
1.  [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 서비스를 빌드하고 실행합니다. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][서비스 디자인 및 구현](../../../../docs/framework/wcf/designing-and-implementing-services.md), [서비스 구성](../../../../docs/framework/wcf/configuring-services.md), 및 [호스팅 서비스](../../../../docs/framework/wcf/hosting-services.md)합니다.  
  
2.  사용 하 여는 [ServiceModel Metadata 유틸리티 도구 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) 를 클라이언트에 대 한 계약 (인터페이스)를 생성 합니다.  
  
3.  클라이언트 코드에서 <xref:System.ServiceModel.ChannelFactory%601> 클래스를 사용하여 여러 개의 끝점 수신기를 만듭니다.  
  
## <a name="example"></a>예  
 [!code-csharp[c_HowToUseChannelFactory#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtousechannelfactory/cs/source.cs#1)]
 [!code-vb[c_HowToUseChannelFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtousechannelfactory/vb/source.vb#1)]
