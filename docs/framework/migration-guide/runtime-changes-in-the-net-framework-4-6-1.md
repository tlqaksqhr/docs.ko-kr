---
title: ".NET Framework 4.6.1의 런타임 변경 내용 | Microsoft 문서"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- runtime changes, .NET Framework
- runtime changes, .NET Framework 4.6.1
- application compatibility
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b8c6ec4d0bad4a769fb4d19a98c9e8a4eda0db78
ms.lasthandoff: 04/18/2017

---
# <a name="runtime-changes-in-the-net-framework-461"></a>.NET Framework 4.6.1의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 이전 버전의 .NET Framework를 대상으로 하지만 이후 버전의 .NET Framework 런타임에서 실행되는 기존 앱에 영향을 줄 수 있습니다. 서로 다른 .NET Framework 런타임 환경에서 실행되는 응용 프로그램 간의 동작 차이도 포함됩니다. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]의 다음 영역에 이러한 변경 내용이 포함되어 있습니다.  
  
-   [WCF(Windows Communication Foundation)](#WCF)  
  
-   [WPF(Windows Presentation Foundation)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>WCF(Windows Communication Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|`TransportWithMessageCredential` 보안 모드를 사용하는 WCF 바인딩|기본적으로, `TransportWithMessageCredential` 보안 모드를 사용하는 WCF 바인딩에서는 비대칭 보안 키에 부호 없는 "to" 헤더가 포함된 메시지가 허용되지 않습니다. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이하에서 실행되는 앱부터는 이 요건이 완화되어 부호 있는 "to" 헤더가 없는 메시지를 수신할 수 있습니다.|이 동작은 옵트인 동작입니다. 부호 없는 "to" 헤더가 포함된 메시지를 허용하려면 다음 구성 설정을 앱 구성 파일의 [\<<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 추가합니다.<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> 이 기능은 옵트인 기능이기 때문에 기존 앱의 동작에는 영향을 주지 않습니다.|Microsoft Edge|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|<xref:System.Windows.Controls.ItemsControl>가 가상화(<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) 및 항목 스크롤(<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>)을 사용하여 컬렉션을 표시할 때와 컨트롤을 통해 스크롤하여 해당 환경에서 픽셀 단위로 항목 높이를 표시할 때 <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>가 컬렉션의 모든 항목에 대해 반복합니다.   이와 같은 반복 중에 UI는 응답하지 않습니다. 컬렉션의 크기가 큰 경우 중단으로 인식될 수 있습니다.<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이와 같은 반복은 이전 릴리스에서도 다른 상황에서 발생합니다. 예를 들어, 픽셀 높이가 서로 다른 항목이 나타나는 즉시 픽셀 스크롤(<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>)할 때, 해당 환경과 하위 항목 수가 다른 항목이 나타나는 즉시 (그룹화가 활성화된 <xref:System.Windows.Controls.TreeView> 컨트롤 또는 <xref:System.Windows.Controls.ItemsControl> 등에서) 계층 구조 데이터를 항목 스크롤할 때 발생합니다.<br /><br /> 항목 스크롤을 하고 픽셀 높이가 다른 경우 계층 구조 데이터의 레이아웃에서 버그를 수정하기 위해 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에 반복이 도입되었습니다.  데이터가 단일 구조(계층 구조가 아님)인 경우 반복이 필요하지 않으며 이 경우 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]이 반복을 수행하지 않습니다.|반복이 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]에서 발생하지만 이전 릴리스에서는 발생하지 않는 경우 즉, <xref:System.Windows.Controls.ItemsControl>이 항목의 픽셀 높이가 서로 다른 단일 구조 목록을 항목 스크롤하는 경우 다음과 같은 두 가지 방법으로 해결할 수 있습니다.<br /><br /> [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md)를 설치합니다.<br /><br /> [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]용 [핫픽스 HR 1605](https://support.microsoft.com/en-us/kb/3154529)를 설치합니다.|사소함|  
## <a name="see-also"></a>참고 항목  
 [4.6.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)
