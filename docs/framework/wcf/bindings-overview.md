---
title: "Windows Communication Foundation 바인딩 개요"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF], overview
ms.assetid: cfb5842f-e0f9-4c56-a015-f2b33f258232
caps.latest.revision: "16"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a131574e0e3de8507a91807d5de2899238c14628
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="windows-communication-foundation-bindings-overview"></a>Windows Communication Foundation 바인딩 개요
바인딩은 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 서비스의 끝점에 연결하기 위해 필요한 통신 세부 사항을 지정하는 데 사용되는 개체입니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스의 각 끝점에 대해 바인딩을 올바로 지정해야 합니다. 이 항목에서는 바인딩이 정의하는 통신 세부 사항의 형식, 바인딩의 요소, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에 포함되는 바인딩 및 끝점에 대해 바인딩을 지정할 수 있는 방법을 간략하게 설명합니다.  
  
## <a name="what-a-binding-defines"></a>바인딩이 정의하는 내용  
 바인딩의 정보는 매우 기본적이거나 매우 복잡할 수 있습니다. 가장 기본적인 바인딩은 끝점에 연결하는 데 사용해야 하는 HTTP 등의 전송 프로토콜만 지정합니다. 보다 일반적으로, 끝점 연결 방법과 관련해서 바인딩에 포함되는 정보는 다음 범주 중 하나에 해당합니다.  
  
 프로토콜  
 신뢰할 수 있는 메시징 기능 또는 트랜잭션 컨텍스트 흐름 설정 중 하나인 사용되는 보안 메커니즘을 결정합니다.  
  
 Encoding  
 메시지 인코딩(예: 텍스트 또는 이진)을 결정합니다.  
  
 전송  
 사용할 내부 전송 프로토콜(예: TCP 또는 HTTP)을 결정합니다.  
  
## <a name="the-elements-of-a-binding"></a>바인딩의 요소입니다.  
 바인딩은 기본적으로 순서가 지정된 바인딩 요소 스택으로 구성됩니다. 각 바인딩 요소는 서비스 끝점에 연결하는 데 필요한 통신 정보의 일부를 지정합니다. 스택의 가장 낮은 두 계층은 모두 필수입니다. 스택 맨 아래에는 전송 바인딩 요소가 있고 바로 위에 메시지 인코딩 사양을 포함하는 요소가 있습니다. 다른 통신 프로토콜을 지정하는 선택적 바인딩 요소는 이 두 개의 필수 요소 위의 계층에 있습니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]이러한 바인딩 요소 및 해당 올바른 순서로 참조 [사용자 지정 바인딩](../../../docs/framework/wcf/extending/custom-bindings.md)합니다.  
  
## <a name="system-provided-bindings"></a>시스템 제공 바인딩  
 바인딩의 정보는 복잡할 수 있으며 일부 설정이 다른 설정과 호환되지 않을 수 있습니다. 이런 이유로 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에는 시스템 제공 바인딩 집합이 포함되어 있습니다. 이러한 바인딩은 대부분의 응용 프로그램 요구 사항을 처리합니다. 다음 클래스는 시스템 제공 바인딩의 몇 가지 예를 나타냅니다.  
  
-   <xref:System.ServiceModel.BasicHttpBinding>: ASP.NET 웹 서비스 기반 서비스 등 웹 서비스에 연결하는 데 적합한, WS-I Basic Profile 사양을 준수하는 HTTP 프로토콜 바인딩입니다.  
  
-   <xref:System.ServiceModel.WSHttpBinding>: 끝점에 연결하는 데 적합한, WS-* 프로토콜을 준수하는 상호 운용 가능한 바인딩입니다.  
  
-   <xref:System.ServiceModel.NetNamedPipeBinding>: [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]를 사용하여 동일한 컴퓨터의 다른 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 끝점에 연결합니다.  
  
-   <xref:System.ServiceModel.NetMsmqBinding>: [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]를 사용하여 다른 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 끝점과의 대기 중인 메시지 연결을 만듭니다.  
  
 모든 설명이 포함 된 전체 목록은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-바인딩 참조 제공 [시스템 제공 바인딩](../../../docs/framework/wcf/system-provided-bindings.md)합니다.  
  
## <a name="using-your-own-bindings"></a>고유한 바인딩 사용  
 포함된 시스템 제공 바인딩에 서비스 응용 프로그램에 필요한 올바른 기능 조합이 없는 경우 고유한 바인딩을 만들 수 있습니다. 이렇게 하는 데는 두 가지 방법이 있습니다. <xref:System.ServiceModel.Channels.CustomBinding> 개체를 사용하여 기존의 바인딩 요소에서 새 바인딩을 만들거나 <xref:System.ServiceModel.Channels.Binding> 바인딩에서 파생하여 완전한 사용자 지정 바인딩을 만들 수 있습니다. [!INCLUDE[crabout](../../../includes/crabout-md.md)]이러한 두 방법을 사용 하 여 바인딩 참조를 만들어 [사용자 지정 바인딩](../../../docs/framework/wcf/extending/custom-bindings.md) 및 [Creating User-Defined 바인딩](../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)합니다.  
  
## <a name="using-bindings"></a>바인딩 사용  
 바인딩 사용은 다음 두 가지 기본 단계로 이루어집니다.  
  
1.  바인딩을 선택하거나 정의합니다. 가장 쉬운 방법은 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]에 포함된 시스템 제공 바인딩 중 하나를 선택하고 기본 설정과 함께 사용하는 것입니다. 시스템 제공 바인딩을 선택하고 요구 사항에 맞게 속성 값을 다시 설정할 수도 있습니다. 또는 제어 및 사용자 지정 수준이 더 높은 사용자 지정 바인딩이나 사용자 정의 바인딩을 만들 수 있습니다.  
  
2.  선택되었거나 정의된 바인딩을 사용하는 끝점을 만듭니다.  
  
## <a name="code-and-configuration"></a>코드 및 구성  
 두 가지 방법, 즉 코드 또는 구성을 통해 바인딩을 정의할 수 있습니다. 이러한 두 접근 방법은 시스템 제공 바인딩을 사용하든 사용자 지정 바인딩을 사용하든 관계가 없습니다. 일반적으로 코드를 사용하면 디자인 타임에 바인딩 정의를 완전히 제어할 수 있습니다. 반면 구성을 사용하면 시스템 관리자나 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 서비스 또는 클라이언트의 사용자가 서비스 응용 프로그램을 다시 컴파일하지 않고도 바인딩의 매개 변수를 변경할 수 있습니다. [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 응용 프로그램이 배포될 특정 컴퓨터 요구 사항을 예측할 방법이 없으므로 이 유연성은 바람직한 경우가 많습니다. 바인딩(및 주소 지정) 정보를 코드와 구분하면 응용 프로그램을 다시 컴파일하거나 다시 배포하지 않고도 해당 정보를 변경할 수 있습니다. 코드에 정의된 바인딩은 구성에 지정된 바인딩 후에 만들어지므로 코드에 정의된 바인딩이 구성에 정의된 모든 바인딩을 덮어쓸 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [바인딩을 사용하여 서비스 및 클라이언트 구성](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
