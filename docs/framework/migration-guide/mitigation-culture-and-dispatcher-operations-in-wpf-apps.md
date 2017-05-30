---
title: "완화: WPF 앱의 문화권 및 발송자 작업 | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 1aee32c5c50c4ff4309f93bff270e6c3b3c8f7cc
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a>완화: WPF 앱의 문화권 및 발송자 작업
.NET Framework 4.6 및 .NET Framework 4.6.1을 대상으로 하는 앱에서는 <xref:System.Windows.Threading.Dispatcher> 내에서 수행한 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성 변경 내용이 해당 발송자 작업 종료 시에 손실됩니다. 마찬가지로 발송자 작업 외부에서 수행된 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>에 대한 변경 내용은 작업이 실행될 때 반영되지 않을 수 있습니다.  
  
 이러한 현상이 발생하는 이유는 <xref:System.Threading.ExecutionContext>가 변경되어 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>가 실행 컨텍스트에 저장되기 때문입니다. WPF 발송자 작업이 작업을 시작할 때 사용된 실행 컨텍스트를 저장하고 작업이 완료되면 이전의 컨텍스트를 복원합니다. 이제는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>가 해당 컨텍스트의 일부이므로 발송자 작업 내의 해당 속성 변경 내용이 작업 외부에서 유지되지 않습니다.  
  
## <a name="impact"></a>영향  
 이러한 현상으로 인해 실제로 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성 변경 내용이 WPF UI 콜백과 WPF 응용 프로그램의 다른 코드 간에 전달되지 않을 수 있습니다.  
  
## <a name="mitigation"></a>완화  
 이 변경 내용의 영향을 받은 앱은 다음 두 가지 방식으로 해결할 수 있습니다.  
  
-   원하는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>를 필드에 저장한 다음, 올바른 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>가 설정된 모든 <xref:System.Windows.Threading.Dispatcher> 작업 본문(UI 이벤트 콜백 처리기 포함)을 체크 인합니다.  
  
-   <xref:System.Threading.ExecutionContext> 변경 내용은 .NET Framework 4.6 또는 .NET Framework 4.6.1을 대상으로 하는 WPF 앱에만 영향을 주므로 .NET Framework 4.5.2 또는 4.6.2 이상의 .NET Framework 버전을 대상으로 지정하면 이러한 변경을 방지할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
