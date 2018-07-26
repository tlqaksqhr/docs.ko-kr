---
title: Windows Communication Foundation 바인딩
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: edbcba1cda914d58dee7a11fcb3309254a52a66c
ms.sourcegitcommit: 2d8b7488d94101b534ca3e9780b1c1e840233405
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39198145"
---
# <a name="windows-communication-foundation-bindings"></a>Windows Communication Foundation 바인딩
Windows Communication Foundation (WCF) 다른 소프트웨어와 통신 하는 방법에서 응용 프로그램에 대 한 소프트웨어를 작성 하는 방법을 구분 합니다. 바인딩은 클라이언트와 서비스 간에 통신하는 데 필요한 전송, 인코딩 및 프로토콜 세부 정보를 지정하는 데 사용됩니다. WCF 바인딩을 사용 하 여 서로 통신 하는 당사자가 바인딩 세부 정보를 대부분 합의 해야 하므로 끝점의 기본 연결을 표시를 생성 합니다. 이를 수행하는 가장 쉬운 방법은 서비스 클라이언트가 서비스 끝점에서 사용하는 동일한 바인딩을 사용하는 것입니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [구성 Windows Communication Foundation 서비스 및 클라이언트에 대 한 바인딩을 사용 하 여](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)입니다.  
  
 바인딩은 바인딩 요소의 컬렉션으로 구성됩니다. 각 요소는 끝점이 클라이언트와 통신하는 방법의 일부를 설명합니다. 바인딩에는 하나 이상의 전송 바인딩 요소, 전송 바인딩 요소가 기본적으로 제공할 수 있는 하나 이상의 메시지 인코딩 바인딩 요소 및 여러 개의 다른 프로토콜 바인딩 요소가 포함되어 있어야 합니다. 이 설명에서 런타임을 빌드하는 프로세스를 통해 각 바인딩 요소가 코드를 해당 런타임에 적용할 수 있습니다.  
  
 WCF 바인딩 요소는 일반적인 선택 항목을 포함 하는 바인딩을 제공 합니다. 이러한 바인딩을 기본 설정에 사용하거나 사용자 요구 사항에 따라 그러한 기본값을 수정할 수 있습니다. 이러한 시스템 제공 바인딩에 바인딩 요소와 해당 설정을 직접 제어할 수 있는 속성이 있습니다. 또한 바인딩의 각 버전에 고유한 이름을 지정하여 여러 버전의 바인딩을 함께 사용할 수 있습니다. 자세한 내용은 참조 하세요 [Configuring System-Provided 바인딩](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)합니다.  
  
 이러한 시스템 제공 바인딩 중 하나에서 제공하지 않는 바인딩 요소의 컬렉션이 필요한 경우 필요한 바인딩 요소의 컬렉션으로 구성된 사용자 지정 바인딩을 만들 수 있습니다. 이러한 사용자 지정 바인딩은 쉽게 만들 수 있고 새 클래스가 필요하지 않지만 바인딩 요소나 해당 설정을 제어하는 속성을 제공하지는 않습니다. 바인딩 요소에 액세스하고 그러한 요소를 포함하는 컬렉션을 통해 해당 설정을 수정할 수 있습니다. 자세한 내용은 참조 하세요 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [시스템 제공 바인딩 구성](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 사용 하 여 일반적인 시나리오를 지원 하기 위해 WCF 제공 하는 바인딩을 수정 하는 방법을 설명 합니다.  
  
 [바인딩을 사용 하 여 Windows Communication Foundation 서비스 및 클라이언트 구성](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 선언적 구성을 사용 하 고 코드에서 명령적으로 서비스 및 클라이언트에 대 한 Windows Communication Foundation (WCF) 바인딩을 정의 하는 방법에 설명 합니다.  
  
 [사용자 지정 바인딩](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 <xref:System.ServiceModel.Channels.CustomBinding>의 정의와 언제 사용되는지에 대해 설명합니다.  
  
## <a name="reference"></a>참조  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a>관련 단원  
 [바인딩 확장](../../../../docs/framework/wcf/extending/extending-bindings.md)
