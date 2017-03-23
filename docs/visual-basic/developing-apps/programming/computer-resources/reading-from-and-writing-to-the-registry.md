---
title: "Reading from and Writing to the Registry (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "My.Computer.Registry object, tasks"
  - "registry, writing to"
  - "registry, reading"
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Reading from and Writing to the Registry (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

이 항목에서는 작업 및 레지스트리와 관련 된 개념 항목에 설명 합니다.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서는 프로그래밍할 때 레지스트리에 액세스하기 위해 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]에서 제공하는 함수를 사용하거나 .NET Framework의 레지스트리 클래스를 사용할 수 있습니다.  레지스트리는 운영 체제의 정보와 시스템에 호스팅되는 응용 프로그램의 정보를 호스팅합니다.  레지스트리를 사용하면 시스템 리소스나 보호되는 정보가 부적절하게 액세스될 수 있으므로 보안상 위험할 수 있습니다.  
  
## 단원 내용  
 [How to: Create a Registry Key and Set Its Value](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 사용 하는 방법에 설명 합니다는 `CreateSubKey` 및 `SetValue` 메서드를의 `My.Computer.Registry` 레지스트리 키를 만들고 값을 설정 하는 개체입니다.  
  
 [How to: Read a Value from a Registry Key](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 사용 하는 방법에 설명 합니다는 `GetValue` 메서드는 `My.Computer.Registry` 개체는 레지스트리 키에서 값을 읽으려면.  
  
 [How to: Delete a Registry Key](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 사용 하는 방법에 설명의 `DeleteSubKey` 메서드는 `My.Computer.Registry.CurrentUser` 레지스트리 키를 삭제 하려면 속성.  
  
 [Microsoft.Win32 네임스페이스를 사용하여 레지스트리 읽기 및 쓰기](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 사용 하는 방법에 설명 합니다는 `Registry` 및 `RegistryKey` 클래스에는 [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] 레지스트리에 액세스 하.  
  
 [Security and the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 레지스트리와 관련된 보안 문제를 설명합니다.  
  
## 관련 단원  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 `My.Computer.Registry` 개체의 멤버를 나열하고 설명합니다.  
  
 <xref:Microsoft.Win32.Registry>  
 `Registry` 클래스를 간략하게 설명하고 각 키와 멤버에 대한 링크를 제공합니다.