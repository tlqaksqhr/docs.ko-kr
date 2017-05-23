---
title: "완화: 긴 경로 지원 | Microsoft Docs"
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
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 40b4b94ac3058dda88b44c82110d4c749566e2b2
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-long-path-support"></a>완화: 긴 경로 지원
[!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱부터 경로 또는 정규화된 파일 이름이 260(또는 `MAX_PATH`)자를 초과하는 경우 파일 시스템 I/O 메서드는 더 이상 <xref:System.IO.PathTooLongException>을 자동으로 throw하지 않습니다. 대신 최대 32,000자의 긴 경로가 지원됩니다.  
  
## <a name="impact"></a>영향  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 다시 컴파일되었으며 이전에 경로가 260자를 초과했으므로 <xref:System.IO.PathTooLongException>을 자동으로 throw했던 앱은 이제 다음 조건에서만 <xref:System.IO.PathTooLongException>을 throw합니다.  
  
-   경로 길이가 <xref:System.Int16.MaxValue?displayProperty=fullName>(32, 767)자보다 긴 경우  
  
-   운영 체제가 `COR_E_PATHTOOLONG` 또는 동급을 반환하는 경우  
  
 [!INCLUDE[net_v461](../../../includes/net-v461-md.md)] 이전 버전을 대상으로 하는 앱의 레거시 동작은 경로가 260자를 초과할 때마다 런타임에서 자동으로 <xref:System.IO.PathTooLongException>을 throw하는 것입니다.  
  
## <a name="mitigation"></a>완화  
 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)]를 대상으로 하는 앱의 경우 원치 않을 경우 app.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음을 추가하여 긴 경로 지원을 옵트아웃(opt out)할 수 있습니다.  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=true" />   
</runtime>  
```  
  
 이전 버전의 .NET Framework를 대상으로 하지만 [!INCLUDE[net_v462](../../../includes/net-v462-md.md)] 이상에서 실행되는 앱의 경우 app.config 파일의 [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) 섹션에 다음 줄을 추가하여 긴 경로 지원을 옵트인(opt in)할 수 있습니다.  
  
```xml  
<runtime>   
   <AppContextSwitchOverrides value="Switch.System.IO.BlockLongPaths=false" />   
</runtime>  
```  
  
## <a name="see-also"></a>참고 항목  
 [대상 다시 지정 변경 내용](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6-2.md)

