---
title: "완화: 긴 경로 지원"
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
ms.assetid: 3cbe2d77-6e2c-4665-a6c5-7000b9ad6890
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 138e96c3d45b79ccf30f6a3d39f0af26a48c0117
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-long-path-support"></a><span data-ttu-id="d0d3e-102">완화: 긴 경로 지원</span><span class="sxs-lookup"><span data-stu-id="d0d3e-102">Mitigation: Long Path Support</span></span>
<span data-ttu-id="d0d3e-103">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터는 경로 또는 정규화된 파일 이름이 260(또는 `MAX_PATH`)자를 초과하더라도 파일 시스템 I/O 메서드가 더 이상 <xref:System.IO.PathTooLongException>을 자동으로 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-103">Starting with apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)],  file system I/O methods not longer automatically throw a <xref:System.IO.PathTooLongException> if a path or fully qualified file name exceeds 260 (or `MAX_PATH`) characters.</span></span> <span data-ttu-id="d0d3e-104">대신 최대 32,000자의 긴 경로가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-104">Instead, long paths of up to 32K characters are supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="d0d3e-105">영향</span><span class="sxs-lookup"><span data-stu-id="d0d3e-105">Impact</span></span>  
 <span data-ttu-id="d0d3e-106">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 다시 컴파일되었으며 이전에 경로가 260자를 초과하여 <xref:System.IO.PathTooLongException>을 자동으로 throw했던 앱은 이제 다음 조건에서만 <xref:System.IO.PathTooLongException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-106">Apps recompiled to target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] and that previously threw a <xref:System.IO.PathTooLongException> automatically because a path exceeded 260 characters will now throw a <xref:System.IO.PathTooLongException> only under the following conditions:</span></span>  
  
-   <span data-ttu-id="d0d3e-107">경로의 길이가 <xref:System.Int16.MaxValue?displayProperty=fullName>(32,767)자보다 긴 경우</span><span class="sxs-lookup"><span data-stu-id="d0d3e-107">The length of the path is greater than  <xref:System.Int16.MaxValue?displayProperty=fullName> (32,767) characters.</span></span>  
  
-   <span data-ttu-id="d0d3e-108">운영 체제가 `COR_E_PATHTOOLONG` 또는 동급을 반환하는 경우</span><span class="sxs-lookup"><span data-stu-id="d0d3e-108">The operating system returns `COR_E_PATHTOOLONG` or its equivalent.</span></span>  
  
 <span data-ttu-id="d0d3e-109">[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이하 버전을 대상으로 하는 앱의 레거시 동작은 경로가 260자를 초과할 때마다 런타임에서 자동으로 <xref:System.IO.PathTooLongException>을 throw하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-109">The legacy behavior for apps that target the[!INCLUDE[net_v461](../../../includes/net-v461-md.md)] and earlier is that the runtime automatically throws a <xref:System.IO.PathTooLongException> whenever a path exceeds 260 characters.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="d0d3e-110">완화</span><span class="sxs-lookup"><span data-stu-id="d0d3e-110">Mitigation</span></span>  
 <span data-ttu-id="d0d3e-111">[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱의 경우 원치 않을 경우 app.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 긴 경로 지원을 옵트아웃(opt out)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-111">For apps that target the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], you can opt out of long path support if it is not desirable by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 <span data-ttu-id="d0d3e-112">이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상에서 실행되는 앱의 경우 app.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 줄을 추가하여 긴 경로 지원을 옵트인(opt in)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0d3e-112">For apps that target earlier versions of the .NET Framework but run on the [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] or later., you can opt in to long path support by adding the following to    to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d0d3e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d0d3e-113">See Also</span></span>  
 [<span data-ttu-id="d0d3e-114">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="d0d3e-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

