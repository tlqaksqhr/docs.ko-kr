---
title: "How to: Delete a Registry Key in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.DeleteSetting"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "GetSetting function"
  - "registry, deleting values"
  - "GetAllSettings function"
  - "registry keys, deleting"
  - "registry, deleting keys"
  - "examples [Visual Basic], registry"
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
caps.latest.revision: 28
caps.handback.revision: 28
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Delete a Registry Key in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

<xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> 및 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> 메서드를 사용하여 레지스트리 키를 삭제할 수 있습니다.  
  
## 절차  
  
#### 레지스트리 키를 삭제하려면  
  
-   `DeleteSubKey` 메서드를 사용하여 레지스트리 키를 삭제합니다.  이 예제에서는 CurrentUser 하이브의 Software\/TestApp 키를 삭제합니다.  코드의 이 키를 적절한 문자열로 변경하거나 사용자가 지정한 정보에 맞게 변경할 수 있습니다.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## 강력한 프로그래밍  
 `DeleteSubKey` 메서드는 키\/값 쌍이 없을 경우 빈 문자열을 반환합니다.  
  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   키 이름이 `Nothing`인 경우\(<xref:System.ArgumentNullException>\)  
  
-   사용자에게 레지스트리 키를 삭제할 수 있는 권한이 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   키 이름이 255자 제한을 초과하는 경우\(<xref:System.ArgumentException>\)  
  
-   레지스트리 키가 읽기 전용인 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## .NET Framework 보안  
 충분한 런타임 권한이 부여되지 않았거나\(<xref:System.Security.Permissions.RegistryPermission>\) 사용자에게 설정을 만들거나 작성할 수 있는 올바른 액세스 권한\(ACL에 따라 결정됨\)이 없으면 레지스트리 호출이 실패합니다.  예를 들어, 코드 액세스 보안 권한을 가지고 있는 로컬 응용 프로그램이 운영 체제 권한은 가지고 있지 않은 경우가 여기에 해당합니다.  
  
## 참고 항목  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>   
 <xref:Microsoft.Win32.RegistryKey>   
 [Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)