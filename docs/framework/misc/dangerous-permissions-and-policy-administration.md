---
title: "위험한 권한 및 정책 관리"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0c8a01cbae2077838a8eef3f2f673e7d9d646717
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="dangerous-permissions-and-policy-administration"></a>위험한 권한 및 정책 관리
.NET Framework가 권한을 제공하는 보호되는 몇몇 작업은 보안 시스템의 보안을 손상시킬 수 있습니다. 이렇게 위험한 권한은 필요한 경우에만, 그리고 신뢰할 수 있는 코드에만 제공되어야 합니다. 일반적으로 이러한 권한이 부여되면 악성 코드를 방어할 수 없습니다.  
  
> [!NOTE]
>  [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서는 .NET Framework 보안 모델 및 용어 대한 중요한 변경 내용이 있습니다. 이러한 변경에 대 한 자세한 내용은 참조 [보안 변경 내용](../../../docs/framework/security/security-changes.md)합니다.  
  
 위험한 권한은 다음 표에 설명되어 있습니다.  
  
|사용 권한|잠재적 위험|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|관리 코드에서 비관리 코드를 호출하도록 허용하므로 위험할 수 있습니다.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|이 코드는 유효성 검사가 없어도 모든 작업을 수행할 수 있습니다.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|잘못된 증명 정보로 보안 정책을 속일 수 있습니다.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|보안 정책을 수정하는 기능으로 보안을 해제할 수 있습니다.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|직렬화를 사용하면 접근성 메커니즘을 피할 수 있습니다. 자세한 내용은 [보안 및 직렬화](../../../docs/framework/misc/security-and-serialization.md)를 참조하세요.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|현재 보안 주체를 설정하는 기능은 역할 기반 보안을 속일 수 있습니다.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|스레드 조작은 스레드와 관련된 보안 상태로 인해 위험합니다.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|접근성 메커니즘을 무력화하는 데 전용 멤버를 사용할 수 있습니다.|  
  
## <a name="see-also"></a>참고 항목  
 [보안 코딩 지침](../../../docs/standard/security/secure-coding-guidelines.md)
