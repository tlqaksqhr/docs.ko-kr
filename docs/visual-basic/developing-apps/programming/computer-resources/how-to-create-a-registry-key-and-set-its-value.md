---
title: "How to: Create a Registry Key and Set Its Value in Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "RegistryKey.CreateSubKey"
  - "RegistryKey.SetValue"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "registry keys, creating"
  - "registry, adding values"
  - "registry, adding keys"
  - "registry keys, setting values"
  - "examples [Visual Basic], registry"
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: 30
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 30
---
# How to: Create a Registry Key and Set Its Value in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

`My.Computer.Registry` 개체의 `CreateSubKey` 메서드를 사용하여 레지스트리 키를 만들 수 있습니다.  
  
## 절차  
  
#### 레지스트리 키를 만들려면  
  
-   `CreateSubKey` 메서드에 키를 배치할 상위 하이브와 키 이름을 지정합니다.   `Subkey`  매개 변수는 대\/소문자를 구분하지 않습니다.  이 예제에서는 HKEY\_CURRENT\_USER 아래에 `MyTestKey` 레지스트리 키를 만듭니다.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]  
  
#### 레지스트리 키를 만들고 키 값을 설정하려면  
  
1.  `CreateSubkey` 메서드에 키를 배치할 상위 하이브와 키 이름을 지정합니다.  이 예제에서는 HKEY\_CURRENT\_USER 아래에 `MyTestKey` 레지스트리 키를 만듭니다.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]  
  
2.  `SetValue` 메서드를 사용하여 값을 설정합니다.  이 예제에서는 문자열 값을 설정합니다. 이때   즉, "MyTestKeyValue"가 "This is a test value"로 설정됩니다.  
  
     [!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]  
  
## 예제  
 이 예제에서는 HKEY\_CURRENT\_USER 아래에 레지스트리 키 `MyTestKey`를 만든 다음 문자열 값 `MyTestKeyValue`를 `This is a test value`로 설정합니다.  
  
 [!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]  
  
## 강력한 프로그래밍  
 키를 넣을 적합한 위치를 찾으려면 레지스트리 구조를 살펴 봅니다.  예를 들어, 현재 사용자의 HKEY\_CURRENT\_USER\\Software 키를 열고 회사 이름을 갖는 키를 만들 수 있습니다.  그런 다음 해당 레지스트리 값을 회사 키에 추가하면 됩니다.  
  
 웹 응용 프로그램에서 레지스트리를 읽을 경우 현재 사용자는 웹 응용 프로그램에 구현된 인증 및 가장에 따라 달라집니다.  
  
 데이터를 로컬 컴퓨터\(<xref:Microsoft.Win32.Registry.LocalMachine>\)에 쓰는 것보다는 사용자 폴더\(<xref:Microsoft.Win32.Registry.CurrentUser>\)에 쓰는 것이 더 안전합니다.  
  
 레지스트리 값을 만들 때는 해당 값이 이미 존재하는 경우 어떻게 처리할 것인지 결정해야 합니다.  악의적인 프로세스가 이미 해당 값을 만들어 액세스하고 있을 수도 있습니다.  레지스트리 값에 입력한 데이터는 다른 프로세스에서도 사용할 수 있습니다.  이를 방지하려면 <xref:Microsoft.Win32.RegistryKey.GetValue%2A> 메서드를 사용합니다.  이 메서드는 키가 아직 없을 경우 `Nothing`을 반환합니다.  
  
 레지스트리 키는 ACL\(액세스 제어 목록\)에 의해 보호되기는 하지만 암호 등의 비밀을 레지스트리에 일반 텍스트로 저장하면 보안상 위험합니다.  
  
 다음 조건에서 예외가 발생할 수 있습니다.  
  
-   키 이름이 `Nothing`인 경우\(<xref:System.ArgumentNullException>\)  
  
-   사용자에게 레지스트리 키를 만들 수 있는 권한이 없는 경우\(<xref:System.Security.SecurityException>\)  
  
-   키 이름이 255자 제한을 초과하는 경우\(<xref:System.ArgumentException>\)  
  
-   키가 닫힌 경우\(<xref:System.IO.IOException>\)  
  
-   레지스트리 키가 읽기 전용인 경우\(<xref:System.UnauthorizedAccessException>\)  
  
## .NET Framework 보안  
 이 프로세스를 실행하려면 어셈블리에 <xref:System.Security.Permissions.RegistryPermission> 클래스에서 부여한 권한 수준이 있어야 합니다.  부분 신뢰 컨텍스트에서 실행 중인 경우에는 권한이 부족하여 프로세스에서 예외를 throw할 수 있습니다.  마찬가지로 사용자에게는 설정을 만들거나 쓸 수 있는 올바른 ACL이 있어야 합니다.  예를 들어, 코드 액세스 보안 권한을 가지고 있는 로컬 응용 프로그램이 운영 체제 권한은 가지고 있지 않은 경우가 여기에 해당합니다.  자세한 내용은 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)을 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>   
 <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)   
 [코드 액세스 보안 기본 사항](../Topic/Code%20Access%20Security%20Basics.md)