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
# <a name="mitigation-culture-and-asynchronous-operations"></a><span data-ttu-id="68632-102">완화: 문화권 및 비동기 작업</span><span class="sxs-lookup"><span data-stu-id="68632-102">Mitigation: Culture and Asynchronous Operations</span></span>
<span data-ttu-id="68632-103">[!INCLUDE[net_v46](../../../includes/net-v46-md.md)] 이상 버전을 대상으로 하는 앱의 경우 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>는 비동기 작업 전반에 걸쳐 이동하는 스레드의 <xref:System.Threading.ExecutionContext>에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="68632-103">For apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] and later versions, <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are stored in a thread's <xref:System.Threading.ExecutionContext>, which flows across asynchronous operations.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="68632-104">영향</span><span class="sxs-lookup"><span data-stu-id="68632-104">Impact</span></span>  
 <span data-ttu-id="68632-105">이 변경의 결과로 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>의 변경 내용은 나중에 비동기적으로 실행되는 작업에 반영됩니다.</span><span class="sxs-lookup"><span data-stu-id="68632-105">As a result of this change, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are reflected in tasks which are later run asynchronously.</span></span> <span data-ttu-id="68632-106">이는 모든 비동기 작업에서 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>을 시스템 기본값으로 다시 설정하는 이전 .NET Framework 버전의 동작과 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="68632-106">This differs from the behavior of previous .NET Framework versions, which would reset <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to the system default  in all asynchronous tasks.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="68632-107">완화</span><span class="sxs-lookup"><span data-stu-id="68632-107">Mitigation</span></span>  
 <span data-ttu-id="68632-108">이 변경 내용의 영향을 받은 앱은 다음 두 가지 방식으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68632-108">Apps affected by this change can work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="68632-109">비동기 작업의 첫 번째 작업으로 원하는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성을 명시적으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68632-109">By explicitly setting the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> property as the first operation in an asynchronous task.</span></span>  
  
-   <span data-ttu-id="68632-110">다음 `AppContextSwitchOverrides` 요소를 응용 프로그램 구성 파일에 추가하여 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>을 전달하지 않는 이전 동작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68632-110">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by adding the following `AppContextSwitchOverrides` element to the application's configuration file:</span></span>  
  
    ```xml  
    <configuration>  
        <runtime>  
            <AppContextSwitchOverrides value="Switch.System.Globalization.NoAsyncCurrentCulture=true" />  
        </runtime>  
    </configuration>  
    ```  
  
-   <span data-ttu-id="68632-111">다음 호환성 스위치를 프로그래밍 방식으로 설정하여 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>을 전달하지 않는 이전 동작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68632-111">By opting into the old behavior of not flowing <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> by setting the following compatibility switch programatically:</span></span>  
  
    ```csharp  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true);  
    ```  
  
    ```vb  
    AppContext.SetSwitch("Switch.System.Globalization.NoAsyncCurrentCulture", true)  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="68632-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68632-112">See Also</span></span>  
 [<span data-ttu-id="68632-113">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="68632-113">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

