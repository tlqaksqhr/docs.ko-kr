---
title: "완화: 문화권 및 비동기 작업 | Microsoft Docs"
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
ms.assetid: d2cdb578-9923-47df-9ffd-5865333ac1a4
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: c2dbf60cacf47be3c448b5683b771840ef85ddaf
ms.contentlocale: ko-kr
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a>완화: 문화권 및 비동기 작업
[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 및 이후 버전을 대상으로 하는 앱의 경우 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>은 비동기 작업에서 이동하는 스레드의 <xref:System.Threading.ExecutionContext>에 저장됩니다.  
  
## <a name="impact"></a>영향  
 이러한 변경으로 인해 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>에 대한 변경 내용은 이후에 비동기적으로 실행되는 작업에 리플렉션됩니다. 이것은 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>를 모든 비동기 작업에서 시스템 기본값으로 초기화하는 이전 .NET Framework 버전의 동작과는 다릅니다.  
  
## <a name="mitigation"></a>완화  
 이 변경 내용의 영향을 받은 앱은 다음 두 가지 방식으로 해결할 수 있습니다.  
  
-   원하는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성을 비동기 작업의 첫 번째 작업으로 명시적으로 설정하여  
  
-   응용 프로그램의 구성 파일에 다음 `AppContextSwitchOverrides` 요소를 추가하여 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>를 진행하지 않는 이전 동작으로 옵트인(opt in)함으로써  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   다음 호환성 전환을 프로그래밍 방식으로 설정하여 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>를 진행하지 않는 이전 동작으로 옵트인(opt in)함으로써  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

