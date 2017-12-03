---
title: "Windows Communication Foundation 바인딩"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: d6fd1bf29af743e5bfcd466ffdf7430c389635de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2017
---
# <a name="windows-communcation-foundation-bindings"></a>Windows Communication Foundation 바인딩
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]는 응용 프로그램 소프트웨어를 작성하는 방법과 그러한 소프트웨어가 다른 소프트웨어와 통신하는 방법을 구분합니다. 바인딩은 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 데 사용됩니다. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 바인딩을 사용하여 끝점의 기본 연결 표시를 생성하므로 통신 당사자들이 대부분의 바인딩 상세 정보에 동의해야 합니다. 이를 수행하는 가장 쉬운 방법은 서비스 클라이언트가 서비스 끝점에서 사용하는 동일한 바인딩을 사용하는 것입니다. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]이 작업을 수행 하 [구성 Windows Communication Foundation 서비스 및 클라이언트에 대 한 바인딩을 사용 하 여](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)합니다.  
  
 바인딩은 바인딩 요소의 컬렉션으로 구성됩니다. 각 요소는 끝점이 클라이언트와 통신하는 방법의 일부를 설명합니다. 바인딩에는 하나 이상의 전송 바인딩 요소, 전송 바인딩 요소가 기본적으로 제공할 수 있는 하나 이상의 메시지 인코딩 바인딩 요소 및 여러 개의 다른 프로토콜 바인딩 요소가 포함되어 있어야 합니다. 이 설명에서 런타임을 빌드하는 프로세스를 통해 각 바인딩 요소가 코드를 해당 런타임에 적용할 수 있습니다.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]는 공통적인 바인딩 요소가 선택된 바인딩을 제공합니다. 이러한 바인딩을 기본 설정에 사용하거나 사용자 요구 사항에 따라 그러한 기본값을 수정할 수 있습니다. 이러한 시스템 제공 바인딩에 바인딩 요소와 해당 설정을 직접 제어할 수 있는 속성이 있습니다. 또한 바인딩의 각 버전에 고유한 이름을 지정하여 여러 버전의 바인딩을 함께 사용할 수 있습니다. 자세한 내용은 참조 [Configuring System-Provided 바인딩](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)합니다.  
  
 이러한 시스템 제공 바인딩 중 하나에서 제공하지 않는 바인딩 요소의 컬렉션이 필요한 경우 필요한 바인딩 요소의 컬렉션으로 구성된 사용자 지정 바인딩을 만들 수 있습니다. 이러한 사용자 지정 바인딩은 쉽게 만들 수 있고 새 클래스가 필요하지 않지만 바인딩 요소나 해당 설정을 제어하는 속성을 제공하지는 않습니다. 바인딩 요소에 액세스하고 그러한 요소를 포함하는 컬렉션을 통해 해당 설정을 수정할 수 있습니다. 자세한 내용은 참조 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [시스템 제공 바인딩 구성](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 일반 시나리오를 지원하기 위해 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]에서 제공하는 바인딩을 사용하고 수정하는 방법을 설명합니다.  
  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 코드에서 명령적으로 및 구성을 사용하여 선언적으로 서비스 및 클라이언트에 대한 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 바인딩을 정의하는 방법을 설명합니다.  
  
 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 <xref:System.ServiceModel.Channels.CustomBinding>의 정의와 언제 사용되는지에 대해 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>관련 단원  
 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)
