---
title: "How to: Read a Value from a Registry Key in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "registry keys, determining if a value exists in"
  - "My.Computer.Registry object, examples"
  - "registry, determining if values exist"
  - "registry keys, reading from"
  - "registry, reading"
ms.assetid: 775d0a57-68c9-464e-8949-9a39bd29cc64
caps.latest.revision: 31
caps.handback.revision: 31
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Read a Value from a Registry Key in Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`My.Computer.Registry` 개체의 `GetValue` 메서드를 사용하여 Windows 레지스트리의 값을 읽을 수 있습니다.  
  
 다음 예제에서는 "Software\\MyApp" 라는 키를 없으면 예외가 throw 됩니다.  경우는 `ValueName`"이름", 다음 예제에서는 존재 하지 않는 `Nothing` 이 반환 됩니다.  
  
 `GetValue` 메서드는 사용할 수 있습니다 특정 레지스트리 키에 지정 된 값이 있는지 확인 합니다.  
  
 코드 웹 응용 프로그램에서 레지스트리를 읽을 경우 현재 사용자로 인증 한 웹 응용 프로그램에서 구현 되는 가장 결정 됩니다.  
  
### 레지스트리 키에서 값을 읽으려면  
  
-   `GetValue` 메서드에 경로와 이름을 지정하여 레지스트리 키에서 값을 읽습니다.  다음 예제에서는 `HKEY_CURRENT_USER\Software\MyApp`에서 `Name` 값을 읽고 이 값을 메시지 상자에 표시합니다.  
  
     [!code-vb[VbResourceTasks#4](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_1.vb)]  
  
 이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  코드 조각 선택의 **Windows 운영 체제 \> 레지스트리**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
### 레지스트리 키에 값이 있는지 확인하려면  
  
-   `GetValue` 메서드를 사용하여 해당 값을 가져옵니다.  다음 코드는 값이 있으며 표시 되지 않는 경우 메시지를 반환 하는지 여부를 확인 합니다.  
  
     [!code-vb[VbResourceTasks#12](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-read-a-value-from-a-registry-key_2.vb)]  
  
## 강력한 프로그래밍  
 레지스트리에는 데이터를 저장하는 데 사용되는 최상위\(또는 루트\) 키가 들어 있습니다.  예를 들어, HKEY\_LOCAL\_MACHINE 루트 키는 모든 사용자가 사용하는 컴퓨터 수준의 설정을 저장하는 데 사용되고, HKEY\_CURRENT\_USER는 개별 사용자의 고유 데이터를 저장하는 데 사용됩니다.  
  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   키 이름이 `Nothing`인 경우\(<xref:System.ArgumentNullException>\)  
  
-   사용자에게 레지스트리 키를 읽을 수 있는 권한이 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   키 이름이 255자 제한을 초과하는 경우\(<xref:System.ArgumentException>\)  
  
## .NET Framework 보안  
 이 프로세스를 실행하려면 어셈블리에 <xref:System.Security.Permissions.RegistryPermission> 클래스에서 부여한 권한 수준이 있어야 합니다.  부분 신뢰 컨텍스트에서 실행 중인 경우에는 권한이 부족하여 프로세스에서 예외를 throw할 수 있습니다.  마찬가지로 사용자에게는 설정을 만들거나 쓸 수 있는 올바른 ACL이 있어야 합니다.  예를 들어, 코드 액세스 보안 권한을 가지고 있는 로컬 응용 프로그램이 운영 체제 권한은 가지고 있지 않은 경우가 여기에 해당합니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.Win32.RegistryHive>   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)