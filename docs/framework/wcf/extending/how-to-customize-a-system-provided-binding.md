---
title: '방법: 시스템 제공 바인딩 사용자 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f8b97862-e8bb-470d-8b96-07733c21fe26
ms.openlocfilehash: 40efa49836561351dc14c2cb49d906a6d344a5bc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-customize-a-system-provided-binding"></a>방법: 시스템 제공 바인딩 사용자 지정
Windows Communication Foundation (WCF)에 기본 바인딩 요소의 속성 중 일부에 속성을 구성할 수 있도록 여러 시스템 제공 바인딩이 포함 되어 있습니다. 이 항목에서는 바인딩 요소의 속성을 설정하여 사용자 지정 바인딩을 만드는 방법을 보여 줍니다.  
  
 직접 만들고 시스템 제공 바인딩을 사용 하지 않고 바인딩 요소를 구성 하는 방법에 대 한 자세한 내용은 참조 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
 만들기 및 사용자 지정 바인딩 확장에 대 한 자세한 내용은 참조 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)합니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 모든 바인딩에 이루어져 *바인딩 요소의*합니다. 각 바인딩 요소는 <xref:System.ServiceModel.Channels.BindingElement> 클래스에서 파생됩니다. <xref:System.ServiceModel.BasicHttpBinding>과 같은 시스템 제공 바인딩은 자체 바인딩 요소를 만들고 구성합니다. 이 항목에서는 특히 <xref:System.ServiceModel.BasicHttpBinding> 클래스와 같은 바인딩에서 직접 노출되지 않는 이러한 바인딩 요소의 속성에 액세스하여 이를 변경하는 방법을 보여 줍니다.  
  
 개별 바인딩 요소는 <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스로 표시되는 컬렉션에 포함되며, 트랜잭션 흐름, 신뢰할 수 있는 세션, 보안, 복합 이중, 단방향, 스트림 보안, 메시지 인코딩 및 전송 순서로 추가됩니다. 나열된 모든 바인딩 요소가 모든 바인딩에서 필요한 것은 아닙니다. 사용자 정의 바인딩 요소도 앞에서 설명한 동일한 순서로 이 바인딩 요소에 나타날 수 있습니다. 예를 들어, 사용자 정의 전송은 바인딩 요소 컬렉션의 마지막 요소여야 합니다.  
  
 <xref:System.ServiceModel.BasicHttpBinding> 클래스에는 다음 세 가지 바인딩 요소가 포함됩니다.  
  
1.  HTTP 전송(메시지 수준 보안)과 함께 사용되는 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement> 클래스 또는 전송 계층에서 보안을 제공하는 경우(HTTP 전송 사용) 사용되는 <xref:System.ServiceModel.Channels.TransportSecurityBindingElement> 클래스 중 하나인 선택적 보안 바인딩 요소  
  
2.  <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> 또는 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> 중 하나인 필수 메시지 인코더 바인딩 요소  
  
3.  <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 또는 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement> 중 하나인 필수 전송 바인딩 요소  
  
 다음이 예제에서는 바인딩의 인스턴스를 만들, 생성 한 *사용자 지정 바인딩* 여기에서 사용자 지정 바인딩에서 바인딩 요소를 검사 하 고 설정 HTTP 바인딩 요소를 찾으면 해당 `KeepAliveEnabled` 속성 를`false`. `KeepAliveEnabled` 속성이 `BasicHttpBinding`에서 직접 노출되지 않으므로 사용자 지정 바인딩을 만들어 바인딩 요소 아래에서 탐색하여 이 속성을 설정해야 합니다.  
  
### <a name="to-modify-a-system-provided-binding"></a>시스템 제공 바인딩을 수정하려면  
  
1.  <xref:System.ServiceModel.BasicHttpBinding> 클래스의 인스턴스를 만들고 보안 모드를 메시지 수준으로 설정합니다.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#1)]
     [!code-vb[C_HowTo_ChangeStandardBinding#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#1)]  
  
2.  바인딩에서 사용자 지정 바인딩을 만들고 사용자 지정 바인딩의 속성 중 하나에서 <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스를 만듭니다.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#2)]
     [!code-vb[C_HowTo_ChangeStandardBinding#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#2)]  
  
3.  <xref:System.ServiceModel.Channels.BindingElementCollection> 클래스를 순환 검색하여 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 클래스가 있으면 <xref:System.ServiceModel.Channels.HttpTransportBindingElement.KeepAliveEnabled%2A> 속성을 `false`로 설정합니다.  
  
     [!code-csharp[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_changestandardbinding/cs/program.cs#3)]
     [!code-vb[C_HowTo_ChangeStandardBinding#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_changestandardbinding/vb/program.vb#3)]  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement>  
 <xref:System.ServiceModel.BasicHttpBinding>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)
