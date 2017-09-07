---
title: "완화: 문화권 및 비동기 작업"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: debcae8281c832d2815e1b9896fbbcb725c8ffc3
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-asynchronous-operations"></a>완화: 문화권 및 비동기 작업
[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 이상 버전을 대상으로 하는 앱의 경우 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>는 비동기 작업 전반에 걸쳐 이동하는 스레드의 <xref:System.Threading.ExecutionContext>에 저장됩니다.  
  
## <a name="impact"></a>영향  
 이 변경의 결과로 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>의 변경 내용은 나중에 비동기적으로 실행되는 작업에 반영됩니다. 이는 모든 비동기 작업에서 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>을 시스템 기본값으로 다시 설정하는 이전 .NET Framework 버전의 동작과 다릅니다.  
  
## <a name="mitigation"></a>완화  
 이 변경 내용의 영향을 받은 앱은 다음 두 가지 방식으로 해결할 수 있습니다.  
  
-   비동기 작업의 첫 번째 작업으로 원하는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성을 명시적으로 설정합니다.  
  
-   다음 `AppContextSwitchOverrides` 요소를 응용 프로그램 구성 파일에 추가하여 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>을 전달하지 않는 이전 동작을 선택합니다.  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   다음 호환성 스위치를 프로그래밍 방식으로 설정하여 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>을 전달하지 않는 이전 동작을 선택합니다.  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

