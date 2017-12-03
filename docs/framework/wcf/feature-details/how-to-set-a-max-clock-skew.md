---
title: "방법: 최대 클럭 오차 설정"
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
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31548f3190425f4c50e68369320828b11ee3928c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-set-a-max-clock-skew"></a>방법: 최대 클럭 오차 설정
두 개의 컴퓨터에서 클록 설정이 서로 다른 경우 시간 중심 기능이 비활성화될 수 있습니다. 이 가능성을 줄이기 위해 `MaxClockSkew` 설정을 <xref:System.TimeSpan>으로 설정할 수 있습니다. 이 속성은 다음 두 개의 클래스에서 사용할 수 있습니다.  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  중요에 대 한 보안 대화를로 변경 된 `MaxClockSkew` 속성 서비스 또는 클라이언트가 부트스트랩 되 면 이루어져야 합니다. 이 위해는 속성을 설정 해야 하는 <xref:System.ServiceModel.Channels.SecurityBindingElement> 에서 반환 되는 <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>합니다.  
  
 시스템 제공 바인딩 중 하나에서 속성을 변경하려면 바인딩 컬렉션에서 보안 바인딩 요소를 찾아 `MaxClockSkew` 속성을 새 값으로 설정합니다. 두 개의 클래스는 <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 및 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>에서 파생됩니다. 컬렉션에서 보안 바인딩을 검색하는 경우 `MaxClockSkew` 속성을 제대로 설정하기 위해 이러한 형식 중 하나를 캐스팅해야 합니다. 다음 예제에서는 <xref:System.ServiceModel.WSHttpBinding>를 사용하는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>을 사용합니다. 각 시스템 제공 바인딩에 사용할 보안 바인딩 형식을 지정 하는 목록에 대 한 참조 [시스템 제공 바인딩](../../../../docs/framework/wcf/system-provided-bindings.md)합니다.  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a>코드에서 새 클록 오차 값으로 사용자 지정 바인딩을 만들려면  
  
1.  > [!WARNING]
    >  코드에서 다음 네임 스페이스에 대 한 참조 추가 참고: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, 및 <xref:System.ServiceModel.Security.Tokens>합니다.  
  
     <xref:System.ServiceModel.WSHttpBinding> 클래스의 인스턴스를 만들고 보안 모드를 <xref:System.ServiceModel.SecurityMode.Message>로 설정합니다.  
  
2.  <xref:System.ServiceModel.Channels.BindingElementCollection> 메서드를 호출하여 <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> 클래스의 새 인스턴스를 만듭니다.  
  
3.  <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> 클래스의 <xref:System.ServiceModel.Channels.BindingElementCollection> 메서드를 사용하여 보안 바인딩 요소를 찾습니다.  
  
4.  <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> 메서드를 사용하는 경우 실제 형식으로 캐스팅합니다. 아래 예제에서는 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 형식으로 캐스팅합니다.  
  
5.  보안 바인딩 요소에서 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> 속성을 설정합니다.  
  
6.  적절한 서비스 형식 및 기본 주소로 <xref:System.ServiceModel.ServiceHost>를 만듭니다.  
  
7.  <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> 메서드를 사용하여 끝점을 추가하고 <xref:System.ServiceModel.Channels.CustomBinding>을 포함합니다.  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a>구성에서 MaxClockSkew를 설정하려면  
  
1.  만들기는 [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) 에 [ \<바인딩 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) 요소 섹션.  
  
2.  만들기는 [ \<바인딩 >](../../../../docs/framework/misc/binding.md) 요소는 `name` 특성을 적절 한 값입니다. 다음 예제에서는 이 특성을 `MaxClockSkewBinding`으로 설정합니다.  
  
3.  인코딩 요소를 추가합니다. 다음 예제에서는 추가 [ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)합니다.  
  
4.  추가 [ \<보안 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) 요소는 `authenticationMode` 특성을 적절 한 설정입니다. 다음 예제에서는 특성을 `Kerberos`로 설정하여 서비스가 Windows 인증을 사용하도록 지정합니다.  
  
5.  추가 [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) 설정 하 고는 `maxClockSkew` 특성 형식의 값으로 `"##:##:##"`합니다. 다음 예제에서는 이 특성을 7분으로 설정합니다. 필요에 따라 추가 [ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) 설정 하 고는 `maxClockSkew` 특성을 적절 한 설정입니다.  
  
6.  전송 요소를 추가합니다. 다음 예제에서는 [ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)합니다.  
  
7.  보안 대화에 대 한 보안 설정을 부트스트랩에서 발생 해야는 [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) 요소입니다.  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [방법: SecurityBindingElement를 사용 하 여 사용자 지정 바인딩을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
