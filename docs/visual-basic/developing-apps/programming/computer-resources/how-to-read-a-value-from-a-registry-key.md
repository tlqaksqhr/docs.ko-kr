---
title: "방법: Visual Basic에서 레지스트리 키 값 읽기 | Microsoft 문서"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- registry keys, determining if a value exists in
- My.Computer.Registry object, examples
- registry, determining if values exist
- registry keys, reading from
- registry, reading
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b5054e277895d185ab8ec6f6a2950d5dedbef390
ms.contentlocale: ko-kr
ms.lasthandoff: 05/22/2017

---
# <a name="how-to-read-a-value-from-a-registry-key-in-visual-basic"></a>방법: Visual Basic에서 레지스트리 키 값 읽기
`My.Computer.Registry` 개체의 `GetValue` 메서드를 사용하여 Windows 레지스트리의 값을 읽을 수 있습니다.  
  
 다음 예제의 "Software\MyApp" 키가 없으면 예외가 throw됩니다. `ValueName`(다음 예제의 "Name")이 없으면 `Nothing`이 반환됩니다.  
  
 `GetValue` 메서드를 사용하여 지정된 값이 특정 레지스트리 키에 있는지 확인할 수도 있습니다.  
  
 코드가 웹 응용 프로그램에서 레지스트리를 읽는 경우 현재 사용자는 웹 응용 프로그램에 구현된 인증 및 가장에 의해 결정됩니다.  
  
### <a name="to-read-a-value-from-a-registry-key"></a>레지스트리 키에서 값을 읽으려면  
  
-   `GetValue` 메서드를 사용하고 경로 및 이름을 지정하여 레지스트리 키에서 값을 읽습니다. 다음 예제에서는 `HKEY_CURRENT_USER\Software\MyApp`에서 `Name` 값을 읽고 메시지 상자에 표시합니다.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로 사용할 수도 있습니다. 코드 조각 선택에서 **Windows 운영 체제 > 레지스트리**에 있습니다. 자세한 내용은 [코드 조각](https://docs.microsoft.com/visualstudio/ide/code-snippets)을 참조하세요.  
  
### <a name="to-determine-whether-a-value-exists-in-a-registry-key"></a>레지스트리 키에 값이 있는지 확인하려면  
  
-   `GetValue` 메서드를 사용하여 값을 검색합니다. 다음 코드는 값이 있는지 확인하고, 값이 없는 경우 메시지를 반환합니다.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## <a name="robust-programming"></a>강력한 프로그래밍  
 레지스트리는 데이터를 저장하는 데 사용되는 최상위 또는 루트 키를 포함합니다. 예를 들어 HKEY_LOCAL_MACHINE 루트 키는 모든 사용자가 사용하는 컴퓨터 수준 설정을 저장하는 데 사용되고, HKEY_CURRENT_USER는 개별 사용자와 관련된 데이터를 저장하는 데 사용됩니다.  
  
 다음 조건에서 예외가 발생합니다.  
  
-   키의 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)  
  
-   사용자에게 레지스트리 키에서 읽을 수 있는 권한이 없는 경우(<xref:System.Security.SecurityException>)  
  
-   키 이름이 255자 제한을 초과하는 경우(<xref:System.ArgumentException>)  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 이 프로세스를 실행하려면 어셈블리에 <xref:System.Security.Permissions.RegistryPermission> 클래스에서 부여한 권한 수준이 필요합니다. 부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다. 마찬가지로, 사용자에게 설정을 만들거나 쓸 수 있는 올바른 ACL이 있어야 합니다. 예를 들어 코드 액세스 보안 권한이 있는 로컬 응용 프로그램에는 운영 체제 권한이 없을 수 있습니다. 자세한 내용은 [코드 액세스 보안 기본 사항](https://msdn.microsoft.com/library/33tceax8)을 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [레지스트리 읽기 및 쓰기](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)
