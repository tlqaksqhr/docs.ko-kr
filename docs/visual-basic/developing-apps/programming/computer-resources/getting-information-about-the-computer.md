---
title: "Getting Information about the Computer (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
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
  - "My.Computer.Info object, tasks"
ms.assetid: 13c145bc-5c85-4fea-a5dd-2ca8681a0252
caps.latest.revision: 16
caps.handback.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Getting Information about the Computer (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

`My.Computer.Info` 개체는 컴퓨터의 메모리, 로드된 어셈블리, 이름 및 운영 체제에 대한 정보를 가져오는 속성을 제공합니다.  
  
## 설명  
 이 표에서는 `My.Computer.Info` 개체를 통해 일반적으로 수행되는 작업과 각 작업의 수행 방법을 설명하는 항목을 보여 줍니다.  
  
|||  
|-|-|  
|To|참조|  
|응용 프로그램이 설치되는 컴퓨터에 사용할 수 있는 가상 주소 공간의 크기를 확인합니다.|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.TotalVirtualMemory%2A>|  
|응용 프로그램이 실행되는 컴퓨터의 플랫폼 형식을 확인합니다.|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSPlatform%2A>|  
|응용 프로그램이 실행되는 컴퓨터의 운영 체제를 확인합니다.|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSFullName%2A>|  
|응용 프로그램이 실행되는 컴퓨터에 설치된 서비스 팩을 확인합니다.|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.OSVersion%2A>|  
|응용 프로그램이 실행되는 컴퓨터에 설치된 `UICulture`를 확인합니다.|<xref:Microsoft.VisualBasic.Devices.ComputerInfo.InstalledUICulture%2A>|  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.Devices.ServerComputer.Info%2A>