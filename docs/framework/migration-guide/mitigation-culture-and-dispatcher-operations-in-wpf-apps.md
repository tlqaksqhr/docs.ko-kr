---
title: "완화: WPF 앱의 문화권 및 발송자 작업"
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41fc52679884d547809f1c1e9f47e29eb668cb8e
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a><span data-ttu-id="981ca-102">완화: WPF 앱의 문화권 및 발송자 작업</span><span class="sxs-lookup"><span data-stu-id="981ca-102">Mitigation: Culture and Dispatcher Operations in WPF Apps</span></span>
<span data-ttu-id="981ca-103">.NET Framework 4.6 및 .NET Framework 4.6.1을 대상으로 하는 앱에서는 <xref:System.Windows.Threading.Dispatcher> 내에서 수행한 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성 변경 내용이 해당 발송자 작업 종료 시에 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-103">In apps that target the .NET Framework 4.6 and the .NET Framework 4.6.1, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties that are made within a <xref:System.Windows.Threading.Dispatcher> are lost at the end of that dispatcher operation.</span></span> <span data-ttu-id="981ca-104">마찬가지로 발송자 작업 외부에서 수행된 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>에 대한 변경 내용은 작업이 실행될 때 반영되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-104">Similarly, changes to <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> made outside of a dispatcher operation may not be reflected when that operation executes.</span></span>  
  
 <span data-ttu-id="981ca-105">이러한 현상이 발생하는 이유는 <xref:System.Threading.ExecutionContext>가 변경되어 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>가 실행 컨텍스트에 저장되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-105">This is due to a change in <xref:System.Threading.ExecutionContext> that causes the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to be stored in the execution context.</span></span> <span data-ttu-id="981ca-106">WPF 발송자 작업이 작업을 시작할 때 사용된 실행 컨텍스트를 저장하고 작업이 완료되면 이전의 컨텍스트를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-106">WPF dispatcher operations store the execution context used to begin the operation and restore the previous context when the operation is completed.</span></span> <span data-ttu-id="981ca-107">이제는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>가 해당 컨텍스트의 일부이므로 발송자 작업 내의 해당 속성 변경 내용이 작업 외부에서 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-107">Because <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are now part of that context, changes to them within a dispatcher operation are not persisted outside of the operation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="981ca-108">영향</span><span class="sxs-lookup"><span data-stu-id="981ca-108">Impact</span></span>  
 <span data-ttu-id="981ca-109">이러한 현상으로 인해 실제로 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 및 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> 속성 변경 내용이 WPF UI 콜백과 WPF 응용 프로그램의 다른 코드 간에 전달되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-109">Practically, this means that changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties may not flow between WPF UI callbacks and other code in a WPF application.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="981ca-110">완화</span><span class="sxs-lookup"><span data-stu-id="981ca-110">Mitigation</span></span>  
 <span data-ttu-id="981ca-111">이 변경 내용의 영향을 받은 앱은 다음 두 가지 방식으로 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-111">Apps affected by this change may work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="981ca-112">원하는 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>를 필드에 저장한 다음, 올바른 <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> 또는 <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName>가 설정된 모든 <xref:System.Windows.Threading.Dispatcher> 작업 본문(UI 이벤트 콜백 처리기 포함)을 체크 인합니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-112">By storing the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in a field and checking in all <xref:System.Windows.Threading.Dispatcher> operation bodies (including UI event callback handlers) that the correct <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> is set.</span></span>  
  
-   <span data-ttu-id="981ca-113"><xref:System.Threading.ExecutionContext> 변경 내용은 .NET Framework 4.6 또는 .NET Framework 4.6.1을 대상으로 하는 WPF 앱에만 영향을 주므로 .NET Framework 4.5.2 또는 4.6.2 이상의 .NET Framework 버전을 대상으로 지정하면 이러한 변경을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="981ca-113">Because the change to <xref:System.Threading.ExecutionContext> only affects WPF apps that target the .NET Framework 4.6 or the .NET Framework 4.6.1, this change can be avoided by targeting the .NET Framework 4.5.2 or by targeting a version of the .NET Framework starting with 4.6.2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="981ca-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="981ca-114">See Also</span></span>  
 [<span data-ttu-id="981ca-115">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="981ca-115">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

