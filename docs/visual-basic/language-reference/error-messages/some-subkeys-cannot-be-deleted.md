---
title: "Some subkeys cannot be deleted | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
ms.assetid: 14562137-af43-4972-84c1-a380a90f7d6c
caps.latest.revision: 8
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 8
---
# Some subkeys cannot be deleted
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

레지스트리 키를 삭제하려고 했지만 일부 하위 키를 삭제할 수 없어서 작업이 실패했습니다.  대개 이 문제는 권한이 부족할 때 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   지정된 하위 키에 대한 삭제 권한이 있는지 확인합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy?displayProperty=fullName>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:System.Security.Permissions.RegistryPermission>