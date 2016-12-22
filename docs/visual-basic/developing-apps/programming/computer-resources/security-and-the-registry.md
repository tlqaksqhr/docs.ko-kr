---
title: "Security and the Registry (Visual Basic) | Microsoft Docs"
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
  - "security [Visual Basic], registry"
  - "registry, security issues"
ms.assetid: 9980aff7-2f69-492b-8f66-29a9a76d3df5
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Security and the Registry (Visual Basic)
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

이 페이지에서는 레지스트리에 데이터를 저장할 경우의 보안 문제에 대해 설명합니다.  
  
## 권한  
 레지스트리 키는 ACL\(액세스 제어 목록\)에 의해 보호되기는 하지만 암호 등의 비밀을 레지스트리에 일반 텍스트로 저장하면 보안상 위험합니다.  
  
 레지스트리를 사용하면 시스템 리소스나 보호되는 정보가 부적절하게 액세스될 수 있으므로 보안상 위험할 수 있습니다.  이러한 속성을 사용하려면 레지스트리 변수에 대한 액세스를 관리하는 <xref:System.Security.Permissions.RegistryPermissionAccess> 열거형의 읽기 및 쓰기 권한이 있어야 합니다.  완전 신뢰로 실행되는 모든 코드\(기본 보안 정책에서는 사용자의 로컬 하드 디스크에 설치된 모든 코드\)는 레지스트리에 액세스하는 데 필요한 권한을 가지고 있습니다.  자세한 내용은 <xref:System.Security.Permissions.RegistryPermission> 클래스를 참조하십시오.  
  
 레지스트리 변수는 <xref:System.Security.Permissions.RegistryPermission>이 없는 코드가 액세스할 수 있는 메모리 위치에 저장되지 않아야 합니다.  마찬가지로, 사용 권한을 부여할 때는 작업을 수행하는 데 필요한 최소한의 권한을 부여합니다.  
  
 레지스트리 권한 액세스 값은 <xref:System.Security.Permissions.RegistryPermissionAccess> 열거형으로 정의됩니다.  다음 표에서는 해당 멤버에 대해 설명합니다.  
  
|값|레지스트리 변수에 대한 권한|  
|-------|---------------------|  
|`AllAccess`|만들기, 읽기 및 쓰기|  
|`Create`|Create|  
|`NoAccess`|액세스 권한 없음|  
|`Read`|Read|  
|`Write`|Write|  
  
## 레지스트리 키의 값 검사  
 레지스트리 값을 만들 때는 해당 값이 이미 존재하는 경우 어떻게 처리할 것인지 결정해야 합니다.  악의적인 프로세스가 이미 해당 값을 만들어 액세스하고 있을 수도 있습니다.  레지스트리 값에 입력한 데이터는 다른 프로세스에서도 사용할 수 있습니다.  이를 방지하려면 `GetValue` 메서드를 사용합니다.  이 메서드는 키가 아직 없을 경우 `Nothing`을 반환합니다.  
  
> [!IMPORTANT]
>  웹 응용 프로그램에서 레지스트리를 읽을 경우 현재 사용자의 ID는 웹 응용 프로그램에 구현된 인증 및 가장에 따라 달라집니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>   
 [Reading from and Writing to the Registry](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)