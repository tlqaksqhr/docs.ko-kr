---
title: "완화: 경로 콜론 검사"
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
ms.assetid: a0bb52de-d279-419d-8f23-4b12d1a3f36e
caps.latest.revision: 5
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8eb6864213aa4420f7a4373b9abbf173880f035f
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-path-colon-checks"></a>완화: 경로 콜론 검사
[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 이전에 지원되지 않던 경로를 지원하도록 여러 가지 변경이 수행되었습니다(길이 및 형식 측면에서). 특히 적절한 드라이브 구분 기호 구문(콜론)에 대한 확인이 좀 더 정확해졌습니다.  
  
## <a name="impact"></a>영향  
 이러한 변경으로 인해 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> 메서드에서 이전에 지원했던 일부 URI 경로가 차단됩니다.  
  
## <a name="mitigation"></a>완화  
 전에는 허용되었지만 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> 메서드로 더 이상 지원되지 않는 경로 문제를 해결하려면 다음을 수행할 수 있습니다.  
  
-   URL에서 스키마를 수동으로 제거합니다. 예를 들어 URL에서 `file://`을 제거합니다.  
  
-   URI를 <xref:System.Uri> 생성자에 전달하고 <xref:System.Uri.LocalPath%2A?displayProperty=fullName> 속성 값을 검색합니다.  
  
-   `Switch.System.IO.UseLegacyPathHandling`<xref:System.AppContext> 스위치를 `true`로 설정하여 새 경로 정규화를 취소합니다.  
  
    ```xml  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

