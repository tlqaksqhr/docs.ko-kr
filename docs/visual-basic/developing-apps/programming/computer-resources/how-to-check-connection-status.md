---
title: "How to: Check Connection Status in Visual Basic | Microsoft Docs"
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
  - "Web connections"
  - "IsAvailable property, about IsAvailable"
  - "connections, checking status"
  - "connection status"
ms.assetid: 4d9ee8ab-9a6f-4279-ace4-b75afc976a74
caps.latest.revision: 26
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 26
---
# How to: Check Connection Status in Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

<xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A> 속성을 사용하여 컴퓨터가 작동 중인 네트워크나 인터넷에 연결되어 있는지 여부를 확인할 수 있습니다.  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note-settings-general-md.md)]  
  
### 컴퓨터에 작동 중인 연결이 있는지 확인하려면  
  
-   `IsAvailable` 속성이 `True`인지 아니면 `False`인지 확인합니다.  다음 코드에서는 속성의 상태를 확인하여 보고합니다.  
  
     [!code-vb[VbResourceTasks#3](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-check-connection-_1.vb)]  
  
     이 코드 예제는 IntelliSense 코드 조각으로도 사용할 수 있습니다.  이 코드 조각은 코드 조각 선택기의 **연결 및 네트워킹**에 있습니다.  자세한 내용은 [코드 조각](/visual-studio/ide/code-snippets)를 참조하십시오.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.IsAvailable%2A>