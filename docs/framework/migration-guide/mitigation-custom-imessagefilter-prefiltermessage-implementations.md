---
title: "완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: b37d1d7ff75aebfcdf3e849931a5d2b3924d5d7a
ms.openlocfilehash: fe7290f3a887f2c4d52e52a6aff708e0e9fe415f
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a>완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현
[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이상의 .NET Framework 버전을 대상으로 하는 Windows Forms 앱에서는 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 구현이 다음에 해당하는 경우 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드를 호출할 때 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=fullName> 구현이 메시지를 안전하게 필터링할 수 있습니다.  
  
-   다음 중 하나 또는 두 가지 모두를 수행합니다.  
  
    -   <xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드를 호출하여 메시지 필터 추가  
  
    -   <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 메서드를 호출하여 메시지 필터 제거 메서드를 재정의합니다.  
  
-   **그와 동시에** <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=fullName> 메서드를 호출하여 메시지를 펌핑하는 경우  
  
## <a name="impact"></a>영향  
 이 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]부터 .NET Framework 버전을 대상으로 하는 Windows Forms 응용 프로그램에만 영향을 줍니다.  
  
 이전 버전의 .NET Framework를 대상으로 하는 Windows Forms 앱에서는 경우에 따라 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=fullName> 메서드를 호출할 때 이러한 구현이 <xref:System.IndexOutOfRangeException> 예외를 throw할 수 있습니다.  
  
## <a name="mitigation"></a>완화  
 이러한 변경을 원치 않는 경우 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 또는 이후 버전을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 또는 이후 버전에서 실행되는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)

