---
title: '완화: 아이콘 개체의 PNG 프레임'
ms.date: 03/30/2017
ms.assetid: ca87fefb-7144-4b4e-8832-5a939adbb4b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c3ee5cc03f684acf103c96ecd14387f119bf0bdc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="mitigation-png-frames-in-icon-objects"></a><span data-ttu-id="422e1-102">완화: 아이콘 개체의 PNG 프레임</span><span class="sxs-lookup"><span data-stu-id="422e1-102">Mitigation: PNG Frames in Icon Objects</span></span>
<span data-ttu-id="422e1-103">.NET Framework 4.6부터는 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 메서드가 PNG 프레임이 있는 아이콘을 <xref:System.Drawing.Bitmap> 개체로 성공적으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="422e1-103">Starting with the .NET Framework 4.6, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method successfully converts icons with PNG frames into <xref:System.Drawing.Bitmap> objects.</span></span>  
  
 <span data-ttu-id="422e1-104">.NET Framework 4.5.2 및 이전 버전을 대상으로 하는 앱에서는 <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> 개체에 PNG 프레임이 있는 경우 <xref:System.ArgumentOutOfRangeException> 메서드가 <xref:System.Drawing.Icon> 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="422e1-104">In apps that target the .NET Framework 4.5.2 and earlier versions, the <xref:System.Drawing.Icon.ToBitmap%2A?displayProperty=nameWithType> method throws an <xref:System.ArgumentOutOfRangeException> exception if the <xref:System.Drawing.Icon> object has PNG frames.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="422e1-105">영향</span><span class="sxs-lookup"><span data-stu-id="422e1-105">Impact</span></span>  
 <span data-ttu-id="422e1-106">이 변경은 <xref:System.ArgumentOutOfRangeException> 개체에 PNG 프레임이 있을 때 throw되는 <xref:System.Drawing.Icon> 에 대해 특수 처리를 구현하고 .NET Framework 4.6을 대상으로 다시 컴파일되는 앱에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="422e1-106">This change affects apps that are recompiled to target the .NET Framework 4.6 and that implement special handling for the <xref:System.ArgumentOutOfRangeException> that is thrown when an <xref:System.Drawing.Icon> object has PNG frames.</span></span> <span data-ttu-id="422e1-107">.NET Framework 4.6에서 실행되는 경우 변환이 성공하고 <xref:System.ArgumentOutOfRangeException> 이 더 이상 throw되지 않습니다. 따라서 예외 처리기가 더 이상 호출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="422e1-107">When running under the .NET Framework 4.6, the conversion is successful, an <xref:System.ArgumentOutOfRangeException> is no longer thrown, and therefore the exception handler is no longer invoked.</span></span>  
  
### <a name="mitigation"></a><span data-ttu-id="422e1-108">완화</span><span class="sxs-lookup"><span data-stu-id="422e1-108">Mitigation</span></span>  
 <span data-ttu-id="422e1-109">이 동작이 필요 없는 경우 다음 요소를 app.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 추가하여 이전 동작을 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="422e1-109">If this behavior is undesirable, you can retain the previous behavior by adding the following element to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true" />  
```  
  
 <span data-ttu-id="422e1-110">App.config 파일에 이미 `AppContextSwitchOverrides` 요소가 포함되어 있는 경우 새 값은 다음과 같이 `value` 특성과 병합되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="422e1-110">If the app.config file already contains the `AppContextSwitchOverrides` element, the new value should be merged with the `value` attribute like this:</span></span>  
  
```xml  
<AppContextSwitchOverrides   
      value="Switch.System.Drawing.DontSupportPngFramesInIcons=true;<previous key>=<previous value>" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="422e1-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="422e1-111">See Also</span></span>  
 [<span data-ttu-id="422e1-112">대상 다시 지정 변경 내용</span><span class="sxs-lookup"><span data-stu-id="422e1-112">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
