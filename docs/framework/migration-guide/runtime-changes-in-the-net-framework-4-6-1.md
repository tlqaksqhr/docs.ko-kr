---
title: ".NET Framework 4.6.1의 런타임 변경 내용 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - ".NET Framework 런타임 변경 내용"
  - ".NET Framework 4.6.1 런타임 변경 내용"
  - "응용 프로그램 호환성"
ms.assetid: 9d97421c-5fee-4523-98c9-a158e7e6a1ee
caps.latest.revision: 5
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 5
---
# .NET Framework 4.6.1의 런타임 변경 내용
드문 경우지만 런타임 변경 내용이 이전 버전의 .NET Framework를 대상으로 하지만 이후 버전의 .NET Framework 런타임에서 실행되는 기존 앱에 영향을 줄 수 있습니다. 서로 다른 .NET Framework 런타임 환경에서 실행되는 응용 프로그램 간의 동작 차이도 포함됩니다. [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 다음 영역에 변경 내용을 포함 합니다.  
  
-   [Windows Communication Foundation (WCF)](#WCF)  
  
-   [Windows Presentation Foundation (WPF)](#WPF)  
  
<a name="WCF"></a>   
## <a name="windows-communication-foundation-wcf"></a>WCF(Windows Communication Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|사용 하 여 WCF 바인딩을 `TransportWithMessageCredential` 보안 모드|기본적으로 WCF 바인딩을 사용 하는 `TransportWithMessageCredential` 보안 모드를 사용 하 여 서명 되지 않은 메시지 수 없습니다 "to" 비대칭 보안 키에 대 한 헤더입니다. 아래에서 실행 되는 앱부터는 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)],이 요구 사항을 완화 하 고 "헤더에"가 서명 되지 않도록 메시지를 받을 수 있습니다.|이 동작은 옵트인 동작입니다. "헤더 에" 서명 되지 않은 메시지를 허용 하려면 다음 구성 설정 추가 [ <> \> ](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 응용 프로그램의 구성 파일의 섹션:<br /><br /> `<runtime>     <AppContextSwitchOverrides value="Switch.System.ServiceModel.AllowUnsignedToHeader=true" />  </runtime>`<br /><br /> 이 기능은 옵트인 기능이기 때문에 기존 앱의 동작에는 영향을 주지 않습니다.|Microsoft Edge|  
  
<a name="WPF"></a>   
## <a name="windows-presentation-foundation-wpf"></a>WPF(Windows Presentation Foundation)  
  
|기능|변경|영향|범위|  
|-------------|------------|------------|-----------|  
|<xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName>|때는 <xref:System.Windows.Controls.ItemsControl> 가상화를 사용 하 여 컬렉션을 표시 (<xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A> = `true`) 및 항목 스크롤 (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>), 해당 네트워크 환경에서 해당 높이 픽셀 단위로 다른 항목을 표시 하는 컨트롤을 스크롤할 때와 <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> 컬렉션의 모든 항목에 대해 반복 합니다.   이 반복; 동안 UI가 응답 하지  시스템 중단으로 인식 되어이 컬렉션 큰 경우.<br /><br /> 이전 릴리스에서에 다른 상황에서이 반복이 발생 된 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]합니다. 예를 들어 픽셀 스크롤할 때 발생 (<xref:System.Windows.Controls.VirtualizingPanel.ScrollUnit%2A>=<xref:System.Windows.Controls.ScrollUnit?displayProperty=fullName>) 항목 스크롤할 때 다른 픽셀 높이 항목을 발생 시 계층적 데이터 (마찬가지로 <xref:System.Windows.Controls.TreeView> 컨트롤 또는 <xref:System.Windows.Controls.ItemsControl> 사용 하도록 설정 하는 그룹화) 인접 한 환경 보다 하위 항목의 개수가 다른 항목을 발생 시.<br /><br /> 에 도입 된 반복 항목 스크롤 및 다른 픽셀 높이의 경우는 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 버그를 수정 하에 계층적 데이터의 레이아웃입니다.  플랫 데이터 인 경우 필요 하지 않습니다 (계층이 없으므로 있음) 및 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 경우에 수행 하지는 않습니다.|반복에서 발생 하는 경우는 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 있지만-즉, 이전 버전에 없는 경우는 <xref:System.Windows.Controls.ItemsControl> 항목-스크롤 하는 단순 목록-다른 픽셀 높이의 항목으로는 두 해결 방법을 찾으려면:<br /><br /> 설치는 [.NET Framework 4.6.2](../../../docs/framework/install/guide-for-developers.md)합니다.<br /><br /> 설치 [핫픽스 HR 1605](https://support.microsoft.com/en-us/kb/3154529) 에 대 한는 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]합니다.|사소함|  
  
## <a name="see-also"></a>참고 항목  
 [4.6.1의 응용 프로그램 호환성](../../../docs/framework/migration-guide/application-compatibility-in-the-net-framework-4-6-1.md)