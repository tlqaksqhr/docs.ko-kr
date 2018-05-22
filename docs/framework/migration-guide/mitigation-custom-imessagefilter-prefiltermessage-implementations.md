---
title: '완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현'
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 78d8ba7f872095920e7fda727f46fc10b989ed37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="99cc2-102">완화: 사용자 지정 IMessageFilter.PreFilterMessage 구현</span><span class="sxs-lookup"><span data-stu-id="99cc2-102">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>
<span data-ttu-id="99cc2-103">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이상의 .NET Framework 버전을 대상으로 하는 Windows Forms 앱에서는 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 다음에 해당하는 경우 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드를 호출할 때 사용자 지정 <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> 구현이 메시지를 안전하게 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99cc2-103">In Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)], a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>  
  
-   <span data-ttu-id="99cc2-104">다음 중 하나 또는 두 가지 모두를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc2-104">Does one or both of the following:</span></span>  
  
    -   <span data-ttu-id="99cc2-105"><xref:System.Windows.Forms.Application.AddMessageFilter%2A> 메서드를 호출하여 메시지 필터 추가</span><span class="sxs-lookup"><span data-stu-id="99cc2-105">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>  
  
    -   <span data-ttu-id="99cc2-106"><xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> 메서드를 호출하여 메시지 필터 제거</span><span class="sxs-lookup"><span data-stu-id="99cc2-106">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="99cc2-107">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="99cc2-107">method.</span></span>  
  
-   <span data-ttu-id="99cc2-108">**그와 동시에** <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> 메서드를 호출하여 메시지를 펌핑하는 경우</span><span class="sxs-lookup"><span data-stu-id="99cc2-108">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="99cc2-109">영향</span><span class="sxs-lookup"><span data-stu-id="99cc2-109">Impact</span></span>  
 <span data-ttu-id="99cc2-110">이 변경은 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)]부터 .NET Framework 버전을 대상으로 하는 Windows Forms 응용 프로그램에만 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="99cc2-110">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)].</span></span>  
  
 <span data-ttu-id="99cc2-111">이전 버전의 .NET Framework를 대상으로 하는 Windows Forms 앱에서는 경우에 따라 <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> 메서드를 호출할 때 이러한 구현이 <xref:System.IndexOutOfRangeException> 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99cc2-111">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="99cc2-112">완화</span><span class="sxs-lookup"><span data-stu-id="99cc2-112">Mitigation</span></span>  
 <span data-ttu-id="99cc2-113">이러한 변경을 원치 않는 경우 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 또는 이후 버전을 대상으로 하는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 사용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99cc2-113">If this change is undesirable, apps that target the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />   
</runtime>  
```  
  
 <span data-ttu-id="99cc2-114">또한 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 또는 이후 버전에서 실행되는 앱은 앱 구성 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 구성 설정을 추가하여 이 동작을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99cc2-114">In addition, apps that target previous versions of the .NET Framework but are running under the [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>  
  
```xml  
<runtime>  
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="99cc2-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="99cc2-115">See Also</span></span>  
 [<span data-ttu-id="99cc2-116">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="99cc2-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-1.md)
