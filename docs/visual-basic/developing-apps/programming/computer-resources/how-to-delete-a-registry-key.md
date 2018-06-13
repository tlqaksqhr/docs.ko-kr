---
title: '방법: Visual Basic에서 레지스트리 키 삭제'
ms.date: 07/20/2015
f1_keywords:
- vb.DeleteSetting
helpviewer_keywords:
- GetSetting function [Visual Basic]
- registry [Visual Basic], deleting values
- GetAllSettings function
- registry keys [Visual Basic], deleting
- registry [Visual Basic], deleting keys
- examples [Visual Basic], registry
ms.assetid: ab9aca0e-42b0-4ff7-8ff9-845a4bfdf9f2
ms.openlocfilehash: 8a983436b8c7415f0d356d65ae7d6c5ffd1c2db5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33583853"
---
# <a name="how-to-delete-a-registry-key-in-visual-basic"></a>방법: Visual Basic에서 레지스트리 키 삭제
<xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%29> 및 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%28System.String%2CSystem.Boolean%29> 메서드를 사용하여 레지스트리 키를 삭제할 수 있습니다.  
  
## <a name="procedure"></a>프로시저  
  
#### <a name="to-delete-a-registry-key"></a>레지스트리 키를 삭제하려면  
  
-   `DeleteSubKey` 메서드를 사용하여 레지스트리 키를 삭제합니다. 이 예제에서는 CurrentUser 하이브에서 Software/TestApp 키를 삭제합니다. 코드에서 이 키를 적절한 문자열로 변경하거나 사용자가 제공한 정보를 사용하도록 할 수 있습니다.  
  
     [!code-vb[VbResourceTasks#19](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-delete-a-registry-key_1.vb)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 키/값 쌍이 존재하지 않는 경우 `DeleteSubKey` 메서드는 빈 문자열을 반환합니다.  
  
 다음 조건에서 예외가 발생합니다.  
  
-   키의 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)  
  
-   사용자에게 레지스트리 키를 삭제할 수 있는 권한이 없는 경우(<xref:System.Security.SecurityException>)  
  
-   키 이름이 255자 제한을 초과하는 경우(<xref:System.ArgumentException>)  
  
-   레지스트리 키가 읽기 전용인 경우(<xref:System.UnauthorizedAccessException>)  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 충분한 런타임 권한이 부여되지 않았거나(<xref:System.Security.Permissions.RegistryPermission>) 사용자에게 설정을 만들거나 쓰기 위한 올바른 액세스 권한(ACL에 따라 결정됨)이 없는 경우 레지스트리 호출에 실패합니다. 예를 들어 코드 액세스 보안 권한이 있는 로컬 응용 프로그램에는 운영 체제 권한이 없을 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey.DeleteSubKey%2A>  
 <xref:Microsoft.Win32.RegistryKey>  
 [보안 및 레지스트리](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 [레지스트리 읽기 및 쓰기](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
