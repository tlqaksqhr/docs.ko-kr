---
title: "완화: 경로 콜론 검사 | Microsoft Docs"
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
translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b5e2426fc81c8fd38994a4124cf71af8ec445bfb
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-path-colon-checks"></a>완화: 경로 콜론 검사
[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 이전에 지원되지 않던 경로를 지원하도록 여러 가지 변경이 수행되었습니다(길이 및 형식 측면에서). 특히 적절한 드라이브 구분 기호 구문(콜론)에 대한 확인이 좀 더 정확해졌습니다.  
  
## <a name="impact"></a>영향  
 이러한 변경 내용은 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> 메서드가 이전에 지원했던 일부 URI 경로를 차단합니다.  
  
## <a name="mitigation"></a>완화  
 이전에 허용 가능했으나 <xref:System.IO.Path.GetDirectoryName%2A?displayProperty=fullName> 및 <xref:System.IO.Path.GetPathRoot%2A?displayProperty=fullName> 메서드에서 더 이상 지원하지 않는 경로 문제를 해결하려면 다음을 수행할 수 있습니다.  
  
-   URL에서 스키마를 수동으로 제거합니다. 예를 들어 URL에서 `file://`을 제거합니다.  
  
-   <xref:System.Uri> 생성자에 해당 URI를 전달하고 <xref:System.Uri.LocalPath%2A?displayProperty=fullName> 속성의 값을 검색합니다.  
  
-   `Switch.System.IO.UseLegacyPathHandling` <xref:System.AppContext> 스위치를 `true`로 설정하여 새 경로 정규화를 옵트아웃(opt out)합니다.  
  
    ```xml  
  
    <runtime>  
        <AppContextSwitchOverrides value="Switch.System.IO.UseLegacyPathHandling=true" />    
    </runtime>  
  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)
